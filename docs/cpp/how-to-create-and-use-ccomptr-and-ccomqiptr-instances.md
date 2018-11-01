---
title: 'Gewusst wie: Erstellen und Verwenden von CComPtr- und CComQIPtr-Instanzen'
ms.custom: how-to
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b0356cfb-12cc-4ee8-b988-8311ed1ab5e0
ms.openlocfilehash: 8065e0b8782c1c28d83aa6fc9690150793fe51ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518702"
---
# <a name="how-to-create-and-use-ccomptr-and-ccomqiptr-instances"></a>Gewusst wie: Erstellen und Verwenden von CComPtr- und CComQIPtr-Instanzen

In der klassischen Windows-Programmierung werden Bibliotheken häufig als COM-Objekte (oder genauer gesagt, als COM-Server) implementiert. Viele Windows-Betriebssystemkomponenten werden als COM-Server implementiert, und viele Mitwirkende bieten Bibliotheken in dieser Form. Informationen zu den COM-Grundlagen finden Sie unter [Component Object Model (COM)](/windows/desktop/com/component-object-model--com--portal).

Speichern Sie beim Instanziieren eines Component Object Model-Objekts (COM) den Schnittstellenzeiger in einem intelligenten COM-Zeiger, der die Zählung von Verweisen mit Aufrufen von `AddRef` und `Release` im Destruktor durchführt. Wenn Sie die Active Template Library (ATL) oder die Microsoft Foundation Class-Bibliothek (MFC-Bibliothek) verwenden, verwenden Sie den intelligenten `CComPtr` -Zeiger. Wenn Sie ATL bzw. MFC nicht verwenden, verwenden Sie `_com_ptr_t`. Da es kein COM-Äquivalent zu `std::unique_ptr`gibt, verwenden Sie diese intelligenten Zeiger sowohl für Szenarien mit einzelnen als auch mehreren Besitzern. Sowohl `CComPtr` als auch `ComQIPtr` unterstützt Verschiebungsvorgänge mit rvalue-Verweisen.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie `CComPtr` verwenden, um ein COM-Objekt zu instanziieren und Zeiger auf seine Schnittstellen abzurufen. Beachten Sie, dass die Memberfunktion `CComPtr::CoCreateInstance` anstelle der Win32-Funktion gleichen Namens verwendet wird, um das COM-Objekt zu erstellen.

[!code-cpp[COM_smart_pointers#01](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_1.cpp)]

`CComPtr` und die zugehörigen Elemente sind Teil der ATL und definiert \<"atlcomcli.h" >. `_com_ptr_t` im deklarierten \<"comip.h" >. Der Compiler erstellt Spezialisierungen von `_com_ptr_t` , wenn er Wrapperklassen für Typbibliotheken generiert.

## <a name="example"></a>Beispiel

ATL stellt auch `CComQIPtr`bereit, der eine einfachere Syntax verwendet, um ein COM-Objekt zum Abrufen einer zusätzlichen Schnittstelle abzufragen. Wir empfehlen jedoch `CComPtr` , da er alles beherrscht, was `CComQIPtr` kann, und semantisch mehr mit unformatierten COM-Schnittstellenzeigern übereinstimmt. Bei Verwendung eines `CComPtr` zum Abfragen einer Schnittstelle wird der neue Schnittstellenzeiger in einem Ausgabeparameter platziert. Wenn bei dem Aufruf ein Fehler auftritt, wird HRESULT – das normale COM-Muster – zurückgegeben. Mit `CComQIPtr`ist der Zeiger selbst der Rückgabewert, und wenn bei dem Aufruf ein Fehler auftritt, ist kein Zugriff auf den internen HRESULT-Rückgabewert möglich. Die folgenden beiden Zeilen zeigen, wie sich die Fehlerbehandlungsmechanismen in `CComPtr` und `CComQIPtr` unterscheiden.

[!code-cpp[COM_smart_pointers#02](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_2.cpp)]

## <a name="example"></a>Beispiel

`CComPtr` bietet eine Spezialisierung für IDispatch, die das Speichern von Zeigern in COM-Automatisierungskomponenten und das Aufrufen der Methoden über die Schnittstelle mit später Bindung ermöglicht. `CComDispatchDriver` ist eine Typedef für `CComQIPtr<IDispatch, &IIDIDispatch>`, die implizit in `CComPtr<IDispatch>`konvertierbar ist. Daher ist jeder dieser drei Namen äquivalent zu `CComPtr<IDispatch>`, wenn er im Code vorkommt. Das folgende Beispiele zeigt das Abrufen eines Zeigers in das Microsoft Word-Objektmodell mit Verwendung eines `CComPtr<IDispatch>`.

[!code-cpp[COM_smart_pointers#03](../cpp/codesnippet/CPP/how-to-create-and-use-ccomptr-and-ccomqiptr-instances_3.cpp)]

## <a name="see-also"></a>Siehe auch

[Intelligente Zeiger](../cpp/smart-pointers-modern-cpp.md)