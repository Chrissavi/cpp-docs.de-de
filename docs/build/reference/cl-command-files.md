---
title: CL-Befehlsdateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, command files
- command files
- command files, CL compiler
ms.assetid: ec3cea06-2af0-4fe9-a94c-119c9d31b3a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 367ea6dc22777b473cad44f35b1f5e4c34528471
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369876"
---
# <a name="cl-command-files"></a>CL-Befehlsdateien
Eine Befehlsdatei ist eine Textdatei, die Optionen und Dateinamen, geben Sie andernfalls auf, enthält die [Befehlszeile](../../build/reference/compiler-command-line-syntax.md) , oder geben Sie mithilfe der [CL-Umgebungsvariablen](../../build/reference/cl-environment-variables.md). CL akzeptiert eine Compiler-Befehlsdatei als Argument in der CL-Umgebungsvariablen oder in der Befehlszeile angegeben. Anders als in der Befehlszeile oder in der CL-Umgebungsvariablen können Sie in einer Befehlsdatei mehrzeilige Optionen und Dateinamen verwenden.  
  
 Optionen und Dateinamen in einer Befehlsdatei werden gemäß der Position des Befehls Dateinamen in der CL-Umgebungsvariablen oder in der Befehlszeile verarbeitet. Wenn die Option/Link in der Befehlsdatei angezeigt wird, sind alle Optionen auf der Rest der Zeile an den Linker übergeben. Optionen in nachfolgenden Zeilen in der Befehlsdatei und Optionen in der Befehlszeile nach dem Aufruf der Befehlsdatei werden weiterhin als Compileroptionen akzeptiert. Weitere Informationen dazu, wie die Reihenfolge der Optionen für deren Interpretation auswirkt, finden Sie unter [Reihenfolge von CL-Optionen](../../build/reference/order-of-cl-options.md).  
  
 Eine Befehlsdatei darf nicht den CL-Befehl. Jede Option muss beginnen und enden in derselben Zeile; Sie können den umgekehrten Schrägstrich nicht verwenden (\\) eine Option über zwei Zeilen zu kombinieren.  
  
 Eine Befehlsdatei wird angegeben, indem ein at-Zeichen (@) gefolgt von einem Filename; der Dateiname kann einen absoluten oder relativen Pfad angeben.  
  
 Beispielsweise wird von der folgende Befehl in einer Datei mit dem Namen auf:  
  
```  
/Og /link LIBC.LIB  
```  
  
 und geben Sie den folgenden CL-Befehl aus:  
  
```  
CL /Ob2 @RESP MYAPP.C  
```  
  
 der Befehl CL lautet wie folgt:  
  
```  
CL /Ob2 /Og MYAPP.C /link LIBC.LIB  
```  
  
 Beachten Sie, dass die Befehlszeile und die Befehlsdatei Befehle effektiv kombiniert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)