---
title: Compilerwarnung (Stufe 4) C4471 | Microsoft Docs
ms.custom: ''
ms.date: 04/24/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4471
dev_langs:
- C++
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a530cee3c3fcfec8566d46b116fcc4e71760ed11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302684"
---
# <a name="compiler-warning-level-4-c4471"></a>Compilerwarnung (Stufe 4) C4471
"*Enumeration*': eine Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung benötigen einen zugrunde liegenden Typ (Int wird angenommen)  
  
Eine Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung wurde ohne einen Spezifizierer für den zugrunde liegenden Typ gefunden. Standardmäßig geht davon aus Visual C++ `int` des zugrunde liegenden Typs für eine Enumeration ist. Dies kann Probleme verursachen, wenn Sie ein anderen Typ in der Enumerationsdefinition beispielsweise verwendet wird, wenn ein anderer expliziter Typ angegeben wird, oder ein anderen Typ implizit durch einen Initialisierer festgelegt wird. Möglicherweise müssen Sie auch Portabilitätsproblemen; andere Compiler gehen Sie nicht `int` der zugrunde liegende Typ einer Enumeration ist.  
  
Diese Warnung ist standardmäßig deaktiviert; Verwenden Sie/Wall oder/w*N*4471 aktivieren Sie ihn in der Befehlszeile aus, oder verwenden #pragma [Warnung](../../preprocessor/warning.md) in der Quelldatei.  
  
In einigen Fällen hat diese Warnung unbegründete. Wenn Sie eine Vorwärtsdeklaration für eine Enumeration nach der Definition angezeigt wird, kann diese Warnung ausgelöst werden. Beispielsweise ist dieser Code gültig ist, obwohl sie C4471 führen kann:  
  
```cpp  
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```  
  
## <a name="example"></a>Beispiel  
Im Allgemeinen ist es sicher ist, verwenden Sie die vollständige Definition für eine Enumeration ohne bereichseinschränkung anstelle einer Vorwärtsdeklaration. Sie können die Definition in einer Headerdatei und fügen Sie ihn in den Quelldateien, die darauf verweisen. Dies funktioniert in C ++ 98 und höher geschriebenen Code. Es wird empfohlen, diese Lösung für Portabilität und Vereinfachung der Verwaltung.  
  
```cpp  
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```  
  
## <a name="example"></a>Beispiel  
In C ++ 11 können Sie einen expliziten Typ und dessen Vorwärtsdeklaration einer Enumeration ohne bereichseinschränkung hinzufügen. Diese Lösung wird empfohlen, nur dann, wenn die Verwendung der Definition anstelle einer Vorwärtsdeklaration complex-Header Aufnahme Logik verhindert wird. Diese Lösung kann dazu führen, dass ein Wartungsproblem: Wenn Sie den zugrunde liegenden Typ, der für die Enumerationsdefinition verwendet, müssen Sie auch alle von der Vorwärtsdeklarationen entsprechend ändern, oder ändern unter Automatische Fehler im Code müssen Umständen. Sie können eine Headerdatei, um dieses Problem weitgehendst auszuschließen Vorwärtsdeklaration abgelegt.  
  
```cpp  
// C4471c.cpp
// Client code for enumeration defined in C4471d.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example;    // C4471, int assumed
// To fix, replace the lines above with the forward declarations:
// enum Example : unsigned;
// ...
```  
  
```cpp  
// C4471d.cpp
// Definition for enumeration used in C4471c.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example : unsigned { item = 0x80000000 }; // explicit type
// ...
```  
  
Wenn Sie einen expliziten Typ für eine Enumeration angeben, sollten Sie Sie auch die Warnung aktivieren [C4369](compiler-warning-level-1-C4369.md), die ist standardmäßig aktiviert. Hierdurch wird die Fälle, in denen ein Enumerationselement einen anderen Typ als dem explizit angegebenen Typs erfordert.
  
## <a name="example"></a>Beispiel  
Sie können den Code, um einer bereichsbezogenen Enumeration ist ein Feature verwenden, die neu in C ++ 11 ist ändern. Die Definition und irgendeinen Clientcode, der den Enumerationstyp wird verwendet, müssen zum Verwenden einer Enumeration mit Gültigkeitsbereich geändert werden. Es wird empfohlen, dass Sie eine Enumeration mit Gültigkeitsbereich verwenden, wenn Sie Probleme mit Namespacekonflikte, haben wie die Namen der Enumeration definierten Elemente auf den Bereich der Enumeration beschränkt sind. Eine weitere Funktion von einer Enumeration mit Gültigkeitsbereich ist, dass Membern implizit in einen anderen Typ für einen Ganzzahl- oder Enumeration konvertiert werden können, der Quelle geringfügige Fehler sein kann.

```cpp  
// C4471e.cpp
// Client code for scoped enumeration defined in C4471f.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum Example;    // C4471
// To fix, replace the line above with the forward declaration:
// enum class Example;
// ...
```  
  
```cpp  
// C4471f.cpp
// Definition for scoped enumeration used in C4471e.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum class Example { item = 0 };
// ...
```  
  
