---
title: __vmx_vmwrite | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmwrite
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b87aeafd1b9c0c1a35e3f5d99ab5b9d76410b4d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337716"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Microsoft-spezifisch**  
  
 Schreibt den angegebenen Wert für das angegebene Feld in der aktuellen virtuellen Maschine Steuerelement-Struktur (VMCS).  
  
## <a name="syntax"></a>Syntax  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `Field`|Das VMCS-Feld zu schreiben.|  
|[in] `FieldValue`|Der Wert in das Feld VMCS zu schreiben.|  
  
## <a name="return-value"></a>Rückgabewert  
 0  
 Der Vorgang wurde erfolgreich ausgeführt.  
  
 1  
 Bei dem Vorgang ist ein Fehler mit erweitertem Status aufgetreten, der im `VM-instruction error field` der aktuellen VMCS verfügbar ist.  
  
 2  
 Bei dem Vorgang ist ein Fehler ohne verfügbaren Status aufgetreten.  
  
## <a name="remarks"></a>Hinweise  
 Die `__vmx_vmwrite` -Funktion ist gleichbedeutend mit der `VMWRITE` computeranweisung. Der Wert, der die `Field` Parameter ist eine codierte Feldindex, die in der Intel-Dokumentation beschrieben wird. Dokumentieren Sie für Weitere Informationen suchen, für das Dokument "Intel Virtualization technische Spezifikation für der IA-32 Intel Architecture" Dokumentnummer C97063-002 auf der [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) Website, und klicken Sie dann finden Sie in Anhang C Dokument.  
  
## <a name="requirements"></a>Anforderungen  
  
|Systemintern|Architektur|  
|---------------|------------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h >  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)