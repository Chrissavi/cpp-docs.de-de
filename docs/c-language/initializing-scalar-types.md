---
title: Initialisieren von skalaren Typen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing scalar types
- register variables
- initialization, scalar types
- initializing variables, scalar types
- scalar types
- static variables, initializing
- automatic storage class, initializing scalar types
- automatic storage class
- types [C], initializing
ms.assetid: 73c516f5-c3ad-4d56-ab3b-f2a82b621104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fef7356768a594694e0fcf3415c66ef63568a7cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392360"
---
# <a name="initializing-scalar-types"></a>Initialisieren von skalaren Typen
Beim Initialisieren von skalaren Typen wird der Wert von *assignment-expression* der Variablen zugewiesen. Die Konvertierungsregeln für Zuweisungen gelten. (Weitere Informationen zu Konvertierungsregeln finden Sie unter [Typkonvertierungen](../c-language/type-conversions-c.md).)  
  
## <a name="syntax"></a>Syntax  
 `declaration`:  
 *declaration-specifiers init-declarator-list* opt **;**  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *init-declarator-list*:  
 *init-declarator*  
  
 *init-declarator-list* **,** *init-declarator*  
  
 *init-declarator*:  
 *declarator*  
  
 *declarator*  **=**  *initializer* /* Für skalare Initialisierung \*/  
  
 *initializer*:  
 *assignment-expression*  
  
 Sie können Variablen jeden Typs initialisieren, vorausgesetzt, dass Sie die folgenden Regeln beachten:  
  
-   Variablen, die auf der Dateigültigkeitsebene deklariert werden, können initialisiert werden. Wenn Sie eine Variable auf der externen Ebene nicht explizit initialisieren, wird diese standardmäßig mit 0 initialisiert.  
  
-   Ein konstanter Ausdruck kann verwendet werden, um eine beliebige globale Variable zu initialisieren, die mit **static** *storage-class-specifier* deklariert wird. Variablen, die als **static** deklariert sind, werden initialisiert, wenn die Programmausführung beginnt. Wenn Sie eine globale **static**-Variable nicht explizit initialisieren, wird diese standardmäßig mit 0 (null) initialisiert, und jedem Member, der den Zeigertyp aufweist, wird ein NULL-Zeiger zugewiesen.  
  
-   Variablen, die mit dem **auto**- oder **register**-Speicherklassenspezifizierer deklariert werden, werden jedes Mal initialisiert, wenn die Ausführungssteuerung an den Block übergeben wird, der die Deklaration enthält. Wenn Sie in der Deklaration einer **auto**- oder **register**-Variablen den Initialisierer weglassen, ist der Anfangswert der Variablen nicht definiert. Für automatische Werte und Registerwerte muss der Initialisierer keine Konstante sein, sondern kann ein beliebiger Ausdruck sein, der vorher definierte Werte und sogar Funktionsaufrufe enthält.  
  
-   Die Anfangswerte für externe Variablendeklarationen und alle **static**-Variablen, ob extern oder intern, müssen konstante Ausdrücke sein. (Weitere Informationen finden Sie unter [Konstante Ausdrücke](../c-language/c-constant-expressions.md).) Da die Adresse von allen extern deklarierten oder statischen Variablen konstant ist, kann sie verwendet werden, um eine intern deklarierte **static**-Zeigervariable zu initialisieren. Allerdings kann die Adresse einer **auto**-Variablen nicht als statischer Initialisierer verwendet werden, da sie bei jeder Ausführung des Blocks abweichen kann. Sie können entweder Konstanten- oder Variablenwerte verwenden, um **auto**- und **register**-Variablen zu initialisieren.  
  
-   Wenn die Deklaration eines Bezeichners einen Blockbereich aufweist und der Bezeichner eine externe Bindung hat, kann die Deklaration nicht über eine Initialisierung verfügen.  
  
## <a name="examples"></a>Beispiele  
 In den folgenden Beispielen werden Initialisierungen dargestellt:  
  
```  
int x = 10;   
```  
  
 Die ganzzahlige Variable `x` wird mit dem konstanten Ausdruck `10` initialisiert.  
  
```  
register int *px = 0;  
```  
  
 Der Zeiger `px` wird mit 0 initialisiert und erzeugt einen "null"-Zeiger.  
  
```  
const int c = (3 * 1024);  
```  
  
 Dieses Beispiel verwendet einen konstanten Ausdruck `(3 * 1024)`, um `c` mit einem konstanten Wert zu initialisieren, der aufgrund des **const**-Schlüsselworts nicht geändert werden kann.  
  
```  
int *b = &x;  
```  
  
 Diese Anweisung initialisiert den Zeiger `b` mit der Adresse der anderen Variablen `x`.  
  
```  
int *const a = &z;  
```  
  
 Der Zeiger `a` wird mit der Adresse einer Variablen namens `z` initialisiert. Da sie aber als **const** spezifiziert ist, kann die Variable `a` nur initialisiert und nie geändert werden. Sie zeigt immer auf denselben Speicherort.  
  
```  
int GLOBAL ;  
  
int function( void )  
{  
    int LOCAL ;  
    static int *lp = &LOCAL;   /* Illegal initialization */  
    static int *gp = &GLOBAL;  /* Legal initialization   */  
    register int *rp = &LOCAL; /* Legal initialization   */  
}  
```  
  
 Die globale Variable `GLOBAL` wird auf der externen Ebene deklariert und hat daher eine globale Lebensdauer. Die lokale Variable `LOCAL` hat die **auto**-Speicherklasse, und sie hat nur während der Ausführung der Funktion, in der sie deklariert wird, eine Adresse. Daher ist der Versuch, die **static**-Zeigervariable `lp` mit der Adresse von `LOCAL` zu initialisieren, unzulässig. Die **static**-Zeigervariable `gp` kann mit der Adresse von `GLOBAL` initialisiert werden, da diese Adresse immer gleich ist. Entsprechend kann `*rp` initialisiert werden, da `rp` eine lokale Variable ist und einen nicht konstanten Initialisierer haben kann. Immer wenn der Block erreicht wird, hat `LOCAL` eine neue Adresse, die dann `rp` zugewiesen wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Initialisierung](../c-language/initialization.md)