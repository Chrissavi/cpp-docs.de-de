---
title: Platform::StringReference-Klasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::StringReference::StringReference
- VCCORLIB/Platform::StringReference::Data
- VCCORLIB/Platform::StringReference::Length
- VCCORLIB/Platform::StringReference::GetHSTRING
- VCCORLIB/Platform::StringReference::GetString
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
ms.openlocfilehash: 7b6ab42dc630ce7e0014534064e8f1ce6da00857
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182989"
---
# <a name="platformstringreference-class"></a>Platform::StringReference-Klasse

Ein Optimierungstyp, den Sie verwenden können, um Zeichenfolgendaten in `Platform::String^` Eingabeparametern mit minimalem Kopiervorgängen weitere Methoden zu übergeben.

## <a name="syntax"></a>Syntax

```cpp
class StringReference
```

### <a name="remarks"></a>Hinweise

### <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[StringReference::StringReference](#ctor)|Zwei Konstruktoren für das Erstellen von Instanzen von `StringReference`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[StringReference::Data](#data)|Gibt die Zeichenfolgendaten als char16-Wertearray zurück.|
|[StringReference::Length](#length)|Gibt die Anzahl der Zeichen in der Zeichenfolge zurück.|
|[StringReference::GetHSTRING](#gethstring)|Gibt die Zeichenfolgendaten als HSTRING zurück.|
|[StringReference::GetString](#getstring)|Gibt die Zeichenfolgendaten als `Platform::String^`zurück.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[StringReference::operator=](#operator-assign)|Weist ein `StringReference` -Element einer neuen `StringReference` -Instanz zu.|
|[StringReference::operator()](#operator-call)|Konvertiert ein `StringReference` -Element in ein `Platform::String^`-Element.|

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Plattform

**Header:** vccorlib.h

## <a name="data"></a>  Stringreference:: Data-Methode

Gibt die Inhalte dieses `StringReference` als char16-Wertearray zurück.

### <a name="syntax"></a>Syntax

```cpp
const ::default::char16 * Data() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Array von char16-UNICODE-Textzeichen.

## <a name="gethstring"></a>  Stringreference:: Gethstring-Methode

Gibt den Inhalt der Zeichenfolge als `__abi_HSTRING` zurück.

### <a name="syntax"></a>Syntax

```cpp
__abi_HSTRING GetHSTRING() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `__abi_HSTRING` mit den eigentlichen Zeichenfolgedaten.

### <a name="remarks"></a>Hinweise

## <a name="getstring"></a>  Stringreference:: GetString-Methode

Gibt den Inhalt der Zeichenfolge als `Platform::String^` zurück.

### <a name="syntax"></a>Syntax

```cpp
__declspec(no_release_return) __declspec(no_refcount)
    ::Platform::String^ GetString() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `Platform::String^`, das die eigentlichen Zeichenfolgedaten enthält.

## <a name="length"></a>  Stringreference:: Length-Methode

Gibt die Anzahl der Zeichen in der Zeichenfolge zurück.

### <a name="syntax"></a>Syntax

```cpp
unsigned int Length() const;
```

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl ohne Vorzeichen, die die Anzahl von Zeichen in der Zeichenfolge angibt.

### <a name="remarks"></a>Hinweise

## <a name="operator-assign"></a>  Stringreference:: Operator =-Operator

Weist das angegebene Objekt dem aktuellen `StringReference`-Objekt zu.

### <a name="syntax"></a>Syntax

```cpp
StringReference& operator=(const StringReference& __fstrArg);
StringReference& operator=(const ::default::char16* __strArg);
```

### <a name="parameters"></a>Parameter

*__fstrArg*<br/>
Die Adresse eines `StringReference`-Objekts, das zum Initialisieren des aktuellen `StringReference`-Objekts verwendet wird.

*__strArg*<br/>
Zeiger auf ein Array von char16-Werten das zum Initialisieren des aktuellen `StringReference`-Objekts verwendet wird.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein Objekt des Typs `StringReference`.

### <a name="remarks"></a>Hinweise

Da `StringReference` eine Standard-c++-Klasse und keine Verweisklasse ist, erscheint nicht in der **Objektkatalog**.

## <a name="operator-call"></a>  Stringreference::Operator()-Operator

Konvertiert ein `StringReference`-Objekt in ein `Platform::String^`-Objekt.

### <a name="syntax"></a>Syntax

```cpp
__declspec(no_release_return) __declspec(no_refcount)
         operator ::Platform::String^() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für ein Objekt des Typs `Platform::String`

## <a name="ctor"></a>  StringReference::StringReference-Konstruktor

Initialisiert eine neue Instanz der `StringReference`-Klasse.

### <a name="syntax"></a>Syntax

```cpp
StringReference();
StringReference(const StringReference& __fstrArg);
StringReference(const ::default::char16* __strArg);
StringReference(const ::default::char16* __strArg, size_t __lenArg);
```

### <a name="parameters"></a>Parameter

*__fstrArg*<br/>
Der `StringReference`, dessen Daten zum Initialisieren der neuen Instanz verwendet werden.

*__strArg*<br/>
Zeiger auf ein char16-Wertearray, das zum Initialisieren der neuen Instanz verwendet wird.

*__lenArg*<br/>
Die Anzahl von Elementen in `__strArg`.

### <a name="remarks"></a>Hinweise

Die erste Version dieses Konstruktors ist der Standardkonstruktor. Die zweite Version initialisiert eine neue `StringReference`-Instanzklasse aus dem Objekt, das durch den `__fstrArg`-Parameter spezifiziert wird. Die dritten und vierten Überladungen initialisieren eine neue `StringReference`-Instanz aus einem char16-Wertearray. char16 stellt ein 16-Bit-UNICODE-Textzeichen dar.

## <a name="see-also"></a>Siehe auch

[Platform::StringReference-Klasse](../cppcx/platform-stringreference-class.md)
