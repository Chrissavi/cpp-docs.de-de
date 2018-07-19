---
title: Runtime_checks | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
dev_langs:
- C++
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 817afaff738b2528bd165e814517c8399cd8a151
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33840663"
---
# <a name="runtimechecks"></a>runtime_checks
Dient der Deaktivierung oder Wiederherstellung der [/RTC](../build/reference/rtc-run-time-error-checks.md) -Einstellungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
#pragma runtime_checks( "[runtime_checks]", {restore | off} )  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können nur Laufzeitüberprüfungen aktivieren, die mit einer Compileroption aktiviert wurden. Wenn Sie beispielsweise keine /RTCs angeben, ermöglicht die Angabe von `#pragma runtime_checks( "s", restore)` keine Überprüfung der Stapelrahmen.  
  
 Das **runtime_checks** -Pragma muss außerhalb der Funktion angezeigt werden und tritt für die erste definierte Funktion in Kraft, nachdem das Pragma sichtbar ist. Die Argumente **restore** und **off** schalten die in *runtime_checks* angegebenen Optionen ein oder aus.  
  
 Die Option *runtime_checks* kann leer sein oder mehrere Parameter aus der folgenden Tabelle enthalten.  
  
### <a name="parameters-of-the-runtimechecks-pragma"></a>Parameter des runtime_checks-Pragmas  
  
|Parameter|Typ der Laufzeitüberprüfung|  
|--------------------|-----------------------------|  
|**s**|Aktiviert die Überprüfung des Stapels (Frames).|  
|**c**|Meldet die Zuweisung eines Werts zu einem kleineren Datentyp, der zu einem Datenverlust führt.|  
|**n**|Zeigt an, wenn eine Variable verwendet wird, bevor sie definiert ist.|  
  
 Hierbei handelt es sich um dieselben Buchstaben, die mit der /RTC-Compileroption verwendet werden. Zum Beispiel:  
  
```  
#pragma runtime_checks( "sc", restore )  
```  
  
 Verwenden des **runtime_checks** -Pragmas mit einer leeren Zeichenfolge (**""**) ist eine besondere Form der Direktive:  
  
-   Wenn Sie den Parameter **off** verwenden, werden die in der vorstehenden Tabelle aufgeführten Laufzeitfehlerüberprüfungen deaktiviert.  
  
-   Wenn Sie den **restore** -Parameter verwenden, werden die Laufzeitfehlerüberprüfungen auf die mit der /RTC-Compileroption angegebenen zurückgesetzt.  
  
```  
#pragma runtime_checks( "", off )  
.  
.  
.  
#pragma runtime_checks( "", restore )   
```  
  
## <a name="see-also"></a>Siehe auch  
 [Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
