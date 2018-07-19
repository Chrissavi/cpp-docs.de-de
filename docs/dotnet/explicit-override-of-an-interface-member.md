---
title: Explizites Überschreiben eines Schnittstellenmembers | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 811112d2721edccede6c7b4a278189fdec874523
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110440"
---
# <a name="explicit-override-of-an-interface-member"></a>Explizites Überschreiben eines Schnittstellenmembers
Die Syntax zum Deklarieren eines expliziten Überschreiben eines Schnittstellenmembers innerhalb einer Klasse wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
 Häufig möchten Sie zwei Instanzen eines Schnittstellenmembers innerhalb einer Klasse zu bieten, die Schnittstelle – eine, die verwendet wird implementiert, wenn die Klassenobjekte über eine Schnittstelle Handle bearbeitet werden, und Klassenobjekte Sortierergebnissen verwendet wird, über die Klassenschnittstelle. Zum Beispiel:  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 In Managed Extensions geschieht dies durch eine explizite Deklaration der Schnittstellenmethode bereitstellen, mit dem Namen der Methode, die mit dem Namen der Schnittstelle qualifiziert. Die klassenspezifische Instanz ist nicht qualifiziert. Dadurch entfällt die Notwendigkeit, Downcasting den Rückgabewert der `Clone`, in diesem Beispiel, wenn er explizit über eine Instanz des aufgerufen `R`.  
  
 In der neuen Syntax wurde ein allgemeiner Mechanismus für die überschreibende eingeführt, der die Managed Extensions-Syntax ersetzt. Unserem Beispiel würde wie folgt umgeschrieben werden:  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 Diese Version erfordert, dass es sich bei der Schnittstellenmember wird explizit außer Kraft gesetzt werden erhält einen eindeutigen Namen innerhalb der Klasse. Hier haben ich bereitgestellt, der komplizierte Name `InterfaceClone`. Das Verhalten ist immer noch die gleiche - Aufruf über die `ICloneable` -Schnittstelle wird der umbenannte `InterfaceClone`, aufgerufen, während über ein Objekt des Typs `R` Ruft das zweite `Clone` Instanz.  
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C + c++ / CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Explizite Überschreibungen](../windows/explicit-overrides-cpp-component-extensions.md)