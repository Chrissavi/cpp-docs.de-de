---
title: Ratschläge für allgemeine MBCS-Programmierung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- _mbcs
dev_langs:
- C++
helpviewer_keywords:
- MBCS [C++], dialog box fonts
- MS Shell Dlg
- MBCS [C++], programming
- dialog boxes [C++], fonts
ms.assetid: 7b541235-f3e5-4af0-b2c2-a0112cd5fbfb
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab2b67c82a04a0c355761ec6572a9718d03c4666
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855798"
---
# <a name="general-mbcs-programming-advice"></a>Allgemeine Ratschläge für die MBCS-Programmierung
Verwenden Sie die folgenden Tipps:  
  
-   Verwenden Sie Flexibilität erhalten Sie, wie z. B. Makros zur Laufzeit `_tcschr` und `_tcscpy` nach Möglichkeit. Weitere Informationen finden Sie unter [Zuordnungen für generischen Text in Tchar.h](../text/generic-text-mappings-in-tchar-h.md).  
  
-   Verwenden Sie die C-Laufzeit `_getmbcp` Funktion zum Abrufen von Informationen über die aktuelle Codepage.  
  
-   Zeichenfolgenressourcen nicht wiederverwendet werden. Abhängig von der Zielsprache möglicherweise eine bestimmte Zeichenfolge eine andere Bedeutung, wenn übersetzt. Hauptmenü "File" auf der Anwendungsverzeichnis könnte z. B. unterschiedlich aus der Zeichenfolge "File" in einem Dialogfeld übersetzen. Wenn Sie mehr als eine Zeichenfolge mit dem gleichen Namen verwenden möchten, verwenden Sie für jede verschiedenen Zeichenfolgen-IDs.  
  
-   Möglicherweise möchten herausfinden, ob Ihre Anwendung unter einem MBCS-fähigen Betriebssystem ausgeführt wird. Zu diesem Zweck legen Sie ein Flag beim Programmstart; verlassen Sie sich nicht auf API-Aufrufe.  
  
-   Beim Entwerfen von Dialogfeldern können Sie ca. 30 % zusätzliche Leerzeichen am Ende des statischen Text-Steuerelemente für die MBCS-Übersetzung.  
  
-   Gehen Sie beim Auswählen von Schriftarten für Ihre Anwendung sein, da einige Schriftarten nicht auf allen Systemen verfügbar sind.  
  
-   Verwenden Sie bei der Auswahl der Schriftart für Dialogfelder [MS Shell Dlg](http://msdn.microsoft.com/library/windows/desktop/dd374112) anstelle von MS Sans Serif oder Helvetica. MS Shell Dlg wird durch die richtige Schriftart vom System vor dem Erstellen des Dialogfelds "" ersetzt. Die Verwendung von MS Shell Dlg wird sichergestellt, dass alle Änderungen im Betriebssystem für den Umgang mit dieser Schriftart automatisch zur Verfügung stehen. (MFC ersetzt MS Shell Dlg durch DEFAULT_GUI_FONT oder Systemschriftart unter Windows 95, Windows 98 und Windows NT 4, da diese Systeme MS Shell Dlg nicht ordnungsgemäß behandeln.)  
  
-   Beim Entwerfen Ihrer Anwendung entscheiden Sie, welche Zeichenfolgen lokalisiert werden können. Im Zweifelsfall wird davon ausgegangen Sie, dass alle angegebene Zeichenfolge lokalisiert werden. Kombinieren Sie Zeichenfolgen, die lokalisiert werden können daher nicht mit denen, die nicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Tipps für die MBCS-Programmierung](../text/mbcs-programming-tips.md)   
 [Inkrementieren und Dekrementieren von Zeigern](../text/incrementing-and-decrementing-pointers.md)