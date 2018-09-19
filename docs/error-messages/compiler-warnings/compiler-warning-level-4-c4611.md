---
title: Compilerwarnung (Stufe 4) C4611 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4611
dev_langs:
- C++
helpviewer_keywords:
- C4611
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 723976dc8b7085ede9b3157445ff3026de6fc4b9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091048"
---
# <a name="compiler-warning-level-4-c4611"></a>Compilerwarnung (Stufe 1) C4600

Interaktion zwischen "Function" und C++-objektlöschung ist nicht portabel

Auf manchen Plattformen ist die Funktionen, die umfassen **catch** unterstützen möglicherweise keine C++-Objektsemantik der Zerstörung, wenn außerhalb des gültigen Bereichs.

Verwenden Sie zum Vermeiden von unerwartetem Verhalten **catch** in Funktionen, die Konstruktoren und Destruktoren besitzen.

Diese Warnung wird nur einmal ausgegeben; finden Sie unter [Pragma-Warnung](../../preprocessor/warning.md).