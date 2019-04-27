---
title: BSCMAKE-Warnung BK4504
ms.date: 11/04/2016
f1_keywords:
- BK4504
helpviewer_keywords:
- BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
ms.openlocfilehash: 7ffcb7c2e6ae512006ccd29c87b05c53fdfcaef5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279293"
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE-Warnung BK4504

Datei enthält zu viele Verweise. Weitere Verweise von dieser Quelle ignoriert

Die CPP-Datei enthält mehr als 64.000 Symbolverweise. Wenn BSCMAKE 64.000 Verweise in einer Datei aufgetreten ist, wird es alle weiteren Verweise ignoriert.

Um das Problem zu beheben, unterteilen Sie die Datei in zwei oder mehr Dateien, von denen jeder maximal 64.000 hat Symbolverweise, oder verwenden Sie die `#pragma component(browser)` Präprozessordirektive Limit-Symbole, die für bestimmte Verweise generiert werden. Weitere Informationen finden Sie unter [Komponente](../../preprocessor/component.md).