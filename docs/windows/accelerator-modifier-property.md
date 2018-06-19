---
title: Eigenschaft "Modifizierer" Accelerator | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Modifier property
ms.assetid: f05a9379-e037-4cfb-b6ef-d2c655bcfa7f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d99d4656f2835f9adb60f310e429c4ccb97ac7b6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854053"
---
# <a name="accelerator-modifier-property"></a>Eigenschaft "Modifizierer" von Zugriffstasten
Die folgenden sind Einträge zulässig für die Eigenschaft "Modifizierer" in der Zugriffstastentabelle.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**Keine**|Benutzer drückt die Schlüssel-Wert. Dies ist am effizientesten mit den ASCII/ANSI-Werten 001 bis 026, was interpretiert wird als ^ A bis ^ Z (STRG + A bis STRG-Z).|  
|**ALT-Taste**|Der Benutzer muss vor dem Schlüssel-Wert die ALT-Taste drücken.|  
|**STRG**|Benutzer muss vor dem Schlüssel-Wert die STRG-Taste drücken. Mit dem ASCII-Typ ist ungültig.|  
|**Umschalttaste gedrückt**|Der Benutzer muss die UMSCHALTTASTE gedrückt, bevor der Schlüssel-Wert drücken.|  
|**Strg + Alt**|Der Benutzer muss die STRG-Taste und bevor der Schlüssel-Wert die ALT-Taste drücken. Mit dem ASCII-Typ ist ungültig.|  
|**STRG + UMSCHALT**|Benutzer muss drücken Sie die STRG-Taste und die UMSCHALTTASTE gedrückt, bevor der Schlüssel-Wert. Mit dem ASCII-Typ ist ungültig.|  
|**ALT + UMSCHALT**|Benutzer muss drücken Sie die ALT-Taste und die UMSCHALTTASTE gedrückt, bevor der Schlüssel-Wert. Mit dem ASCII-Typ ist ungültig.|  
|**Strg + Alt + Umschalt**|Benutzer drücken vor dem Schlüssel-Wert STRG und ALT, UMSCHALT. Mit dem ASCII-Typ ist ungültig.|  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)