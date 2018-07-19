---
title: Versiegeln einer virtuellen Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c85f4775025d3661fdfbf8967b310fb733f452b3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164595"
---
# <a name="sealing-a-virtual-function"></a>Versiegeln einer virtuellen Funktion
Die Syntax für das Versiegeln einer virtuellen Funktion hat gegenüber Managed Extensions für C++ in Visual C++ geändert.  
  
 Die `__sealed` -Schlüsselwort wird in Managed Extensions verwendet, so ändern Sie entweder einen Verweistyp, nachfolgende Ableitung von untersagen (finden Sie unter [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md)), oder ändern eine virtuelle Funktion untersagen nachfolgende Überschreiben der Methode in einer abgeleiteten Klasse. Zum Beispiel:  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 In diesem Beispiel `derived::f()` überschreibt die `base::f()` -Instanz basierend auf die genaue Übereinstimmung der Funktionsprototypen. Die `__sealed` -Schlüsselwort Gibt an, dass es sich bei eine nachfolgenden Klasse geerbt von der abgeleiteten Klasse eine Überschreibung der bereitstellen kann `derived::f()`.  
  
 In der neuen Syntax `sealed` wird nach der Signatur, statt an einer beliebigen Stelle vor dem tatsächlichen Funktionsprototyp angezeigt werden, wie bisher erlaubten zulässiger platziert. Darüber hinaus die Verwendung von `sealed` verlangt eine ausdrückliche Verwendung von der `virtual` -Schlüsselworts. D. h. die ordnungsgemäße Übersetzung von `derived`oben lautet wie folgt:  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 Das Fehlen der `virtual` Schlüsselwort in dieser Instanz führt zu einem Fehler. In der neuen Syntax wird das kontextbezogene Schlüsselwort `abstract` kann verwendet werden, anstelle von der `=0` um eine rein virtuelle Funktion anzugeben. Diese Möglichkeit wurde in Managed Extensions nicht unterstützt. Zum Beispiel:  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 kann als umgeschrieben werden  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C + c++ / CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)