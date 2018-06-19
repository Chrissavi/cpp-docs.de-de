---
title: Verwenden von Setjmp Longjmp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- longjmp_cpp
- setjmp_cpp
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling, setjmp/longjmp functions
- setjmpex.h
- longjmp function in C++ programs
- setjmp.h
- setjmp function
- setjmp function, C++ programs
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dee79d5b81e968e89e8072fb545c86f33be9bcce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422604"
---
# <a name="using-setjmplongjmp"></a>Verwenden von "setjmp/longjmp"
Wenn [Setjmp](../c-runtime-library/reference/setjmp.md) und [Longjmp](../c-runtime-library/reference/longjmp.md) werden zusammen verwendet werden, sie bieten eine Möglichkeit zum Ausführen eines nicht lokalen `goto`. Sie werden in der Regel verwendet, um die Ausführungssteuerung an den Fehlerbehandlungs- oder Wiederherstellungscode in einer vorher aufgerufenen Routine zu übergeben, ohne die standardmäßigen Aufruf- oder Rückgabekonventionen zu verwenden.  
  
> [!CAUTION]
>  `setjmp` und `longjmp` unterstützen jedoch die C++-Objektsemantik nicht und beeinträchtigen möglicherweise die Leistung, indem sie die Optimierung für lokale Variablen verhindern. Aus diesem Grund wird empfohlen, sie nicht in C++-Programmen zu verwenden. Wir empfehlen die Verwendung `try` / `catch` stattdessen erstellt.  
  
 Wenn Sie verwenden möchten `setjmp` / `longjmp` auch in einem C++-Programm einschließen \<setjmp.h > oder \<setjmpex.h > um ordnungsgemäße Interaktion zwischen den Funktionen und C++-Ausnahmebehandlung zu gewährleisten. Bei Verwendung von [/EH](../build/reference/eh-exception-handling-model.md) zum Kompilieren, werden Destruktoren für lokale Objekte während der stapelentladung aufgerufen. Bei Verwendung von **/EHs** zu kompilieren, und eine der Funktionen-Aufrufe eine Funktion, die verwendet [Nothrow](../cpp/nothrow-cpp.md) und die Funktion, die verwendet `nothrow` Aufrufe `longjmp`, und klicken Sie dann die Entladung Destruktor nicht auftreten kann, Abhängig von der Optimierer.  
  
 In portablem Code ist bei Ausführung eines nicht lokalen `goto`, das `longjmp` aufruft, die ordnungsgemäße Zerstörung von framebasierten Objekten möglicherweise unzuverlässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Kombination von C (strukturiert)- und C++-Ausnahmen](../cpp/mixing-c-structured-and-cpp-exceptions.md)