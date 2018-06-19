---
title: '/ Zc: trigraphs (Trigraphen-Ersetzung) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Conformance compiler options
- Zc compiler options (C++)
ms.assetid: e3d6058f-400d-4966-a3aa-800cfdf69cbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e465b62944b360d6fdb09da1230f3353658437b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379870"
---
# <a name="zctrigraphs-trigraphs-substitution"></a>/Zc:trigraphs (Trigraphen-Ersetzung)

Wenn **/Zc: trigraphs** angegeben ist, wird der Compiler eine Folge von Zeichen Trigraph mit einem entsprechenden Interpunktionszeichen ersetzt.

## <a name="syntax"></a>Syntax

> **/Zc:trigraphs**[**-**]  

## <a name="remarks"></a>Hinweise

Ein *Trigraph* besteht aus zwei aufeinander folgenden Fragezeichen ("?") gefolgt von einem eindeutigen dritten Zeichen. Die standardmäßige C-Sprache unterstützt Trigraphen für Quelldateien, die einen Zeichensatz verwenden, der keine passenden grafische Darstellungen für einige Interpunktionszeichen enthalten. Z. B. wenn Trigraphen aktiviert sind, ersetzt der Compiler die "?? = "Trigraph mit dem Zeichen"#". Über C ++ 14 können werden Trigraphen in c unterstützt. Die C ++ 17-standard entfernt Trigraphen aus der Programmiersprache C++. In C++-Code der **/Zc: trigraphs** (Compileroption) ermöglicht die Ersetzung von trigraphsequenzen durch die entsprechenden Interpunktionszeichen. **/Zc:trigraphs-** Trigraphen-Ersetzung deaktiviert.

Die **/Zc: trigraphs** Option ist standardmäßig deaktiviert, und die Option ist nicht betroffen, wenn die [/ liberalen-](permissive-standards-conformance.md) angegeben wird.

Eine Liste der C/C++-Trigraphen, und ein Beispiel, das zeigt, wie Trigraphen verwendet, finden Sie unter [Trigraphen](../../c-language/trigraphs.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Ändern der **Zusatzoptionen** Eigenschaft einschließen **/Zc: trigraphs** oder **/Zc:trigraphs-** und wählen Sie dann **OK**.

## <a name="see-also"></a>Siehe auch

[/Zc (Übereinstimmung)](../../build/reference/zc-conformance.md)<br/>
[Trigraphen](../../c-language/trigraphs.md)<br/>
