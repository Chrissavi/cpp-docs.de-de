---
title: Lexicographical_compare (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::lexicographical_compare
dev_langs:
- C++
helpviewer_keywords:
- lexicographical_compare function [STL/CLR]
ms.assetid: 9ec217f3-5523-4f90-a0cc-8fb7dbe4946b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 49d5243b729e8e1beeeb11536a80bb6937d25879
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128671"
---
# <a name="lexicographicalcompare-stlclr"></a>lexicographical_compare (STL/CLR)
Vergleicht zwei Sequenzen elementweise, um zu bestimmen, welche der beiden kleiner ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<class _InIt1, class _InIt2> inline  
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2);  
template<class _InIt1, class _InIt2, class _Pr> inline  
    bool lexicographical_compare(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _Pr _Pred);  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Funktion verhält sich wie die C++-Standardbibliothek Funktion `lexicographical_compare`. Weitere Informationen finden Sie unter [Lexicographical_compare](../standard-library/algorithm-functions.md#lexicographical_compare).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<Cliext-Algorithmus >  
  
 **Namespace:** Cliext  
  
## <a name="see-also"></a>Siehe auch  
 [algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)