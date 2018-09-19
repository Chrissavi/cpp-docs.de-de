---
title: Compilerfehler C2722 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2722
dev_langs:
- C++
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9138172bb108095c4e72407f1e17e8f4fa2370c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082663"
---
# <a name="compiler-error-c2722"></a>Compilerfehler C2722

":: Operator': Operatorbefehl unzulässig; Verwenden Sie "Operator" Operator "

Ein `operator` Anweisung Neudefinitionen `::new` oder `::delete`. Die `new` und `delete` Operatoren global sind, sodass der Bereichsauflösungsoperator (`::`) ist ohne Bedeutung. Entfernen Sie die `::` Operator.