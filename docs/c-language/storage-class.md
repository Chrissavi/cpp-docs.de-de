---
title: Speicherklasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- linkage [C++], external
- function storage class
- function specifiers, storage class
- storage classes
- Microsoft-specific storage classes
- external linkage, storage-class specifiers
- static storage class specifiers
ms.assetid: 39a79ba6-edf5-42b6-8e45-f94227603dd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5473a3c11268e7e8563d95392ec6439e55c03bf4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757161"
---
# <a name="storage-class"></a>Speicherklasse
Der Speicherklassenspezifizierer in einer Funktionsdefinition gibt für die Funktion entweder die Speicherklasse `extern` oder **static** an.  
  
## <a name="syntax"></a>Syntax

*function-definition*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *attribute-seq*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

/\* *attribute-seq* ist Microsoft-spezifisch \*/

*declaration-specifiers*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*storage-class-specifier* *declaration-specifiers*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-specifier* *declaration-specifiers*<sub>opt</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*type-qualifier* *declaration-specifiers*<sub>opt</sub>  

*storage-class-specifier*: /\* Für Funktionsdefinitionen \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**extern**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**static**

Wenn *storage-class-specifier* in einer Funktionsdefinition nicht enthalten ist, verwendet die Speicherklasse standardmäßig `extern`. Sie können eine Funktion explizit als `extern` deklarieren, dies ist jedoch nicht erforderlich.  
  
Wenn die Deklaration einer Funktion den *storage-class-specifier* `extern` enthält, hat der Bezeichner dieselben Verknüpfungen wie jede sichtbare Deklaration des Bezeichners mit Dateigültigkeitsbereich. Wenn es keine sichtbare Deklaration mit Dateigültigkeitsbereich gibt, verfügt der Bezeichner über externe Verknüpfung. Wenn ein Bezeichner über einen Dateigültigkeitsbereich, aber nicht über *storage-class-specifier* verfügt, hat der Bezeichner keine externe Verknüpfung. Externe Verknüpfung bedeutet, dass jede Instanz des Bezeichners das gleiche Objekt bzw. die gleiche Funktion bezeichnet. Weitere Informationen zu Verknüpfungen und zum Dateigültigkeitsbereich erhalten Sie im Artikel über [Lebensdauer, Bereich, Sichtbarkeit und Verknüpfung](../c-language/lifetime-scope-visibility-and-linkage.md).  
  
Funktionsdeklarationen für Blockbereiche mit einem anderen Speicherklassenspezifizierer als `extern` generieren Fehler.  
  
Eine Funktion mit der Speicherklasse **static** wird nur innerhalb der Quelldatei angezeigt, in der sie definiert ist. Alle anderen Funktionen, ob ihnen die Speicherklasse `extern` explizit oder implizit zugewiesen, sind in allen Quelldateien im Programm sichtbar. Wenn **static** als Speicherklasse gewünscht wird, muss diese auf dem ersten Vorkommen einer Deklaration (wenn vorhanden) der Funktion und in der Definition der Funktion deklariert werden.  
  
**Microsoft-spezifisch**  
  
Wenn die Microsoft-Erweiterungen aktiviert werden, wird für eine Funktion, die ursprünglich ohne Speicherklasse deklariert wurde (oder mit der Speicherklasse `extern`) die Speicherklasse **static** angegeben, wenn die Funktionsdefinition in der gleichen Quelldatei enthalten ist und die Definition die Speicherklasse **static** explizit angibt.  
  
Beim Kompilieren mit der Compileroption "/Ze-", verfügen die Funktionen, die in einem Block mit dem `extern`-Schlüsselwort deklariert werden, über globale Sichtbarkeit. Dies gilt nicht beim Kompilieren mit "/Za". Auf diese Funktion sollte nicht zurückgegriffen werden, wenn die Portabilität von Quellcode zu berücksichtigen ist.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
[C-Funktionsdefinitionen](../c-language/c-function-definitions.md)