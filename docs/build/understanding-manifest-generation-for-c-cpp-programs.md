---
title: Grundlegendes zu Manifestgenerierung für C/c ++ ‑Programme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb6a65c718b88e4072c0ddad19411bb8ea4ddcff
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32381627"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>Manifestgenerierung für C/C++-Programme
Ein [manifest](http://msdn.microsoft.com/library/aa375365) ist ein XML-Dokument, das eine externe XML-Datei oder eine Ressource sein kann, die in einer Anwendung oder Assembly eingebettet. Das Manifest einer [isolierte Anwendung](http://msdn.microsoft.com/library/aa375190) dient zum Verwalten der Namen und Versionen freigegebener Seite-an-Seite-Assemblys, die an die die Anwendung zur Laufzeit gebunden werden soll. Das Manifest einer Seite-an-Seite-Assembly gibt seine Abhängigkeiten auf den Namen, Versionen, Ressourcen und andere Assemblys an.  
  
 Es gibt zwei Möglichkeiten, ein Manifest für isolierte Anwendung oder eine Seite-an-Seite-Assembly zu erstellen. Zunächst kann der Verfasser der Assembly manuell eine Manifestdatei Regeln und benennungsanforderungen erstellen. Auch wenn ein Programm nur auf Visual C++-Assemblys wie CRT, MFC, ATL oder anderen abhängig ist, kann dann ein Manifest automatisch vom Linker generiert werden.  
  
 Die Header der Visual C++-Bibliotheken enthalten Assemblyinformationen, und wenn die Clientbibliotheken im Anwendungscode enthalten sind, diese Assemblyinformationen wird vom Linker verwendet werden um ein Manifest für die endgültige Binärdatei zu bilden. Der Linker bettet die Manifestdatei in die Binärdatei nicht und kann nur das Manifest als externe Datei zu generieren. Mit einem Manifest als externe Datei funktioniert nicht für alle Szenarien. Beispielsweise empfiehlt es sich, dass private Assemblys Manifeste eingebettet haben. In Befehlszeilenbuilds beispielsweise solche, die NMAKE verwenden, um Code zu erstellen, kann ein Manifest mit dem manifest Tool eingebettet werden. Weitere Informationen finden Sie unter [Manifesten in der Befehlszeile](../build/manifest-generation-at-the-command-line.md). Beim Erstellen von in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], ein Manifest eingebettet werden kann, durch Festlegen einer Eigenschaft für das Manifesttool in der **Projekteigenschaften** Dialogfeld; Siehe [Manifesten in Visual Studio](../build/manifest-generation-in-visual-studio.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzept der isolierten Anwendungen und Seite-an-Seite-Assemblys](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)