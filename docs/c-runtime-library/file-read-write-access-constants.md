---
title: Datei-Lese-/Schreibzugriffkonstanten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.constants.file
dev_langs:
- C++
helpviewer_keywords:
- read/write access constants
- write access constants
- access constants for file read/write
- constants [C++], file attributes
- file read/write access constants
ms.assetid: 56cd1d22-39a5-4fcf-bea2-7046d249e8ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f57ac6ffc3c13c640d7bdf6a2ec64912148bfbc3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32391141"
---
# <a name="file-readwrite-access-constants"></a>Datei-Lese-/Schreibzugriffkonstanten
## <a name="syntax"></a>Syntax  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Konstanten geben den Zugriffstyp für die angeforderte Datei an („a“, „r“ oder „w“). Sowohl der [Übersetzungsmodus](../c-runtime-library/file-translation-constants.md) („b“ oder „t“) als auch der [commit-to-disk-mode](../c-runtime-library/commit-to-disk-constants.md) („c“ oder „n“) kann mit dem Zugriffstyp angegeben werden.  
  
 Die Zugriffstypen werden nachfolgend beschrieben.  
  
 **„a“**  
 Öffnet zum Schreiben am Ende der Datei (Anfügen); erstellt die Datei zuerst, wenn sie nicht vorhanden ist. Alle Schreibvorgänge erfolgen am Ende der Datei. Der Dateizeiger kann mit `fseek` oder **rewind** neu angeordnet werden, er wird jedoch immer wieder zurück an das Ende der Datei verschoben, bevor ein Schreibvorgang durchgeführt wird.  
  
 **„a+“**  
 Wie oben, erlaubt jedoch auch das Lesen.  
  
 **"r"**  
 Öffnet zum Lesen. Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, tritt beim Aufruf zum Öffnen der Datei ein Fehler auf.  
  
 **„r+“**  
 Öffnet sowohl zum Lesen als auch zum Schreiben. Wenn die Datei nicht vorhanden ist oder nicht gefunden werden kann, tritt beim Aufruf zum Öffnen der Datei ein Fehler auf.  
  
 **"w"**  
 Öffnet eine leere Datei zum Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 **„w+“**  
 Öffnet eine leere Datei zum Lesen und Schreiben. Wenn die angegebene Datei vorhanden ist, wird ihr Inhalt zerstört.  
  
 Wenn als Typ „r+“, „w+“ oder „a+“ angegeben wird, sind sowohl Lese- als auch Schreibvorgänge zulässig (die Datei ist zum Aktualisieren geöffnet). Wenn Sie jedoch zwischen Lesen und Schreiben wechseln, muss ein sich dazwischen befindender Vorgang wie `fflush`, `fsetpos`, `fseek` oder **rewind** vorhanden sein. Die aktuelle Position kann für den Vorgang `fsetpos` oder `fseek` angegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [_fdopen, _wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md)   
 [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)   
 [_popen, _wpopen](../c-runtime-library/reference/popen-wpopen.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)