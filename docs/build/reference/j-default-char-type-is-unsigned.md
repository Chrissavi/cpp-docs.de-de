---
title: + J (standardmäßig Typ unsigned Char) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
dev_langs:
- C++
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a93172296b0e2e6d54dc428ffc62812ad979b160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374465"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (Standardmäßig "unsigned char")
Ändert den Standard `char` -Typ aus `signed char` auf `unsigned char`, und die `char` Typ wird erweitert, 0 (null), wenn es um erweitert wurde, wird ein `int` Typ.  
  
## <a name="syntax"></a>Syntax  
  
```  
/J  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn eine `char` Wert explizit deklariert wird, als `signed`, die **"/ j"** Option keine Auswirkung darauf, und der Wert ist signaturerweitert, wenn es zu erweitert wurde, wird ein `int` Typ.  
  
 Die **"/ j"** Option definiert `_CHAR_UNSIGNED`, der verwendet wird, mit `#ifndef` in LIMITS.h-Datei, um den Bereich des Standardwerts definieren `char` Typ.  
  
 ANSI C- und C++ erfordern eine spezifische Implementierung nicht der `char` Typ. Diese Option ist nützlich, wenn Sie mit Zeichendaten arbeiten, die letztendlich in einer anderen Sprache als Englisch übersetzt wird.  
  
> [!NOTE]
>  Wenn Sie diese Compileroption mit ATL-/MFC verwenden, wird möglicherweise ein Fehler generiert. Obwohl Sie diesen Fehler durch die Definition deaktivieren konnte `_ATL_ALLOW_CHAR_UNSIGNED`, dieser problemumgehung wird nicht unterstützt und funktioniert möglicherweise nicht immer.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie im **Projektmappen-Explorer**das Kontextmenü für das Projekt, und wählen Sie **Eigenschaften**aus.  
  
2.  Im Projekt **Eigenschaftenseiten** im Dialogfeld im linken Bereich unter **Konfigurationseigenschaften**, erweitern Sie **C/C++-** und wählen Sie dann **Befehlszeile**.  
  
3.  In der **Zusatzoptionen** Bereich geben die **"/ j"** -Compileroption.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md)