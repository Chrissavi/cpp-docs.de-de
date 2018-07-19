---
title: 'Erweiterungs-DLLs: Übersicht | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bd851b9335e2b1ecffc8873590f176d7ebb2205
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367819"
---
# <a name="mfc-extension-dlls-overview"></a>MFC-Erweiterungs-DLLs: Übersicht
Eine MFC-Erweiterungs-DLL ist eine DLL, die in der Regel verwendbare von bestehenden Microsoft Foundation Class Library-Klassen abgeleitete Klassen implementiert. MFC-Erweiterungs-DLLs werden über die Dynamic Link Library-Version von MFC (auch bekannt als die freigegebene Version von MFC) erstellt. Nur ausführbaren MFC-Dateien (entweder Anwendungen oder regulären MFC-DLLs), die mit der gemeinsam genutzten MFC-Version erstellt wurden, können eine MFC-Erweiterungs-DLL verwenden. Mit dem eine MFC-Erweiterungs-DLL können Sie neue benutzerdefinierte Klassen von MFC ableiten und dann bieten diese erweiterte MFC-Version für Anwendungen, die die DLL aufrufen.  
  
 Erweiterungs-DLLs können auch dazu verwendet werden, von MFC abgeleitete Objekte zwischen Anwendung und DLL zu übergeben. Die dem übergebenen Objekt zugeordneten Memberfunktionen befinden sich in dem Modul, in dem das Objekt erstellt wurde. Da diese Funktionen bei Verwendung die gemeinsam genutzten DLL-Version von MFC ordnungsgemäß exportiert werden, können Sie kostenlos MFC übergeben oder Zeiger von MFC abgeleitete Objekte zwischen einer Anwendung und den MFC-Erweiterungs-DLLs geladen.  
  
 Ein Beispiel für eine DLL, die die grundlegenden Anforderungen von einer MFC-Erweiterungs-DLL erfüllt ist, finden Sie im MFC-Beispiel [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). Betrachten Sie insbesondere die Testdll1.cpp und Testdll2.cpp-Dateien ein.  
  
 Beachten Sie, die den Begriff AFXDLL nicht mehr in der Dokumentation zu Visual C++ verwendet wird. Eine MFC-Erweiterungs-DLL hat dieselben Merkmale wie die frühere AFXDLL.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [MFC-Erweiterungs-DLLs initialisieren](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [MFC extension DLLs (MFC-Erweiterungs-DLLs)](../build/extension-dlls.md)  
  
-   [Using Database, OLE, and Sockets MFC extension DLLs in regular MFC DLLs (Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs)](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC-fremde DLLs: Übersicht](../build/non-mfc-dlls-overview.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Erstellen einer MFC-DLL](../mfc/reference/mfc-dll-wizard.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Arten von DLLs](../build/kinds-of-dlls.md)