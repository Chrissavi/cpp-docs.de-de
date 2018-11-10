---
title: 'Unicode: Der Breitzeichensatz'
ms.date: 11/04/2016
f1_keywords:
- c.international
helpviewer_keywords:
- Unicode [C++], wide character set
- wide characters [C++], Unicode
ms.assetid: b6a05a21-59a5-4d30-8c85-2dbe185f7a74
ms.openlocfilehash: 0432de1203d595947eb958a032870a929f00aeb0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618295"
---
# <a name="unicode-the-wide-character-set"></a>Unicode: Der Breitzeichensatz

Ein Breitzeichen ist ein mehrsprachiger 2-Byte-Zeichencode. Alle in der modernen Computerwelt verwendeten Zeichen, einschließlich technischer Symbole und spezieller Veröffentlichungszeichen, können nach der Unicode-Spezifikation als Breitzeichen dargestellt werden. Der Unicode-Standard wurde von einem großen Konsortium entwickelt und überarbeitet, zu dem auch Microsoft gehört, und zählt heute zu den etablierten Standards.

Ein Breitzeichen weist den Typ **wchar_t** auf. Eine Breitzeichenzeichenfolge wird als **wchar_t[]**-Array dargestellt, auf das mit einem `wchar_t*`-Zeiger gezeigt wird. Sie können jedes ASCII-Zeichen als Breitzeichen darstellen, indem Sie den Buchstaben **L** dem Zeichen voranstellen. L'\0' ist beispielsweise das abschließende (16-Bit) NULL-Breitzeichen. Auf ähnliche Weise können Sie jedes ASCII-Zeichenfolgenliteral als Breitzeichen-Zeichenfolgenliteral darstellen, indem Sie einfach den Buchstabe L dem ASCII-Literal voranstellen (L"Hello").

Im Allgemeinen nehmen Breitzeichen mehr Arbeitsspeicher in Anspruch als Multibytezeichen, werden aber schneller verarbeitet. Darüber hinaus kann jeweils nur ein Gebietsschema in der Multibytecodierung dargestellt werden, während alle Zeichensätze der Welt gleichzeitig von der Unicode-Darstellung dargestellt werden können.

## <a name="see-also"></a>Siehe auch

[Internationalisierung](../c-runtime-library/internationalization.md)<br/>
[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
