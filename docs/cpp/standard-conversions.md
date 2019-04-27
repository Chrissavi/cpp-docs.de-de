---
title: Standardkonvertierungen
ms.date: 11/19/2018
helpviewer_keywords:
- standard conversions, categories of
- L-values [C++]
- conversions, standard
ms.assetid: ce7ac8d3-5c99-4674-8229-0672de05528d
ms.openlocfilehash: aee100bdc7e8ba6dd7d06c6bca9ed39c09cf2d97
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267276"
---
# <a name="standard-conversions"></a>Standardkonvertierungen

Die Programmiersprache C++ definiert Konvertierungen zwischen ihren grundlegenden Typen. Sie definiert auch Konvertierungen für Zeiger- und Verweistypen sowie und für abgeleitete "pointer-to-member"-Typen. Diese Konvertierungen werden als bezeichnet *standardkonvertierungen*.

In diesem Abschnitt werden die folgenden Standardkonvertierungen erläutert:

- Ganzzahlige Erweiterungen

- Integrale Konvertierungen

- Unverankerte Konvertierungen

- Unverankerte und integrale Konvertierungen

- Arithmetische Konvertierungen

- Zeigerkonvertierungen

- Verweiskonvertierungen

- Konvertierungen von Zeiger in Member

    > [!NOTE]
    >  Benutzerdefinierte Typen können eigene Konvertierungen festlegen. Konvertierung von benutzerdefinierten Typen finden Sie im [Konstruktoren](../cpp/constructors-cpp.md) und [Konvertierungen](../cpp/user-defined-type-conversions-cpp.md).

Der folgende Code bewirkt Konvertierungen (in diesen Beispiel ganzzahlige Erweiterungen):

```cpp
long  long_num1, long_num2;
int   int_num;

// int_num promoted to type long prior to assignment.
long_num1 = int_num;

// int_num promoted to type long prior to multiplication.
long_num2 = int_num * long_num2;
```

Das Ergebnis einer Konvertierung ist nur dann ein l-Wert, wenn hierdurch ein Verweistyp erstellt wird. Zum Beispiel eine benutzerdefinierte Konvertierung deklariert als `operator int&()` einen Verweis zurück und ist ein l-Wert. Allerdings eine Konvertierung deklariert als `operator int()`gibt ein Objekt zurück und ist kein l-Wert.

## <a name="integral-promotions"></a>Ganzzahlige Erweiterungen

Objekte eines ganzzahligen Typs können in einen anderen größeren ganzzahligen Typ (d. h. einen Typ, der einen größeren Satz von Werten darstellen kann) konvertiert werden. Dieser Typ der Erweiterungskonvertierung wird als "ganzzahlige Erweiterung" bezeichnet. Mit der ganzzahligen Erweiterung können Sie immer dann Folgendes in einem Ausdruck verwenden, wenn ein anderer ganzzahliger Typ verwendet werden kann:

- Objekte, Literale und Konstanten Typs **Char** und **short Int**

- Enumerationstypen

- **Int** -Bitfelder

- Enumeratoren

C++-Erweiterungen sind "wertneutral". Das heißt, es ist gewährleistet, dass der Wert nach der Erweiterung derselbe ist wie der Wert vor der Erweiterung. In wertneutralen, Objekte kürzerer ganzzahliger Typen (wie Bitfelder oder Objekte des Typs **Char**) Typ heraufgestuft werden **Int** Wenn **Int** können die vollständige darstellen der Bereich des ursprünglichen Typs. Wenn **Int** nicht das gesamte Spektrum Werte darstellen, und klicken Sie dann das Objekt Typ heraufgestuft wird **ganze Zahl ohne Vorzeichen**. Obwohl diese Strategie dieselbe ist, wie die von ANSI C verwendete, behalten wertneutrale Konvertierungen nicht die Vorzeichenneutralität des Objekts bei.

Wertneutrale Erweiterungen und vorzeichenneutrale Erweiterungen erzeugen normalerweise dieselben Ergebnisse. Allerdings können sie zu unterschiedlichen Ergebnissen führen, wenn das erweiterte Objekt eines der folgenden ist:

- Ein Operand vom **/**, `%`, `/=`, `%=`, **<**, **\< =**, **>**, oder **>=**

   Diese Operatoren benötigen Vorzeichen zum Bestimmen des Ergebnisses. Daher ergeben wert- und vorzeichenneutrale Erweiterungen andere Ergebnisse, wenn sie auf diese Operanden angewendet werden.

- Der linke Operand des **>>** oder **>>=**

   Diese Operatoren behandeln Mengen mit Vorzeichen und Mengen ohne Vorzeichen unterschiedlich, wenn eine Verschiebeoperation ausgeführt wird. Für Mengen mit Vorzeichen wird das Vorzeichenbit beim Verschieben einer Menge nach rechts in die frei werdenden Bitpositionen übertragen. Bei Mengen ohne Vorzeichen werden die frei werdenden Bitpositionen mit Nullen gefüllt.

- Ein Argument zu einer überladenen Funktion oder zum Operand eines überladenen Operators, das vom Vorzeichen des Typs des Operanden für die Argumentübereinstimmung abhängt. (Finden Sie unter [überladene Operatoren](../cpp/operator-overloading.md) für Weitere Informationen zum Definieren von überladenen Operatoren.)

## <a name="integral-conversions"></a>Integrale Konvertierungen

Ganzzahlige Konvertierungen werden zwischen Ganzzahltypen ausgeführt. Die ganzzahligen Typen sind **Char**, **Int**, und **lange** (und die **kurze**, **signiert**, und **ohne Vorzeichen** Versionen dieser Typen).

**Signiert, um ohne Vorzeichen**

Objekte aus Ganzzahltypen mit Vorzeichen können in entsprechende Typen ohne Vorzeichen konvertiert werden. Wenn diese Konvertierungen erfolgen, ändert sich das eigentliche Bitmuster nicht. Die Daten werden jedoch anders interpretiert. Codebeispiel:

```cpp
#include <iostream>

using namespace std;
int main()
{
    short  i = -3;
    unsigned short u;

    cout << (u = i) << "\n";
}
// Output: 65533
```

Im vorherigen Beispiel eine **kurz signiert**, `i`definiert und mit einer negativen Zahl initialisiert. Der Ausdruck `(u = i)` bewirkt, dass `i` zu konvertierenden ein **unsigned short** vor der Zuweisung zu `u`.

**Ohne Vorzeichen mit Vorzeichen**

Objekte aus Ganzzahltypen ohne Vorzeichen können in entsprechende Typen mit Vorzeichen konvertiert werden. Allerdings kann eine solche Konvertierung zur Fehlinterpretation von Daten führen, wenn der Wert des vorzeichenlosen Objekts außerhalb des Bereichs liegt, der vom Typ mit Vorzeichen darstellbar ist, wie im folgenden Beispiel veranschaulicht:

```cpp
#include <iostream>

using namespace std;
int main()
{
short  i;
unsigned short u = 65533;

cout << (i = u) << "\n";
}
//Output: -3
```

Im vorherigen Beispiel `u` ist ein **unsigned short** ganzzahliges Objekt, das in eine Menge mit Vorzeichen zum Auswerten des Ausdrucks konvertiert werden muss `(i = u)`. Weil der Wert ordnungsgemäß kann, können Sie in dargestellt werden eine **kurz signiert**, die Daten wie gezeigt fehlinterpretiert.

## <a name="floating-point-conversions"></a>Gleitkommakonvertierungen

Ein Objekt vom Gleitkommatyp kann gefahrlos in einen genaueren Gleitkommatyp konvertiert werden, d. h. die Konvertierung verursacht keinen Signifikanzverlust. Beispielsweise sind Konvertierungen aus **"float"** zu **doppelte** oder **doppelte** zu **long double** unproblematisch, und der Wert bleibt unverändert.

Ein Objekt vom Gleitkommatyp kann auch in einen weniger genauer Typ konvertiert werden, wenn es in einem Bereich ist, der von diesem Typ darstellbar ist. (Finden Sie unter [Grenzwerte für Gleitkommakonstanten](../cpp/floating-limits.md) für die Bereiche von Gleitkommatypen.) Wenn der ursprüngliche Wert nicht exakt darstellbar ist, kann er in den nächsten höheren oder niedrigeren darstellbaren Wert konvertiert werden. Wenn kein solcher Wert vorhanden ist, ist das Ergebnis nicht definiert. Betrachten Sie das folgende Beispiel:

```cpp
cout << (float)1E300 << endl;
```

Der maximale Wert vom Typ darstellbar **"float"** ist 3.402823466E38 – eine Zahl wesentlich kleiner als 1E300. Aus diesem Grund wird die Zahl in unendlich konvertiert wird, und das Ergebnis ist "inf".

## <a name="conversions-between-integral-and-floating-point-types"></a>Konvertierungen zwischen ganzzahligem Typ und Gleitkommatyp

Bestimmte Ausdrücke können bewirken, dass Objekte vom Typ "float" in Ganzzahltypen konvertiert werden oder umgekehrt. Wenn ein Objekt eines ganzzahligen Typs in einen Gleitkommatyp konvertiert wird und der ursprüngliche Wert nicht exakt dargestellt werden kann, ist das Ergebnis der nächsthöhere oder nächstniedrigere darstellbare Wert.

Wenn ein Objekt vom Gleitkommatyp in einen ganzzahligen Typ konvertiert wird, werden die Nachkommastellen abgeschnitten. Im Konvertierungsprozess erfolgt keine Rundung. Abschneiden bedeutet, dass eine Zahl wie 1,3 in 1 und-1.3 konvertiert wird auf-1 konvertiert wird.

## <a name="arithmetic-conversions"></a>Arithmetische Konvertierungen

Viele binäre Operatoren (ausführlicher [Ausdrücke mit Binäroperatoren](../cpp/expressions-with-binary-operators.md)) führen zu Konvertierungen von Operanden und zu Ergebnissen führen, die gleiche Weise. Die Art und Weise der Konvertierung durch diese Operatoren wird als "übliche arithmetische Konvertierungen" bezeichnet. Arithmetische Konvertierungen von Operanden unterschiedlicher systemeigener Typen werden entsprechend der Darstellung in der folgenden Tabelle ausgeführt. Typedef-Typen verhalten sich entsprechend ihren zugrunde liegenden systemeigenen Typen.

### <a name="conditions-for-type-conversion"></a>Bedingungen für die Typkonvertierung

|Bedingungen erfüllt|Umwandeln|
|--------------------|----------------|
|Einer der Operanden ist vom Typ **long double**.|Anderer Operand wird in den Typ konvertiert **long double**.|
|Vorangehende Bedingung nicht erfüllt und jeder Operand ist vom Typ **doppelte**.|Anderer Operand wird in den Typ konvertiert **doppelte**.|
|Vorangehende Bedingungen nicht erfüllt und jeder Operand ist vom Typ **"float"**.|Anderer Operand wird in den Typ konvertiert **"float"**.|
|Vorausgehende Bedingungen nicht erfüllt (keiner der Operanden ist vom Typ „floating“).|Ganzzahlige Erweiterungen werden bei den Operanden wie folgt ausgeführt:<br /><br />– Wenn ein Operand vom Typ **unsigned long**, der andere Operand wird in den Typ konvertiert **unsigned long**.<br />– Wenn vorherige Bedingung nicht erfüllt, und wenn ein Operand vom Typ **lange** und der andere vom Typ **ganze Zahl ohne Vorzeichen**, beide Operanden sind in den Typ konvertiert **unsigned long**.<br />– Wenn die oben genannten zwei Bedingungen nicht erfüllt sind, und wenn ein Operand vom Typ **lange**, der andere Operand wird in den Typ konvertiert **lange**.<br />– Wenn die oben genannten drei Bedingungen nicht erfüllt sind, und wenn ein Operand vom Typ **ganze Zahl ohne Vorzeichen**, der andere Operand wird in den Typ konvertiert **ganze Zahl ohne Vorzeichen**.<br />– Wenn keines der oben genannten Bedingungen erfüllt sind, werden beide Operanden Typ konvertiert **Int**.|

Das folgende Codebeispiel veranschaulicht die Konvertierungsregeln, die in der Tabelle beschrieben werden:

```cpp
double dVal;
float fVal;
int iVal;
unsigned long ulVal;

int main() {
   // iVal converted to unsigned long
   // result of multiplication converted to double
   dVal = iVal * ulVal;

   // ulVal converted to float
   // result of addition converted to double
   dVal = ulVal + fVal;
}
```

Die erste Anweisung im vorangehenden Beispiel zeigt die Multiplikation von zwei ganzzahligen Typen, nämlich `iVal` und `ulVal`. Die Bedingung erfüllt ist, dass keiner der Operanden unverankert ist und ein Operand vom Typ **ganze Zahl ohne Vorzeichen**. Aus diesem Grund der andere Operand, `iVal`, ist in den Typ konvertiert **ganze Zahl ohne Vorzeichen**. Das Ergebnis wird `dVal` zugewiesen. Die Bedingung erfüllt ist, ein Operand ist vom Typ **doppelte**daher die **ganze Zahl ohne Vorzeichen** Ergebnis der Multiplikation ist in den Typ konvertiert **doppelte**.

Die zweite Anweisung im vorherigen Beispiel wird gezeigt, Hinzufügen einer **"float"** und ein ganzzahliger Typ, `fVal` und `ulVal`. Die `ulVal` Variable ist in den Typ konvertiert **"float"** (dritte Bedingung in der Tabelle). Das Ergebnis der Addition wird in den Typ konvertiert **doppelte** (zweite Bedingungen in der Tabelle) und zugewiesen `dVal`.

## <a name="pointer-conversions"></a>Zeigerkonvertierungen

Zeiger können bei der Zuweisung, Initialisierung, beim Vergleich und bei anderen Ausdrücken konvertiert werden.

### <a name="pointer-to-classes"></a>Zeiger auf Klassen

Es gibt zwei Fälle, in denen ein Zeiger auf eine Klasse in einen Zeiger auf eine Basisklasse konvertiert werden kann.

Der erste Fall tritt auf, wenn auf die bezeichnete Basisklasse zugegriffen werden kann und die Konvertierung eindeutig ist. (Finden Sie unter [mehrere Basisklassen](../cpp/multiple-base-classes.md) für Weitere Informationen zu mehrdeutige Basisklasse verweisen.)

Ob auf eine Basisklasse zugegriffen werden kann, hängt von der Art der Vererbung bei der Ableitung ab. Betrachten Sie die Vererbung, wie in der folgenden Abbildung veranschaulicht.

![Vererbungsdiagramm mit Basis&#45;Klasse Barrierefreiheit](../cpp/media/vc38xa1.gif "Vererbungsdiagramm mit Basis&#45;Klasse Barrierefreiheit") <br/>
Vererbungsdiagramm für Abbildung der Basisklasse-Barrierefreiheit

Die folgende Tabelle zeigt die Zugriffsmöglichkeiten auf die Basisklassen bei der Situation, die in der Abbildung veranschaulicht wird.

### <a name="base-class-accessibility"></a>Zugriff auf Basisklassen

|Typ der Funktion|Ableitung|Konvertierung von<br /><br /> B * a\* zulässig?|
|----------------------|----------------|-------------------------------------------|
|Externe (nicht im Klassenumfang enthaltene) Funktion|Private|Nein|
||Protected|Nein|
||Public|Ja|
|B-Memberfunktion (im B-Bereich)|Private|Ja|
||Protected|Ja|
||Public|Ja|
|C-Memberfunktion (im C-Bereich)|Private|Nein|
||Protected|Ja|
||Public|Ja|

Im zweiten Fall, in dem ein Zeiger auf eine Klasse in einen Zeiger auf eine Basisklasse konvertiert werden kann, wird eine explizite Typkonvertierung verwendet. (Finden Sie unter [expliziter Typkonvertierungsoperator](explicit-type-conversion-operator-parens.md) für Weitere Informationen zu expliziten typkonvertierungen.)

Das Ergebnis einer solchen Konvertierung ist ein Zeiger auf das "Unterobjekt", den Teil des Objekts, der vollständig von der Basisklasse beschrieben wird.

Der folgende Code definiert zwei Klassen, `A` und `B`, wobei `B` von `A` abgeleitet ist. (Weitere Informationen zu Vererbung, finden Sie unter [abgeleitete Klassen](../cpp/inheritance-cpp.md).) Zudem definiert der Code `bObject`, ein Objekt vom Typ `B`, und zwei Zeiger (`pA` und `pB`), die auf das Objekt zeigen.

```cpp
// C2039 expected
class A
{
public:
    int AComponent;
    int AMemberFunc();
};

class B : public A
{
public:
    int BComponent;
    int BMemberFunc();
};
int main()
{
   B bObject;
   A *pA = &bObject;
   B *pB = &bObject;

   pA->AMemberFunc();   // OK in class A
   pB->AMemberFunc();   // OK: inherited from class A
   pA->BMemberFunc();   // Error: not in class A
}
```

Der Zeiger `pA` ist vom Typ `A *`, der als "Zeiger auf ein Objekt vom Typ `A`" interpretiert werden kann. Mitglieder der `bObject` `(`wie z. B. `BComponent` und `BMemberFunc`) gelten nur für geben `B` und sind daher nicht zugegriffen werden kann, über `pA`. Der `pA`-Zeiger erlaubt nur Zugriff auf die Eigenschaften (Memberfunktionen und Daten) des Objekts, die in der Klasse `A` definiert sind.

### <a name="pointer-to-function"></a>Zeiger auf Funktion

Ein Zeiger auf eine Funktion konvertiert werden kann, Typ `void *`, wenn Typ `void *` ist groß genug, um diesen Zeiger aufzunehmen.

### <a name="pointer-to-void"></a>Zeiger auf void

Zeiger vom Typ **"void"** konvertiert werden kann, auf die Zeiger in einen anderen Typ, aber nur mit einer expliziten Typumwandlung (im Gegensatz zu c). Ein Zeiger auf einen beliebigen Typ kann implizit konvertiert werden, um einen Zeiger auf den Typ **"void"**. Ein Zeiger auf ein unvollständiges Objekt eines Typs konvertiert werden kann, auf einen Zeiger auf **"void"** (implizit) und zurück (explizit). Das Ergebnis einer solchen Konvertierung entspricht dem Wert des ursprünglichen Zeigers. Ein Objekt gilt als unvollständig, wenn es zwar deklariert ist, die Informationen zur Bestimmung seiner Größe oder Basisklasse jedoch unzureichend sind.

Ein Zeiger auf ein Objekt, das nicht ist **const** oder **flüchtige** implizit in einen Zeiger vom Typ konvertiert werden kann `void *`.

### <a name="const-and-volatile-pointers"></a>const- und volatile-Zeiger

C++ stellt keine standardkonvertierung von einem **const** oder **flüchtige** Typ in einen Typ, der nicht **const** oder **flüchtige**. Allerdings kann jede Art der Konvertierung mithilfe expliziter Typumwandlungen festgelegt werden (einschließlich unsicherer Konvertierungen).

> [!NOTE]
>  C++-Zeiger auf Member, außer Zeiger auf statische Member, unterscheiden sich von normalen Zeigern und haben nicht die gleichen Standardkonvertierungen. Zeiger auf statische Member sind normale Zeiger und haben die gleichen Konvertierungen wie normale Zeiger.

### <a name="null-pointer-conversions"></a>NULL-Zeigerkonvertierungen

Ein ganzzahliger konstanter Ausdruck, der mit Null ausgewertet wird, oder ein solcher Ausdruck, der in einen Zeigertyp umgewandelt wird, wird in einen Zeiger mit der Bezeichnung "NULL-Zeiger" umgewandelt. Für diesen Zeiger wird sichergestellt, dass er ungleich einem Zeiger auf ein gültiges Objekt oder eine Funktion ist (abgesehen von Zeigern auf basierte Objekte, die den gleichen Offset haben können und dennoch auf verschiedene Objekte zeigen können).

In C ++ 11 die ["nullptr"](../cpp/nullptr.md) Typ soll der C-Stil-null-Zeiger bevorzugt werden.

### <a name="pointer-expression-conversions"></a>Zeiger-Ausdruck-Konvertierungen

Jeder Ausdruck mit einem Arraytyp kann in einen Zeiger des gleichen Typs konvertiert werden. Das Ergebnis der Konvertierung ist ein Zeiger auf das erste Arrayelement. Im folgenden Beispiel wird eine solche Konvertierung veranschaulicht:

```cpp
char szPath[_MAX_PATH]; // Array of type char.
char *pszPath = szPath; // Equals &szPath[0].
```

Ein Ausdruck, der eine Funktion ergibt, die einen bestimmten Typ zurückgibt, wird in einen Zeiger auf eine Funktion konvertiert, die diesen Typ zurückgibt, ausgenommen unter folgenden Bedingungen:

- Der Ausdruck wird als Operand für Address-of-Operators verwendet (**&**).

- Der Ausdruck wird als Operand des Funktionsaufrufoperators verwendet.

## <a name="reference-conversions"></a>Verweiskonvertierungen

Ein Verweis auf eine Klasse kann in den folgenden Fällen in einen Verweis auf eine Basisklasse konvertiert werden:

- Die angegebene Basisklasse kann zugegriffen werden.

- Die Konvertierung ist eindeutig. (Finden Sie unter [mehrere Basisklassen](../cpp/multiple-base-classes.md) für Weitere Informationen zu mehrdeutige Basisklasse verweisen.)

Das Ergebnis der Konvertierung ist ein Zeiger auf das Unterobjekt, das die Basisklasse darstellt.

## <a name="pointer-to-member"></a>Zeiger auf Member

Zeiger auf Klassenmember können bei der Zuweisung, Initialisierung, beim Vergleich und bei anderen Ausdrücken konvertiert werden. In diesem Abschnitt werden die folgenden Konvertierungen von Zeigern in Elemente beschrieben:

## <a name="pointer-to-base-class-member"></a>Zeiger auf Basisklassenmember

Ein Zeiger auf den Member einer Basisklasse kann in einen Zeiger auf den Member einer Klasse konvertiert werden, die davon abgeleitet ist, wenn die folgenden Bedingungen erfüllt sind:

- Auf die entgegengesetzte Konvertierung von Zeigern auf eine abgeleitete Klasse in Zeiger auf eine Basisklasse kann zugegriffen werden.

- Die abgeleitete Klasse erbt nicht virtuell von der Basisklasse.

Wenn der linke Operand ein Zeiger auf einen Member ist, muss der rechte Operand vom Typ „pointer-to-member“ oder ein konstanter Ausdruck sein, der als 0 ausgewertet wird. Diese Zuweisung ist nur in den folgenden Fällen gültig:

- Der rechte Operand ist ein Zeiger auf einen Member derselben Klasse wie der linke Operand.

- Der linke Operand ist ein Zeiger auf den Member einer Klasse, die öffentlich und eindeutig von der Klasse des rechten Operanden abgeleitet wird.

## <a name="integral-constant-conversions"></a>Konvertierungen von ganzzahligen Konstanten

Ein ganzzahliger konstanter Ausdruck, der mit Null ausgewertet wird, wird in einen Zeiger mit der Bezeichnung "NULL-Zeiger" konvertiert. Für diesen Zeiger wird sichergestellt, dass er ungleich einem Zeiger auf ein gültiges Objekt oder eine Funktion ist (abgesehen von Zeigern auf basierte Objekte, die den gleichen Offset haben können und dennoch auf verschiedene Objekte zeigen können).

Der folgende Code veranschaulicht die Definition eines Zeigers auf einen Member `i` in Klasse `A`. Der Zeiger `pai` wird mit 0 initialisiert. Das ist der NULL-Zeiger.

```cpp
class A
{
public:
int i;
};

int A::*pai = 0;

int main()
{
}
```

## <a name="see-also"></a>Siehe auch

[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)