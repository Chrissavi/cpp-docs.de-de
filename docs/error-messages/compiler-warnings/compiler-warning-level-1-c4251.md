---
title: Compilerwarnung (Stufe 1) C4251 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4251
dev_langs:
- C++
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 366d66a38685e75e47d8921f9ebd525b334ced7e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282131"
---
# <a name="compiler-warning-level-1-c4251"></a>Compilerwarnung (Stufe 1) C4251
'Bezeichner': Klasse "Type" Dll-Schnittstelle, die von der Klasse "Typ2" verwendet werden muss  
  
 Die Möglichkeit der Beschädigung von Daten zu minimieren, wenn eine Klasse mit exportieren [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), sicherstellen, dass:  
  
-   Alle statischen Daten ist der Zugriff über Funktionen, die von der DLL exportiert werden.  
  
-   Inlinemethoden der Klasse können statische Daten ändern.  
  
-   Inlinemethoden Ihrer Klasse verwenden CRT-Funktionen oder andere Bibliotheksfunktionen statische Daten (finden Sie unter [potenzielle Fehler übergeben CRT-Objekten über DLL-Grenzen](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) für Weitere Informationen).  
  
-   Keine Methoden der Klasse (unabhängig von inlining) können auch Typen, für die Instanziierung in der EXE und DLL statische Datenunterschiede haben.  
  
 Sie können vermeiden, Exportieren von Klassen definieren, die eine DLL, die definiert eine Klasse mit virtuellen Funktionen und Funktionen aufrufen kann, instanziieren und Löschen von Objekten des Typs.  Sie können dann virtuelle Funktionen nur für den Typ aufrufen.  
  
 Weitere Informationen zum Exportieren von Vorlagen finden Sie unter [ http://support.microsoft.com/default.aspx?scid=KB; EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4251 kann ignoriert werden, wenn Sie aus einem Typ in der C++-Standardbibliothek, die eine Debugversion kompilieren abgeleitet werden (**/MTd**) und, in dem die Fehlermeldung des Compilers auf _Container_base bezieht.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```