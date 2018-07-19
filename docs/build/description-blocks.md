---
title: Beschreibungsblöcke | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- description blocks
- NMAKE program, description blocks
- blocks, description
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0784f08c479a8c8f3968ef61a01431cd9e0ca71e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367107"
---
# <a name="description-blocks"></a>Beschreibungsblöcke
Ein Beschreibungsblock ist eine Abhängigkeit optional gefolgt von einem Befehlsblock:  
  
```  
targets... : dependents...  
    commands...  
```  
  
 Eine Abhängigkeit Linie gibt an, ein oder mehrere Ziele und keinem oder mehreren abhängigen Elemente. Ein Ziel muss am Anfang der Zeile sein. Separate Ziele von abhängigen Dateien von einem Doppelpunkt (:)), Leerzeichen oder Tabstopps sind zulässig. Um die Zeile zu teilen, verwenden Sie einen umgekehrten Schrägstrich (\) nach einem Ziel "oder" abhängig. Wenn ein Ziel nicht vorhanden ist, hat einen früheren Zeitstempel als eine abhängige oder ist eine [Pseudoziel](../build/pseudotargets.md), NMAKE führt die Befehle aus. Wenn eine abhängige Datei ein Ziel an anderer Stelle ist und nicht vorhanden ist oder in Bezug auf seine eigenen abhängigen Elemente veraltet ist, aktualisiert NMAKE die abhängigen vor dem Aktualisieren der aktuellen Abhängigkeit.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
 [Targets](../build/targets.md) (MSBuild-Ziele)  
  
 [Abhängige Dateien](../build/dependents.md)  
  
## <a name="see-also"></a>Siehe auch  
 [NMAKE-Referenz](../build/nmake-reference.md)