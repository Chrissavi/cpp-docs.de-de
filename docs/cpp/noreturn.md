---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: f9ca61c9d734ccdd6b8d8374ed3a7c4128ee3d5e
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857371"
---
# <a name="noreturn"></a>noreturn

**Microsoft-spezifisch**

Dieses **__declspec** Attribut weist den Compiler an, dass eine Funktion nicht zurückgibt. Folglich weiß der Compiler, dass der Code, der einem Rückruf einer **__declspec (noreturn)** -Funktion folgt, nicht erreichbar ist.

Wenn der Compiler eine Funktion mit einem Kontrollpfad findet, die keinen Wert zurückgibt, wird eine Warnung (C4715) oder Fehlermeldung (C2202) generiert. Wenn der Steuerelement Pfad aufgrund einer Funktion, die nie zurückgibt, nicht erreicht werden kann, können Sie **__declspec (noreturn)** verwenden, um diese Warnung oder den Fehler zu verhindern.

> [!NOTE]
>  Das Hinzufügen von **__declspec (noreturn)** zu einer Funktion, die zurückgegeben werden soll, kann zu undefiniertem Verhalten führen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel enthält die **else** -Klausel keine Return-Anweisung.  Wenn Sie `fatal` als **__declspec (noreturn)** deklarieren, wird ein Fehler oder eine Warnmeldung vermieden.

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Stichwörter](../cpp/keywords-cpp.md)