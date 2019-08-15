---
title: 'Vorgehensweise: Erstellen einer klassischen COM-Komponente mit WRL'
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
ms.openlocfilehash: ec762b07caa30ce9aa6f4c67f84bb66ae884a7cf
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498387"
---
# <a name="how-to-create-a-classic-com-component-using-wrl"></a>Vorgehensweise: Erstellen einer klassischen COM-Komponente mit WRL

Sie können die Windows-Runtime C++ Template Library (WRL) verwenden, um grundlegende klassische COM-Komponenten für die Verwendung in Desktop-Apps zu erstellen, zusätzlich zur Verwendung für universelle Windows-Plattform-Apps (UWP). Für die Erstellung von COM-Komponenten ist für C++ die Windows-Runtime Vorlagen Bibliothek möglicherweise weniger Code als für ATL erforderlich. Informationen über die Teilmenge von com, die von der C++ Windows-Runtime Vorlagen Bibliothek unterstützt wird, finden Sie unter [Windows-Runtime C++ Template Library (WRL)](windows-runtime-cpp-template-library-wrl.md).

In diesem Dokument wird gezeigt, wie Sie C++ die Windows-Runtime Vorlagen Bibliothek zum Erstellen einer grundlegenden COM-Komponente verwenden. Obwohl Sie den Bereitstellungsmechanismus, der für Ihre Anforderungen am besten geeignet ist, verwenden können, zeigt dieses Dokument auch eine einfache Möglichkeit zur Registrierung und Nutzung der COM-Komponente aus einer Desktop-App.

### <a name="to-use-the-windows-runtime-c-template-library-to-create-a-basic-classic-com-component"></a>So verwenden Sie die C++ Windows-Runtime Vorlagen Bibliothek zum Erstellen einer grundlegenden klassischen COM-Komponente

1. Erstellen Sie in Visual Studio ein **leeres** Projektmappenprojekt. Benennen Sie das Projekt, z `WRLClassicCOM`. b.

2. Fügen Sie der Projekt Mappe ein **Win32-Projekt** hinzu. Benennen Sie das Projekt, z `CalculatorComponent`. b. Wählen Sie auf der Registerkarte **Anwendungseinstellungen** die Option **dll**aus.

3. Fügen Sie dem Projekt eine Datei mit **mittlerer l-Datei (. idl)** hinzu. Benennen Sie die Datei, z `CalculatorComponent.idl`. b.

4. Fügen Sie diesen Code zu CalculatorComponent.idl hinzu:

   [!code-cpp[wrl-classic-com-component#1](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]

5. Definieren Sie die `CalculatorComponent` Klasse in CalculatorComponent.cpp. Die `CalculatorComponent` Klasse erbt von [Microsoft:: WRL:: runtimeclass](runtimeclass-class.md). [Microsoft:: WRL:: runtimeclassflags\<classiccom >](runtimeclassflags-structure.md) gibt an, dass die Klasse von " [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) " und nicht von " [iinspectable](/windows/win32/api/inspectable/nn-inspectable-iinspectable)" abgeleitet ist. (`IInspectable` ist nur für Windows-Runtime App-Komponenten verfügbar.) erstellt eine Factory für die-Klasse, die mit Funktionen wie z. b. [cokreateinstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)verwendet werden kann. `CoCreatableClass`

   [!code-cpp[wrl-classic-com-component#2](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]

6. Verwenden Sie den folgenden Code, um den Code `dllmain.cpp`in zu ersetzen. Diese Datei definiert die DLL-Exportfunktionen. Diese Funktionen verwenden die [Microsoft:: WRL:: Module](module-class.md) -Klasse zum Verwalten der Klassenfactorys für das Modul.

   [!code-cpp[wrl-classic-com-component#3](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]

7. Fügen Sie eine **Modul Definitionsdatei (. def)** zum Projekt hinzu. Benennen Sie die Datei, z `CalculatorComponent.def`. b. Diese Datei gibt dem Linker die Namen der zu exportierenden Funktionen.

8. Fügen Sie diesen Code zu CalculatorComponent.def hinzu:

    ```
    LIBRARY

    EXPORTS
        DllGetActivationFactory PRIVATE
        DllGetClassObject       PRIVATE
        DllCanUnloadNow         PRIVATE
    ```

9. Der Linker-Befehlszeile runtimeobject.lib hinzufügen. Informationen zur Vorgehensweise finden Sie unter [. Lib-Dateien als Eingabe für den Linker](../../build/reference/dot-lib-files-as-linker-input.md).

### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Nutzen Sie die COM-Komponente aus einer Desktop-App.

1. Registrieren Sie die COM-Komponente mit der Windows-Registrierung. Erstellen Sie zu diesem Zweck eine Registrierungseinträge-Datei, benennen `RegScript.reg`Sie Sie, und fügen Sie den folgenden Text hinzu. `C:\temp\WRLClassicCOM\Debug\CalculatorComponent.dll`Ersetzen  *\<Sie dll-Path >* durch den Pfad der dll, z. –.

    ```
    Windows Registry Editor Version 5.00

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}]
    @="CalculatorComponent Class"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\InprocServer32]
    @="<dll-path>"
    "ThreadingModel"="Apartment"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Programmable]

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\TypeLib]
    @="{9D3E6826-CB8E-4D86-8B14-89F0D7EFCD01}"

    [HKEY_CLASSES_ROOT\Wow6432Node\CLSID\{E68F5EDD-6257-4E72-A10B-4067ED8E85F2}\Version]
    @="1.0"
    ```

2. Führen Sie regscript. reg aus, oder fügen Sie es dem **Postbuildereignis**Ihres Projekts hinzu. Weitere Informationen finden Sie unter [Dialog Feld "Präbuildereignis/Postbuildereignis-Befehlszeile](/visualstudio/ide/reference/pre-build-event-post-build-event-command-line-dialog-box)".

3. Fügen Sie der Projekt Mappe ein **Win32-Konsolen Anwendungs** Projekt hinzu. Benennen Sie das Projekt, z `Calculator`. b.

4. Verwenden Sie diesen Code, um den Inhalt `Calculator.cpp`von zu ersetzen:

   [!code-cpp[wrl-classic-com-component#6](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]

## <a name="robust-programming"></a>Stabile Programmierung

In diesem Dokument werden Standard-com-Funktionen verwendet, um zu veranschaulichen C++ , dass Sie die Windows-Runtime Vorlagen Bibliothek verwenden können, um eine COM-Komponente zu erstellen und für jede com-aktivierte Technologie verfügbar zu machen. Sie können auch Windows-Runtime C++ Vorlagen Bibliothekstypen wie z. b. [Microsoft:: WRL:: comptr](comptr-class.md) in Ihrer Desktop-App verwenden, um die Lebensdauer von com und anderen Objekten zu verwalten. Im folgenden Code wird die Windows-Runtime C++ -Vorlagen Bibliothek verwendet, um die Gültigkeitsdauer des `ICalculatorComponent` Zeigers zu verwalten. Die `CoInitializeWrapper` Klasse ist ein RAII-Wrapper, der sicherstellt, dass die COM-Bibliothek freigegeben wird und dass die Lebensdauer der COM-Bibliothek länger ist als die vom `ComPtr` intelligenten Zeiger-Objekt.

[!code-cpp[wrl-classic-com-component#7](../codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]

## <a name="see-also"></a>Siehe auch

[C++-Vorlagenbibliothek für Windows-Runtime (WRL)](windows-runtime-cpp-template-library-wrl.md)