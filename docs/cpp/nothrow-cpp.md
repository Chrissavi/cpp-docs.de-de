---
title: Nothrow (C++) | Microsoft Docs
ms.custom: ''
ms.date: 01/03/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- nothrow_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], nothrow
- nothrow __declspec keyword
ms.assetid: 0a475139-459c-4ec6-99e8-7ecd0d7f44a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69a706577cf112c3d8a3b7748f72679f7213936d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420649"
---
# <a name="nothrow-c"></a>nothrow (C++)

**Microsoft-spezifisch**

Ein erweitertes `__declspec`-Attribut, das in der Deklaration von Funktionen verwendet werden kann.

## <a name="syntax"></a>Syntax  
  
> *Return-Type* __declspec(nothrow) [*Aufruf Konvention*] *Funktionsnamen* ([*Argumentliste*])

## <a name="remarks"></a>Hinweise

Es wird empfohlen, dass alle neuer Code verwendet die [Noexcept](noexcept-cpp.md) Operator statt `__declspec(nothrow)`.

Dieses Attribut weist den Compiler an, dass die deklarierte Funktion und die Funktionen, die aufgerufen werden, nie eine Ausnahme auslösen. Es werden jedoch keine Richtlinie erzwungen. Löst also nie [Terminate](../standard-library/exception-functions.md#terminate) aufgerufen werden soll, im Gegensatz zu `noexcept`, oder im **Std:c ++ 17** Modus (Visual Studio 2017 15.5 und höher) `throw()`.

Mit dem Modell für synchrone Ausnahmebehandlung kann der Compiler nun standardmäßig die Mechanismen der Lebensdauerverfolgung gewisser entladbarer Objekte in einer solchen Funktion eliminieren, wodurch die Codegröße erheblich reduziert wird. Angesichts der folgenden Präprozessordirektive angegeben, die drei Funktionsdeklarationen gleichwertig in **/std:c ++ 14** Modus:

```cpp
#define WINAPI __declspec(nothrow) __stdcall

void WINAPI f1();
void __declspec(nothrow) __stdcall f2();
void __stdcall f3() throw();
```

In **/std:c ++ 17** Modus `throw()` entspricht nicht den anderen Personen, mit denen `__declspec(nothrow)` leistungsbeeinträchtigungen verursacht `std::terminate` , wenn eine Ausnahme, von der Funktion ausgelöst wird aufgerufen werden soll.

Die `void __stdcall f3() throw();` Deklaration verwendet die Syntax, die vom C++-Standard definiert. In C ++ 17 die `throw()` Schlüsselwort wurde als veraltet markiert.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)  
[noexcept](noexcept-cpp.md)  
[Schlüsselwörter](../cpp/keywords-cpp.md)  
