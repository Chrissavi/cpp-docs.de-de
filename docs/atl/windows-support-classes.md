---
title: Windows-Unterstützungsklassen (ATL)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
ms.openlocfilehash: 5880fd970d885da84edd94f9f2c7a47ec326ebe1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195480"
---
# <a name="windows-support-classes"></a>Windows-Unterstützungsklassen

Die folgenden Klassen bieten Unterstützung für Windows:

- [_U_MENUorID](../atl/reference/u-menuorid-class.md) bietet Wrapper für `CreateWindow` und `CreateWindowEx`.

- [CWindow](../atl/reference/cwindow-class.md) enthält Methoden zum Bearbeiten eines Fensters. `CWindow` ist die Basisklasse für `CWindowImpl`, `CDialogImpl` und `CContainedWindow`.

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) implementiert ein Fenster, die basierend auf einem neuen Fensterklasse. Ermöglicht Ihnen zudem Unterklasse oder übergeordnete Klasse des Fensters.

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) implementiert ein Dialogfeld.

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) implementiert ein Dialogfeld (gebunden oder ungebunden), die ActiveX-Steuerelemente hostet.

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) implementiert ein Dialogfeld (gebunden oder ungebunden) mit grundlegender Funktionalität.

- [CAxWindow](../atl/reference/caxwindow-class.md) bearbeitet ein Fenster, das ein ActiveX-Steuerelement hostet.

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) bietet Methoden zum Bearbeiten von ein Fenster, ein ActiveX-Steuerelement hostet, und bietet auch Unterstützung für die lizenzierten ActiveX-Steuerelemente hosten.

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) implementiert ein Fenster in einem anderen Objekt enthalten sind.

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) verwaltet die Informationen eine neue Windows-Klasse.

- [CDynamicChain](../atl/reference/cdynamicchain-class.md) unterstützt dynamische Verkettung von meldungszuordnungen.

- [CMessageMap](../atl/reference/cmessagemap-class.md) ermöglicht, die ein Objekt, dessen Meldung verfügbar zu machen für andere Objekte zuordnet.

- [CWinTraits](../atl/reference/cwintraits-class.md) bietet eine einfache Methode zur Standardisierung der Merkmale eines ATL-Fenster-Objekts.

- [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) werden Standardwerte für Window-Stile und erweiterte Stile verwendet, um ein Fenster zu erstellen. Diese Werte werden hinzugefügt, mit der logischen OR-Operator, um Werte während der Erstellung eines Fensters.

## <a name="related-articles"></a>Verwandte Artikel

[ATL-Fensterklassen](../atl/atl-window-classes.md)

[ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../atl/atl-class-overview.md)<br/>
[Meldungszuordnungsmakros](../atl/reference/message-map-macros-atl.md)<br/>
[Fensterklassen-Makros](../atl/reference/window-class-macros.md)
