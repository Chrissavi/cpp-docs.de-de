---
title: Linkertoolfehler Lnk1112 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1112
dev_langs:
- C++
helpviewer_keywords:
- LNK1112
ms.assetid: 425793d8-37e6-4072-9b6e-c3d4e9c12562
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79ca2afc7270a69c443447d1b294ee7ec8bbe5a7
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704996"
---
# <a name="linker-tools-error-lnk1112"></a>Linkertoolfehler LNK1112

> Modul-Computertyp "*Typ1*"steht in Konflikt mit dem Zielcomputertyp"*Typ2*"

## <a name="remarks"></a>Hinweise

Die als Eingabe festgelegten Objektdateien wurden für unterschiedliche Computertypen kompiliert.

Wenn Sie z. B. versuchen, eine mit **/clr** und eine mit **/clr:pure** kompilierte Objektdatei (Computertyp CEE) zu verknüpfen, generiert der Linker den Fehler LNK1112. Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird.

Wenn Sie ein Modul mit dem [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] -Compiler und ein anderes Modul mit dem x86-Compiler erstellen und dann versuchen, diese zu verknüpfen, wird vom Linker gleichsam der Fehler LNK1112 generiert.

Eine mögliche Ursache für diesen Fehler ist, dass Sie eine 64-Bit-Anwendung entwickeln, aber keiner der 64-Bit-Compiler von Visual C++ installiert ist. In diesem Fall stehen die 64-Bit-Konfigurationen nicht zur Verfügung. Um dieses Problem zu beheben, führen Sie das Installationsprogramm für Visual Studio aus und installieren die fehlenden Komponenten von C++.

Dieser Fehler kann auch auftreten, wenn Sie die **aktive Projektmappenkonfiguration** im **Konfigurations-Manager** ändern und anschließend versuchen, das Projekt zu erstellen, bevor Sie die Zwischenprojektdateien gelöscht haben. Wählen Sie zum Beheben dieses Fehlers **Projektmappe neu erstellen** aus dem Menü **Erstellen** aus. Sie können auch **Projektmappe bereinigen** aus dem Menü **Erstellen** auswählen und die Projektmappe anschließend erstellen.

## <a name="see-also"></a>Siehe auch

- [Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)
