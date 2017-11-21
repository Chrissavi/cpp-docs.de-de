---
title: char_traits&lt;char&gt;-Struktur | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iosfwd/std::char_traits<char>
- char_traits<char >
dev_langs: C++
helpviewer_keywords: char_traits<char> class
ms.assetid: abd9373a-77db-4031-bf4b-f8ac15087581
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fe7255c5b9ad2ec9d2d1f226e1b40bda8fda7a56
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="chartraitsltchargt-struct"></a>char_traits&lt;char&gt;-Struktur
Eine Struktur, die eine Spezialisierung der Vorlagenstruktur **char_traits\<CharType>** für ein Element des Typs `char` ist.  
  
## <a name="syntax"></a>Syntax  
  
```
template <>  
struct char_traits<char>;
```  
  
## <a name="remarks"></a>Hinweise  
 Dank der Spezialisierung kann die Struktur Bibliotheksfunktionen nutzen, die Objekte dieses Typs `char` bearbeiten.  
  
## <a name="example"></a>Beispiel  
 Siehe die Typdefinitionen und Memberfunktionen der Vorlagenklasse [Char_traits-Klasse](../standard-library/char-traits-struct.md)