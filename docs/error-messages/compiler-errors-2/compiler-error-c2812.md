---
title: Compilerfehler C2812 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2812
dev_langs:
- C++
helpviewer_keywords:
- C2812
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c5469e4f7be3c164cc63fa30f5069009846be48
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705022"
---
# <a name="compiler-error-c2812"></a>Compilerfehler C2812

> \#Import wird nicht unterstützt, mit/clr: pure und/CLR: safe

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

[#import-Direktive](../../preprocessor/hash-import-directive-cpp.md) wird nicht unterstützt, mit **/CLR: pure** und **/CLR: safe** da `#import` erfordert die Verwendung eines systemeigenen Compiler-Unterstützung-Bibliotheken.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird C2812 generiert.

```cpp
// C2812.cpp
// compile with: /clr:pure /c
#import "importlib.tlb"   // C2812
```