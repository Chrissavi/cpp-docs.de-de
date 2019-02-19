---
title: Argumentbeschreibung
ms.date: 11/04/2016
helpviewer_keywords:
- envp argument
- main function, syntax
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 91c2cbe3-9aca-4277-afa1-6137eb8fb704
ms.openlocfilehash: 71301bd5eedf2806e97b8d24d95beaf2843427ad
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2019
ms.locfileid: "56148503"
---
# <a name="argument-description"></a>Argumentbeschreibung

Der `argc`-Parameter in den **main**- und **wmain**-Funktionen ist eine ganze Zahl, die angibt, wie viele Argumente über die Befehlszeile an das Programm übergeben werden. Da der Programmname als ein Argument gilt, ist der Wert von `argc` mindestens 1.

## <a name="remarks"></a>Anmerkungen

Der `argv`-Parameter ist ein Array von Zeigern auf auf NULL endende Zeichenfolgen, die die Programmargumente darstellen. Jedes Element des Arrays zeigt auf eine Zeichenfolgendarstellung eines Arguments, das an **main** (oder **wmain**) übergeben wird. (Informationen zu Arrays finden Sie unter [Arraydeklarationen](../c-language/array-declarations.md).) Der `argv`-Parameter kann entweder als Array von Zeigern auf Typ `char` (`char *argv[]`) oder als Zeiger auf Zeiger vom Typ `char` (`char **argv`) deklariert werden. Bei **wmain** kann der `argv`-Parameter entweder als Array von Zeigern auf Typ `wchar_t` (`wchar_t *argv[]`) oder als Zeiger auf Zeiger vom Typ `wchar_t` (`wchar_t **argv`) deklariert werden.

Gemäß der Konvention ist `argv`**[0]** der Befehl, mit dem das Programm aufgerufen wird.  Allerdings ist es möglich, einen Prozess mit [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) zu erstellen, und wenn Sie sowohl das erste als auch das zweite Argument (`lpApplicationName` und `lpCommandLine`) verwenden, ist `argv`**[0]** möglicherweise kein ausführbarer Name. Verwenden Sie [GetModuleFileName](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea), um den ausführbaren Namen abzurufen.

Der letzte Zeiger (`argv[argc]`) ist **NULL**. (Unter [getenv](../c-runtime-library/reference/getenv-wgetenv.md) in der *Laufzeitbibliotheksreferenz* finden Sie Informationen über eine alternative Möglichkeit zum Abrufen von Umgebungsvariablen.)

**Microsoft-spezifisch**

Der Parameter `envp` ist ein Zeiger auf einen Array von Zeichenfolgen, die mit NULL enden und die Werte darstellen, die in den Variablen der Benutzerumgebung festgelegt wurden. Der Parameter `envp` kann als ein Array von Zeigern auf `char` (`char *envp[]`) deklariert werden oder als ein Zeiger auf Zeiger auf `char` (`char **envp`). In einer **wmain**-Funktion kann der `envp`-Parameter als Array von Zeigern auf `wchar_t` (`wchar_t *envp[]`) oder als Zeiger auf die Zeiger auf `wchar_t` (`wchar_t **envp`) deklariert werden. Das Ende des Arrays wird durch einen **NULL** \*-Zeiger angegeben. Beachten Sie, dass der Umgebungsblock, der an **main** oder **wmain** übergeben wird, eine „fixierte“ Kopie der aktuellen Umgebung ist. Wenn Sie danach die Umgebung durch einen Aufruf von _**putenv** oder `_wputenv` ändern, wird die aktuelle Umgebung geändert (wie durch `getenv`/`_wgetenv` und die `_environ`- oder `_wenviron`-Variablen zurückgegeben), aber der von `envp` referenzierte Block ändert sich nicht. Der Parameter `envp` ist kompatibel mit ANSI in C, aber nicht in C++.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[main-Funktion und Programmausführung](../c-language/main-function-and-program-execution.md)
