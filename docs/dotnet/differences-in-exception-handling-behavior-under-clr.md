---
title: Unterschiede im Ausnahmebehandlungsverhalten unter / CLR
ms.date: 11/04/2016
helpviewer_keywords:
- EXCEPTION_CONTINUE_EXECUTION macro
- set_se_translator function
ms.assetid: 2e7e8daf-d019-44b0-a51c-62d7aaa89104
ms.openlocfilehash: e7c91e0f369a4e6fe24e656f1b9e8504d7cb434a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750428"
---
# <a name="differences-in-exception-handling-behavior-under-clr"></a>Unterschiede im Ausnahmebehandlungsverhalten unter /CLR

[Grundlegende Konzepte zur Verwendung verwalteter Ausnahmen](../dotnet/basic-concepts-in-using-managed-exceptions.md) Behandlung von Ausnahmen in verwalteten Anwendungen erläutert. In diesem Thema werden die Unterschiede zwischen dem Standardverhalten der Ausnahmebehandlung und einigen Einschränkungen im Detail erläutert. Weitere Informationen finden Sie unter [der _set_se_translator-Funktion](../c-runtime-library/reference/set-se-translator.md).

##  <a name="vcconjumpingoutofafinallyblock"></a> Herausspringen aus einer Finally-Block

In den systemeigenen C/C++-Code aus einem __ springen**schließlich** Block, die über die strukturierte Ausnahmebehandlung (SEH) ist zulässig, obwohl es sich um eine Warnung erzeugt.  Klicken Sie unter ["/ CLR"](../build/reference/clr-common-language-runtime-compilation.md), Herausspringen aus einer **schließlich** Block verursacht einen Fehler:

```cpp
// clr_exception_handling_4.cpp
// compile with: /clr
int main() {
   try {}
   finally {
      return 0;   // also fails with goto, break, continue
    }
}   // C3276
```

##  <a name="vcconraisingexceptionswithinanexceptionfilter"></a> Auslösen von Ausnahmen innerhalb eines Ausnahmefilters

Wenn eine Ausnahme ausgelöst wird, während der Verarbeitung einer [Ausnahmefilter](../cpp/writing-an-exception-filter.md) in verwaltetem Code wird die Ausnahme abgefangen und behandelt, als ob der Filter 0 zurückgibt.

Dies unterscheidet sich das Verhalten in systemeigenem Code, in denen eine geschachtelte Ausnahme ausgelöst wird, die **ExceptionRecord** -Feld in der **EXCEPTION_RECORD** Struktur (wie vom [ GetExceptionInformation](/windows/desktop/Debug/getexceptioninformation)) festgelegt ist, und die **ExceptionFlags** -Feld legt fest, das Bit 0 x 10. Das folgende Beispiel veranschaulicht dieses unterschiedliche Verhalten:

```cpp
// clr_exception_handling_5.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

#ifndef false
#define false 0
#endif

int *p;

int filter(PEXCEPTION_POINTERS ExceptionPointers) {
   PEXCEPTION_RECORD ExceptionRecord =
                     ExceptionPointers->ExceptionRecord;

   if ((ExceptionRecord->ExceptionFlags & 0x10) == 0) {
      // not a nested exception, throw one
      *p = 0; // throw another AV
   }
   else {
      printf("Caught a nested exception\n");
      return 1;
    }

   assert(false);

   return 0;
}

void f(void) {
   __try {
      *p = 0;   // throw an AV
   }
   __except(filter(GetExceptionInformation())) {
      printf_s("We should execute this handler if "
                 "compiled to native\n");
    }
}

int main() {
   __try {
      f();
   }
   __except(1) {
      printf_s("The handler in main caught the "
               "exception\n");
    }
}
```

### <a name="output"></a>Output

```Output
Caught a nested exception
We should execute this handler if compiled to native
```

##  <a name="vccondisassociatedrethrows"></a> Erneutes Auslösen mit aufgehobener

**"/ CLR"** unterstützt nicht das erneute Auslösen einer Ausnahme außerhalb eines Catch-Handlers (bekannt als eine Auslösen mit aufgehobener Zuordnung). Behandelt Ausnahmen dieses Typs als standard C++ Rethrow. Wenn ein nicht verbundenes Rethrow gefunden wird, wenn eine aktive verwaltete Ausnahme vorhanden ist, wird die Ausnahme als C++-Ausnahme umschlossen und dann erneut ausgelöst. Ausnahmen dieses Typs können nur als eine Ausnahme des Typs abgefangen werden <xref:System.Runtime.InteropServices.SEHException>.

Im folgende Beispiel wird veranschaulicht, eine verwaltete Ausnahme, die als C++-Ausnahme erneut ausgelöst wird:

```cpp
// clr_exception_handling_6.cpp
// compile with: /clr
using namespace System;
#include <assert.h>
#include <stdio.h>

void rethrow( void ) {
   // This rethrow is a dissasociated rethrow.
   // The exception would be masked as SEHException.
   throw;
}

int main() {
   try {
      try {
         throw gcnew ApplicationException;
      }
      catch ( ApplicationException^ ) {
         rethrow();
         // If the call to rethrow() is replaced with
         // a throw statement within the catch handler,
         // the rethrow would be a managed rethrow and
         // the exception type would remain
         // System::ApplicationException
      }
   }

    catch ( ApplicationException^ ) {
      assert( false );

      // This will not be executed since the exception
      // will be masked as SEHException.
    }
   catch ( Runtime::InteropServices::SEHException^ ) {
      printf_s("caught an SEH Exception\n" );
    }
}
```

### <a name="output"></a>Output

```Output
caught an SEH Exception
```

##  <a name="vcconexceptionfiltersandexception_continue_execution"></a> Ausnahmefilter und EXCEPTION_CONTINUE_EXECUTION

Wenn Sie einen Filter zurückgibt `EXCEPTION_CONTINUE_EXECUTION` in einer verwalteten Anwendung wird diese behandelt, als ob der Filter zurückgegeben `EXCEPTION_CONTINUE_SEARCH`. Weitere Informationen zu diesen Konstanten finden Sie unter [versuchen-except-Anweisung](../cpp/try-except-statement.md).

Das folgende Beispiel veranschaulicht diesen Unterschied:

```cpp
// clr_exception_handling_7.cpp
#include <windows.h>
#include <stdio.h>
#include <assert.h>

int main() {
   int Counter = 0;
   __try {
      __try  {
         Counter -= 1;
         RaiseException (0xe0000000|'seh',
                         0, 0, 0);
         Counter -= 2;
      }
      __except (Counter) {
         // Counter is negative,
         // indicating "CONTINUE EXECUTE"
         Counter -= 1;
      }
    }
    __except(1) {
      Counter -= 100;
   }

   printf_s("Counter=%d\n", Counter);
}
```

### <a name="output"></a>Output

```Output
Counter=-3
```

##  <a name="vcconthe_set_se_translatorfunction"></a> _Set_se_translator-Funktion

Legen Sie die Translator-Funktion, durch einen Aufruf von `_set_se_translator`, wirkt sich auf nur abfängt in nicht verwaltetem Code. Das folgende Beispiel veranschaulicht diese Einschränkung:

```cpp
// clr_exception_handling_8.cpp
// compile with: /clr /EHa
#include <iostream>
#include <windows.h>
#include <eh.h>
#pragma warning (disable: 4101)
using namespace std;
using namespace System;

#define MYEXCEPTION_CODE 0xe0000101

class CMyException {
public:
   unsigned int m_ErrorCode;
   EXCEPTION_POINTERS * m_pExp;

   CMyException() : m_ErrorCode( 0 ), m_pExp( NULL ) {}

   CMyException( unsigned int i, EXCEPTION_POINTERS * pExp )
         : m_ErrorCode( i ), m_pExp( pExp ) {}

   CMyException( CMyException& c ) : m_ErrorCode( c.m_ErrorCode ),
                                      m_pExp( c.m_pExp ) {}

   friend ostream& operator <<
                 ( ostream& out, const CMyException& inst ) {
      return out <<  "CMyException[\n" <<
             "Error Code: " << inst.m_ErrorCode <<  "]";
    }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS pExp ) {
   cout <<  "In my_trans_func.\n";
   throw CMyException( u, pExp );
}

#pragma managed
void managed_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE, 0, 0, 0 );
   }
   catch ( CMyException x ) {}
   catch ( ... ) {
      printf_s("This is invoked since "
               "_set_se_translator is not "
               "supported when /clr is used\n" );
    }
}

#pragma unmanaged
void unmanaged_func() {
   try  {
      RaiseException( MYEXCEPTION_CODE,
                      0, 0, 0 );
   }
   catch ( CMyException x ) {
      printf("Caught an SEH exception with "
             "exception code: %x\n", x.m_ErrorCode );
    }
    catch ( ... ) {}
}

// #pragma managed
int main( int argc, char ** argv ) {
   _set_se_translator( my_trans_func );

   // It does not matter whether the translator function
   // is registered in managed or unmanaged code
   managed_func();
   unmanaged_func();
}
```

### <a name="output"></a>Output

```Output
This is invoked since _set_se_translator is not supported when /clr is used
In my_trans_func.
Caught an SEH exception with exception code: e0000101
```

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../windows/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../windows/safe-cast-cpp-component-extensions.md)<br/>
[Ausnahmebehandlung](../cpp/exception-handling-in-visual-cpp.md)
