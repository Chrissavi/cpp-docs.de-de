---
title: Tokeneinfügender Operator (##) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '##'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- '## preprocessor operator'
ms.assetid: 4f173503-990f-4bff-aef3-ec4d1f1458ef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6e224c0327a7ba50c3e13ca78d749f41ad4641f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33842230"
---
# <a name="token-pasting-operator-"></a>Tokeneinfügender Operator (##)
Die doppelten Nummernzeichen oder "Token-Pasting"-Operator (**##**), die den "Zusammenführen" Operator bezeichnet wird, wird in objektähnlichen und funktionsähnlichen Makros verwendet. Er ermöglicht die Verknüpfung separater Token zu einem Token und kann daher nicht der erste oder letzte Token in der Makrodefinition sein.  
  
 Wenn ein formaler Parameter in einer Makrodefinition dem Operator „token-pasting“ voran- oder nachgestellt ist, wird der formale Parameter sofort durch das nicht erweiterte tatsächliche Argument ersetzt. Die Makroerweiterung wird nicht vor der Ersetzung für das Argument ausgeführt.  
  
 Anschließend wird jedes Vorkommen des Token-Pasting-Operators in *-Token-String* wird entfernt, und die Token vorausgehende und folgende es verkettet werden. Das daraus resultierende Token muss ein gültiges Token sein. Ist dies der Fall, wird das Token auf eine mögliche Ersetzung überprüft, falls es einen Makronamen darstellt. Der Bezeichner steht für den Namen, unter dem die verketteten Token vor der Ersetzung im Programm bekannt sind. Jedes Token stellt ein an anderer Stelle definiertes Token dar, entweder im Programm oder in der Compilerbefehlszeile. Leerzeichen, die dem Operator vor- oder nachgestellt sind, sind optional.  
  
 In diesem Beispiel wird die Verwendung der Zeichenfolgenoperatoren und Operatoren zum Einfügen eines Tokens beim Festlegen der Programmausgabe veranschaulicht:  
  
```  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
```  
  
 Beim Aufrufen eines Makros mit einem numerischen Argument wie  
  
```  
paster( 9 );  
```  
  
 gibt das Makro  
  
```  
printf_s( "token" "9" " = %d", token9 );  
```  
  
 aus, das zu Folgendem wird:  
  
```  
printf_s( "token9 = %d", token9 );  
```  
  
## <a name="example"></a>Beispiel  
  
```  
// preprocessor_token_pasting.cpp  
#include <stdio.h>  
#define paster( n ) printf_s( "token" #n " = %d", token##n )  
int token9 = 9;  
  
int main()  
{  
   paster(9);  
}  
```  
  
```Output  
token9 = 9  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessoroperatoren](../preprocessor/preprocessor-operators.md)