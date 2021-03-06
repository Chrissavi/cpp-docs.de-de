---
title: StopAndAnalyzeTracingSessionA
description: Die C++ Build Insights SDK StopAndAnalyzeTracingSessionA-Funktionsreferenz.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- StopAndAnalyzeTracingSessionA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 51a979b68cd87c5e7fd07b28acec80c2d7b81cf6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323735"
---
# <a name="stopandanalyzetracingsessiona"></a>StopAndAnalyzeTracingSessionA

::: moniker range="<=vs-2015"

Das C++ Build Insights SDK ist mit Visual Studio 2017 und höher kompatibel. Um die Dokumentation zu diesen Versionen anzuzeigen, legen Sie das Visual **Studio-Versionsauswahlsteuerelement** für diesen Artikel auf Visual Studio 2017 oder Visual Studio 2019 fest. Es befindet sich oben im Inhaltsverzeichnis auf dieser Seite.

::: moniker-end
::: moniker range=">=vs-2017"

Die `StopAndAnalyzeTracingSessionA` Funktion beendet eine fortlaufende Ablaufverfolgungssitzung und speichert die resultierende Ablaufverfolgung in einer temporären Datei. Eine Analysesitzung wird dann sofort mit der temporären Datei als Eingabe gestartet. Ausführbare Dateien, die diese Funktion aufrufen, müssen über Administratorrechte verfügen.

## <a name="syntax"></a>Syntax

```cpp
enum RESULT_CODE StopAndAnalyzeTracingSessionA(
    const char*                 sessionName,
    TRACING_SESSION_STATISTICS* statistics,
    const ANALYSIS_DESCRIPTOR*  analysisDescriptor);
```

### <a name="parameters"></a>Parameter

*sessionName*\
Der Name der zu beendenden Ablaufverfolgungssitzung. Verwenden Sie denselben Sitzungsnamen wie an [StartTracingSession](start-tracing-session.md), [StartTracingSessionA](start-tracing-session-a.md)oder [StartTracingSessionW](start-tracing-session-w.md)übergeben.

*Statistiken*\
Zeiger auf ein [TRACING_SESSION_STATISTICS](../other-types/tracing-session-statistics-struct.md) Objekt. `StopAndAnalyzeTracingSessionA`schreibt Ablaufverfolgungssammlungsstatistiken in diesem Objekt, bevor es zurückgegeben wird.

*analyseDescriptor*\
Zeiger auf ein [ANALYSIS_DESCRIPTOR](../other-types/analysis-descriptor-struct.md) Objekt. Verwenden Sie dieses Objekt, um die `StopAndAnalyzeTracingSessionA`Analysesitzung zu konfigurieren, die von gestartet wird.

### <a name="return-value"></a>Rückgabewert

Ein Ergebniscode aus der [RESULT_CODE](../other-types/result-code-enum.md) Enumerum.

::: moniker-end
