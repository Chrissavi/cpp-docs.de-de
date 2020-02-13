---
title: 'Gewusst wie: Verwenden eines Nachrichtenblockfilters'
ms.date: 11/04/2016
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
ms.openlocfilehash: 074d3989ce48b0b6d69206e3f83c374a2ec65c93
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142814"
---
# <a name="how-to-use-a-message-block-filter"></a>Gewusst wie: Verwenden eines Nachrichtenblockfilters

In diesem Dokument wird veranschaulicht, wie mit einer Filterfunktion ermöglicht wird, dass ein asynchroner Nachrichtenblock eine Nachricht auf der Grundlage der Nutzlast dieser Nachricht annimmt oder ablehnt.

Wenn Sie ein Nachrichtenblock Objekt wie z. b. eine Parallelität [:: Unbounded_buffer](reference/unbounded-buffer-class.md), einen Parallelitäts [::](../../parallel/concrt/reference/call-class.md)-Befehl oder einen " [parallelcurrency:: Transformer](../../parallel/concrt/reference/transformer-class.md)" erstellen, können Sie eine *Filterfunktion* angeben, die bestimmt, ob der Nachrichtenblock eine Nachricht akzeptiert oder ablehnt. Eine Filterfunktion ist eine hilfreiche Möglichkeit, um sicherzustellen, dass nur bestimmte Werte von einem Nachrichtenblock empfangen werden.

Filter Funktionen sind wichtig, da Sie es Ihnen ermöglichen, Nachrichten Blöcke zum bilden von *Datenfluss Netzwerken*zu verbinden. Nachrichtenblöcke in einem Datenflussnetzwerk steuern den Datenfluss, indem sie nur Nachrichten verarbeiten, die bestimmte Kriterien erfüllen. Vergleichen Sie dies mit dem Ablaufsteuerungsmodell, in dem der Datenfluss mit Steuerungsstrukturen, z. B. Bedingungsanweisungen, Schleifen usw., gesteuert wird.

Dieses Dokument enthält ein einfaches Beispiel für die Verwendung eines Nachrichtenfilters. Weitere Beispiele, in denen Nachrichtenfilter und das Datenfluss Modell verwendet werden, um Nachrichten Blöcke zu verbinden, finden Sie unter Exemplarische Vorgehensweise [: Erstellen eines Daten](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md) Fluss-Agents und Exemplarische Vorgehensweise [: Erstellen eines Bild Verarbeitungs Netzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md).

## <a name="example"></a>Beispiel

Betrachten Sie die folgende Funktion `count_primes`, die die grundlegende Verwendung eines Nachrichtenblocks veranschaulicht, der keine eingehenden Nachrichten filtert. Der Message-Block fügt Primzahlen an ein [Std:: Vector](../../standard-library/vector-class.md) -Objekt an. Die `count_primes`-Funktion sendet Zahlen an den Nachrichtenblock, empfängt die Ausgabewerte des Nachrichtenblocks und gibt die Zahlen, die Primzahlen sind, an die Konsole aus.

[!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]

Das `transformer`-Objekt verarbeitet alle Eingabewerte. Es benötigt jedoch nur die Werte, bei denen es sich um Primzahlen handelt. Die Anwendung kann zwar so geschrieben werden kann, dass der Nachrichtenabsender nur Primzahlen sendet, jedoch können die Anforderungen des Nachrichtenempfängers nicht immer bekannt sein.

## <a name="example"></a>Beispiel

Die folgende Funktion `count_primes_filter` führt die gleiche Aufgabe wie die `count_primes`-Funktion aus. Das `transformer`-Objekt in dieser Version verwendet jedoch eine Filterfunktion, damit nur die Werte angenommen werden, die Primzahlen sind. Die Funktion, die die Aktion ausführt, empfängt nur Primzahlen. Daher muss sie die `is_prime`-Funktion nicht aufrufen.

Da das `transformer`-Objekt nur Primzahlen empfängt, kann das `transformer`-Objekt selbst die Primzahlen enthalten. Das bedeutet, dass das `transformer`-Objekt in diesem Beispiel nicht benötigt wird, um dem `vector`-Objekt die Primzahlen hinzuzufügen.

[!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]

Das `transformer`-Objekt verarbeitet jetzt nur die Werte, die Primzahlen sind. Im vorherigen Beispiel verarbeitet das `transformer`-Objekt alle Nachrichten. Daher muss im vorherigen Beispiel die gleiche Anzahl von Nachrichten empfangen werden, wie gesendet wurden. In diesem Beispiel wird das Ergebnis der [parallelcurrency:: Send](reference/concurrency-namespace-functions.md#send) -Funktion verwendet, um zu bestimmen, wie viele Nachrichten vom `transformer` Objekt empfangen werden. Die `send`-Funktion gibt **true** zurück, wenn der Nachrichten Puffer die Nachricht annimmt, und **false** , wenn der Nachrichten Puffer die Nachricht ablehnt. Daher stimmt die Häufigkeit, mit der der Nachrichtenpuffer die Nachricht annimmt, mit der Anzahl der Primzahlen überein.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht das vollständige Beispiel. In dem Beispiel werden die `count_primes`-Funktion und die `count_primes_filter`-Funktion aufgerufen.

[!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Kopieren Sie den Beispielcode, und fügen Sie ihn in ein Visual Studio-Projekt ein, oder fügen Sie ihn in eine Datei mit dem Namen `primes-filter.cpp` ein, und führen Sie dann den folgenden Befehl in einem Visual Studio-Eingabe Aufforderungs Fenster aus.

> **cl. exe/EHsc PRIMES-Filter. cpp**

## <a name="robust-programming"></a>Robuste Programmierung

Eine Filterfunktion kann eine Lambda-Funktion, ein Funktionsobjekt oder ein Funktionszeiger sein. Jede Filterfunktion nimmt eines der folgenden Formate an:

```Output
bool (T)
bool (T const &)
```

Um das unnötige Kopieren von Daten zu vermeiden, verwenden Sie das zweite Format bei einem aggregierten Typ, der anhand des Werts übertragen wird.

## <a name="see-also"></a>Weitere Informationen

[Asynchrone Agents Library](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[Exemplarische Vorgehensweise: Erstellen eines Datenfluss-Agent](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[Exemplarische Vorgehensweise: Erstellen eines Bildverarbeitungsnetzwerks](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[transformer-Klasse](../../parallel/concrt/reference/transformer-class.md)
