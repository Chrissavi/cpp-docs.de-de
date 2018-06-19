---
title: EXPORTE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- EXPORTS
dev_langs:
- C++
helpviewer_keywords:
- EXPORTS .def file statement
ms.assetid: dbcd7579-b855-44c4-bd27-931e157657f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7cc7a9995fdc5be786712752e30015337b9f1607
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376825"
---
# <a name="exports"></a>EXPORTS
Führt einen Abschnitt mit mindestens einer Exportdefinition ein, die die exportierten Namen oder Ordinalzahlen von Funktionen oder Daten angibt. Jede Definition muss sich in einer separaten Zeile befinden.  
  
```  
EXPORTS  
   definition  
```  
  
## <a name="remarks"></a>Hinweise  
 Die erste `definition` kann sich in derselben Zeile wie das `EXPORTS`-Schlüsselwort oder in einer nachfolgenden Zeile befinden. Die .DEF-Datei kann eine oder mehrere `EXPORTS`-Anweisungen enthalten.  
  
 Die Syntax für eine Export-`definition` lautet:  
  
```  
  
entryname[=internalname] [@ordinal [NONAME]] [[PRIVATE] | [DATA]]  
```  
  
 `entryname` ist der Funktions- oder Variablenname, den Sie exportieren möchten. Dieser ist erforderlich. Wenn sich der Name, den Sie exportieren, von dem Namen in der DLL unterscheiden, geben Sie den Namen des Exports in der DLL an, indem Sie `internalname` verwenden. Wenn Ihre DLL beispielsweise eine Funktion `func1` exportiert und Sie möchten, dass Aufrufer sie als `func2` verwenden, würden Sie Folgendes angeben:  
  
```  
EXPORTS  
   func2=func1  
```  
  
 Da der Visual C++-Compiler die Namensergänzung für C++-Funktionen verwendet, müssen den ergänzten Namen als `entryname` oder `internalname` verwenden oder die exportierten Funktionen über `extern "C"` im Quellcode definieren. Der Compiler ergänzt auch C-Funktionen, mit denen die [__stdcall](../../cpp/stdcall.md) -Aufrufkonvention mit einem Unterstrich (_) als Präfix und Suffix besteht das at-Zeichen (@) gefolgt von der Anzahl von Bytes (dezimal) in der Argumentliste.  
  
 Um die vom Compiler erzeugten, ergänzten Namen zu ermitteln, verwenden die [DUMPBIN](../../build/reference/dumpbin-reference.md) Tool oder die Linkeroption [/MAP](../../build/reference/map-generate-mapfile.md) Option. Die ergänzten Namen sind compilerspezifisch. Wenn Sie die ergänzten Namen in der .DEF-Datei exportieren, müssen die ausführbaren Dateien, die zur DLL verknüpfen, ebenfalls mit derselben Version des Compilers erstellt werden. Damit wird sichergestellt, dass die ergänzten Namen im Aufrufer den exportierten Namen in der .DEF-Datei entsprechen.  
  
 Sie können @`ordinal` verwenden, um anzugeben, dass eine Zahl und nicht der Funktionsname in die Exporttabelle der DLL geht. Viele Windows-DLLs exportieren Ordinalzahlen, um Legacycode zu unterstützen. Es war üblich, Ordinalzahlen in 16-Bit-Windows-Code zu verwenden, weil das dazu beitragen kann, die Größe einer DLL zu minimieren. Es wird nicht empfohlen, Funktionen anhand der Ordinalzahl zu exportieren, es sei denn, die Clients Ihrer DLL benötigen sie zur Legacyunterstützung. Da die .LIB-Datei die Zuordnung zwischen der Ordinalzahl und der Funktion enthält, können Sie den Funktionsnamen verwenden, wie Sie es normalerweise in Projekten tun würden, die die DLL verwenden.  
  
 Durch Verwendung des optionalen `NONAME`-Schlüsselworts können Sie nur anhand der Ordinalzahl exportieren und die Größe der Exporttabelle in der resultierenden DLL reduzieren. Jedoch, wenn Sie verwenden möchten [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) in der DLL müssen Sie die Ordinalzahl kennen, da der Name nicht gültig ist.  
  
 Das optionale Schlüsselwort `PRIVATE` verhindert, dass `entryname` in die von LINK generierte Importbibliothek eingeschlossen wird. Es wirkt sich nicht auf den Export des ebenfalls von LINK generierten Image aus.  
  
 Das optionale Schlüsselwort `DATA` gibt an, dass ein Export Daten und nicht Code umfasst. Das folgende Beispiel zeigt, wie Sie eine Datenvariable namens `exported_global` exportieren könnten:  
  
```  
EXPORTS  
   exported_global DATA  
```  
  
 Es gibt vier Möglichkeiten für das Exportieren einer Definition, aufgelistet in empfohlener Reihenfolge:  
  
1.  Die [__declspec(dllexport)](../../cpp/dllexport-dllimport.md) Schlüsselwort im Quellcode  
  
2.  Eine `EXPORTS`-Anweisung in einer .DEF-Datei  
  
3.  Ein [/EXPORT](../../build/reference/export-exports-a-function.md) -Spezifikation in einem Linkbefehl  
  
4.  Ein [Kommentar](../../preprocessor/comment-c-cpp.md) -Direktive im Quellcode des Formulars `#pragma comment(linker, "/export: definition ")`  
  
 Alle vier Methoden können im selben Programm verwendet werden. Wenn LINK ein Programm erstellt, das Exporte enthält, wird auch eine Importbibliothek erstellt, es sei denn, im Build wird eine .EXP-Datei verwendet.  
  
 Hier ist ein Beispiel für einen EXPORTS-Abschnitt:  
  
```  
EXPORTS  
   DllCanUnloadNow      @1          PRIVATE  
   DllWindowName = WindowName       DATA  
   DllGetClassObject    @4 NONAME   PRIVATE  
   DllRegisterServer    @7  
   DllUnregisterServer  
```  
  
 Wenn Sie eine Variable aus einer DLL über dien .DEF-Datei exportieren, müssen Sie `__declspec(dllexport)` nicht in der Variable angeben. Sie müssen jedoch in jeder Datei, die die DLL verwendet, immer noch `__declspec(dllimport)` in der Deklaration der Daten verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)