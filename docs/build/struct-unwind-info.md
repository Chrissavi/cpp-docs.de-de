---
title: Struktur UNWIND_INFO | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 14b17a79905ffc7814e2aecf92e90f3db526453f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383240"
---
# <a name="struct-unwindinfo"></a>struct UNWIND_INFO
Die Entladung Info Datenstruktur wird verwendet, um die Auswirkungen aufzeichnet, die eine Funktion weist auf den Stack-Pointer und, in dem die nicht flüchtigen Register auf dem Stapel gespeichert werden:  
  
|||  
|-|-|  
|UBYTE: 3|Version|  
|UBYTE: 5|Flags|  
|UBYTE|Größe von prolog|  
|UBYTE|Anzahl von entladungscodes|  
|UBYTE: 4|Frame-Register|  
|UBYTE: 4|Frame-Register-Offset (skalieren)|  
|USHORT * n|Entladen Sie Codes array|  
|Variable|Entweder kann der Form (1) oder (2) im folgenden werden|  
  
 (1) Ausnahmehandler  
  
|||  
|-|-|  
|ULONG|Adresse des ausnahmehandlers|  
|-Variable|Sprachspezifischer Handlerdaten (optional)|  
  
 (2) verkettete entladen, Info  
  
|||  
|-|-|  
|ULONG|Funktion-Startadresse|  
|ULONG|Funktion-Endadresse|  
|ULONG|Entladen Sie Info-Adresse|  
  
 Die UNWIND_INFO-Struktur muss DWORD im Arbeitsspeicher ausgerichtet sein. Die Bedeutung der einzelnen Felder lautet wie folgt:  
  
 **Version**  
 Die Versionsnummer der Entladedaten, gegenwärtig 1.  
  
 **Flags**  
 Derzeit sind drei Flags definiert:  
  
 UNW_FLAG_EHANDLER: die Funktion verfügt über einen Ausnahmehandler, der beim Suchen nach Funktionen, die Ausnahmen untersuchen müssen aufgerufen werden soll.  
  
 UNW_FLAG_UHANDLER die Funktion verfügt über einen Beendigungshandler, der beim Entladen einer Ausnahme aufgerufen werden soll.  
  
 UNW_FLAG_CHAININFO diese Struktur ist nicht das primäre Replikat für die Prozedur Info entladen. Die verketteten entladen stattdessen Info, dass der Eintrag ist der Inhalt des vorherigen RUNTIME_FUNCTION-Eintrag. Finden Sie unter den folgenden Text eine Erläuterung der Verkettete Entladeinfostrukturen. Wenn dieses Flag festgelegt ist, müssen die Flags UNW_FLAG_EHANDLER und UNW_FLAG_UHANDLER gelöscht werden. Außerdem müssen die Frame-Register und -Stack Zuordnung Felder die gleichen Werte wie in der primären Info entladen aufweisen.  
  
 **Größe von prolog**  
 Die Länge des Funktionsprologs in Byte.  
  
 **Anzahl von entladungscodes**  
 Dies ist die Anzahl der Slots im Array Codes entladen. Beachten Sie, dass einige Codes (z. B. UWOP_SAVE_NONVOL) entladen erfordern mehr als einen Slot, der im Array.  
  
 **Frame-register**  
 Wert ungleich NULL ist, klicken Sie dann die Funktion Frame-Pointer verwendet, und dieses Feld ist die Anzahl der nicht flüchtigen Register als Frame-Pointer, mit der gleichen Codierung für das Feld Vorgang Informationen Framezeiger verwendet.  
  
 **Frame registrieren Offset (skalieren)**  
 Wenn der Frame-Register-Feld ungleich NULL ist, ist dies die skalierte Offset von RSP, die auf das FP Reg angewendet wird, wenn er eingerichtet wird. Die tatsächliche FP Reg RSP + 16 festgelegt ist * diese Zahl, sodass Offsets von 0 bis 240. Dies ermöglicht das FP Reg in die Mitte der lokalen stapelzuordnung für dynamische Stapelrahmen ermöglicht eine bessere Code Dichte über kürzere Anweisungen (mehrere Anweisungen können signierten 8-Bit-Offset Formulars) verweist.  
  
 **Entladen Sie Codes array**  
 Dies ist ein Array von Elementen, die den Effekt des Prologs nicht flüchtigen Register und RSP erläutert. Die Bedeutungen der einzelnen Elemente finden Sie im Abschnitt auf UNWIND_CODE. Für die Ausrichtung enthält dieses Array immer auswirkt eine gerade Anzahl von Einträgen, wobei der abschließende Eintrag potenziell nicht verwendet (in diesem Fall das Array eine länger als angegeben durch die Anzahl der Entladung Codes Feld sein wird).  
  
 **Adresse des ausnahmehandlers**  
 Dies ist eine Relative Image-Zeiger auf die Funktion sprachspezifische Ausnahme/Beendigungshandler (wenn das UNW_FLAG_CHAININFO-Flag klar ist, und eines der Flags UNW_FLAG_EHANDLER oder UNW_FLAG_UHANDLER festgelegt ist).  
  
 **Sprachspezifischer Handlerdaten**  
 Dies ist die Funktion sprachspezifischer Handler Ausnahmedaten. Das Format dieser Daten ist nicht angegeben wurde und vollständig vom Handler für bestimmte Ausnahmen in Verwendung bestimmt.  
  
 **Verkettet entladen, Info**  
 Wenn das UNW_FLAG_CHAININFO-Flag festgelegt ist, und klicken Sie dann die UNWIND_INFO-Struktur mit drei UWORDs endet.  Diese UWORDs stellen die RUNTIME_FUNCTION-Informationen für die Funktion des verketteten Entladevorgangs dar.  
  
## <a name="see-also"></a>Siehe auch  
 [Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)