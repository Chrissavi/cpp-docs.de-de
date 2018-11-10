---
title: Byte- und weite Streams
ms.date: 11/04/2016
f1_keywords:
- Byte and Wide Streams
helpviewer_keywords:
- byte streams
- wide streams
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
ms.openlocfilehash: bb14cbd5caed413425810bfe017e068f4b4b4257
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590426"
---
# <a name="byte-and-wide-streams"></a>Byte- und weite Streams

Ein Bytestream verarbeitet eine Datei als Bytesequenz. Innerhalb des Programms weist der Stream die identische Sequenz von Bytes auf.

Im Gegensatz dazu verarbeitet ein weiter Stream eine Datei als Sequenz von generalisierten Multibytezeichen, die eine große Bandbreite an Codierungsregeln mit sich bringen können. (Text- und Binärdateien werden weiterhin wie zuvor beschrieben gelesen und geschrieben.) Innerhalb des Programms sieht der Stream wie die entsprechende Breitzeichensequenz aus. Konvertierungen zwischen den beiden Darstellungen erfolgen innerhalb der C-Standardbibliothek. Die Konvertierungsregeln können grundsätzlich durch einen Aufruf von [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) geändert werden, mit dem die Kategorie `LC_CTYPE` geändert wird. Jeder weite Stream bestimmt die Konvertierungsregeln zu dem Zeitpunkt, an dem es weit ausgerichtet wird, und behält diese Regeln bei, wenn anschließend die Kategorie `LC_CTYPE` geändert wird.

Für die Positionierung in einem weiten Stream gelten dieselben Einschränkungen wie für Textstreams. Darüber hinaus muss der Dateipositionszeiger eventuell auch eine statusabhängige Codierung verarbeiten. Diese enthält in der Regel einen Byteoffset innerhalb des Streams und ein Objekt vom Typ `mbstate_t`. Daher ist das Aufrufen von [fgetpos](../c-runtime-library/reference/fgetpos.md) die einzig zuverlässige Möglichkeit, um eine Dateiposition in einem weiten Stream zu ermitteln; die zuverlässige Möglichkeit, um eine auf diese Weise ermittelte Position wiederherzustellen, gelingt durch Aufrufen von [fsetpos](../c-runtime-library/reference/fsetpos.md).

## <a name="see-also"></a>Siehe auch

[Dateien und Streams](../c-runtime-library/files-and-streams.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)