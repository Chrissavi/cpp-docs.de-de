---
title: Compilerfehler C2692
ms.date: 11/04/2016
f1_keywords:
- C2692
helpviewer_keywords:
- C2692
ms.assetid: 02ade3b4-b757-448b-b065-d7d71bc3f441
ms.openlocfilehash: c469f4944417c9116c7316b01642dd4b370b8c4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611158"
---
# <a name="compiler-error-c2692"></a>Compilerfehler C2692

"Funktionsname": vollständige Funktionen mit Prototyp erforderlich sind, im C-Compiler mit der "/ Clr" Option

Wenn Code Kompilieren für .NET verwaltet werden, erfordert der C-Compiler Funktionsdeklarationen ANSI. Darüber hinaus, wenn eine Funktion keine Parameter akzeptiert, sie müssen explizit deklarieren `void` als Parametertyp.