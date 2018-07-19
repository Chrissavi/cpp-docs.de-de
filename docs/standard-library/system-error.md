---
title: '&lt;system_error&gt; | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <system_error>
- system_error
dev_langs:
- C++
helpviewer_keywords:
- system_error header
ms.assetid: 5e046c6e-48d9-4740-8c8a-05f3727c1215
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f182df5bda73f9b31c86407cc1475ee6c5ec9b9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33856943"
---
# <a name="ltsystemerrorgt"></a>&lt;system_error&gt;

Fügen Sie den Header \<System_error > zum Definieren der Ausnahmeklasse `system_error` und Vorlagen für die Verarbeitung von Systemfehlern auf niedriger Ebene beziehen.

## <a name="syntax"></a>Syntax

```cpp
#include <system_error>
```

### <a name="objects"></a>erzwingen

|||
|-|-|
|[generic_category](../standard-library/system-error-functions.md#generic_category)|Stellt die Kategorie für allgemeine Fehler dar.|
|[system_category](../standard-library/system-error-functions.md#system_category)|Stellt die Kategorie für Fehler dar, die von Low-Level-Systemüberläufen verursacht wurden.|

### <a name="typedefs"></a>Typedefs

|Typname|Beschreibung|
|-|-|
|[generic_errno](../standard-library/system-error-typedefs.md#generic_errno)|Ein Typ, der die Enumeration darstellt, die die symbolischen Namen für alle von Posix in `<errno.h>` definierten Fehlercodemakros bietet.|

### <a name="functions"></a>Funktionen

|Funktion|Beschreibung|
|-|-|
|[make_error_code](../standard-library/system-error-functions.md#make_error_code)|Sie erstellt ein `error_code`-Objekt.|
|[make_error_condition](../standard-library/system-error-functions.md#make_error_condition)|Sie erstellt ein `error_condition`-Objekt.|

### <a name="operators"></a>Operatoren

|Operator|Beschreibung|
|-|-|
|[operator==](../standard-library/system-error-operators.md#op_eq_eq)|Testet, ob das Objekt links vom Operator gleich dem Objekt rechts vom Operator ist.|
|[operator!=](../standard-library/system-error-operators.md#op_neq)|Testet, ob das Objekt links vom Operator ungleich dem Objekt rechts vom Operator ist.|
|[operator<](../standard-library/system-error-operators.md#op_lt)|Testet, ob ein Objekt kleiner ist als das Objekt, das für den Vergleich übergeben wurde.|

### <a name="enumerations"></a>Enumerationen

|||
|-|-|
|[errc](../standard-library/system-error-enums.md#errc)|Gibt symbolische Namen für alle Fehlercodemakros an, die von Posix in `<errno.h>` definiert sind.|

### <a name="classes-and-structs"></a>Klassen und Strukturen

|||
|-|-|
|[error_category](../standard-library/error-category-class.md)|Stellt die abstrakte, allgemeine Basis für Objekte dar, die eine Fehlercodekategorie beschreibt.|
|[error_code](../standard-library/error-code-class.md)|Stellt Low-Level-Systemfehler dar, die von der Implementierung abhängen.|
|[error_condition](../standard-library/error-condition-class.md)|Stellt benutzerdefinierte Fehlercodes dar.|
|[is_error_code_enum](../standard-library/is-error-code-enum-class.md)|Stellt ein Typprädikat dar, das auf die [error_code-Klasse](../standard-library/error-code-class.md)-Enumeration testet.|
|[is_error_condition_enum](../standard-library/is-error-condition-enum-class.md)|Stellt ein Typprädikat dar, das auf die [error_codition-Klasse](../standard-library/error-condition-class.md)-Enumeration testet.|
|[system_error](../standard-library/system-error-class.md)|Eine Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Low-Level-Systemüberlauf zu melden.|

## <a name="requirements"></a>Anforderungen

**Header:** \<system_error>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
