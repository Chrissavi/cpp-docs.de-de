---
title: 'Module:: getactivationfactory-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 837cb68173ca1994de6bc560882d617bb3aa03e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33887012"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory-Methode
Ruft eine aktivierungsfactory für das Modul an.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pActivatibleClassId`  
 Die IID der Common Language Runtime-Klasse.  
  
 `ppIFactory`  
 Die IActivationFactory für die angegebene Runtime-Klasse.  
  
 `serverName`  
 Der Name einer Teilmenge von Klassenfactorys im aktuellen Modul. Geben Sie den Servernamen in verwendet die [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) -Makro, oder geben Sie `nullptr` der Standardservername abgerufen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; Das HRESULT, andernfalls zurückgegebenes GetActivationFactory.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
[Module-Klasse](../windows/module-class.md) [ActivatableClass-Makros](../windows/activatableclass-macros.md)