---
title: 'Platform:: IntPtr-Wertklasse | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
dev_langs:
- C++
helpviewer_keywords:
- Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b54facc94be3f43b500e38371e0eba9e00d130a4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33088153"
---
# <a name="platformintptr-value-class"></a>Platform::IntPtr-Wertklasse
Stellt einen Zeiger oder ein Handle mit Vorzeichen dar, dessen Größe plattformspezifisch ist (32-Bit oder 64-Bit).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public value struct IntPtr  
```  
  
### <a name="members"></a>Member  
 IntPtr hat die folgenden Mitglieder:  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[IntPtr::IntPtr](#ctor)|Initialisiert eine neue Instanz von IntPtr.|  
|[IntPtr::op_explicit-Operator](#op-explicit)|Konvertiert den angegebenen Parameter in einen IntPtr oder einen Zeiger auf einen IntPtr-Wert.|  
|[IntPtr::ToInt32](#toint32)|Konvertiert den aktuellen IntPtr in eine 32-Bit-Ganzzahl.|  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  

## <a name="ctor"> </a> IntPtr::IntPtr-Konstruktor
Initialisiert eine neue Instanz von IntPtr mit dem angegebenen Wert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
### <a name="parameters"></a>Parameter  
 Wert  
 Ein 64-Bit-Handle oder -Zeiger oder ein Zeiger auf einen 64-Bit-Wert oder einen 32-Bit-Wert, der in einen 64-Bit-Wert konvertiert werden kann.  
  


## <a name="op-explicit"> </a> IntPtr::op_explicit-Operator
Konvertiert den angegebenen Parameter in einen IntPtr oder einen Zeiger auf einen IntPtr-Wert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
### <a name="parameters"></a>Parameter  
 value1  
 Ein Zeiger auf ein Handle oder einem IntPtr.  
  
 value2  
 Eine 32-Bit-Ganzzahl, die in einen IntPtr konvertiert werden kann.  
  
 value3  
 Ein IntPtr.  
  
### <a name="return-value"></a>Rückgabewert  
 Der erste und zweite Operator gibt ein IntPtr zurück. Der dritte Operator gibt einen Zeiger auf den Wert zurück, der durch das aktuelle IntPtr dargestellt wird.  
  


## <a name="toint32"> </a> IntPtr:: Toint32-Methode
Konvertiert den aktuellen IntPtr-Wert in eine 32-Bit-Ganzzahl.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
int32 IntPtr::ToInt32();  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine 32-Bit-Ganzzahl  
  
  
## <a name="see-also"></a>Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)