---
title: Implementieren eine duale Schnittstelle (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDispatchImpl class, implementing dual interfaces
- dual interfaces, implementing
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34cc55e4466dba094bf70e734340b40237207f3c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356731"
---
# <a name="implementing-a-dual-interface"></a>Eine duale Schnittstelle implementieren
Implementieren Sie eine duale Schnittstelle verwenden die [IDispatchImpl](../atl/reference/idispatchimpl-class.md) Klasse, die eine standardmäßige Implementierung des bildet die `IDispatch` Methoden in eine duale Schnittstelle. Weitere Informationen finden Sie unter [Implementing the IDispatch Interface](http://msdn.microsoft.com/en-us/0e171f7f-0022-4e9b-ac8e-98192828e945).  
  
 Diese Klasse verwenden zu können:  
  
-   Definieren Sie die duale Schnittstelle in einer Typbibliothek ein.  
  
-   Leiten Sie eine Klasse aus einer Spezialisierung von `IDispatchImpl` (übergeben Sie Informationen über die Schnittstelle und die Typbibliothek als Vorlagenargumente).  
  
-   Fügen Sie einen Eintrag (oder Einträge) der COM-Zuordnung, die duale Schnittstelle über verfügbar zu machen `QueryInterface`.  
  
-   Implementieren Sie die Vtable Teil der Schnittstelle in die Klasse.  
  
-   Stellen Sie sicher, dass die Typbibliothek, die die Schnittstellendefinition enthält, die zur Laufzeit an Ihren Objekten verfügbar ist.  
  
## <a name="atl-simple-object-wizard"></a>ATL-Assistent für einfache Objekte  
 Wenn Sie eine neue Schnittstelle und eine neue Klasse zu implementieren, erstellen möchten, können Sie mithilfe der [ATL-Klasse hinzufügen (Dialogfeld)](../ide/add-class-dialog-box.md), und klicken Sie dann die [ATL-Assistent für einfache Objekte](../atl/reference/atl-simple-object-wizard.md).  
  
## <a name="implement-interface-wizard"></a>Assistent zum Implementieren von Schnittstellen  
 Wenn Sie eine vorhandene Schnittstelle haben, können Sie die [Assistent zum Implementieren von Schnittstelle](../atl/reference/adding-a-new-interface-in-an-atl-project.md) Hinzufügen der erforderlichen Basisklasse, COM-Zuordnungseinträge und das Gerüst eines methodenimplementierungen zu einer vorhandenen Klasse.  
  
> [!NOTE]
>  Möglicherweise müssen Sie die generierten Basisklasse anpassen, sodass die Haupt- und Nebenversionsnummern Versionsnummern der Typbibliothek als Vorlagenargumente, um übergeben werden Ihre `IDispatchImpl` Basisklasse. Der Assistent zum Implementieren von Schnittstelle überprüft nicht die Versionsnummer der Typbibliothek für Sie.  
  
## <a name="implementing-idispatch"></a>Implementieren der IDispatch  
 Können Sie eine `IDispatchImpl` Basisklasse, um eine Implementierung einer Dispinterface bereitstellen, indem Sie einfach den entsprechenden Eintrag in der COM-Zuordnung angeben (mithilfe der [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) oder [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid) Makros) als stehen Ihnen eine Typbibliothek, die eine entsprechende duale Schnittstelle beschreibt. Es ist üblich, das zum Implementieren der `IDispatch` auf diese Weise z. B.-Schnittstelle. Die ATL-Assistent für einfache Objekte und implementieren Assistent Schnittstelle für beide wird davon ausgegangen, dass Sie beabsichtigen, implementieren `IDispatch` in auf diese Weise so sie fügen den entsprechenden Eintrag zur Zuordnung.  
  
> [!NOTE]
>  ATL bietet die [IDispEventImpl](../atl/reference/idispeventimpl-class.md) und [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) Klassen können Sie die Disp-Schnittstellen implementieren, ohne dass eine Typbibliothek, die die Definition eine duale Schnittstelle enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)

