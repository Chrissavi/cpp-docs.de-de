---
title: Ergänzte Namen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- decorated names, definition
- name decoration [C++]
- names [C++], decorated
ms.assetid: a4e9ae8e-b239-4454-b401-4102793cb344
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 794e7583158379f84c5ee20408fb784aca213669
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379379"
---
# <a name="decorated-names"></a>Ergänzte Namen
Funktionen, Daten und Objekte werden in C- und C++-Programmen intern durch ihre ergänzten Namen dargestellt. Ein *ergänzten Namens* ist eine codierte Zeichenfolge, die vom Compiler während der Kompilierung eines Objekts, Daten oder Funktionsdefinition erstellt. Er zeichnet Aufrufkonventionen, Typen, Funktionsparameter und sonstige Informationen zusammen mit dem Namen auf. Diese namensergänzung, auch bekannt als *namenszerlegung*, hilft den Linker suchen die richtigen Funktionen und-Objekte beim Verknüpfen einer ausführbaren Datei.  
  
 Die Konventionen für Namensergänzungen haben sich in den verschiedenen Versionen von Visual C++ geändert und können auf verschiedenen Zielarchitekturen ebenfalls unterschiedlich sein. Um die ordnungsgemäße Verknüpfung mit Quelldateien zu gewährleisten, die mit Visual C++ erstellt wurden, müssen C- und C++-DLLs sowie Bibliotheken mit dem gleichen Compilertoolset, den gleichen Kennzeichnungen und der gleichen Zielarchitektur kompiliert werden.  
  
 **Inhalt**  
  
-   [Verwenden von ergänzten Namen](#Using)  
  
-   [Format eines C++ ergänzten Namen](#Format)  
  
-   [Ergänzten Namens in C-Format](#FormatC)  
  
-   [Anzeigen von ergänzten Namen](#Viewing)  
  
-   [Anzeigen von undekorierten Namen](#Undecorated)  
  
##  <a name="Using"></a> Verwenden von ergänzten Namen  
 In der Regel müssen Sie den ergänzten Namen nicht kennen, um Code schreiben zu können, der erfolgreich kompiliert werden kann und richtige Verknüpfungen aufweist. Ergänzte Namen sind ein internes Implementierungsdetail des Compilers und Linkers. Die Tools können den Name in der Regel auch in seiner nicht ergänzten Form behandeln. Ein ergänzter Name ist jedoch manchmal erforderlich, wenn Sie einen Funktionsnamen zum Linker oder anderen Tools angeben. Um zum Beispiel überladene C++-Funktionen, Member von Namespaces, Klassenkonstruktoren, Destruktoren und spezielle Memberfunktionen angeben zu können, müssen Sie den ergänzten Namen verwenden. Weitere Informationen zu den Optionskennzeichnungen und anderen Situationen, in denen ergänzte Namen erforderlich sind, finden Sie in der Dokumentation zu den von Ihnen verwendeten Tools und Optionen.  
  
 Wenn Sie den Funktionsnamen, die Klasse, die Aufrufkonvention, den Rückgabetyp oder einen Parameter ändern, ändert sich auch der ergänzte Name. In diesem Fall müssen Sie den neuen ergänzten Namen abrufen und ihn überall dort verwenden, wo der ergänzte Name angegeben ist.  
  
 Die Namensergänzung ist auch dann wichtig, wenn eine Verknüpfen mit Code erfolgt, der in einer anderen Programmiersprache geschrieben wurde oder andere Compiler verwendet. Verschiedene Compilern verwenden unterschiedliche Konventionen für die Namensergänzung. Wenn Ihre ausführbare Datei eine Verknüpfung zu Code enthält, der in einer anderen Sprache geschrieben wurde, müssen Sie insbesondere darauf achten, dass die exportierten und importierten Namen und Aufrufkonventionen übereinstimmen. Der Assemblersprachcode muss die Aufrufkonventionen und die ergänzten Namen von Visual C++ verwenden, um eine Verknüpfung mit Quellcode zu gewährleisten, der mit Visual C++ geschrieben wurde.  
  
##  <a name="Format"></a> Format eines C++ ergänzten Namen  
 Ein ergänzter Name für eine C++-Funktion enthält die folgenden Informationen:  
  
-   Der Funktionsname.  
  
-   Die Klasse, dessen Mitglied die Funktion ist, wenn es sich um eine Memberfunktion handelt. Dies kann die Klasse einschließen, die die Klasse umschließt, welche die Funktion enthält usw.  
  
-   Der Namespace, zu dem die Funktion gehört, wenn sie Teil eines Namespace ist.  
  
-   Die Typen der Funktionsparameter.  
  
-   Die Aufrufkonvention.  
  
-   Der Rückgabetyp der Funktion.  
  
 Die Namen der Funktion und der Klasse werden im ergänzten Namen codiert. Der Rest des ergänzten Namens ist ein Code, der nur für den Compiler und Linker eine interne Bedeutung hat. Es folgen Beispiele für nicht ergänzte und ergänzte Namen in C++.  
  
|Nicht ergänzter Name|Ergänzter Name|  
|----------------------|--------------------|  
|`int a(char){int i=3;return i;};`|`?a@@YAHD@Z`|  
|`void __stdcall b::c(float){};`|`?c@b@@AAGXM@Z`|  
  
##  <a name="FormatC"></a> Ergänzten Namens in C-Format  
 Das Format einer Ergänzung für eine C-Funktion hängt von der Aufrufkonvention ab, die in der Deklaration verwendet wird. Dies isst in der folgenden Tabelle dargestellt. Dies ist auch das Ergänzungsformat, das verwendet wird, wenn C++-Code mit einer `extern "C"` Verknüpfung deklariert wird. Die Standardaufrufkonvention ist `__cdecl`. Beachten Sie, dass Funktion in einer 64-Bit-Umgebung nicht ergänzt werden.  
  
|Aufrufkonvention|Dekoration|  
|------------------------|----------------|  
|`__cdecl`|Führender Unterstrich (**_**)|  
|`__stdcall`|Führender Unterstrich (**_**) und nachfolgendes @-Zeichen (@) gefolgt von der Anzahl der Bytes in der Parameterliste im Dezimalformat|  
|`__fastcall`|Führende und nachfolgende @-Zeichen gefolgt von einer Dezimalzahl, die die Anzahl der Bytes in der Parameterliste darstellt|  
|`__vectorcall`|Zwei nachfolgende @-Zeichen (@@) gefolgt von einer Bytes-Dezimalzahl in der Parameterliste|  
  
##  <a name="Viewing"></a> Anzeigen von ergänzten Namen  
 Sie erhalten das ergänzte Format eines Symbolnamens, wenn Sie die Quelldatei mit den Daten, dem Objekt oder der Funktionsdefinition bzw. dem Prototypen kompiliert haben. Um ergänzte Namen im Programm zu untersuchen, können Sie eine der folgenden Methoden verwenden:  
  
-   #### <a name="to-use-a-listing-to-view-decorated-names"></a>Verwenden einer Auflistung zum Anzeigen ergänzter Namen  
  
    1.  Generieren Sie eine Liste, indem Sie die Quelldatei, die die Daten, Objekt oder Funktionsdefinition enthält mit dem Prototypen oder Kompilieren der [Dateityp auflisten](../../build/reference/fa-fa-listing-file.md) legen Sie auf die Assembly mit Quellcode-Compileroption (**Angabe von/FAS**).  
  
         Geben Sie z. B. `cl /c /FAs example.cpp` an einer Eingabeaufforderung Developer, um eine Auflistungsdatei generieren example.asm.  
  
    2.  Suchen Sie in der ausgegebenen Auflistungsdatei die Zeile, die mit „PUBLIC“ beginnt und mit einem Semikolon endet, gefolgt vom nicht ergänzten Daten- oder Funktionsnamen. Das Symbol zwischen „PUBLIC“ und dem Semikolon ist der ergänzte Name.  
  
-   #### <a name="to-use-dumpbin-to-view-decorated-names"></a>Verwenden von DUMPBIN zum Anzeigen von ergänzten Namen  
  
    1.  Um die exportierten Symbolen in eine OBJ- oder LIB-Datei anzuzeigen, geben Sie `dumpbin /symbols` `objfile` an einer Developer-Eingabeaufforderung.  
  
    2.  Um das ergänzte Format eines Symbols zu finden, suchen Sie nach dem nicht ergänzten Namen in Klammern. Der ergänzte Name befindet sich in der gleichen Zeile nach einer Pipe (&#124;)-Zeichen und vor dem nicht ergänzten Namen.  
  
##  <a name="Undecorated"></a> Anzeigen von undekorierten Namen  
 Mit „undname.exe“ können Sie einen ergänzten Namen in das nicht ergänzte Format konvertieren. Dieses Beispiel zeigt, wie dies funktioniert:  
  
```  
C:\>undname ?func1@a@@AAEXH@Z  
Microsoft (R) C++ Name Undecorator  
Copyright (C) Microsoft Corporation. All rights reserved.  
  
Undecoration of :- "?func1@a@@AAEXH@Z"  
is :- "private: void __thiscall a::func1(int)"  
```  
  
## <a name="see-also"></a>Siehe auch  
 [C/C++-Buildtools](../../build/reference/c-cpp-build-tools.md)   
 [Verwenden von "extern" zur Angabe der Verknüpfung](../../cpp/using-extern-to-specify-linkage.md)