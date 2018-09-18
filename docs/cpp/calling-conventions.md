---
title: Aufrufkonventionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97a03e8c73f75e51a955805cd4ad76b902b0373c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071483"
---
# <a name="calling-conventions"></a>Aufrufkonventionen

Der Compiler für Visual C/C++ stellt mehrere unterschiedliche Konventionen für das Aufrufen von internen und externen Funktionen bereit. Das Verständnis dieser verschiedenen Ansätze hilft Ihnen, Ihr Programm zu debuggen und den Code mit Routinen in Assemblysprache zu verknüpfen.

In diesen Themen werden die Unterschiede zwischen den Aufrufkonventionen, wie Argumente übergeben werden und wie Werte über Funktionen zurückgegeben werden, erläutert. Es werden auch reine Funktionsaufrufe, eine erweiterte Funktion, die es erlaubt, Ihren eigenen Einleitungs- und Epilogcode zu schreiben, besprochen.

Informationen zu den Aufrufkonventionen für X64-Prozessoren finden Sie unter [Aufrufkonvention](../build/calling-convention.md).

## <a name="topics-in-this-section"></a>Themen in diesem Abschnitt

- [Argumentübergabe und Benennungskonventionen](../cpp/argument-passing-and-naming-conventions.md) (`__cdecl`, `__stdcall`, `__fastcall`, usw.)

- [Aufrufbeispiel:Funktionsprototyp und Aufruf](../cpp/calling-example-function-prototype-and-call.md)

- [Verwendung von naked-Funktionsaufrufe, um benutzerdefinierte Prolog-und Epilogcode zu schreiben.](../cpp/naked-function-calls.md)

- [Gleitkomma-Coprozessor und Aufrufkonventionen](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [Veraltete Aufrufkonventionen](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>Siehe auch

[Microsoft-spezifische Modifizierer](../cpp/microsoft-specific-modifiers.md)