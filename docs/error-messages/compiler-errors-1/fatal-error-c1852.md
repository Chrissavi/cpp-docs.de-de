---
title: Schwerwiegender Fehler C1852
ms.date: 11/04/2016
f1_keywords:
- C1852
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
ms.openlocfilehash: 895c2fc988c9566f9e50b1ac1a18eb4dc1c6661a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601499"
---
# <a name="fatal-error-c1852"></a>Schwerwiegender Fehler C1852

'Dateiname' ist keine gültige vorkompilierte Headerdatei.

Die Datei ist kein vorkompilierter Header.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:

1. Es wurde eine ungültige Datei mit **/Yu** oder **#pragma hdrstop**angegeben.

1. Wenn Sie keine andere Angabe vornehmen, nimmt der Compiler die Dateierweiterung PCH an.