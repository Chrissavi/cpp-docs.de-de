---
title: Vermeiden von Problembereichen bei Multithreadprogrammen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], troubleshooting
- errors [C++], multithreaded programs
- threading [C++], troubleshooting
- troubleshooting [C++], multithreading
ms.assetid: 06cc231d-bb5a-409d-8bd3-676c9e2a8c5b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5af4c1ca6a86b2cff457aee12e8337103ce7f42d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686613"
---
# <a name="avoiding-problem-areas-with-multithread-programs"></a>Vermeiden von Problembereichen bei Multithreadprogrammen
Es gibt mehrere Probleme, die Sie erstellen, verknüpfen oder Ausführen einer C-Multithreadprogramm auftreten können. Einige der häufigsten Probleme werden in der folgenden Tabelle beschrieben. (Eine ähnliche Erläuterung von MFC-Sicht, finden Sie unter [Multithreading: Tipps für die Programmierung](../parallel/multithreading-programming-tips.md).)  
  
|Problem|Mögliche Ursache|  
|-------------|--------------------|  
|Sie erhalten ein Meldungsfeld angezeigt, dass das Programm eine Schutz-Verletzung verursacht hat.|Viele Win32-Programmierfehler zu Verletzungen der Schutz führen. Eine häufige Ursache von Verletzungen der Schutz wird der indirekte Zuweisung zu null-Zeiger. Da dies führt dazu, dass das Programm versucht auf Arbeitsspeicher zuzugreifen, die nicht zu der er gehört, wird ein Verstoß Schutz ausgegeben.<br /><br /> Eine einfache Möglichkeit zum Ermitteln der Ursache eines Verstoßes Schutz wird das Programm mit Debuginformationen kompiliert, und führen Sie es dann mithilfe des Debuggers in der Visual C++-Umgebung. Wenn die allgemeine schutzverletzung tritt auf, Windows übergibt die Steuerung an den Debugger, und der Cursor befindet sich auf die Zeile, die das Problem verursacht hat.|  
|Das Programm generiert zahlreiche Fehler in der Kompilierung und Verknüpfung.|Sie können viele potenzielle Probleme vermeiden, indem der Compiler Warnstufe auf die höchsten Werte festlegen und heeding die Warnmeldungen an. Mithilfe der Ebene 3 oder Ebene 4 Warnungsoptionen können Sie unbeabsichtigte datenkonvertierungen, fehlende Funktionsprototypen und Verwendung von nicht-ANSI-Features erkennen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Multithreading bei C und Win32](../parallel/multithreading-with-c-and-win32.md)