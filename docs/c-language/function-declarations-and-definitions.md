---
title: Funktionsdeklarationen und -definitionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- local declarations
- function definitions, function declarations
- declaring functions, function definitions
- internal declarations
- external declarations
- function prototypes, basics
- external linkage, function declarations
- declaring functions
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 704e8defa8aac640ce5011e5789d4af36380b7a0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32384992"
---
# <a name="function-declarations-and-definitions"></a>Funktionsdeklarationen und -definitionen
Funktionsprototypen legen den Namen der Funktion, des Rückgabetyps und des Typs und der Anzahl von formalen Parametern fest. Eine Funktionsdefinition enthält den Funktionsrumpf.  
  
## <a name="remarks"></a>Hinweise  
 Funktions- und Variablendeklarationen können innerhalb oder außerhalb einer Funktionsdefinition angezeigt werden. Jede Deklaration innerhalb einer Funktionsdefinition wird auf "interner" oder "lokaler" Ebene angezeigt. Eine Deklaration außerhalb aller Funktionsdefinitionen wird auf "externer", globaler" oder auf Ebene des "Dateigültigkeitsbereichs" angezeigt. Variable Definitionen, wie Deklarationen, können auf der internen Ebene (innerhalb einer Funktionsdefinition) oder auf der externen Ebene angezeigt (außerhalb aller Funktionsdefinitionen) werden. Funktionsdefinitionen treten immer auf der externen Ebene auf. Funktionsdefinitionen werden unter [Funktionsdefinitionen](../c-language/c-function-definitions.md) näher erläutert. Funktionsprototypen werden unter [Funktionsprototypen](../c-language/function-prototypes.md) behandelt.  
  
## <a name="see-also"></a>Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)