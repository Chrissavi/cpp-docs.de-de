---
title: Machen eine ATL-Objekt nicht erstellbare | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.objects
dev_langs:
- C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 05707c6771d641d383825a07d0b26a90fdf46cb1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358260"
---
# <a name="making-an-atl-object-noncreatable"></a>Erstellen eine nicht erstellbare ATL-Objekt
Sie können die Attribute eines ATL-basierten COM-Objekts ändern, sodass ein Client das Objekt direkt erstellt werden kann. In diesem Fall würde das Objekt werden durch einen Methodenaufruf zurückgegeben wird, auf einem anderen Objekt anstatt direkt erstellt.  
  
### <a name="to-make-an-object-noncreatable"></a>Ein Objekt Noncreatable vornehmen.  
  
1.  Entfernen Sie die [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto) für das Objekt. Wenn Sie das Objekt nicht erstellbare das Steuerelement jedoch registriert werden soll, ersetzen Sie mit [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto).  
  
2.  Hinzufügen der [Noncreatable](../../windows/noncreatable.md) -Attribut auf die Co-Klasse in der IDL-Datei. Zum Beispiel:  
  
 ```  
 [  
    uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
 {  
 [default] interface IMyInterface;  
 }  
 ```  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Visual C++-Projekttypen](../../ide/visual-cpp-project-types.md)   
 [Erstellen von Desktopprojekten mit Anwendungs-Assistenten](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmieren mit ATL- und C-Laufzeitcode](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Grundlagen von ATL-COM-Objekten](../../atl/fundamentals-of-atl-com-objects.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

