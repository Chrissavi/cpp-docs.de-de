---
title: Verwenden die MFC-Quelldateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69079e6f74743a82aa9e9b9b1c13703e480c904c
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951542"
---
# <a name="using-the-mfc-source-files"></a>Verwenden der MFC-Quelldateien
Die Microsoft Foundation Class (MFC)-Bibliothek bietet vollständige Quellcode. Headerdateien (. h) befinden sich im Verzeichnis \atlmfc\include; Implementierungsdateien (.cpp) sind im Verzeichnis \atlmfc\src\mfc.  
  
 Diese Artikelreihe erläutert, die angeben, die MFC verwendet, um die verschiedenen Teile der einzelnen Klassen, was bedeutet, dass diese Kommentare und was Sie erwarten soll, finden Sie in den einzelnen Abschnitten zu kommentieren. Visual C++-Assistenten verwenden ähnliche Konventionen für die Klassen, die sie für Sie erstellen, und wahrscheinlich finden Sie diese Konventionen nützlich für Ihren eigenen Code.  
  
 Sie möglicherweise kennen die **öffentlichen**, **geschützt**, und **private** C++-Schlüsselwörter. Bei Betrachtung der MFC-Headerdateien, werden Sie feststellen, dass jede Klasse, die mehrere der einzelnen aufweisen kann. Beispielsweise Funktionen und Variablen öffentlichen Member möglicherweise unter mehr als einem **öffentlichen** Schlüsselwort. Dies ist, da MFC Membervariablen und Funktionen auf Grundlage ihrer Verwendung nicht durch den Typ, der zulässigen Zugriffstyp trennt. MFC verwendet **private** sparsam; auch Elemente berücksichtigt, Implementierungsdetails sind im Allgemeinen geschützt und oft sind öffentlich. Obwohl der Zugriff auf die Implementierungsdetails abgeraten wird, verbleibt MFC die Entscheidung Sie.  
  
 In der MFC-Quelldateien und die Dateien, die die MFC-Anwendungs-Assistent erstellt, finden Sie Kommentare, wie diese in Klassendeklarationen (in der Regel in dieser Reihenfolge):  
  
 `// Constructors`  
  
 `// Attributes`  
  
 `// Operations`  
  
 `// Overridables`  
  
 `// Implementation`  
  
 In dieser Familie Artikel behandelten Themen gehören:  
  
-   [Ein Beispiel für Kommentare](../mfc/an-example-of-the-comments.md)  
  
-   [Der / / Implementierung Kommentar](../mfc/decrement-implementation-comment.md)  
  
-   [Der / / konstruktorenkommentar](../mfc/decrement-constructors-comment.md)  
  
-   [Der / / Attributes-Kommentar](../mfc/decrement-attributes-comment.md)  
  
-   [Der / / Operations-Kommentar](../mfc/decrement-operations-comment.md)  
  
-   [Der / / Overridables-Kommentar](../mfc/decrement-overridables-comment.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

