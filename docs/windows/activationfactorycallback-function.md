---
title: ActivationFactoryCallback-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2f1bae2c503f4e5f0c887a46956248184ece9a1e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857323"
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback-Funktion
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `activationId`  
 Handle für eine Zeichenfolge, die einen Laufzeitklasse-Namen angibt.  
  
 `ppFactory`  
 Wenn dieser Vorgang abgeschlossen wird, eine aktivierungsfactory, der Parameter entspricht `activationId`.  
  
## <a name="return-value"></a>Rückgabewert  
 „S_OK“ im Erfolgsfall, andernfalls ein HRESULT, das den Fehler beschreibt. Wahrscheinliche Fehler-HRESULTs sind CLASS_E_CLASSNOTAVAILABLE und E_INVALIDARG.  
  
## <a name="remarks"></a>Hinweise  
 Ruft die aktivierungsfactory für die angegebene Aktivierung-ID.  
  
 Windows-Runtime ruft diese Callback-Funktion, um ein Objekt, von dem Common Language Runtime-Klassennamen angegebenen anzufordern.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)