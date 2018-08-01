---
title: Namespaces (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/30/2017
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- namespace_CPP
- using_CPP
dev_langs:
- C++
helpviewer_keywords:
- namespaces [C++], C++
- namespaces [C++]
- namespaces [C++], global
- global namespace
- Visual C++, namespaces
ms.assetid: d1a5a9ab-1cad-47e6-a82d-385bb77f4188
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a68a0a67748e79fe4379cb5f820cca0c845f392
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405482"
---
# <a name="namespaces-c"></a>Namespaces (C++)
Ein Namespace ist ein deklarativer Bereich, der einen Gültigkeitsbereich für die darin enthaltenen Bezeichner darstellt (die Namen von Typen, Funktionen, Variablen usw.). Namespaces werden verwendet, um Code in logischen Gruppen zu organisieren und Namenskonflikte zu vermeiden, die insbesondere dann auftreten können, wenn die Codebasis mehrere Bibliotheken enthält. Alle Bezeichner im Gültigkeitsbereich des Namespaces sind ohne Qualifizierung füreinander sichtbar. Bezeichner außerhalb des Namespaces können die Member zugreifen, indem Sie den vollqualifizierten Namen für jeden Bezeichner, z. B. mit `std::vector<std::string> vec;`, oder ansonsten durch eine [using-Deklaration](../cpp/using-declaration.md) für einen einzelnen Bezeichner (`using std::string`), oder eine [using-Direktive](../cpp/namespaces-cpp.md#using_directives) für alle Bezeichner im Namespace (`using namespace std;`). Der Code in Headerdateien muss immer den vollqualifizierten Namespacenamen verwenden.  
  
 Das folgende Beispiel zeigt eine Namespacedeklaration und drei Verfahren, mit denen Code außerhalb des Namespaces auf die Member zugreifen kann.  
  
```cpp  
namespace ContosoData  
{      
    class ObjectManager   
    {  
    public:  
        void DoSomething() {}  
    };  
    void Func(ObjectManager) {}  
}  
```  
  
 Verwendung des vollqualifizierten Namens:  
  
```cpp  
ContosoData::ObjectManager mgr;  
mgr.DoSomething();  
ContosoData::Func(mgr);  
```  
  
 Verwendung einer using-Deklaration, um einen Bezeichner in den Gültigkeitsbereich einzubinden:  
  
```cpp  
using ContosoData::ObjectManager;  
ObjectManager mgr;  
mgr.DoSomething();  
```  
  
 Verwendung einer using-Anweisung, um den gesamten Namespaceinhalt in den Gültigkeitsbereich einzubinden:  
  
```cpp  
using namespace ContosoData;
  
ObjectManager mgr;  
mgr.DoSomething();  
Func(mgr);  
```  
  
## <a id="using_directives"></a> using-Direktiven  
 Die **mit** -Direktive ermöglicht die Verwendung aller Namen in einer **Namespace** ohne die *Namespacename* als expliziter Qualifizierer. Verwenden einer Anweisung in einer Implementierungsdatei (d. h. *.cpp), wenn Sie mehrere verschiedene Bezeichner in einem Namespace; verwenden Wenn Sie nur ein oder zwei Bezeichner verwenden, sollten Sie eine mit Deklaration, um nur diese Bezeichner in Umfang und nicht alle Bezeichner im Namespace zu bringen. Wenn eine lokale Variable denselben Namen wie eine Namespacevariable besitzt , wird die Namespacevariable ausgeblendet. Es ist ein Fehler, wenn eine Namespacevariable mit dem gleichen Namen wie eine globale Variable vorliegt.  
  
> [!NOTE]
>  Eine using-Direktive kann am Anfang einer CPP-Datei (im Dateigültigkeitsbereich) platziert werden oder innerhalb einer Klassen- oder Funktionsdefinition.  
>   
>  Vermeiden Sie generell das Einfügen von using-Direktiven in Headerdateien (*.h), da jede Datei, die diesen Header enthält, den gesamten Namespaceinhalt in den Gültigkeitsbereich einbinden kann; dies kann dazu führen, dass Probleme mit ausgeblendeten Namen und Namenskonflikte auftreten, die sehr schwer zu beheben sind. Verwenden Sie immer vollqualifizierte Namen in einer Headerdatei. Wenn diese Namen zu lang werden, können Sie einen Namespacealias verwenden, um sie zu kürzen. (Siehe unten.)  
  
## <a name="declaring-namespaces-and-namespace-members"></a>Deklarieren von Namespaces und Namespacemembern  
 In der Regel deklarieren Sie einen Namespace in einer Headerdatei. Wenn sich die Funktionsimplementierungen in einer separaten Datei befinden, qualifizieren Sie die Funktionsnamen, wie in diesem Beispiel gezeigt.  
  
```cpp  
//contosoData.h   
#pragma once  
namespace ContosoDataServer  
{  
    void Foo();  
    int Bar();  
}  
```  
  
 Funktionsimplementierungen in contosodata.cpp sollten den vollqualifizierten Namen verwenden, auch wenn man eine **mit** -Direktive am Anfang der Datei:  
  
```cpp  
#include "contosodata.h"  
using namespace ContosoDataServer;   
  
void ContosoDataServer::Foo() // use fully-qualified name here  
{  
   // no qualification needed for Bar()  
   Bar();   
}  
  
int ContosoDataServer::Bar(){return 0;}  
```  
  
 Ein Namespace kann in mehreren Blöcken in einer einzelnen Datei oder in mehreren Dateien deklariert werden. Der Compiler verbindet die Teile während der Vorverarbeitung, und der resultierende Namespace enthält alle Member, die in allen Teilen deklariert sind. Ein Beispiel hierfür ist der std-Namespace, der in jeder der Headerdateien in der Standardbibliothek deklariert wird.  
  
 Member eines benannten Namespaces können außerhalb des Namespaces definiert werden, in denen sie durch explizite Qualifizierung des definierten Namens deklariert werden. Allerdings muss sich die Definition nach der Deklaration in einem Namespace befinden, der den Namespace der Deklaration einschließt. Zum Beispiel:  
  
```cpp  
// defining_namespace_members.cpp  
// C2039 expected  
namespace V {  
        void f();  
    }  
  
    void V::f() { }        // ok  
    void V::g() { }        // C2039, g() is not yet a member of V  
  
    namespace V {  
        void g();  
    }  
}  
```  
  
 Dieser Fehler kann auftreten, wenn Namespacemember über mehrere Headerdateien deklariert werden und Sie diese Header nicht in der richtigen Reihenfolge eingeschlossen haben.  
  
## <a name="the-global-namespace"></a>Der globale Namespace  
 Wenn ein Bezeichner nicht in einem expliziten Namespace deklariert ist, ist er Teil des impliziten globalen Namespaces. Versuchen Sie es im Allgemeinen keine Deklarationen im globalen Gültigkeitsbereich, wenn möglich, mit Ausnahme des Einstiegspunkts ["main"-Funktion](../c-language/main-function-and-program-execution.md), die sich im globalen Namespace erforderlich ist. Um einen globalen Bezeichner explizit zu qualifizieren, verwenden Sie den Bereichsauflösungsoperator ohne Namen, wie in `::SomeFunction(x);`. Dadurch wird der Bezeichner von allen anderen Elementen gleichen Namens in allen anderen Namespaces unterschieden, und es vereinfacht außerdem das Verständnis Ihres Codes für andere.  
  
## <a name="the-std-namespace"></a>Der Namespace "std"  
 Alle C++-Standardbibliothekstypen und-Funktionen werden in deklariert die `std` Namespaces oder Namespaces geschachtelt `std`.  
  
## <a name="nested-namespaces"></a>Geschachtelte Namespaces  
 Namespaces können geschachtelt werden. Ein gewöhnlicher geschachtelter Namespace hat nicht qualifizierten Zugriff auf seine übergeordnete Member, aber die übergeordneten Member haben keinen nicht qualifizierten Zugriff auf den geschachtelten Namespace (es sei denn, er ist als Inline deklariert), wie im folgenden Beispiel gezeigt:  
  
```cpp  
namespace ContosoDataServer  
{  
    void Foo();   
  
    namespace Details  
    {  
        int CountImpl;  
        void Ban() { return Foo(); }  
    }  
  
    int Bar(){...};  
    int Baz(int i) { return Details::CountImpl; }      
}  
```  
  
 Gewöhnliche geschachtelte Namespaces können verwendet werden, um interne Implementierungsdetails zu kapseln, die nicht Teil der öffentlichen Schnittstelle des übergeordnete Namespaces sind.  
  
## <a name="inline-namespaces-c-11"></a>Inlinenamespaces (C++ 11)  
 Im Gegensatz zu einem gewöhnlichen geschachtelten Namespace werden Member eines Inlinenamespaces als Member des übergeordneten Namespaces behandelt. Dieses Merkmal ermöglicht es, die argumentabhängige Suche für überladene Funktionen auch für Funktionen zu verwenden, die Überladungen in einem übergeordneten und einem geschachtelten Inlinenamespace aufweisen. Außerdem können Sie dadurch eine Spezialisierung in einem übergeordneten Namespace für eine Vorlage deklarieren, die im Inlinenamespace deklariert ist. Das folgende Beispiel zeigt, wie externer Code standardmäßig an den Inlinenamespace gebunden wird:  
  
```cpp  
//Header.h  
#include <string>  
  
namespace Test  
{  
    namespace old_ns  
    {  
        std::string Func() { return std::string("Hello from old"); }  
    }  
  
    inline namespace new_ns  
    {  
        std::string Func() { return std::string("Hello from new"); }  
    }  
}  
  
#include "header.h"  
#include <string>  
#include <iostream>  
  
int main()  
{  
    using namespace Test;  
    using namespace std;  
  
    string s = Func();  
    std::cout << s << std::endl; // "Hello from new"  
    return 0;  
}  
```  
  
 Das folgende Beispiel zeigt, wie Sie eine Spezialisierung in einem übergeordneten Namespace einer Vorlage deklarieren, die in einem Inlinenamespace deklariert ist:  
  
```cpp  
namespace Parent  
{  
    inline namespace new_ns  
    {  
         template <typename T>  
         struct C  
         {  
             T member;  
         };  
    }  
     template<>  
     class C<int> {};  
}  
```  
  
 Inlinenamespaces können als Mechanismus für die Versionskontrolle verwendet werden, um Änderungen an der öffentlichen Schnittstelle einer Bibliothek zu verwalten. Sie können beispielsweise einen einzelnen übergeordneten Namespace erstellen und jede Version der Schnittstelle in einem eigenen Namespace kapseln, der innerhalb des übergeordneten Namespaces geschachtelt ist. Der Namespace, der die aktuelle oder bevorzugte Version enthält, wird als Inlinenamespace qualifiziert und daher so verfügbar gemacht, als handele es sich um einen direkten Member des übergeordnete Namespaces. Clientcode, der Parent::Class aufruft, wird automatisch an den neuen Code gebunden. Clients, die die ältere Version verwenden möchten, können weiterhin darauf zugreifen, indem sie den vollqualifizierten Pfad zu dem geschachtelten Namespace verwenden, der diesen Code enthält.  
  
 Das inline-Schlüsselwort muss auf die erste Deklaration des Namespaces in einer Kompilierungseinheit angewendet werden.  
  
 Das folgende Beispiel zeigt zwei Versionen einer Schnittstelle, beide in einem geschachtelten Namespace. Der `v_20`-Namespace weist einige Änderungen gegenüber der `v_10`-Schnittstelle auf und ist als Inline gekennzeichnet. Clientcode, der die neue Bibliothek verwendet `Contoso::Funcs::Add` aufruft, ruft die v_20-Version auf. Bei Code, der versucht, `Contoso::Funcs::Divide` aufzurufen, wird jetzt ein Fehler zur Kompilierzeit ausgegeben. Wenn diese Funktion wirklich benötigt wird, kann durch explizites Aufrufen von `Contoso::v_10::Funcs::Divide` immer noch auf die `v_10`-Version zugegriffen werden.  
  
```cpp  
namespace Contoso  
{  
    namespace v_10  
    {  
        template <typename T>  
        class Funcs  
        {  
        public:  
            Funcs(void);  
            T Add(T a, T b);  
            T Subtract(T a, T b);  
            T Multiply(T a, T b);  
            T Divide(T a, T b);  
        };  
    }  
  
    inline namespace v_20  
    {  
        template <typename T>  
        class Funcs  
        {  
        public:  
            Funcs(void);  
            T Add(T a, T b);  
            T Subtract(T a, T b);  
            T Multiply(T a, T b);  
            std::vector<double> Log(double);  
            T Accumulate(std::vector<T> nums);  
      };  
    }  
}  
```  
  
## <a id="namespace_aliases"></a> Namespace-Aliase  
 Namespacenamen müssen eindeutig sein, was bedeutet, dass sie häufig nicht zu kurz sein dürfen. Wenn Code aufgrund eines langen Namens schwer zu lesen ist oder die Eingabe einer Headerdatei Umstände bereitet, wenn keine using-Direktiven verwendet werden können, können Sie einen Namespacealias als Abkürzung für den tatsächlichen Namen erstellen. Zum Beispiel:  
  
```cpp  
namespace a_very_long_namespace_name { class Foo {}; }  
namespace AVLNN = a_very_long_namespace_name;  
void Bar(AVLNN::Foo foo){ }  
```  
  
## <a name="anonymous-or-unnamed-namespaces"></a>anonyme oder unbenannte Namespaces  
 Sie können einen expliziten Namespace erstellen, ihm aber keinen Namen zuweisen:  
  
```cpp  
namespace  
{  
    int MyFunc(){}  
}  
```  
  
 Dies ist einen Namespace unbenannten oder anonymen bezeichnet und ist nützlich, wenn Sie Variablendeklarationen für Code in anderen Dateien unsichtbar möchten (d. h. versehen internen Verknüpfung) ohne einen benannten Namespace zu erstellen. Der gesamte Code in einer bestimmten Datei kann die Bezeichner in einem unbenannten Namespace sehen, aber die Bezeichner, zusammen mit dem Namespace selbst, sind außerhalb dieser Datei nicht sichtbar – oder genauer gesagt außerhalb der Übersetzungseinheit.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Definitionen](declarations-and-definitions-cpp.md)