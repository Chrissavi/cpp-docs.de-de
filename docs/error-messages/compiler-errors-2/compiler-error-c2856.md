---
title: Compilerfehler C2856 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2856
dev_langs:
- C++
helpviewer_keywords:
- C2856
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df6226bfd2fc11f05f894091f4ff02c145d09e11
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072711"
---
# <a name="compiler-error-c2856"></a>Compilerfehler C2856

\#Pragma-Hdrstop kann nicht innerhalb eines #if-Block befinden.

Die `hdrstop` Pragma kann nicht innerhalb des Texts eines Blocks für die bedingte Kompilierung nicht platziert werden.

Verschieben der `#pragma hdrstop` Anweisung, um einen Bereich, der nicht in enthalten ist ein `#if/#endif` Block.