---
title: __vmx_vmresume | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmresume
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmresume intrinsic
- VMRESUME instruction
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8809489a71410af21e47d8771ec208340fc893a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33330878"
---
# <a name="vmxvmresume"></a>__vmx_vmresume
**Microsoft-spezifisch**  
  
 Setzt einen VMX-Vorgang ohne Stamm mithilfe der aktuellen Kontrollstruktur des virtuellen Computers (Virtual Machine Control Structure, VMCS) fort.  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## <a name="return-value"></a>Rückgabewert  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|0|Der Vorgang wurde erfolgreich ausgeführt.|  
|1|Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.|  
|2|Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Anwendung kann einen „VM-enter“-Vorgang mithilfe der [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) - oder `__vmx_vmresume` -Funktion ausführen. Die `__vmx_vmlaunch` -Funktion kann nur mit einer VMCS verwendet werden, deren Startstatus `Clear`lautet, während die `__vmx_vmresume` -Funktion nur mit einer VMCS verwendet werden kann, deren Startstatus `Launched`lautet. Verwenden Sie daher die [__vmx_vmclear](../intrinsics/vmx-vmclear.md) -Funktion zum Festlegen des Startstatus einer VMCS auf `Clear`. Verwenden Sie dann die `__vmx_vmlaunch` -Funktion für den ersten „VM-enter“-Vorgang und die `__vmx_vmresume` -Funktion für nachfolgende „VM-enter“-Vorgänge.  
  
 Die `__vmx_vmresume` -Funktion entspricht der `VMRESUME` -Computeranweisung. Diese Funktion unterstützt die Interaktion zwischen dem Monitor des virtuellen Computers eines Hosts mit einem Gastbetriebssystem und seinen Anwendungen. Dokumentieren Sie für Weitere Informationen suchen Sie nach dem PDF-Dokument "Intel Virtualization technische Spezifikation für der IA-32 Intel Architecture" Dokumentnummer C97063-002 auf der [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) Standort.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmclear](../intrinsics/vmx-vmclear.md)