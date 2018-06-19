---
title: Compilerfehler C3353 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3353
dev_langs:
- C++
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47c9d1dd8c21e56613b9da00fc2bf4f7fbeafcca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33253904"
---
# <a name="compiler-error-c3353"></a>Compilerfehler C3353
'Delegat': Ein Delegat kann nur von einer globalen Funktion oder einer Memberfunktion eines verwalteten oder WinRT-Typs erstellt werden.  
  
 Delegaten, deklariert, wobei die [Delegieren](../../windows/delegate-cpp-component-extensions.md) -Schlüsselwort verwenden, können nur im globalen Gültigkeitsbereich deklariert werden.  
  
 Im folgenden Beispiel wird C3353 generiert:  
  
```  
// C3353.cpp  
// compile with: /clr  
delegate int f;   // C3353  
```