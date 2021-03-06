---
title: __based-Grammatik
ms.date: 11/04/2016
helpviewer_keywords:
- based addressing
ms.assetid: a68ff750-c7fa-4c0c-8d5f-2df76e4686c5
ms.openlocfilehash: 539ccef65477bafe2c46ce328bdaf65f52aff1b9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229154"
---
# <a name="__based-grammar"></a>__based-Grammatik

**Microsoft-spezifisch**

Die basierende Adressierung ist nützlich, wenn eine genaue Kontrolle über das Segment erforderlich ist, in dem Objekte zugeordnet sind (statische und dynamische basierende Daten).

Die einzige Form der in 32-Bit-und 64-Bit-Kompilierungen akzeptablen basierten Adressierung ist "basierend auf einem Zeiger", die einen Typ definiert, der eine 32-Bit-oder 64-Bit-Verschiebung zu einer 32-Bit-oder einer 64-Bit-Basis oder basierend auf enthält **`void`** .

## <a name="grammar"></a>Grammatik

*based-Range-Modifier*: **__based (**  *Basis Ausdruck*  **)**

*Basis Ausdruck*: *based-variablebased-Abstract-declaratorsegment-NameSEGMENT-Cast*

*based-Variable*: *Bezeichner*

*based-Abstract-declarator*: *abstract-declarator*

*Basistyp*: *Typname*

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Basierte Zeiger](../cpp/based-pointers-cpp.md)
