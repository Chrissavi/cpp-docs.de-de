---
title: Plattform, Default- und Cli-Namespaces (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- lang
- cli
dev_langs:
- C++
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b466a94aba9f19907a5438a8b8e623d65aa0ac2d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33880741"
---
# <a name="platform-default-and-cli-namespaces--c-component-extensions"></a>Platform-, default- und cli-Namespaces (Komponentenerweiterungen für C++)
Ein Namespace qualifiziert die Namen von Sprachelementen, sodass sie keinen Konflikt mit ansonsten identischen Namen an anderer Stelle im Quellcode verursachen. Angenommen, ein Konflikt von geschachteltem Klassennamen könnten verhindern, dass den Compiler erkennen [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md). Namespaces werden vom Compiler verwendet, jedoch nicht in der kompilierten Assembly beibehalten.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 Beim Erstellen des Projekts stellt Visual C++ einen Standardnamespace für das Projekt bereit. Sie können den Namespace manuell umbenennen, obwohl in Windows-Runtime der Namen der winmd-Datei den Namen des Stammnamespace übereinstimmen muss.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Weitere Informationen finden Sie unter [Namespaces und typsichtbarkeit (C + c++ / CX)](http://msdn.microsoft.com/library/windows/apps/hh969551.aspx).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Syntax**  
  
```  
using namespace cli;  
```  
  
 **Hinweise**  
  
 Die C + c++ / CLI unterstützt die `cli` Namespace. Beim Kompilieren mit **"/ CLR"** die `using` -Anweisung im Syntaxabschnitt wird impliziert.  
  
 Die folgenden Sprachfunktionen sind im `cli`-Namespace:  
  
-   [Arrays](../windows/arrays-cpp-component-extensions.md)  
  
-   [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)  
  
-   [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)  
  
-   ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, dass es möglich ist, ein Symbol im `cli`-Namespace als benutzerdefiniertes Symbol im Code zu verwenden.  Sobald dies geschehen ist, müssen Sie die Verweise jedoch explizit oder implizit auf das `cli`-Sprachelement des gleichen Namens qualifizieren.  
  
```  
// cli_namespace.cpp  
// compile with: /clr  
using namespace cli;  
int main() {  
   array<int> ^ MyArray = gcnew array<int>(100);  
   int array = 0;  
  
   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062  
  
   // OK  
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);  
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)