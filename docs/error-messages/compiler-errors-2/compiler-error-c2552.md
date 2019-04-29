---
title: Compilerfehler C2552
ms.date: 11/04/2016
f1_keywords:
- C2552
helpviewer_keywords:
- C2552
ms.assetid: 0e0ab759-788a-4faf-9337-80d4b9e2e8c9
ms.openlocfilehash: ddd3755a4fcabf8c097c359f31c9cc189b36f79a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353130"
---
# <a name="compiler-error-c2552"></a>Compilerfehler C2552

"Bezeichner": Initialisierung nicht zusammengesetzter Typen mit Initialisierungsliste ist nicht möglich

Der Aggregatbezeichner wurde falsch initialisiert.

[Aggregate](../../c-language/initializing-aggregate-types.md) als definiert sind:

- Arrays

- Klassen, Strukturen und Unions, die nicht über folgende Elemente verfügen:

   - Konstruktoren

   - Private-Member oder Protected-Member

   - Basisklassen

   - Virtuelle Funktionen

Außerdem sind in Visual C++ Datentypen in Aggregaten, die Konstruktoren enthalten, nicht zulässig.

Beim Versuch, für einen Typ eine Aggregatinitialisierung durchzuführen, kann aus den folgenden Gründen C2552 ausgelöst werden:

- Der Typ verfügt über einen oder mehrere benutzerdefinierte Konstruktoren.

- Der Typ verfügt über einen oder mehrere nicht statische private Datenmember.

- Der Typ verfügt über eine oder mehrere virtuelle Funktionen.

- Der Typ verfügt über eine Basisklasse.

- Ein Typ ist eine Verweisklasse oder eine CLR-Schnittstelle.

- Der Typ verfügt über ein Array ohne festgelegte Größe (Array der Größe 0), dessen Elemente Destruktoren haben.

Im folgenden Beispiel wird C2552 generiert:

```
// C2552.cpp
// compile with: /clr
#include <string>
using namespace std;

struct Pair_Incorrect {
private:
   string m_name;
   double m_val;
};

struct Pair_Correct1 {
public:
   Pair_Correct1(string name, double val)
      : m_name(name), m_val(val) {}

private:
   string m_name;
   double m_val;
};

struct Pair_Correct2 {
public:
   string m_name;
   double m_val;
};

int main() {
   // To fix, add a constructor to this class and use it for
   // initializing the data members, see Pair_Correct1 (below)
   // or
   // Do not have any private or protected non-static data members,
   // see Pair_Correct2 (below).  Pair_Correct2 is not recommended in
   // case your object model requires some non-static data members to
   // be private or protected

   string name("John");
   Pair_Incorrect pair1 = { name, 0.0 };   // C2552

   // initialize a CLR immutable value type that has a constructor
   System::DateTime dt = {2001, 4, 12, 22, 16, 49, 844};   // C2552

   Pair_Correct1 pair2( name, 0.0 );
   Pair_Correct1 pair3 = Pair_Correct1( name, 0.0 );
   Pair_Correct2 pair4 = { name, 0.0 };
   System::DateTime dt2(2001, 4, 12, 22, 16, 49, 844);
}
```