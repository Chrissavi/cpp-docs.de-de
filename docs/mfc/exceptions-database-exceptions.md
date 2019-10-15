---
title: 'Ausnahmen: Daten Bank Ausnahmen'
ms.date: 09/17/2019
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
ms.openlocfilehash: c279c5b788cc7bd8a68fe36128c116d8df91c2eb
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095824"
---
# <a name="exceptions-database-exceptions"></a>Ausnahmen: Daten Bank Ausnahmen

In diesem Artikel wird erläutert, wie Daten Bank Ausnahmen behandelt werden. Die meisten Informationen in diesem Artikel gelten unabhängig davon, ob Sie mit den MFC-Klassen für Open Database Connectivity (ODBC) oder MFC-Klassen für Datenzugriffs Objekte (DAO) arbeiten. Material, das für ein oder das andere Modell spezifisch ist, wird explizit gekennzeichnet. Folgende Themen werden behandelt:

- [Ansätze für die Ausnahmebehandlung](#_core_approaches_to_exception_handling)

- [Beispiel für eine Daten Bank Ausnahmebehandlung](#_core_a_database_exception.2d.handling_example)

##  <a name="_core_approaches_to_exception_handling"></a>Ansätze für die Ausnahmebehandlung

Der Ansatz ist identisch, unabhängig davon, ob Sie mit DAO (veraltet) oder ODBC arbeiten.

Sie sollten immer Ausnahmehandler schreiben, um Ausnahmebedingungen zu behandeln.

Der einfachste Ansatz zum Abfangen von Daten Bank Ausnahmen besteht darin, die Anwendung mit Ausnahme Szenarios zu testen. Bestimmen Sie die wahrscheinlichen Ausnahmen, die für einen Vorgang in Ihrem Code auftreten können, und erzwingen Sie die Ausnahme. Überprüfen Sie dann die Ausgabe der Ablauf Verfolgung, um anzuzeigen, welche Ausnahme ausgelöst wird, oder überprüfen Sie die zurückgegebenen Fehlerinformationen im Debugger. Dadurch erhalten Sie Informationen zu den Rückgabecodes, die für die von Ihnen verwendeten Ausnahme Szenarios angezeigt werden.

### <a name="error-codes-used-for-odbc-exceptions"></a>Für ODBC-Ausnahmen verwendete Fehler Codes

Zusätzlich zu den vom Framework definierten Rückgabecodes, die Namen der Form **AFX_SQL_ERROR_XXX**haben, basieren einige [cdbexceptions](../mfc/reference/cdbexception-class.md) auf [ODBC](../data/odbc/odbc-basics.md) -Rückgabecodes. Die Rückgabecodes für solche Ausnahmen haben Namen in der Form **SQL_ERROR_XXX**.

Die Rückgabecodes, die von den Datenbankklassen zurückgegeben werden können – sowohl von Framework als auch von ODBC definiert  – werden unter dem [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) -Datenmember der `CDBException`-Klasse dokumentiert. Weitere Informationen zu Rückgabecodes, die von ODBC definiert werden, finden Sie in der ODBC SDK *-Programmier Referenz* in der MSDN Library.

### <a name="error-codes-used-for-dao-exceptions"></a>Für DAO-Ausnahmen verwendete Fehler Codes

Für DAO-Ausnahmen sind in der Regel weitere Informationen verfügbar. Sie können auf Fehlerinformationen über drei Datenmember eines abgefangenen [CDaoException](../mfc/reference/cdaoexception-class.md) -Objekts zugreifen:

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) enthält einen Zeiger auf ein [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) -Objekt, das die Fehlerinformationen in der DAO-Auflistung von Fehler Objekten kapselt, die der Datenbank zugeordnet sind.

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) enthält einen erweiterten Fehlercode aus den MFC-DAO-Klassen. Diese Fehlercodes, die Namen der Form **AFX_DAO_ERROR_XXX**aufweisen, werden unter dem Datenmember in `CDaoException`dokumentiert.

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) enthält ggf. einen OLE **SCODE** aus DAO. Sie müssen jedoch nur selten mit diesem Fehlercode arbeiten. In der Regel sind weitere Informationen in den anderen beiden Datenmembern verfügbar. Weitere Informationen zu **SCODE** -Werten finden Sie unter dem-Datenmember.

Weitere Informationen zu DAO-Fehlern, dem DAO-Fehlerobjekttyp und der DAO-Fehler Auflistung finden Sie Unterklasse [CDaoException](../mfc/reference/cdaoexception-class.md).

##  <a name="_core_a_database_exception.2d.handling_example"></a>Beispiel für eine Daten Bank Ausnahmebehandlung

Im folgenden Beispiel wird versucht, ein [CRecordset](../mfc/reference/crecordset-class.md)-abgeleitetes Objekt auf dem Heap mit dem **New** -Operator zu erstellen und dann das Recordset (für eine ODBC-Datenquelle) zu öffnen. Ein ähnliches Beispiel für die DAO-Klassen finden Sie unter "DAO Exception example" weiter unten.

### <a name="odbc-exception-example"></a>Beispiel für eine ODBC-Ausnahme

Die [Open](../mfc/reference/crecordset-class.md#open) Member-Funktion kann eine Ausnahme auslösen (vom Typ " [CDBException](../mfc/reference/cdbexception-class.md) " für die ODBC-Klassen), sodass `Open` der Code mit einem **try** -Block in Klammern gesetzt wird. Der nachfolgende **catch** -Block fängt `CDBException`eine ab. Sie können das Ausnahme Objekt selbst untersuchen, `e`aber in diesem Fall ist es ausreichend zu wissen, dass der Versuch, ein Recordset zu erstellen, fehlgeschlagen ist. Der **catch** -Block zeigt ein Meldungs Feld an und bereinigt das Recordset-Objekt.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>Beispiel für DAO-Ausnahme

Das DAO-Beispiel ähnelt dem Beispiel für ODBC, aber Sie können in der Regel weitere Arten von Informationen abrufen. Der folgende Code versucht auch, ein Recordset zu öffnen. Wenn bei diesem Versuch eine Ausnahme ausgelöst wird, können Sie einen Datenmember des Ausnahme Objekts auf Fehlerinformationen überprüfen. Wie beim vorherigen ODBC-Beispiel ist es wahrscheinlich ausreichend, zu wissen, dass der Versuch, ein Recordset zu erstellen, fehlgeschlagen ist.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Dieser Code Ruft eine Fehlermeldungs Zeichenfolge vom [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) -Member des Ausnahme Objekts ab. MFC füllt diesen Member aus, wenn er die Ausnahme auslöst.

Eine Erläuterung der Fehlerinformationen, die von einem `CDaoException` -Objekt zurückgegeben werden, finden Sie unter Classes [CDaoException](../mfc/reference/cdaoexception-class.md) und [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md).

Wenn Sie mit Microsoft Jet-Datenbanken (MDB) arbeiten und in den meisten Fällen, wenn Sie mit ODBC arbeiten, gibt es nur ein Fehler Objekt. In seltenen Fällen, in denen Sie eine ODBC-Datenquelle verwenden und mehrere Fehler auftreten, können Sie die Fehler Auflistung von DAO durchlaufen, basierend auf der Anzahl von Fehlern, die von [CDaoException:: GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount)zurückgegeben werden. Jedes Mal, wenn die Schleife durchlaufen wird, wird [CDaoException:: GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) aufgerufen, um den `m_pErrorInfo` Datenmember erneut aufzufüllen.

## <a name="see-also"></a>Siehe auch

[Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)
