---
title: C-Laufzeitfehler R6002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6002
dev_langs:
- C++
helpviewer_keywords:
- R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50a970ecea4fdd7d397c09672b0548be947cab1e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298563"
---
# <a name="c-runtime-error-r6002"></a>C-Laufzeitfehler R6002
gleitkommaunterstützung nicht geladen  
  
 Die notwendige Gleitkomma-Bibliothek wurde nicht verknüpft.  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da es sich um ein internes Problem enthält. Es gibt mehrere mögliche Ursachen für diesen Fehler, aber es ist häufig verursacht durch einen Fehler in der app-Code oder indem Sie versuchen, die zum Ausführen einer app, die nicht für den bestimmten Computer-Prozessor erstellt wurde.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Dieser Fehler kann in Ihrer app auftreten, wenn die Gleitkomma-Bibliothek wurde nicht verknüpft. Überprüfen Sie eine der folgenden Ursachen:  
  
-   Eine Formatzeichenfolge für einen `printf_s` oder `scanf_s` Funktion enthalten eine Gleitkommaformat-Spezifikation und die Anwendung keine, Gleitkommazahlen-Punktwerte oder Variablen. Um dieses Problem zu beheben, verwenden eines gleitkommaarguments Gleitkommaformat-Spezifikation entsprechen, oder führen Sie eine Gleitkomma-Zuweisung an anderer Stelle im Programm. Dies bewirkt, dass gleitkommaunterstützung geladen werden soll.  
  
-   Der Compiler minimiert Größe eines Programms durch gleitkommaunterstützung nur bei Bedarf geladen. Der Compiler kann nicht erkennt Gleitkommaoperationen oder Gleitkommaformat Spezifikationen in Formatzeichenfolgen, die erforderlichen Gleitkomma-Routinen nicht geladen werden kann. Um dieses Problem zu beheben, verwenden eines Gleitkommaformats und Angeben eines gleitkommaarguments, oder führen Sie eine Gleitkomma-Zuweisung an anderer Stelle im Programm. Dies bewirkt, dass gleitkommaunterstützung geladen werden soll.  
  
-   Beim Verknüpfen des Programms wurde eine C-Bibliothek in einem Programm gemischtsprachigen vor einer FORTRAN-Bibliothek angegeben. Erneut binden Sie, und geben Sie zuletzt die C-Bibliothek.