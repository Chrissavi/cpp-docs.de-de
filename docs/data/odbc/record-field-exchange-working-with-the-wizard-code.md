---
title: 'Datensatzfeldaustausch: Arbeiten mit Assistenten-Code'
ms.date: 05/09/2019
helpviewer_keywords:
- DoFieldExchange method, overriding
- Unicode, with database classes
- field data members, declaring
- RFX (ODBC), wizard code
- RFX (ODBC), implementing
- field data members
- ODBC, RFX
- m_nParams data member, initializing
- m_nFields data member
- m_nParams data member
- overriding, DoFieldExchange
- m_nFields data member, initializing
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
ms.openlocfilehash: 81b26e61f64623d1e3da5ed207d0e8e43350229d
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708007"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Datensatzfeldaustausch: Arbeiten mit Assistenten-Code

> [!NOTE] 
> Der MFC-ODBC-Consumer-Assistent ist in Visual Studio 2019 und höher nicht verfügbar. Sie können einen Consumer weiterhin manuell erstellen.

In diesem Thema wird der Code erläutert, den der MFC-Anwendungs-Assistent und **Klasse hinzufügen** (wie unter [Hinzufügen eines MFC-ODBC-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md) beschrieben) zur Unterstützung von RFX schreiben, und wird erläutert, wie Sie diesen Code ändern können.

> [!NOTE]
>  Dieses Thema bezieht sich auf aus `CRecordset` abgeleitete Klassen, in denen gesammeltes Abrufen (Massenabrufen) von Zeilen nicht implementiert wurde. Wenn Sie Massenabrufen von Zeilen verwenden, wird der Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk-RFX ist RFX sehr ähnlich. Informationen zu den Unterschieden finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Wenn Sie eine Recordset-Klasse mit dem MFC-Anwendungs-Assistenten oder mit **Klasse hinzufügen** erstellen, schreibt der Assistent die folgenden RFX-bezogenen Elemente anhand der Datenquelle, der Tabelle und der Spalten, die Sie im Assistenten ausgewählt haben:

- Deklarationen der Recordset-Felddatenmember in der Recordset-Klasse

- Eine Überschreibung von `CRecordset::DoFieldExchange`

- Initialisierung von Recordset-Felddatenmemberm im Konstruktor der Recordset-Klasse

##  <a name="_core_the_field_data_member_declarations"></a> Deklarationen von Felddatenmembern

Die Assistenten schreiben Sie die Deklaration einer Recordset-Klasse in eine .h-Datei, die so ähnlich aussieht wie die folgende für die Klasse `CSections`:

```cpp
class CSections : public CRecordset
{
public:
   CSections(CDatabase* pDatabase = NULL);
   DECLARE_DYNAMIC(CSections)

// Field/Param Data
   CString   m_strCourseID;
   CString   m_strInstructorID;
   CString   m_strRoomNo;
   CString   m_strSchedule;
   CString   m_strSectionNo;

// Overrides
   // Wizard generated virtual function overrides
   protected:
   virtual CString GetDefaultConnect();  // Default connection string
   virtual CString GetDefaultSQL();      // Default SQL for Recordset
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support

// Implementation
#ifdef _DEBUG
   virtual void AssertValid() const;
   virtual void Dump(CDumpContext& dc) const;
#endif

};
```

Wenn Sie Parameterdatenmember oder neue Felddatenmember hinzufügen, die Sie selbst binden, fügen Sie diese nach denjenigen hinzu, die vom Assistenten generiert wurden.

Beachten Sie außerdem, dass der Assistent die `DoFieldExchange`-Memberfunktion der Klasse `CRecordset` überschreibt.

##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange-Überschreibung

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) ist das Herzstück von RFX. Das Framework ruft `DoFieldExchange` jedes Mal auf, wenn es entweder Daten aus der Datenquelle in das Recordset oder aus dem Recordset in die Datenquelle verschieben muss. `DoFieldExchange` unterstützt außerdem das Abrufen von Informationen zu Felddatenmembern über die Memberfunktionen [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) und [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull).

Die folgende `DoFieldExchange`-Überschreibung gilt für die `CSections`-Klasse. Der Assistent schreibt die Funktion in der CPP-Datei für Ihre Recordset-Klasse.

```cpp
void CSections::DoFieldExchange(CFieldExchange* pFX)
{
   pFX->SetFieldType(CFieldExchange::outputColumn);
   RFX_Text(pFX, "CourseID", m_strCourseID);
   RFX_Text(pFX, "InstructorID", m_strInstructorID);
   RFX_Text(pFX, "RoomNo", m_strRoomNo);
   RFX_Text(pFX, "Schedule", m_strSchedule);
   RFX_Text(pFX, "SectionNo", m_strSectionNo);
}
```

Beachten Sie die folgenden Hauptmerkmale der Funktion:

- Dieser Abschnitt der Funktion wird als Feldzuordnung bezeichnet.

- Ein Aufruf von `CFieldExchange::SetFieldType` über den `pFX`-Zeiger. Dieser Aufruf gibt an, dass alle RFX-Funktionsaufrufe bis zum Ende von `DoFieldExchange` oder bis zum nächsten Aufruf von `SetFieldType` Ausgabespalten sind. Weitere Informationen hierzu finden Sie unter [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

- Mehrere Aufrufe der globalen Funktion `RFX_Text`: jeweils einer pro Felddatenmember (die alle `CString`-Variablen im Beispiel sind). Diese Aufrufe geben die Beziehung zwischen dem Namen einer Spalte in der Datenquelle und einem Felddatenmember an. Die RFX-Funktionen übernehmen die tatsächliche Datenübertragung. Die Klassenbibliothek stellt RFX-Funktionen für alle gängigen Datentypen bereit. Weitere Informationen über RFX-Funktionen finden Sie unter [Datensatzfeldaustausch: Verwenden der RFX-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).

    > [!NOTE]
    >  Die Reihenfolge der Spalten in Ihrem Resultset muss mit der Reihenfolge der RFX-Funktionsaufrufe in `DoFieldExchange` übereinstimmen.

- Der `pFX`-Zeiger auf ein [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)-Objekt, das vom Framework übergeben wird, wenn es `DoFieldExchange` aufruft. Das `CFieldExchange`-Objekt gibt den Vorgang, den `DoFieldExchange` ausführen soll, die Richtung der Übertragung und weitere Kontextinformationen an.

##  <a name="_core_the_recordset_constructor"></a> Recordset-Konstruktor

Der Recordset-Konstruktor, den die Assistenten schreiben, enthält zwei Dinge im Zusammenhang mit RFX:

- Eine Initialisierung für jeden Felddatenmeber

- Eine Initialisierung für den [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)-Datenmember, der die Anzahl der Felddatenmember enthält

Der Konstruktor für das `CSections`-Recordset-Beispiel sieht wie folgt aus:

```cpp
CSections::CSections(CDatabase* pdb)
   : CRecordset(pdb)
{
   m_strCourseID = "";
   m_strInstructorID = "";
   m_strRoomNo = "";
   m_strSchedule = "";
   m_strSectionNo = "";
   m_nFields = 5;
}
```

> [!NOTE]
>  Wenn Sie neue Felddatenmember manuell hinzufügen, wie dies der Fall ist, wenn Sie neue Spalten dynamisch binden, müssen Sie `m_nFields` inkrementieren. Fügen Sie dazu eine neue Codezeile an, etwa:

```cpp
m_nFields += 3;
```

Dies ist der Code für ein Hinzufügen von drei neuen Feldern. Wenn Sie Parameterdatenmember hinzufügen, müssen Sie den [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)-Datenmember initialisieren, der die Anzahl der Parameterdatenmember enthält. Platzieren Sie die `m_nParams`-Initialisierung außerhalb der Klammern.

## <a name="see-also"></a>Siehe auch

[Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)