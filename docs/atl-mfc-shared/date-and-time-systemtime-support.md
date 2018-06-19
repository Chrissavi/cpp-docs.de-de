---
title: 'Datum und Uhrzeit: SYSTEMTIME-Support | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- system time
- FILETIME structure, with CTime class
- time [C++], formatting
- SYSTEMTIME structure
- dates [C++], MFC
- formatting [C++], time
ms.assetid: 201528e4-2ffa-48fc-af8f-203aa86d942a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecbfd517a0fd535a23920ae21d03f1756babc113
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355399"
---
# <a name="date-and-time-systemtime-support"></a>Datum und Uhrzeit: SYSTEMTIME-Unterstützung
Die [CTime](../atl-mfc-shared/reference/ctime-class.md) -Klasse verfügt über Konstruktoren, die System- und Dateizeiten von Win32 akzeptieren. Wenn Sie `CTime`-Objekte zu diesem Zweck verwenden, müssen Sie deren Initialisierung entsprechend anpassen, wie in diesem Artikel beschrieben.  
  
 Informationen zur SYSTEMTIME-Struktur finden Sie unter [SYSTEMTIME](../mfc/reference/systemtime-structure1.md). Informationen zur FILETIME-Struktur finden Sie unter [FILETIME](../mfc/reference/filetime-structure.md).  
  
 MFC bietet weiterhin `CTime`-Konstruktoren, die Argumente im MS-DOS-Format akzeptieren. Ab MFC-Version 3.0 unterstützt die `CTime`-Klasse jedoch auch einen Konstruktor, der eine Win32-`SYSTEMTIME`-Struktur akzeptiert, und einen anderen, der eine Win32-`FILETIME`-Struktur akzeptiert.  
  
 Die neuen `CTime`-Konstruktoren sind:  
  
-   CTime (const SYSTEMTIME & `sysTime`);  
  
-   CTime (const FILETIME & `fileTime`);  
  
 Der `fileTime`-Parameter ist ein Verweis auf eine Win32-`FILETIME`-Struktur, die die Zeit als einen 64-Bit-Wert darstellt. Dabei handelt es sich um ein zweckmäßigeres Format für die interne Speicherung als eine `SYSTEMTIME`-Struktur und das von Win32 verwendete Format zur Darstellung der Dateierstellungszeit.  
  
 Wenn Ihr Code ein `CTime`-Objekt enthält, das mit der Systemzeit initialisiert wurde, sollten Sie unter Win32 den `SYSTEMTIME`-Konstruktor verwenden.  
  
 Verwenden Sie wahrscheinlich nicht `CTime` `FILETIME` -Initialisierung direkt. Bei Verwendung von einer `CFile` Objekt, das eine Datei zu manipulieren [CFile:: GetStatus](../mfc/reference/cfile-class.md#getstatus) Ruft den Dateizeitstempel ab, für die Sie über eine `CTime` Objekt initialisiert wird, mit einer `FILETIME` Struktur.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren  
  
-   [Allgemeine Datums- und zeitprogrammierung in MFC](../atl-mfc-shared/date-and-time.md)  
  
-   [Automatisierungssupport bei der Datums- und zeitprogrammierung](../atl-mfc-shared/date-and-time-automation-support.md)  
  
-   [Allgemeine Klassen für die Datums- und zeitprogrammierung](../atl-mfc-shared/date-and-time-general-purpose-classes.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Datum und Uhrzeit](../atl-mfc-shared/date-and-time.md)

