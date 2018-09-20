---
title: Welcher Overhead entsteht beim Ableiten einer Klasse von CObject? | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e41f9060ce24b89a0a7faae54ca6207c740475f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46443240"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>Welcher Overhead entsteht beim Ableiten einer Klasse von CObject?

Der Aufwand beim Ableiten einer Klasse [CObject](../mfc/reference/cobject-class.md) ist sehr einfach gehalten. Die abgeleitete Klasse erbt, nur vier virtuelle Funktionen und einem einzelnen [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) Objekt.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse: Häufig gestellte Fragen](../mfc/cobject-class-frequently-asked-questions.md)
