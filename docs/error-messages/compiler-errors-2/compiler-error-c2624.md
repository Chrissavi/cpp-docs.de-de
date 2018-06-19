---
title: Compiler-Fehler C2624 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2624
dev_langs:
- C++
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9edeb5bdef57663d29bb4cfe5427e5bc3f43b7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230663"
---
# <a name="compiler-error-c2624"></a>Compiler-Fehler C2624 generiert
lokale Klassen können nicht verwendet werden, um "Extern" Variablen zu deklarieren  
  
 Eine lokale Klasse oder Struktur nicht zur deklarieren `extern` Variablen.  
  
 Im folgende Beispiel wird C2624 generiert:  
  
```  
// C2624.cpp  
int main() {  
   struct C {};  
   extern C ac;   // C2624  
}  
```