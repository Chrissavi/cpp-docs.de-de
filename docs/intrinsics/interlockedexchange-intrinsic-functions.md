---
title: Funktionen "_InterlockedExchange" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _InterlockedExchange_rel
- _InterlockedExchange8_nf
- _InterlockedExchange_acq_cpp
- _InterlockedExchange_nf
- _InterlockedExchange64_nf
- _InterlockedExchange_HLEAcquire
- _InterlockedExchange_cpp
- _InterlockedExchange64_acq_cpp
- _InterlockedExchange64_acq
- _InterlockedExchange64_HLERelease
- _InterlockedExchange8_acq
- _InterlockedExchange16_acq
- _InterlockedExchange
- _InterlockedExchange64_HLEAcquire
- _InterlockedExchange8
- _InterlockedExchange64_rel
- _InterlockedExchange_acq
- _InterlockedExchange16
- _InterlockedExchange16_rel
- _InterlockedExchange16_nf
- _InterlockedExchange64
- _InterlockedExchange_HLERelease
- _InterlockedExchange64_cpp
- _InterlockedExchange8_rel
dev_langs:
- C++
helpviewer_keywords:
- _InterlockedExchange8
- _InterlockedExchange64 intrinsic
- _InterlockedExchange_acq intrinsic
- InterlockedExchange64 intrinsic
- _InterlockedExchange64_acq intrinsic
- InterlockedExchange64_acq intrinsic
- _InterlockedExchange16_acq
- _InterlockedExchange8_acq
- _InterlockedExchange16
- _InterlockedExchange8_rel
- InterlockedExchange_acq intrinsic
- InterlockedExchange intrinsic
- _InterlockedExchange16_rel
- _InterlockedExchange16_nf
- _InterlockedExchange intrinsic
- _InterlockedExchange8_nf
ms.assetid: be2f232a-6301-462a-a92b-fcdeb8b0f209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6af43074e78ffb66299b9eeda97dd18f073d77fd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599398"
---
# <a name="interlockedexchange-intrinsic-functions"></a>Intrinsische Funktionen „_InterlockedExchange“
**Microsoft-spezifisch**  
  
 Generiert eine atomare Anweisung, um einen angegebenen Wert festzulegen.  
  
## <a name="syntax"></a>Syntax  
  
```  
long _InterlockedExchange(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_acq(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLEAcquire(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_HLERelease(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_nf(  
   long volatile * Target,  
   long Value  
);  
long _InterlockedExchange_rel(  
   long volatile * Target,  
   long Value  
);  
char _InterlockedExchange8(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_acq(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_nf(  
   char volatile * Target,  
   char Value  
);  
char _InterlockedExchange8_rel(  
   char volatile * Target,  
   char Value  
);  
short _InterlockedExchange16(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_acq(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_nf(  
   short volatile * Target,  
   short Value  
);  
short _InterlockedExchange16_rel(  
   short volatile * Target,  
   short Value  
);  
__int64 _InterlockedExchange64(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_acq(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLEAcquire(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_HLERelease(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_nf(  
   __int64 volatile * Target,  
   __int64 Value  
);  
__int64 _InterlockedExchange64_rel(  
   __int64 volatile * Target,  
   __int64 Value  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in, out] `Target`  
 Zeiger auf den Wert, der ausgetauscht werden soll. Die Funktion legt diese Variable auf `Value` fest und gibt ihren vorherigen Wert zurück.  
  
 [in] `Value`  
 Wert, der mit dem Wert ausgetauscht werden soll, auf den von `Target` gezeigt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt den Anfangswert zurück, auf den von `Target` gezeigt wird.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|Header|  
|---------------|------------------|------------|  
|`_InterlockedExchange`, `_InterlockedExchange8`, `_InterlockedExchange16`, `_InterlockedExchange64`|X86, ARM, x64|\<intrin.h>|  
|`_InterlockedExchange_acq`, `_InterlockedExchange_nf`, `_InterlockedExchange_rel`, `_InterlockedExchange8_acq`, `_InterlockedExchange8_nf`, `_InterlockedExchange8_rel`, `_InterlockedExchange16_acq`, `_InterlockedExchange16_nf`, `_InterlockedExchange16_rel`, `_InterlockedExchange64_acq`, `_InterlockedExchange64_nf`, `_InterlockedExchange64_rel`,|ARM|\<intrin.h>|  
|`_InterlockedExchange_HLEAcquire`, `_InterlockedExchange_HLERelease`, `_InterlockedExchange64_HLEAcquire`, `_InterlockedExchange64_HLERelease`|x86, x64|\<immintrin.h>|  
  
## <a name="remarks"></a>Hinweise  
 `_InterlockedExchange` bietet systeminterne compilerunterstützung für die Win32-Windows-SDK [InterlockedExchange](/windows/desktop/api/winbase/nf-winbase-interlockedexchange) Funktion.  
  
 Es gibt mehrere Varianten von `_InterlockedExchange`, die sich basierend auf den beinhalteten Datentypen und in Abhängigkeit davon unterscheiden, ob prozessorspezifische Semantiken zum Abrufen bzw. Freigeben verwendet werden.  
  
 Die `_InterlockedExchange`-Funktion funktioniert mit ganzzahligen 32-Bit-Werten, `_InterlockedExchange8` funktioniert mit ganzzahligen 8-Bit-Werten, `_InterlockedExchange16` funktioniert mit ganzzahligen 16-Bit-Werten, und `_InterlockedExchange64` funktioniert mit ganzzahligen 64-Bit-Werten.  
  
 Verwenden Sie auf ARM-Plattformen die systeminternen Funktionen mit den Suffixen `_acq` und `_rel` für Semantiken zum Abrufen bzw. Freigeben, z. B. am Beginn und am Ende eines kritischen Abschnitts. Die systeminternen Funktionen mit einer `_nf`-Suffix ("no fence") fungieren nicht als Speicherbarriere.  
  
 Auf Intel-Plattformen, die Hardware Lock Elision (HLE)-Anweisungen unterstützen, enthalten die systeminternen Funktionen mit den Suffixen `_HLEAcquire` und `_HLERelease` einen Hinweis für den Prozessor, wie die Leistung durch den Wegfall der Schreibsperre in der Hardware beschleunigt werden kann. Wenn diese systeminternen Funktionen auf Plattformen aufgerufen werden, die HLE nicht unterstützen, wird der Hinweis ignoriert.  
  
 Diese Routinen sind nur als systeminterne Funktionen verfügbar.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel zur Verwendung `_InterlockedExchange`, finden Sie unter [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Konflikt mit dem x86-Compiler](../build/conflicts-with-the-x86-compiler.md)