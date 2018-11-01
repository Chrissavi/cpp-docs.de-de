---
title: invalid_link_target-Klasse
ms.date: 11/04/2016
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
ms.openlocfilehash: 6748ea64f7be20dd5ce4573cd65b6e1084148b48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449113"
---
# <a name="invalidlinktarget-class"></a>invalid_link_target-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn die `link_target`-Methode eines Meldungsblocks aufgerufen wird und der Meldungsblock keine Verknüpfung mit dem Ziel erstellen kann. Dies kann das Ergebnis vom Überschreiten der Anzahl zulässiger Links für den Meldungsblock sein oder das Ergebnis von Versuchen, ein bestimmtes Ziel zweimal mit der gleichen Quelle zu verknüpfen.

## <a name="syntax"></a>Syntax

```
class invalid_link_target : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[invalid_link_target](#ctor)|Überladen. Erstellt ein `invalid_link_target`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_link_target`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> invalid_link_target

Erstellt ein `invalid_link_target`-Objekt.

```
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)

