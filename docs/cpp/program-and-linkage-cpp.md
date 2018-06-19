---
title: Programm und Verknüpfung (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4154f0951b46b1c8badc0224845d2881cc8ad573
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32421366"
---
# <a name="program-and-linkage--c"></a>Programm und Verknüpfung (C++)

In einem C++-Programm kann jedes globale Symbol nur einmal definiert werden, auch wenn die Anwendung besteht aus mehreren Übersetzungseinheiten befinden. Eine Übersetzungseinheit besteht aus einer Implementierungsdatei (.cpp, .hpp, .cxx usw.) und alle Header, die sie direkt oder indirekt enthält. Ein Programm besteht aus einer oder mehreren Übersetzungseinheiten, die miteinander verknüpft sind. 

## <a name="linkage-vs-scope"></a>Die Verknüpfung im Vergleich zu Bereich

Das Konzept der *Verknüpfung* bezieht sich auf die Sichtbarkeit der globalen Symbole (z. B. Variablen, Typnamen und Funktionsnamen) innerhalb des Programms als Ganzes über Übersetzungseinheiten befinden. Das Konzept der *Bereich* bezieht sich auf die Symbole, die innerhalb eines Blocks z. B. Namespace, Klasse oder Funktionsrumpf deklariert werden. Diese Symbole sind nur innerhalb des Bereichs, in dem sie definiert sind. das Konzept der Bindung gilt nicht für sie.

## <a name="external-vs-internal-linkage"></a>Externe und interne Verknüpfung

Globale Non-Const-Variablen und free-Funktionen in der Standardeinstellung haben externe Verknüpfung; Jetzt sind sie in jeder Übersetzungseinheit im Programm sichtbar. Sie können dieses Verhalten überschreiben, indem explizit deklarieren sie als **statische** wird ihre Sichtbarkeit auf derselben Übersetzungseinheit, die in der sie deklariert werden. Diese Bedeutung des **statische** unterscheidet sich von seiner Bedeutung, wenn auf lokale Variablen angewendet. Variablen, die als **const** eine interne Bindung in der Standardeinstellung haben.

## <a name="extern-constexpr-linkage"></a>"Extern" Constexpr-Verknüpfung

In früheren Versionen von Visual Studio hat der Compiler immer eine Constexpr-Variable interne-Verknüpfung selbst, wenn die Variable "extern" markiert wurde. In Visual Studio 2017 Version 15.5 ermöglicht ein neuer Compilerschalter (/Zc:externConstexpr) das richtige standardkonforme Verhalten. Letztendlich wird dies die Standardeinstellung sein.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Wenn eine Headerdatei eine Variable deklariert "extern" Constexpr enthält, muss er markiert sein **__declspec(selectany)** ordnungsgemäß seiner doppelten Deklarationen, die kombiniert werden sollen:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="see-also"></a>Siehe auch

 [Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)