---
title: Schwerwiegender Fehler C1211 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1211
dev_langs:
- C++
helpviewer_keywords:
- C1211
ms.assetid: df0ca70d-ec6e-4400-926a-b877e2599978
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 444d2bc25c2eddd5ea9a0170272bd3e71b61f94f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018525"
---
# <a name="fatal-error-c1211"></a>Schwerwiegender Fehler C1211

Das benutzerdefinierte TypeForwardedTo-Attribut wird von der installierten Laufzeitversion nicht unterstützt.

C1211 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime (CLR) einer früheren Version verwenden.

Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.

Installieren Sie die CLR, die im Lieferumfang des von Ihnen verwendeten Compilers enthalten war, um C1211 zu beheben.

Weitere Informationen finden Sie unter [Typweiterleitung (C++ / CLI)](../../windows/type-forwarding-cpp-cli.md).