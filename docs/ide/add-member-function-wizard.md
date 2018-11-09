---
title: Assistent zum Hinzufügen von Memberfunktionen
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.function.overview
helpviewer_keywords:
- Add Member Function Wizard [C++]
ms.assetid: 13b6defc-faa6-4d57-83db-9dd854cbea3d
ms.openlocfilehash: 6ba95026d712c71a9d706baddfefda548100c64a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615045"
---
# <a name="add-member-function-wizard"></a>Assistent zum Hinzufügen von Memberfunktionen

Dieser Assistent fügt die Funktionsdeklaration eines Members zur Headerdatei und die Implementierung einer Stub-Memberfunktion zur Implementierungsdatei der ausgewählten Klasse hinzu.

Sobald Sie eine Memberfunktion mithilfe des Assistenten hinzugefügt haben, können Sie den Code in der Entwicklungsumgebung bearbeiten.

- **Rückgabetyp**

   Legt den Rückgabetyp für die hinzugefügte Memberfunktion fest. Sie können einen eigenen Rückgabetyp bereitstellen oder einen aus der Liste der verfügbaren Typen auswählen. Weitere Informationen zu Typen finden Sie unter [Grundlegende Typen](../cpp/fundamental-types-cpp.md).

   ||||
   |-|-|-|
   |**char**|**int**|**unsigned int**|
   |**double**|**long**|**unsigned long**|
   |**float**|**short**|**void**|
   |`HRESULT`|**unsigned char**||

- **Funktionsname**

   Legt den Namen der hinzugefügten Memberfunktion fest.

- **Parametertyp**

   Legt den Parametertyp fest, den Sie für die Memberfunktion hinzufügen, falls diese über Parameter verfügt. Sie können einen eigenen Parametertyp bereitstellen oder einen aus der Liste der verfügbaren Typen auswählen.

   ||||
   |-|-|-|
   |**char**|**int**|**unsigned char**|
   |**double**|**long**|**unsigned int**|
   |**float**|**short**|**unsigned long**|

- **Parametername**

   Legt die Parameternamen fest, die Sie für die Memberfunktion hinzufügen, falls diese über Parameter verfügt.

- **Parameterliste**

   Zeigt eine Liste der Parameter an, die Sie zur Memberfunktion hinzugefügt haben. Wenn Sie einen Parameter zur Liste hinzufügen möchten, geben Sie einen Typ und einen Namen in den Feldern **Parametertyp** und **Parametername** ein, und klicken Sie auf **Hinzufügen**. Wenn Sie einen Parameter aus der Liste entfernen möchten, wählen Sie diesen aus, und klicken Sie auf **Entfernen**.

- **Zugriff**

   Legt den Zugriff auf die Memberfunktion fest. Bei Zugriffsmodifizierern handelt es sich um Schlüsselwörter, die den Zugriff festlegen, den andere Klassen auf die Memberfunktion haben. Weitere Informationen zum Festlegen des Zugriffs finden Sie unter [Member-Access Control (Steuerung des Memberzugriffs)](../cpp/member-access-control-cpp.md). Standardmäßig wird die Zugriffsebene von Memberfunktionen auf **public** festgelegt.

   - [public](../cpp/public-cpp.md)

   - [protected](../cpp/protected-cpp.md)

   - [private](../cpp/private-cpp.md)

   Überprüfen Sie, ob die neue Memberfunktion „static“ oder „virtual“ ist und ob diese „inline“ oder „pure“ ist. Wenn Sie die Memberfunktion auf „pure“ festlegen, wird das Kontrollkästchen `Virtual` aktiviert, und das Kontrollkästchen **Inline** wird deaktiviert. Standardmäßig sind Memberfunktionen nicht „static“ und nicht „virtual“.

   |Option|Beschreibung |
   |------------|-----------------|
   |[Static](../cpp/storage-classes-cpp.md)|Gibt an, dass die Funktion sich wie eine globale Funktion verhält und außerhalb der Klasse aufgerufen werden kann, auch wenn die Klasse nicht instanziiert wird. Die Memberfunktion hat keinen Zugriff auf nicht statische Members. Eine Memberfunktion, die als `Static` angegeben ist, kann nicht „virtual“ sein.|
   |[Virtual](../cpp/virtual-cpp.md)|Stellt sicher, dass die richtige Memberfunktion für ein Objekt aufgerufen wird, und zwar unabhängig von dem Ausdruck, mit dem der Aufruf der Memberfunktion erfolgt. Eine Memberfunktion, die als `Virtual` angegeben ist, kann nicht „static“ sein.|
   |**Pure**|Gibt an, dass keine Implementierung für die deklarierte Memberfunktion bereitgestellt wird. Deshalb kann **pure** nur für virtuelle Memberfunktionen angegeben werden. Eine Klasse, die mindestens eine rein virtuelle Memberfunktion enthält, wird als abstrakte Klasse angesehen. Klassen, die von der abstrakten Klasse abgeleitet sind, müssen die rein virtuelle Memberfunktion implementieren, um nicht selbst als abstrakte Klasse angesehen zu werden.|
   |[Inline](../cpp/inline-functions-cpp.md)|Weist den Compiler an, eine Kopie des Memberfunktionstexts an jeder Stelle einzufügen, an der die Memberfunktion aufgerufen wird. Eine Memberfunktion, die als **Inline** angegeben ist, kann nicht „pure“ sein.|

- **CPP-Datei**

   Legt den Speicherort der Datei fest, in die die Implementierung der Stub-Memberfunktion geschrieben wird. Standardmäßig wird diese in die CPP-Datei der Klasse geschrieben, zu der die Memberfunktion hinzugefügt wird. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um den Dateinamen zu ändern. Die Implementierung der Memberfunktion wird den Inhalten der ausgewählten Datei hinzugefügt.

- **Kommentar**

   Fügt einen Kommentar zur Headerdatei der Memberfunktion hinzu.

- **Funktionssignatur**

   Zeigt die Memberfunktion so an, wie Sie im Code angezeigt wird, wenn Sie auf **Fertig stellen** klicken. Sie können den Text in diesem Feld nicht bearbeiten. Ändern Sie die entsprechenden Felder im Assistenten, wenn Sie die Memberfunktion ändern möchten.

## <a name="see-also"></a>Siehe auch

[Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)