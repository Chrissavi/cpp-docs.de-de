---
title: Linkertoolwarnung Lnk4022 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cffb9c4c67bc3003b8dcdda0ad3a2e8d55abe932
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300370"
---
# <a name="linker-tools-warning-lnk4022"></a>Linkertoolwarnung LNK4022
eindeutige Übereinstimmung für das Symbol 'Symbol' wurde nicht gefunden.  
  
 LINK oder LIB mehrere gefunden für das angegebene nicht ergänzten Symbol entspricht, und es konnte nicht die Mehrdeutigkeit aufzulösen. Es wird keine Ausgabedatei (.exe, .dll, .exp oder .lib) erstellt. Diese Warnung durch eine einzige Warnung folgt [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) für jedes Symbol doppelt vorhanden und wird schließlich gefolgt von Schwerwiegender Fehler [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).  
  
 Um diese Warnung zu vermeiden, geben Sie das Symbol in seiner ergänzten Form. Führen Sie [DUMPBIN](../../build/reference/dumpbin-options.md) für das Objekt anzeigen von ergänzten Namen.