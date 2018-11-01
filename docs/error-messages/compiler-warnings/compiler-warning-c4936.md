---
title: Compilerwarnung C4936
ms.date: 11/04/2016
f1_keywords:
- C4936
helpviewer_keywords:
- C4936
ms.assetid: 6676de35-bf1b-4d0b-a70f-b5734130336c
ms.openlocfilehash: bbb69cccbf93be6e97d13db5008780f57e63f9da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537565"
---
# <a name="compiler-warning-c4936"></a>Compilerwarnung C4936

> __declspec wird nur bei einer Kompilierung mit /clr oder /clr:pure unterstützt.

## <a name="remarks"></a>Hinweise

Die **/CLR: pure** Compileroption ist in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt.

Ein `__declspec` -Modifizierer wurde verwendet, der `__declspec` -Modifizierer ist aber nur gültig, wenn er mit einer der [/clr](../../build/reference/clr-common-language-runtime-compilation.md) -Optionen kompiliert wird.

Weitere Informationen finden Sie unter [appdomain](../../cpp/appdomain.md) und [process](../../cpp/process.md).

C4936 wird immer als Fehler ausgegeben.  Sie können C4936 mit dem [warning](../../preprocessor/warning.md) -Pragma deaktivieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C4936 generiert:

```cpp
// C4936.cpp
// compile with: /c
// #pragma warning (disable : 4936)
__declspec(process) int i;   // C4936
__declspec(appdomain) int j;   // C4936
```