---
title: 'Vorgehensweise: Schreiben von Daten in der Windows-Registrierung (C + c++ / CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, writing to
- Visual C++, writing to Windows Registry
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 304bc224be8776c9793af07283c6a5697a4e49eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33130801"
---
# <a name="how-to-write-data-to-the-windows-registry-ccli"></a>Gewusst wie: Schreiben von Daten in die Windows-Registrierung (C++/CLI)
Im folgenden Codebeispiel wird mit der <xref:Microsoft.Win32.Registry.CurrentUser> Schlüssel eine schreibbare Instanz der Erstellung der <xref:Microsoft.Win32.RegistryKey> Klasse entspricht der **Software** Schlüssel. Anschließend wird die <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>-Methode verwendet, um einen neuen Schlüssel zu erstellen und Schlüssel/Wert-Paare hinzuzufügen.  
  
## <a name="example"></a>Beispiel  
  
### <a name="code"></a>Code  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können .NET Framework verwenden, um Zugriff auf die Registrierung mit der <xref:Microsoft.Win32.Registry> und [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx) Klassen, die beide sind definiert, der <xref:Microsoft.Win32> Namespace. Die **Registrierung** Klasse ist ein Container für statische Instanzen der <xref:Microsoft.Win32.RegistryKey> Klasse. Jede Instanz stellt einen Stammregistrierungsknoten dar. Die Instanzen sind <xref:Microsoft.Win32.Registry.ClassesRoot>, <xref:Microsoft.Win32.Registry.CurrentConfig>, <xref:Microsoft.Win32.Registry.CurrentUser>, <xref:Microsoft.Win32.Registry.LocalMachine> und <xref:Microsoft.Win32.Registry.Users>.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Lesen von Daten aus der Windows-Registrierung (C + c++ / CLI)](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)