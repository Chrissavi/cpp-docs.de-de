---
title: Linkertoolwarnung Lnk4221 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4221
dev_langs:
- C++
helpviewer_keywords:
- LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8906c4308b8586d5b1312739921f58063e820deb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33301007"
---
# <a name="linker-tools-warning-lnk4221"></a>Linkertoolwarnung LNK4221
Diese Objektdatei werden keine zuvor nicht definierten öffentlichen Symbole, definiert, damit er von einem Linkvorgang nicht verwendet werden, die diese Bibliothek nutzt  
  
 Berücksichtigen Sie die folgenden zwei Codeausschnitte.  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 Führen Sie zum Kompilieren Sie die Dateien aus, und erstellen zwei Objektdateien, **cl/c a.cpp b.cpp** an einer Eingabeaufforderung. Wenn Sie durch Ausführen der Objektdateien verknüpfen **verknüpfen/out: Test.lib a.obj b.obj lib**, erhalten Sie die LNK4221-Warnung. Wenn Sie die Objekte durch Ausführen von verknüpfen **verknüpfen/out: Test.lib b.obj "a.obj" lib**, erhalten Sie eine Warnung.  
  
 Im zweiten Szenario wird keine Warnung ausgegeben, da der Linker in einer Weise Last in First Out (LIFO) verwendet wird. Im ersten Szenario b.obj wird verarbeitet, bevor Sie "a.obj" und "a.obj" enthält keine neuen Symbole hinzufügen. Durch die Anweisung an des Linkers an, "a.obj" zuerst zu verarbeiten, können Sie die Warnung vermeiden.  
  
 Eine häufige Ursache dieses Fehlers ist, wenn zwei Quelldateien Geben Sie die Option [/Yc (Datei der vorkompilierten Header erstellen)](../../build/reference/yc-create-precompiled-header-file.md) gleichnamige Header-Datei angegeben, der **vorkompilierter Header** Feld. Eine häufige Ursache für dieses Problem befasst sich mit "stdafx.h", da standardmäßig "stdafx.cpp", "stdafx.h" enthält, und alle neuen Symbole werden nicht hinzugefügt. Wenn Sie einer anderen Quelldatei "stdafx.h" mit enthält **"/ Yc"** und die zugehörigen OBJ-Datei vor stdafx.obj verarbeitet wird, löst der Linker LNK4221.  
  
 Eine Möglichkeit zum Beheben dieses Problems besteht darin sicherzustellen, dass für jeden vorkompilierten Header, besteht nur eine Quelldatei, die sie mit umfasst **"/ Yc"**. Alle anderen Quelldateien müssen vorkompilierte Header verwenden. Weitere Informationen zum Ändern dieser Einstellung finden Sie unter [/Yu (vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md).