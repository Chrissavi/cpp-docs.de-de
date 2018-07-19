---
title: Parametertypen (Komponentenerweiterungen für C++)-Attribut | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, parameter types
ms.assetid: d9f127a3-7f08-456f-acc6-256805632712
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64da24a9811046672c317c24bba5332bf09303f9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33860306"
---
# <a name="attribute-parameter-types--c-component-extensions"></a>Attributparametertypen (Komponentenerweiterungen für C++)
Der Compiler müssen Attributen übergebenen Werte zum Zeitpunkt der Kompilierung bekannt sein.  Attributparameter können die folgenden Typen entsprechen:  
  
-   `bool`  
  
-   `char`, `unsigned char`  
  
-   `short`, `unsigned short`  
  
-   `int`, `unsigned int`  
  
-   `long`, `unsigned long`  
  
-   `__int64`, `unsigned __int64`  
  
-   `float`, `double`  
  
-   `wchar_t`  
  
-   `char*`, `wchar_t*` oder `System::String*`  
  
-   `System::Type ^`  
  
-   `System::Object ^`  
  
-   `enum`  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
```  
// attribute_parameter_types.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct AStruct {};  
  
[AttributeUsage(AttributeTargets::ReturnValue)]  
ref struct Attr : public Attribute {  
   Attr(AStruct ^ i){}  
   Attr(bool i){}  
   Attr(){}  
};  
  
ref struct MyStruct {  
   static AStruct ^ x = gcnew AStruct;  
   [returnvalue:Attr(x)] int Test() { return 0; }   // C3104  
   [returnvalue:Attr] int Test2() { return 0; }   // OK  
   [returnvalue:Attr(true)] int Test3() { return 0; }   // OK  
};  
```  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Wenn Sie Attribute angeben, müssen alle unbenannten (mit Feldern fester Breite) Argumente keine benannten Argumente voranstellen.  
  
### <a name="code"></a>Code  
  
```  
// extending_metadata_c.cpp  
// compile with: /clr /c  
using namespace System;  
[AttributeUsage(AttributeTargets::Class)]  
ref class MyAttr : public Attribute {  
public:  
   MyAttr() {}  
   MyAttr(int i) {}  
   property int Priority;  
   property int Version;  
};  
  
[MyAttr]   
ref class ClassA {};   // No arguments  
  
[MyAttr(Priority = 1)]   
ref class ClassB {};   // Named argument  
  
[MyAttr(123)]   
ref class ClassC {};   // Positional argument  
  
[MyAttr(123, Version = 1)]   
ref class ClassD {};   // Positional and named  
```  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Attributparameter können eindimensionale Arrays der vorherigen Typen sein.  
  
### <a name="code"></a>Code  
  
```  
// extending_metadata_d.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzerdefinierte Attribute](../windows/user-defined-attributes-cpp-component-extensions.md)