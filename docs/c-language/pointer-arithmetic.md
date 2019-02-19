---
title: Zeigerarithmetik
ms.date: 11/04/2016
helpviewer_keywords:
- pointer arithmetic
- arithmetic pointer
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
ms.openlocfilehash: c1b3e31561bedece6a6180fbeb13473153a46ab6
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152676"
---
# <a name="pointer-arithmetic"></a>Zeigerarithmetik

Hinzufügevorgänge im Zusammenhang mit einem Zeiger und einer ganzen Zahl geben nur dann sinnvolle Ergebnisse zurück, wenn der Zeigeroperand einen Arraymember adressiert und der Ganzzahlwert eines Offsets innerhalb der Grenzen desselben Arrays erzeugt. Wenn der Ganzzahlwert in einen Adressoffset konvertiert wird, geht der Compiler davon aus, dass zwischen der ursprünglichen Adresse und der Adresse plus Offset nur Speicherpositionen derselben Größe liegen.

Diese Annahme gilt für Arraymember. Definitionsgemäß ist ein Array eine Reihe von Werten desselben Typs. Seine Elemente befinden sich in zusammenhängenden Speicherbereichen. Bei der Speicherung von Typen jeder Art (außer Arrayelemente) ist jedoch nicht gewährleistet, dass der Speicher mit demselben Typ von Bezeichnern gefüllt wird. Das bedeutet, dass Leerzeichen zwischen Speicherpositionen, auch Positionen von gleichen Typ, auftreten können. Daher sind die Ergebnisse des Hinzufügens zu den Adressen oder des Subtrahierens von Adressen aller Werte mit Ausnahme von Arrayelementen nicht definiert.

Auch wenn zwei Zeigerwerte subtrahiert werden, wird so bei der Konvertierung davon ausgegangen, dass nur Werte des gleichen Typs ohne Leerzeichen zwischen den Adressen liegen, die von den Operanden angegeben werden.

## <a name="see-also"></a>Siehe auch

[C-Operatoren (additiv)](../c-language/c-additive-operators.md)
