---
title: . CODE | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff2d66cfc79e84c8c4c7cf92e117c9ac8c84a555
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682486"
---
# <a name="code"></a>.CODE

Bei Verwendung mit [. Modell](../../assembler/masm/dot-model.md), gibt den Anfang ein Codesegment.

## <a name="syntax"></a>Syntax

> . CODE [[Name]]

#### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|`name`|Optionaler Parameter, der den Namen des Codesegments angibt. Der Standardname lautet _TEXT für kleine, klein, kompakte und flachen [Modelle](../../assembler/masm/dot-model.md). Der Standardname lautet *Modulename*_TEXT für andere Modelle.|

## <a name="see-also"></a>Siehe auch

[Anweisungen – Referenz](../../assembler/masm/directives-reference.md)<br/>
[.DATA](../../assembler/masm/dot-data.md)<br/>