---
title: Compilerwarnung (Stufe 1) C4727
ms.date: 11/04/2016
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: be1a248fc2709706e137b543344966735c19064e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386433"
---
# <a name="compiler-warning-level-1-c4727"></a>Compilerwarnung (Stufe 1) C4727

"PCH mit der ein vorkompilierter Header mit dem gleichen Zeitstempel in Datei1" und "Datei2 gefunden wurde.  Verwenden zuerst gefundene wird verwendet.

C4727 tritt auf, beim Kompilieren mehrere Compilands mit **"/ Yc"**, und, in denen der Compiler konnte alle OBJ-Dateien mit dem gleichen PCH-Zeitstempel zu markieren.

Um zu beheben, kompilieren Sie eine Quelldatei mit **/Yc/c** (Pch wird erstellt), und die anderen kompilieren Sie separat mit **/Yu/c** (verwendet Pch), verknüpfen Sie sie zusammen.

Also, wenn Sie Folgendes haben und C4727 generiert:

**cl /clr /GL a.cpp b.cpp c.cpp /Ycstdafx.h**

Sie werden stattdessen die folgenden Schritte:

**cl /clr /GL a.cpp /Ycstdafx.h /c**

**cl /clr /GL b.cpp c.cpp /Yustdafx.h /link a.obj**

Weitere Informationen finden Sie unter

- [/Yc (Vorkompilierte Headerdatei erstellen)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu (Vorkompilierte Headerdatei verwenden)](../../build/reference/yu-use-precompiled-header-file.md)