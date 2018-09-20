---
title: 2.7.2 Datenfreigabe-Attributklauseln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 47347d3c-18bd-441f-99cf-7737564c417f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8c53cace8d50f10fe638ea8604c46e457f69ee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392513"
---
# <a name="272-data-sharing-attribute-clauses"></a>2.7.2 Datenfreigabe-Attributklauseln

Mehrere Direktiven akzeptieren-Klauseln, die einem Benutzer ermöglichen, die gemeinsame Nutzung Attribute von Variablen für die Dauer des Bereichs zu steuern. Freigabe Attribut Klauseln gelten nur für Variablen im lexikalischen Block der Richtlinie auf dem die Klausel wird angezeigt. Nicht alle der folgenden Klauseln sind für alle Anweisungen zulässig. Die Liste der Klauseln, die für eine bestimmte Richtlinie gültig sind, werden mit der Direktive beschrieben.

Wenn eine Variable ist sichtbar, wenn eine parallele oder Arbeit-sharing-Konstrukt festgestellt wird, und die Variable in einer Freigabe Attribut-Klausel nicht angegeben ist oder **Threadprivate** die Richtlinie, klicken Sie dann die Variable wird freigegeben. Statische Variablen, die innerhalb der dynamischen Wertebereich eines parallelen Bereichs deklariert werden, gemeinsam genutzt. Heap zugewiesenen Speicher (z. B. **malloc()** in C oder C++ oder **neue** -Operator in C++) freigegeben wird. (Der Zeiger an den Arbeitsspeicher, kann jedoch jedoch entweder privat oder freigegeben sein.) Variablen mit automatischer Speicherdauer innerhalb der dynamischen Wertebereich eines parallelen Bereichs deklariert sind privat.

Die meisten Klauseln akzeptieren einen *Variablenliste* Argument, das eine durch Trennzeichen getrennte Liste von Variablen ist, die angezeigt werden. Wenn eine Variable in verwiesen Datenfreigabeklausel im Attribut weist einen Typ, der aus einer Vorlage abgeleitet und es keine weiteren Verweise auf diese Variable im Programm, das Verhalten nicht definiert ist.

Alle Variablen, die in Direktivenklauseln angezeigt werden, müssen sichtbar sein. Klauseln nach Bedarf wiederholt werden können, aber keine Variable kann in mehr als eine Klausel angegeben werden, außer dass eine Variable in beiden angegeben werden, kann eine **Firstprivate** und **Lastprivate** Klausel.

Die folgenden Abschnitte beschreiben die Klauseln für die Datenfreigabe-Attribut:

- **private**, [Abschnitt 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) auf Seite 25.

- **Firstprivate**, [Abschnitt 2.7.2.2](../../parallel/openmp/2-7-2-2-firstprivate.md) auf Seite 26.

- **Lastprivate**, [Abschnitt 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) auf Seite "27".

- **freigegebene**, [Abschnitt 2.7.2.4](../../parallel/openmp/2-7-2-4-shared.md) auf Seite "27".

- **standardmäßige**, [Abschnitt 2.7.2.5](../../parallel/openmp/2-7-2-5-default.md) auf Seite 28.

- **Verringerung der**, [Abschnitt 2.7.2.6](../../parallel/openmp/2-7-2-6-reduction.md) auf Seite 28.

- **Copyin**, [Abschnitt 2.7.2.7](../../parallel/openmp/2-7-2-7-copyin.md) auf Seite 31.

- **Copyprivate**, [Abschnitt 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) auf Seite "32".