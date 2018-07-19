---
title: Definieren von C-Inlinefunktionen mit „dllexport“ und „dllimport“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- inline functions [C++], with dllexport and dllimport
- dllimport attribute [C++], inline functions
- dllexport attribute [C++], inline functions
- dllexport attribute [C++]
ms.assetid: 41418f7c-1c11-470b-bb2e-1f8269a239f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58ca4ab6fdfe06dec6d790db3135e42a6eeb39d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384622"
---
# <a name="defining-inline-c-functions-with-dllexport-and-dllimport"></a>Definieren von C-Inlinefunktionen mit dllexport und dllimport
**Microsoft-spezifisch**  
  
 Sie können eine Funktion mit dem `dllexport`-Attribut als inline definieren. In diesem Fall wird die Funktion immer instanziiert und exportiert, unabhängig davon, ob ein beliebiges Modul im Programm auf die Funktion verweist oder nicht. Die Funktion wurde vermutlich von einem anderen Programm importiert.  
  
 Sie können auch eine Funktion als inline definieren, die mit dem **dllimport**-Attribut deklariert wurde. In diesem Fall kann die Funktion (gemäß der Compileroption-Spezifikation "/Ob (inline)") erweitert, aber niemals instanziiert werden. Insbesondere bei Verwendung der Adresse der inline-importierten Funktion wird die Adresse der Funktion in der DLL zurückgegeben. Dieses Verhalten stimmt mit der Übernahme der Adresse einer nicht-inline importierten Funktion überein.  
  
 Statische lokale Daten und Zeichenfolgen in Inlinefunktionen behalten die gleichen Identitäten zwischen der DLL und dem Client wie in einem einzelnen Programm (d. h. eine ausführbare Datei ohne DLL-Schnittstelle) bei.  
  
 Lassen Sie beim Bereitstellen von importierten Inlinefunktionen Sorgfalt walten. Gehen Sie beispielsweise beim Aktualisieren der DLL nicht davon aus, dass der Client die geänderte Version der DLL verwendet. Um sicherzustellen, dass Sie die richtige Version der DLL laden, erstellen Sie auch den DLL-Client neu.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Import- und Exportfunktionen einer DLL](../c-language/dll-import-and-export-functions.md)