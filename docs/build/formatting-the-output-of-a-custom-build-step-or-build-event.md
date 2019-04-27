---
title: Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses
ms.date: 08/27/2018
helpviewer_keywords:
- builds [C++], build events
- custom build steps [C++], output format
- events [C++], build
- build events [C++], output format
- build steps [C++], output format
- builds [C++], custom build steps
ms.assetid: 92ad3e38-24d7-4b89-90e6-5a16f5f998da
ms.openlocfilehash: b0e9a7514704742524f97e55c06ef47c7b36631b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195367"
---
# <a name="formatting-the-output-of-a-custom-build-step-or-build-event"></a>Formatieren der Ausgabe eines benutzerdefinierten Buildschritts oder eines benutzerdefinierten Buildereignisses

Wenn die Ausgabe eines benutzerdefinierten Buildschritts oder -ereignisses ordnungsgemäß formatiert wurde, erhalten Benutzer die folgenden Vorteile:

- Warnungen und Fehler werden im **Ausgabefenster** gezählt.

- Die Ausgabe wird im Fenster **Aufgabenliste** angezeigt.

- Wenn Sie im **Ausgabefenster** auf die Ausgabe klicken, wird das entsprechende Thema angezeigt.

- F1-Vorgänge werden im Fenster **Aufgabenliste** oder im **Ausgabefenster** aktiviert.

Das Format der Ausgabe sollte wie folgt sein:

> {<em>Dateiname</em>**(**<em>Zeilennr.</em> \[**,** <em>Spaltennr.</em>]**)** &#124; *Toolname*} **:** \[ <em>beliebiger Text</em> ] {**Fehler** &#124; **Warnung**} <em>Code + Nummer</em>**:**<em>lokalisierbare Zeichenfolge</em> \[ <em>beliebiger Text</em> ]

Ort:

- {*a* &#124; *b*} ist eine Wahl von entweder *a* oder *b*.

- \[<em>item</em>] ist eine optionale Zeichenfolge oder ein Parameter.

- **bold** stellt ein Literal dar.

Zum Beispiel:

> C:\\*sourcefile.cpp*(134) : Fehler C2143: Syntaxfehler: fehlendes „;“ vor „}“
>
> LINK: Schwerwiegender Fehler LNK1104: Datei „*somelib.lib*“ kann nicht geöffnet werden

## <a name="see-also"></a>Siehe auch

[Grundlagen benutzerdefinierter Buildschritte und Buildereignisse](understanding-custom-build-steps-and-build-events.md)