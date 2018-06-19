---
title: Verkettete Entladeinfostrukturen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87469a381c038462549d20b105b791ddb17b1656
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32366951"
---
# <a name="chained-unwind-info-structures"></a>Verkettete Entladeinfostrukturen
Wenn das UNW_FLAG_CHAININFO-Flag festgelegt ist, klicken Sie dann eine Entladung Info-Struktur ist ein sekundärer und Feld für die freigegebenen Ausnahme-Handler/verkettet-Info-Adresse enthält die primären Entladung-Informationen. Der folgende Code Ruft die primäre entladen Informationen, vorausgesetzt, dass `unwindInfo` die Struktur, die das UNW_FLAG_CHAININFO-flag festgelegt ist.  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 Verkettete Info ist in zwei Situationen nützlich. Zunächst können sie für nicht zusammenhängende Codesegmente verwendet werden. Mithilfe verketteter Info können Sie die Größe der Informationen zur erforderlichen Entladung reduzieren, da Sie keine Entladung Codes Array aus der primären Entladung Info zu duplizieren.  
  
 Verkettete Informationen können auch die flüchtige Register speichert gruppieren. Der Compiler kann eine Verzögerung von einigen volatile Register gespeichert, bis er außerhalb des Funktionsprologs-Eintrag ist. Können Sie dies, dass der primäre Entladung Informationen für den Teil der Funktion vor dem gruppierten Code aufzeichnen und Informationen mit einer nicht-NULL-Größe von Prolog, in dem die entladungscodes in der verketteten Info speichert nicht flüchtigen Register wiedergeben verkettet dann einrichten. In diesem Fall sind die entladungscodes alle Instanzen von UWOP_SAVE_NONVOL. Eine Gruppe, die mithilfe einer CLIENTPUSHINSTALLATION nicht flüchtige Register speichert oder ändert die RSP-Registrierung mithilfe einer zusätzlichen festen stapelzuordnung wird nicht unterstützt.  
  
 Ein UNWIND_INFO-Element, das UNW_FLAG_CHAININFO festgelegt ist kann einen RUNTIME_FUNCTION-Eintrag enthalten, dessen UNWIND_INFO-Element auch UNW_FLAG_CHAININFO (mehrere Komprimierung) festgelegt ist. Die verketteten entladen schließlich Informationen, die Zeiger auf ein Element UNWIND_INFO eingehen, die UNW_FLAG_CHAININFO deaktiviert ist; Dies ist das primäre UNWIND_INFO-Element, die auf der tatsächlichen Prozedureinstiegspunkt verweist.  
  
## <a name="see-also"></a>Siehe auch  
 [Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)