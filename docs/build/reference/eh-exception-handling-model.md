---
title: -EH (Ausnahmebehandlungsmodell) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExceptionHandling
- /eh
- VC.Project.VCCLCompilerTool.ExceptionHandling
dev_langs:
- C++
helpviewer_keywords:
- exception handling, compiler model
- cl.exe compiler, exception handling
- EH compiler option [C++]
- -EH compiler option [C++]
- /EH compiler option [C++]
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96b009a9f209ffcc4bb84550c5f37680ef71c9fe
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379106"
---
# <a name="eh-exception-handling-model"></a>/EH (Ausnahmebehandlungsmodell)
Gibt die Art der Ausnahmebehandlung an, die vom Compiler verwendet werden soll, gibt an, ob Ausnahmeprüfungen wegoptimiert werden sollen, und gibt an, ob C++-Objekte zerstört werden sollen, die sich aufgrund einer Ausnahme nicht mehr im Gültigkeitsbereich befinden. Wenn **/EH** nicht angegeben ist, fängt der Compiler sowohl asynchrone strukturierte Ausnahmen als auch C++-Ausnahmen ab. C++-Objekte, die wegen einer asynchronen Ausnahme außerhalb des Gültigkeitsbereichs liegen, werden jedoch nicht zerstört.  
  
## <a name="syntax"></a>Syntax  
  
```  
/EH{s|a}[c][r][-]  
```  
  
## <a name="arguments"></a>Argumente  
 **a**  
 Das Ausnahmebehandlungsmodell, mit dem sowohl asynchrone (strukturierte) als auch synchrone (C++) Ausnahmen abgefangen werden.  
  
 **s**  
 Das Ausnahmebehandlungsmodell, das nur C++-Ausnahmen abfängt und den Compiler anweist anzunehmen, dass Funktionen, die als `extern "C"` -Funktionen deklariert sind, eine C++-Ausnahme auslösen können.  
  
 **c**  
 Bei Verwendung mit **s** (**/EHsc**) werden nur C++-Ausnahmen erfasst, und der Compiler wird angewiesen anzunehmen, dass Funktionen, die als `extern "C"` -Funktionen deklariert sind, nie eine C++-Ausnahme auslösen.  
  
 **/EHca** entspricht **/EHa**.  
  
 **r**  
 Weist den Compiler an, immer Laufzeitbeendigungsprüfungen für alle `noexcept` -Funktionen zu generieren. Standardmäßig können Laufzeitprüfungen für `noexcept` wegoptimiert werden, wenn der Compiler feststellt, dass die Funktion nur nicht auslösende Funktionen aufruft.  
  
## <a name="remarks"></a>Hinweise  
 Die Compileroption **/EHa** unterstützt die asynchrone strukturierte Ausnahmebehandlung (Structured Exception Handling, SEH) mit der systemeigenen C++-Klausel `catch(...)` . Sie können zur Implementierung von SEH ohne Angabe von **/EHa**die Syntax `__try`, `__except`und `__finally` verwenden. SEH wird zwar von Windows und Visual C++ unterstützt, trotzdem ist die Verwendung der ISO-Standard-C++-Ausnahmebehandlung (**/EHs** oder **/EHsc**) empfehlenswert, da Code damit besser portierbar und flexibler ist. Trotzdem in vorhandenem Code oder für bestimmte Arten von Programmen – z. B. in Code, der zur Unterstützung der common Language Runtime kompiliert ([/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md)) – Sie können es erforderlich sein, SEH verwenden. Weitere Informationen finden Sie unter [Structured Exception Handling (C/C++)](../../cpp/structured-exception-handling-c-cpp.md).  
  
 Die Angabe von **/EHa** und der Versuch, alle Ausnahmen mit `catch(...)` zu behandeln, kann riskant sein. Da asynchrone Ausnahmen größtenteils nicht behebbar sind, gelten sie als schwerwiegende Ausnahmen. Wenn Sie sie abfangen und den Prozess anschließend fortsetzen, können Beschädigungen und Fehler auftreten, die schwer zu finden und zu beheben sind.  
  
 Wenn Sie **/EHs** oder **/EHsc**verwenden, werden durch die `catch(...)` -Klausel keine asynchronen strukturierten Ausnahmen abgefangen. Zugriffverletzungen und verwaltete <xref:System.Exception?displayProperty=fullName> -Ausnahmen werden nicht abgefangen, und beim Erzeugen von asynchronen Ausnahmen werden Objekte im Gültigkeitsbereich nicht beschädigt, auch dann nicht, wenn die asynchrone Ausnahme behandelt wird.  
  
 Wenn Sie **/EHa**verwenden, erhalten Sie möglicherweise ein größeres und weniger leistungsfähiges Image, weil der Compiler einen `try` -Block nicht so aggressiv optimiert. Außerdem bewirkt es ein Verlassen in Ausnahmefiltern, die automatisch die Destruktoren aller lokalen Objekte aufrufen, und zwar selbst dann, wenn der Compiler keinen Code feststellt, der eine C++-Ausnahme auslösen kann. Dies ermöglicht sichere Stapelentladungen für asynchrone Ausnahmen sowie für C++-Ausnahmen. Wenn Sie **/EHs**verwenden, nimmt der Compiler an, dass Ausnahmen nur bei einer `throw` -Anweisung oder bei einem Funktionsaufruf auftreten können. Damit kann der Compiler Code für die Lebensdauerverfolgung vieler nicht entladbarer Objekte entfernen, wodurch sich die Codegröße u. U. deutlich reduziert.  
  
 Es wird empfohlen, Objekte, die mit **/EHa** kompiliert wurden, im selben ausführbaren Modul nicht mit Objekten zu verknüpfen, die mit **/EHs** kompiliert wurden. Wenn Sie eine asynchrone Ausnahme behandeln müssen, indem Sie **/EHa** an einer beliebigen Position innerhalb des Moduls verwenden, kompilieren Sie mithilfe von **/EHa** den gesamten Code im Modul. Sie können die Syntax für die strukturierte Ausnahmebehandlung im selben Modul wie Code verwenden, der mit **/EHs**kompiliert wurde, jedoch dürfen Sie die SEH-Syntax innerhalb einer Funktion nicht mit `try`, `throw`und `catch` kombinieren.  
  
 Verwenden Sie **/EHa** , wenn Sie eine Ausnahme abfangen möchten, die nicht durch eine `throw`. Im nachfolgenden Beispiel wird eine strukturierte Ausnahme generiert und abgefangen:  
  
```cpp  
// compiler_options_EHA.cpp  
// compile with: /EHa  
#include <iostream>  
#include <excpt.h>  
using namespace std;  
  
void fail() {   // generates SE and attempts to catch it using catch(...)  
   try {  
      int i = 0, j = 1;  
      j /= i;   // This will throw a SE (divide by zero).  
      printf("%d", j);   
   }  
   catch(...) {   // catch block will only be executed under /EHa  
      cout<<"Caught an exception in catch(...)."<<endl;  
   }  
}  
  
int main() {  
   __try {  
      fail();   
   }  
  
   // __except will only catch an exception here  
   __except(EXCEPTION_EXECUTE_HANDLER) {     
   // if the exception was not caught by the catch(...) inside fail()  
      cout << "An exception was caught in __except." << endl;  
   }  
}  
```  
  
 Für die **/EHc** -Option muss **/EHs** oder **/EHa** angegeben sein. Die **/clr** Option impliziert **/EHa** (d. h., **/clr /EHa** ist redundant). Vom Compiler wird ein Fehler generiert, wenn **/EHs[c]** nach **/clr**verwendet wird. Optimierungen haben auf dieses Verhalten keinen Einfluss. Wenn die Ausnahme abgefangen wird, werden vom Compiler die Klassendestruktoren für die Objekte aufgerufen, die sich in demselben Gültigkeitsbereich wie die Ausnahme befinden. Wenn eine Ausnahme nicht abgefangen wird, werden diese Destruktoren nicht ausgeführt.  
  
 Weitere Informationen über Beschränkungen für die Ausnahmebehandlung unter **/clr**finden Sie unter [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md).  
  
 Die Option kann mit dem Symbol **-** deaktiviert werden. So wird **/EHsc-** beispielsweise als **/EHs /EHc-** interpretiert und entspricht **/EHs**.  
  
 Die Compileroption **/EHr** -Compileroption erzwingt Laufzeitbeendigungsprüfungen in allen Funktionen, die ein `noexcept` -Attribut haben. Standardmäßig können Laufzeitprüfungen wegoptimiert werden, wenn das Compiler-Back-End feststellt, dass eine Funktion nur *nicht auslösende* Funktionen aufruft. Nicht auslösende Funktionen sind alle Funktionen, die ein Attribut haben, das angibt, dass keine Ausnahmen ausgelöst werden können. Hierzu gehören Funktionen, die mit `noexcept`, `throw()`, `__declspec(nothrow)`markiert sind, sowie **/EHc** -Funktionen, wenn `extern "C"` -Funktionen zu generieren. Zu den nicht auslösenden Funktionen gehört auch jede Funktion, für die der Compiler durch Prüfung ermittelt hat, dass sie nicht auslösend ist. Sie können die Standardeinstellung explizit mit **/EHr-** festlegen.  
  
 Das Attribut für nicht auslösend bedingt jedoch keine Garantie, dass von einer Funktion keine Ausnahmen ausgelöst werden können. Im Unterschied zum Verhalten einer `noexcept` -Funktion sieht der Visual C++-Compiler eine Ausnahme, die durch eine Funktion ausgelöst wurde, die mit `throw()`, `__declspec(nothrow)`oder `extern "C"` deklariert ist, als nicht definiertes Verhalten an. Funktionen, für die diese drei Deklarationsattribute verwendet werden, erzwingen keine Laufzeitbeendigungsprüfungen für Ausnahmen. Sie können die **/EHr** -Option verwenden, um dieses undefinierte Verhalten ermitteln zu können, indem der Compiler gezwungen wird, Laufzeitprüfungen für nicht behandelte Ausnahmen zu generieren, die eine `noexcept` -Funktion umgehen.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie im linken Bereich die Struktur **Konfigurationseigenschaften**, **C/C++**, **Codegenerierung**.  
  
3.  Ändern Sie die Eigenschaft **C++-Ausnahmen aktivieren** .  
  
     Oder legen Sie den Wert für **C++-Ausnahmen aktivieren** auf **Nein**fest, und fügen Sie dann auf der Eigenschaftenseite **Befehlszeile** im Feld **Zusätzliche Optionen** die Compileroption hinzu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Fehler- und Ausnahmebehandlung](../../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Ausnahmespezifikationen (Throw)](../../cpp/exception-specifications-throw-cpp.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)