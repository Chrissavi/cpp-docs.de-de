---
title: Dateien und Streams | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [C++]
- streams
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca0850f0e798067ba48b59a1c2585b8ba87c5451
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062175"
---
# <a name="files-and-streams"></a>Dateien und Streams

Ein Programm kommuniziert mit der Zielumgebung durch Lesen und Schreiben von Dateien. Eine Datei kann Folgendes sein:

- Ein Dataset, das Sie wiederholt lesen und schreiben können.

- Ein Datenstrom von Bytes, der von einem Programm (z.B. einer Pipeline) generiert wird.

- Ein Datenstrom von Bytes, der von einem Peripheriegerät eingeht oder dorthin gesendet wird.

Die beiden letzten Elemente sind interaktive Dateien. Dateien sind in der Regel das wesentliche Mittel, um mit einem Programm zu interagieren. Sie bearbeiten alle diese Arten von Dateien im Wesentlichen in gleicher Weise – durch Aufrufen von Bibliotheksfunktionen. Sie schließen den Standardheader STDIO. H ein, um die meisten dieser Funktionen zu deklarieren.

Bevor Sie viele der Vorgänge für eine Datei ausführen können, muss die Datei geöffnet werden. Beim Öffnen wird einer Datei ein Datenstrom zugeordnet – eine Datenstruktur innerhalb der C-Standardbibliothek, die viele Unterschiede zwischen Dateien verschiedener Art abdeckt. Die Bibliothek verwaltet den Status der einzelnen Datenströme in einem Objekt vom Typ FILE.

Die Zielumgebung öffnet vor dem Programmstart drei Dateien. Sie können eine Datei durch Aufrufen der Bibliotheksfunktion [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) mit zwei Argumenten öffnen. (Die `fopen`-Funktion ist veraltet – verwenden Sie stattdessen [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).) Das erste Argument ist ein Dateiname. Das zweite Argument ist eine C-Zeichenfolge, die Folgendes angibt:

- Ob Sie beabsichtigen, Daten aus der Datei zu lesen, darin zu schreiben oder beides.

- Ob Sie beabsichtigen, neuen Inhalt für die Datei zu generieren (oder eine Datei zu erstellen, sofern sie nicht zuvor vorhanden war) oder den vorhandenen Inhalt unverändert zu lassen.

- Ob das Schreiben in eine Datei vorhandenen Inhalt ändern kann oder nur Bytes am Ende der Datei anhängen sollte.

- Ob Sie einen Text- oder Binärdatenstrom bearbeiten möchten.

Wenn die Datei erfolgreich geöffnet wird, können Sie bestimmen, ob der Datenstrom byteorientiert (Bytedatenstrom) oder weitenorientiert (weiter Datenstrom) sein soll. Ein Datenstrom ist anfänglich nicht gebunden. Das Aufrufen bestimmter Funktionen für den Datenstrom macht ihn byteorientiert, während bestimmte andere Funktionen ihn weitenorientiert machen. Sobald eingerichtet, verwaltet ein Datenstrom seine Orientierung, bis er durch einen Aufruf von [fclose](../c-runtime-library/reference/fclose-fcloseall.md) oder [freopen](../c-runtime-library/reference/freopen-wfreopen.md) geschlossen wird.

© 1989-2001 von P.J. Plauger und Jim Brodie. Alle Rechte vorbehalten.

## <a name="see-also"></a>Siehe auch

[Text- und binäre Streams](../c-runtime-library/text-and-binary-streams.md)<br/>
[Byte- und weite Streams](../c-runtime-library/byte-and-wide-streams.md)<br/>
[Steuern von Streams](../c-runtime-library/controlling-streams.md)<br/>
[Streamzustände](../c-runtime-library/stream-states.md)