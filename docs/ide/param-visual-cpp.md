---
title: '&lt;param&gt; (Visual C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- param
- <param>
dev_langs:
- C++
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f8fae2d8af1b7121290bfbd42b2668afc50034c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217252"
---
# <a name="ltparamgt-visual-c"></a>&lt;param&gt; (Visual C++)
Das \<param>-Tag sollte im Kommentar für eine Methodendeklaration verwendet werden, um einen der Methodenparameter zu beschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
<param name='name'>description</param>  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 Der Name eines Methodenparameters.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.  Der Compiler gibt eine Warnung aus, wenn er `name` nicht findet.  
  
 `description`  
 Eine Beschreibung für den Parameter  
  
## <a name="remarks"></a>Hinweise  
 Der Text für das \<param>-Tag wird in IntelliSense, dem [Objektkatalog](https://msdn.microsoft.com/f89acfc5-1152-413d-9f56-3dc16e3f0470), und im Webbericht für Codekommentare angezeigt.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// xml_param_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_param_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <param name="Int1">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
   }  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)