---
title: Multithreadingunterstützung für älteren Code (Visual C++)
ms.date: 08/27/2018
helpviewer_keywords:
- threading [C++]
- multiple threads
- concurrent programming [C++]
- programming [C++], multithreaded
- multithreading [C++], about multithreading
- multiple concurrent threads
- multithreading [C++]
ms.assetid: 24425b1f-5031-4c6b-aac7-017115a40e7c
ms.openlocfilehash: 649e26c3f0704dfd6740b1a250613545e29316a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407743"
---
# <a name="multithreading-support-for-older-code-visual-c"></a>Multithreadingunterstützung für älteren Code (Visual C++)

Mit Visual C++ können mehrere parallele Ausführungsthreads gleichzeitig ausgeführt werden. Mit Multithreading können Sie Aufgaben im Hintergrund starten, gleichzeitige Eingabestreams sowie eine Benutzeroberfläche verwalten u. v. m.

## <a name="in-this-section"></a>In diesem Abschnitt

[Multithreading bei C und Win32](multithreading-with-c-and-win32.md)<br/>
Bietet Unterstützung beim Erstellen von Multithreadanwendungen mit Microsoft Windows.

[Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md)<br/>
Definiert Prozesse und Threads und erörtert, wie Multithreading in MFC gehandhabt wird.

[Multithreading und Gebietsschemas](multithreading-and-locales.md)<br/>
Erläutert Probleme, die auftreten, wenn Sie die Gebietsschema-Funktionen von C-Laufzeitbibliothek und C++-Standardbibliothek in einer Multithreadanwendung zu verwenden.

## <a name="related-sections"></a>Verwandte Abschnitte

[CWinThread](../mfc/reference/cwinthread-class.md)<br/>
Stellt einen Ausführungsthread innerhalb einer Anwendung dar.

[CSyncObject](../mfc/reference/csyncobject-class.md)<br/>
Beschreibt eine reine virtuelle Klasse, die die Funktionalität bereitstellt, die alle Synchronisierungsobjekte in Win32 gemeinsam haben.

[CSemaphore](../mfc/reference/csemaphore-class.md)<br/>
Stellt eine Semaphore dar - ein Synchronisierungsobjekt, das einer begrenzten Anzahl von Threads in einem oder mehreren Prozessen den Zugriff auf eine Ressource ermöglicht.

[CMutex](../mfc/reference/cmutex-class.md)<br/>
Stellt einen Mutex dar – ein Synchronisierungsobjekt, das Threads den einander ausschließenden Zugriff auf eine Ressource ermöglicht.

[CCriticalSection](../mfc/reference/ccriticalsection-class.md)<br/>
Stellt einen kritischen Abschnitt dar - ein Synchronisierungsobjekt, das jeweils einem Thread den Zugriff auf eine Ressource oder einen Codeabschnitt ermöglicht.

[CEvent](../mfc/reference/cevent-class.md)<br/>
Stellt ein Ereignis dar - ein Synchronisierungsobjekt, das es einem Thread ermöglicht, einen anderen darüber zu benachrichtigen, dass ein Ereignis aufgetreten ist.

[CMultiLock](../mfc/reference/cmultilock-class.md)<br/>
Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.

[CSingleLock](../mfc/reference/csinglelock-class.md)<br/>
Stellt den Mechanismus zur Zugriffssteuerung dar, mit dessen Hilfe der Zugriff auf Ressourcen in einem Multithreadprogramm gesteuert wird.