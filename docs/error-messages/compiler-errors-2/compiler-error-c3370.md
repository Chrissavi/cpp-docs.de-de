---
title: Compilerfehler C3370
ms.date: 11/04/2016
f1_keywords:
- C3370
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
ms.openlocfilehash: 4200cb7840899ad7b3719e949138010bd478ea3f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503182"
---
# <a name="compiler-error-c3370"></a>Compilerfehler C3370

'IDL_Modulname': 'idl_module' ist noch nicht definiert.

Bevor Sie [idl_module](../../windows/attributes/idl-module.md) zum Angeben eines Einstiegpunkts in einer DLL verwenden können, müssen Sie zunächst den Namen der DLL-Datei mithilfe von `idl_module` angeben.

Im folgenden Beispiel wird C3370 generiert:

```cpp
// C3370.cpp
[module(name=MyLibrary)];
// uncomment the following line to resolve the error
// [idl_module(name="name1", dllname=x.dll)];
[idl_module(name="name1"), entry(100)] // C3370
int f1();

int main()
{
}
```
