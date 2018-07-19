---
title: Dialogleisten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, control bars
- CDialogBar class [MFC], dialog bars
- control bars [MFC], dialog bars
- dialog bars
- dialog bars [MFC], about dialog bars
ms.assetid: 485c8055-6bb0-4051-8417-dd2971499321
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7c68ca2725d25b493003ad7d847176c7dd8d17d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348806"
---
# <a name="dialog-bars"></a>Dialogleisten
Eine Dialogleiste ist eine Symbolleiste, eine Art von [Steuerleiste](../mfc/control-bars.md) , kann jede Art von Steuerelement enthalten. Da sie die Merkmale eines nicht modalen Dialogfelds hat eine [CDialogBar](../mfc/reference/cdialogbar-class.md) Objekt eine leistungsstärkere Symbolleiste bereitgestellt.  
  
 Es gibt einige wichtige Unterschiede zwischen einer Symbolleiste und ein `CDialogBar` Objekt. Ein `CDialogBar` -Objekt wird erstellt, aus einer Dialogfeldvorlagen-Ressource, die Sie mit den Visual C++-Dialog-Editor erstellen und können auch einem beliebigen Windows-Steuerelement enthalten. Der Benutzer kann vom Steuerelement Steuerelement auf der Registerkarte. Und Sie können angeben, dass eine Ausrichtung-Formatvorlage, die Dialogleiste mit einem beliebigen Teil des übergeordneten Rahmenfensters ausgerichtet oder direktes zu lassen, wenn die übergeordnetem Element geändert wird. Die folgende Abbildung zeigt eine Dialogleiste mit einer Vielzahl von Steuerelementen.  
  
 ![VC-Dialogleiste](../mfc/media/vc378t1.gif "vc378t1")  
Eine Dialogleiste  
  
 In anderen Hinsicht, arbeiten mit einem `CDialogBar` Objekt ist wie ein nicht modales Dialogfeld arbeiten. Verwenden des Dialog-Editors entwerfen und Erstellen der Dialogfeldressource.  
  
 Einer der Vorteile von Dialogleisten ist, dass sie Steuerelemente, die keine Schaltflächen enthalten können.  
  
 Während der normalen eigener Dialogfeldklassen von abgeleitet ist `CDialog`, eine eigene Klasse für eine Dialogleiste in der Regel nicht abgeleitet werden. Dialogleisten sind Erweiterungen für ein Hauptfenster und alle Dialogleiste Steuerelemente-benachrichtigungsmeldungen, z. B. **BN_CLICKED** oder **EN_CHANGE**, an das übergeordnete Element des Dialogfelds Balkendiagramm, das Hauptfenster gesendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Benutzeroberflächenelemente](../mfc/user-interface-elements-mfc.md)   
 [Beispiel](../visual-cpp-samples.md)

