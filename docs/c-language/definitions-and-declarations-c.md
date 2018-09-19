---
title: Deklarationen und Definitionen (C) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae97ecc055ed7e6a448f2f820e762cafb2c5798
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028674"
---
# <a name="definitions-and-declarations-c"></a>Definitionen und Deklarationen (C)

**Microsoft-spezifisch**

Die DLL-Schnittstelle bezieht sich auf alle Elemente (Funktionen und Daten), von denen bekannt ist, dass sie von irgend einem Programm im System exportiert werden; das heißt, alle Elemente, die als **dllimport** oder `dllexport` deklariert werden. Alle Deklarationen, die in der DLL-Schnittstelle eingeschlossen sind, müssen das **dllimport**- oder das `dllexport`-Attribut angeben. Allerdings kann die Definition nur das `dllexport`-Attribut angeben. Beispielsweise verursacht die folgende Funktionsdefinition einen Compilerfehler:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int func()    /* Error; dllimport prohibited in */
                        /* definition. */
{
   return 1;
}
```

Dieser Code generiert außerdem einen Fehler:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int i = 10;      /* Error; this is a definition. */
```

Dies ist jedoch die richtige Syntax:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport int i = 10;      /* Okay: this is an export definition. */
```

Die Verwendung von `dllexport` setzt eine Definition voraus, während **dllimport** eine Deklaration impliziert. Sie müssen das `extern`-Schlüsselwort mit `dllexport` verwenden, um eine Deklaration zu erzwingen; andernfalls wird eine Definition impliziert.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllImport int k;   /* These are correct and imply */
Dllimport int j;          /* a declaration. */
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Import- und Exportfunktionen einer DLL](../c-language/dll-import-and-export-functions.md)