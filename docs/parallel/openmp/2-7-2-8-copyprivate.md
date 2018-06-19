---
title: 2.7.2.8 Copyprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c809f297da5059a98915e8055dfe23f45074366f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691602"
---
# <a name="2728-copyprivate"></a>2.7.2.8 copyprivate
Die **Copyprivate** -Klausel bietet einen Mechanismus, um eine private Variable zu verwenden, um einen Wert von einem Mitglied eines Teams mit den anderen Mitgliedern zu übertragen. Es ist eine Alternative zur Verwendung einer freigegebenen Variable für den Wert, wenn eine solche freigegebene Variable bereitstellen (z. B. in eine Rekursion, erfordern eine andere Variable auf jeder Ebene) schwierig wäre. Die **Copyprivate** Klausel kann nur verwendet werden, auf die **einzelne** Richtlinie.  
  
 Die Syntax der **Copyprivate** -Klausel ist wie folgt:  
  
```  
  
copyprivate(  
variable-list  
)  
  
```  
  
 Die Auswirkung der **Copyprivate** -Klausel für die Variablen in der Variablenliste tritt ein, nach der Ausführung von einem strukturierten Block zugeordnet der **einzelne** erstellen, und vor allen Threads in der Team die Grenze am Ende des Konstrukts verlassen haben. Klicken Sie auf alle anderen Threads in der Team für jede Variable in der *Variablenliste*, dieser Variablen wird (wie durch Zuweisung) definiert, mit dem Wert des entsprechenden Variable in dem Thread, der das Konstrukt ausgeführt des strukturiert. Block.  
  
 Einschränkungen für die **Copyprivate** Klausel lauten wie folgt:  
  
-   Eine Variable, die im angegebenen der **Copyprivate** Klausel muss nicht angezeigt werden, einer **private** oder **Firstprivate** -Klausel für die gleiche **einzelne**Richtlinie.  
  
-   Wenn eine **einzelne** -Direktive zusammen mit einer **Copyprivate** Klausel in der dynamischen Wertebereich eines parallelen Bereichs festgestellt wird, alle Variablen, die in angegebenen der **Copyprivate** -Klausel sein muss im umschließenden Kontext privat.  
  
-   Eine Variable, die im angegebenen der **Copyprivate** -Klausel muss ein zugänglich eindeutig Kopierzuweisungsoperator aufweisen.