---
title: Kontextbezogene Schlüsselwörter (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal_CPP
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ceea3242087d89b511f6309003efe38d155735d2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871522"
---
# <a name="context-sensitive-keywords--c-component-extensions"></a>Kontextbezogene Schlüsselwörter (Komponentenerweiterungen für C++)
*Kontextbezogene Schlüsselwörter* sind Sprachelemente, die nur in bestimmten Kontexten erkannt werden. Außerhalb des jeweiligen Kontexts kann ein kontextbezogenes Schlüsselwort ein benutzerdefiniertes Symbol sein.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 **Hinweise**  
  
 Die folgende Liste enthält die kontextbezogenen Schlüsselwörter:  
  
-   [abstract](../windows/abstract-cpp-component-extensions.md)  
  
-   [delegate](../windows/delegate-cpp-component-extensions.md)  
  
-   [event](../windows/event-cpp-component-extensions.md)  
  
-   [finally](../dotnet/finally.md)  
  
-   [for each in](../dotnet/for-each-in.md)  
  
-   [initonly](../dotnet/initonly-cpp-cli.md)  
  
-   `internal`   
  
-   [Zeichenfolgenliterale](../windows/literal-cpp-component-extensions.md)  
  
-   [override](../windows/override-cpp-component-extensions.md)  
  
-   [Eigenschaft](../windows/property-cpp-component-extensions.md)  
  
-   [sealed](../windows/sealed-cpp-component-extensions.md)  
  
-   `where` (Teil [Generika](../windows/generics-cpp-component-extensions.md))  
  
 Zur besseren Lesbarkeit empfiehlt es sich um die Verwendung von kontextbezogenen Schlüsselwörtern als benutzerdefinierte Symbole einschränken.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 **Hinweise**  
  
 (Es gibt keine plattformspezifischen Hinweise für diese Funktion.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Hinweise**  
  
 (Es gibt keine plattformspezifischen Hinweise für diese Funktion.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird dargestellt, wie das kontextbezogene Schlüsselwort `property` im entsprechenden Kontext verwendet werden kann, um eine Eigenschaft und eine Variable zu definieren.  
  
```  
// context_sensitive_keywords.cpp  
// compile with: /clr  
public ref class C {  
   int MyInt;  
public:  
   C() : MyInt(99) {}  
  
   property int Property_Block {   // context-sensitive keyword  
      int get() { return MyInt; }  
   }  
};  
  
int main() {  
   int property = 0;               // variable name  
   C ^ MyC = gcnew C();  
   property = MyC->Property_Block;  
   System::Console::WriteLine(++property);  
}  
```  
  
 **Ausgabe**  
  
```Output  
100  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)