---
title: ProgID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f2b2d2168b568c74c5404cc83bab1e5f77570773
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880432"
---
# <a name="progid"></a>progid
Gibt an, die ProgID für ein COM-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      [ progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>Parameter  
 *name*  
 Die ProgID des Objekts darstellt.  
  
 Programm-IDs präsentieren eine lesbaren Version von den Klassenbezeichner (CLSID) verwendet, um COM/ActiveX-Objekte zu identifizieren.  
  
## <a name="remarks"></a>Hinweise  
 Die **progid** C++-Attribut können Sie angeben, die ProgID für ein COM-Objekt. Eine ProgID hat das Format *name1.name2.version*. Wenn Sie keinen angeben einer *Version* für eine ProgID die Standardversion ist 1. Wenn Sie keinen angeben *name1.name2*, der Standardname lautet *classname.classname*. Wenn Sie keinen angeben **progid** und geben Sie **Vi_progid**, *name1.name2* stammen aus **Vi_progid** und die (Weiter sequenzielle Anzahl) Version angefügt wird.  
  
 Wenn ein Attributblock, die verwendet **progid** nicht gleichzeitig verwenden `uuid`, der Compiler überprüft die Registrierung, um festzustellen, ob eine `uuid` vorhanden ist, für den angegebenen **progid**. Wenn **progid** nicht angegeben ist, werden zum Generieren der Version (und die Co-Klasse den Namen eine Co-Klasse zu erstellen) verwendet eine **progid**.  
  
 **ProgID** impliziert die **Co-Klasse** Attribut zu verwenden, d. h. bei Angabe von **progid**, ist dasselbe wie das Angeben der **Co-Klasse** und  **ProgID** Attribute.  
  
 Die **progid** Attribut bewirkt, dass eine Klasse, unter dem angegebenen Namen automatisch registriert werden. Der generierten IDL-Datei wird nicht angezeigt. die **progid** Wert.  
  
 Wenn dieses Attribut in einem Projekt, die ATL verwendet verwendet wird, ändert sich das Verhalten des Attributs. Zusätzlich zu den oben beschriebene Verhalten wird mit diesem Attribut angegebene Informationen verwendet, der **GetProgID** von eingefügten-Funktion die **Co-Klasse** Attribut. Weitere Informationen finden Sie unter der [Coclass](../windows/coclass.md) Attribut.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [Coclass](../windows/coclass.md) für ein Beispiel für die Verwendung von **progid**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [TypeDef, Enum, Union- und Struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Schlüssel progID](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
