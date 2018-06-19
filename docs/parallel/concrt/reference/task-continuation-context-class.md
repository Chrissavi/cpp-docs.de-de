---
title: Task_continuation_context-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
dev_langs:
- C++
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37b218a6db251123513ca155fd491fee7ebabd13
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689180"
---
# <a name="taskcontinuationcontext-class"></a>task_continuation_context-Klasse
Mit der `task_continuation_context`-Klasse können Sie angeben, an welcher Stelle eine Fortsetzung ausgeführt werden soll. Es ist nur hilfreich, diese Klasse aus einer Windows-Runtime-app zu verwenden. Für nicht - Windows-Runtime-apps ist Ausführungskontext der aufgabenfortsetzung von der Laufzeit bestimmt und kann nicht konfiguriert.  
  
## <a name="syntax"></a>Syntax  
  
```
class task_continuation_context : public details::_ContextCallback;
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[get_current_winrt_context](#get_current_winrt_context)|Gibt ein Kontextobjekt für Fortsetzung, die den aktuellen Kontext des Threads Winrt darstellt.|  
|[use_arbitrary](#use_arbitrary)|Erstellt einen Aufgabenfortsetzungskontext, der er es der Laufzeit ermöglicht, den Ausführungskontext für eine Fortsetzung auszuwählen.|  
|[use_current](#use_current)|Gibt ein Kontextobjekt für die Aufgabenfortsetzung zurück, das den aktuellen Ausführungskontext darstellt.|  
|[use_default](#use_default)|Erstellt den standardmäßigen Aufgabenfortsetzungskontext.|  
|[use_synchronous_execution](#use_synchronous_execution)|Gibt ein Kontextobjekt für Fortsetzung, die den synchronen Ausführungskontext darstellt.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ppltasks.h  
  
 **Namespace:** Parallelität  

## <a name="get_current_winrt_context"></a> get_current_winrt_context
 Gibt ein Kontextobjekt für Fortsetzung, die den aktuellen Kontext des Threads WinRT darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
static task_continuation_context get_current_winrt_context();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der aktuelle Kontext des Windows-Runtime-Thread. Gibt eine leere Task_continuation_context zurück, wenn von einem nicht - Windows-Runtime-Kontext aufgerufen.  
  
## <a name="remarks"></a>Hinweise  
 Die `get_current_winrt_context` Methode erfasst den Windows-Runtime-Threadkontext des Aufrufers. Es gibt einen leeren Kontext für nicht - Windows-Runtime-Aufrufer zurück.  
  
 Der Rückgabewert von `get_current_winrt_context` können verwendet werden, um die Laufzeit angeben, dass die Fortsetzung in dem Apartmentmodell der erfassten Kontext (STA oder MTA) ausgeführt werden soll, unabhängig davon, ob die Vorgängeraufgabe apartmentfähig ist. Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird.  
  
 Diese Methode ähnelt der `use_current` -Methode, aber es ist auch verfügbar, systemeigenen C++-Code, ohne die C + c++ / CX-Unterstützung. Es dient für Verwendung durch Benutzer das Schreiben von C++-erweiterte c++ / CX-agnostische Bibliothekscode für den einheitlichen und den Windows-Runtime-Aufrufer. Wenn Sie diese Funktion benötigen, empfehlen wir die `use_current` -Methode, die nur für C++ verfügbar ist c++ / CX-Clients.  
  
  
##  <a name="use_arbitrary"></a> use_arbitrary 

 Erstellt einen Aufgabenfortsetzungskontext, der er es der Laufzeit ermöglicht, den Ausführungskontext für eine Fortsetzung auszuwählen.  
  
```
static task_continuation_context use_arbitrary();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Aufgabenfortsetzungskontext, der einen beliebigen Ort darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn dieser Fortsetzungskontext verwendet wird, wird die Fortsetzung in einem Kontext ausgeführt, den die Laufzeit selbst auswählt, auch wenn die Vorgängeraufgabe apartmentfähig ist.  
  
 `use_arbitrary` kann verwendet werden, um das Standardverhalten für eine Fortsetzung einer apartmentfähigen Aufgabe zu deaktivieren, die in einem STA erstellt wurde.  
  
 Diese Methode ist nur für Windows-Runtime-apps verfügbar.  
  
##  <a name="use_current"></a> use_current 

 Gibt ein Kontextobjekt für die Aufgabenfortsetzung zurück, das den aktuellen Ausführungskontext darstellt.  
  
```
static task_continuation_context use_current();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Ausführungskontext.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erfasst den Windows-Runtime-Kontext des Aufrufers, sodass Fortsetzungen im richtigen Apartment ausgeführt werden können.  
  
 Der Wert, der von `use_current` zurückgegeben wird, teilt der Runtime mit, dass die Fortsetzung im erfassten Kontext (STA oder MTA) ausgeführt werden soll, unabhängig davon, ob die Vorgängeraufgabe apartmentfähig ist. Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird.  
  
 Diese Methode ist nur für Windows-Runtime-apps verfügbar.  
  
##  <a name="use_default"></a> use_default 

 Erstellt den standardmäßigen Aufgabenfortsetzungskontext.  
  
```
static task_continuation_context use_default();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der standardmäßige Fortsetzungskontext.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardkontext wird verwendet, wenn Sie beim Aufrufen der `then`-Methode keinen Fortsetzungskontext angeben. In Windows-Anwendungen für Windows 7 und älter sowie in Desktopanwendungen für Windows 8 und höher bestimmt die Laufzeit, wo Aufgabenfortsetzungen ausgeführt werden. Allerdings ist der standardmäßige Fortsetzungskontext für eine Fortsetzung einer apartmentfähigen Aufgabe in einer Windows-Runtime-app das Apartment, in denen `then` aufgerufen wird.  
  
 Eine apartmentfähige Aufgabe ist eine Aufgabe, die eine `IAsyncInfo`-Windows-Runtime-Schnittstelle entpackt, oder eine Aufgabe, die von einer solchen Aufgabe abgeleitet wird. Wenn Sie eine Fortsetzung einer apartmentfähigen Aufgabe in einem Windows-Runtime-STA planen, wird die Fortsetzung daher in diesem STA ausgeführt.  
  
 Eine Fortsetzung einer nicht apartmentfähigen Aufgabe wird in einem Kontext ausgeführt, den die Laufzeit auswählt.  

## <a name="use_synchronous_execution"></a> task_continuation_context::use_synchronous_execution  
Gibt ein Kontextobjekt für Fortsetzung, die den synchronen Ausführungskontext darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
static task_continuation_context use_synchronous_execution();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Der synchrone Ausführungskontext.  
  
## <a name="remarks"></a>Hinweise  
 Die `use_synchronous_execution` Methode erzwingt, dass die Fortsetzungsaufgabe synchron auf den Kontext, verursacht der Vorgängeraufgabe Abschluss ausgeführt.  
  
 Wenn die vorangehende Aufgabe bereits abgeschlossen ist, wenn die Fortsetzung angefügt ist, wird die Fortsetzung auf dem Kontext, der die Fortsetzung fügt synchron ausgeführt.  
  
 
## <a name="see-also"></a>Siehe auch  
 [Concurrency-Namespace](concurrency-namespace.md)
