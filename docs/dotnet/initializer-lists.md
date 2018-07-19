---
title: Initialisierungslisten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializer lists
ms.assetid: b3e53442-9809-4105-9226-ae845bd20cae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6634b749480e5108548de0c8b53f8b09cc5a42c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33127951"
---
# <a name="initializer-lists"></a>Initialisiererlisten
Initialisierungslisten in Konstruktoren werden jetzt vor dem Konstruktor der Basisklasse aufgerufen.  
  
## <a name="remarks"></a>Hinweise  
 Visual C++ 2005 wurde der Basisklassenkonstruktor vor der Initialisierungsliste aufgerufen, bevor beim Kompilieren mit Managed Extentions für C++. Jetzt beim Kompilieren mit **"/ CLR"**, die Initialisiererliste zuerst aufgerufen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine Sprachänderungen (C++/CLI)](../dotnet/general-language-changes-cpp-cli.md)