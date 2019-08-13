---
title: '&lt;memory&gt;'
ms.date: 08/04/2019
f1_keywords:
- memory/std::<memory>
- <memory>
- std::<memory>
helpviewer_keywords:
- memory header
ms.openlocfilehash: 869a7590d880beba7ccc1d324fd1ba227eeac4e0
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957091"
---
# <a name="ltmemorygt"></a>&lt;memory&gt;

Definiert eine Klasse, einen Operator und mehrere Vorlagen, die beim Zuordnen und Freigeben von Objekten helfen.

## <a name="requirements"></a>Anforderungen

**Header:** \<memory>

**Namespace:** std

## <a name="members"></a>Member

### <a name="functions"></a>Funktionen

|||
|-|-|
|[addressof](../standard-library/memory-functions.md#addressof)|Ruft die echte Adresse eines Objekts ab.|
|[align](../standard-library/memory-functions.md#align)|Gibt einen Zeiger auf einen Bereich einer angegebenen Größe zurück, basierend auf der angegebenen Ausrichtung und der Startadresse.|
|[allocate_shared](../standard-library/memory-functions.md#allocate_shared)|Erstellt `shared_ptr` auf Objekte, die einem angegebenen Typ mit einer angegebenen Zuordnung, zugeordnet und dafür erstellt werden.|
|[atomic_compare_exchange_strong](../standard-library/memory-functions.md#atomic_compare_exchange_strong)||
|[atomic_compare_exchange_weak](../standard-library/memory-functions.md#atomic_compare_exchange_weak)||
|[atomic_compare_exchange_strong_explicit](../standard-library/memory-functions.md#atomic_compare_exchange_strong_explicit)||
|[atomic_compare_exchange_weak_explicit](../standard-library/memory-functions.md#atomic_compare_exchange_weak_explicit)||
|[atomic_exchange](../standard-library/memory-functions.md#atomic_exchange)||
|[atomic_exchange_explicit](../standard-library/memory-functions.md#atomic_exchange_explicit)||
|[atomic_is_lock_free](../standard-library/memory-functions.md#atomic_is_lock_free)||
|[atomic_load](../standard-library/memory-functions.md#atomic_load)||
|[atomic_load_explicit](../standard-library/memory-functions.md#atomic_load_explicit)||
|[atomic_store](../standard-library/memory-functions.md#atomic_store)||
|[atomic_store_explicit](../standard-library/memory-functions.md#atomic_store_explicit)||
|[const_pointer_cast](../standard-library/memory-functions.md#const_pointer_cast)|Konstantenumwandlung in `shared_ptr`.|
|[declare_no_pointers](../standard-library/memory-functions.md#declare_no_pointers)|Einem Garbage Collector wird mitgeteilt, dass die bei einer bestimmten Adresse startenden und in der angegebenen Blockgröße fallenden Zeichen keine nachweisbaren Zeiger enthalten.|
|[declare_reachable](../standard-library/memory-functions.md#declare_reachable)|Der Garbage Collection wird mitgeteilt, dass die angegebene Adresse von zugewiesenem Speicher erreichbar ist.|
|[default_delete](../standard-library/memory-functions.md#default_delete)|Es werden Objekte gelöscht, die `operator new` zugeordnet sind. Kann mit `unique_ptr` verwendet werden.|
|[destroy_at](../standard-library/memory-functions.md#destroy_at)|Kurzformen `destroy` -Methode.|
|[destroy](../standard-library/memory-functions.md#destroy)|Kurzformen `destroy` -Methode.|
|[destroy_n](../standard-library/memory-functions.md#destroy_n)|Kurzformen `destroy` -Methode.|
|[dynamic_pointer_cast](../standard-library/memory-functions.md#dynamic_pointer_cast)|Dynamische Umwandlung in `shared_ptr`.|
|[get_deleter](../standard-library/memory-functions.md#get_deleter)|Rufen Sie den Deleter von `shared_ptr` ab.|
|[get_pointer_safety](../standard-library/memory-functions.md#get_pointer_safety)|Gibt den Typ der Zeigersicherheit zurück, der von einem Garbage Collector angenommen wird.|
|[get_temporary_buffer](../standard-library/memory-functions.md#get_temporary_buffer)|Weist temporären Speicher für eine Elementsequenz zu, die eine bestimmte Anzahl von Elementen nicht überschreitet.|
|[make_shared](../standard-library/memory-functions.md#make_shared)|Erstellt `shared_ptr`, das auf die zugeordneten Objekte zeigt, die mithilfe der Standardbelegung von keinen oder mehreren Argumenten erstellt werden, oder gibt es zurück.|
|[make_unique](../standard-library/memory-functions.md#make_unique)|Erstellt [unique_ptr](../standard-library/unique-ptr-class.md), das auf die zugeordneten Objekt zeigt, die von keinem oder mehreren Argumenten erstellt werden, oder gibt es zurück.|
|[pointer_safety](../standard-library/memory-enums.md#pointer_safety)|Eine Enumeration aller möglichen Rückgabewerte für `get_pointer_safety`.|
|[return_temporary_buffer](../standard-library/memory-functions.md#return_temporary_buffer)|Gibt den temporären Speicher frei, der mithilfe der `get_temporary_buffer`-Vorlagenfunktion zugeordnet wurde.|
|[static_pointer_cast](../standard-library/memory-functions.md#static_pointer_cast)|Statische Umwandlung in `shared_ptr`.|
|[swap](../standard-library/memory-functions.md#swap)|Tauschen Sie zwei `shared_ptr` oder `weak_ptr`-Objekte.|
|[undeclare_no_pointers](../standard-library/memory-functions.md#undeclare_no_pointers)|Einem Garbage Collector wird mitgeteilt, dass die Zeichen im Speicherblock, der von einem Basisadressenzeiger und -blockgröße definiert wurde, jetzt möglicherweise nachweisbare Zeiger enthalten.|
|[undeclare_reachable](../standard-library/memory-functions.md#undeclare_reachable)|`garbage_collector` wird mitgeteilt, dass eine angegebene Speicheradresse nicht erreichbar ist.|
|[uninitialized_copy](../standard-library/memory-functions.md#uninitialized_copy)|Es werden Objekte aus einem angegebenen Eingabebereich in einen nicht initialisierten Zielbereich kopiert.|
|[uninitialized_copy_n](../standard-library/memory-functions.md#uninitialized_copy_n)|Eine Kopie einer angegebenen Anzahl von Elementen aus einem Eingabeiterator wird erstellt. Die Kopien werden in einen Forward-Iterator abgelegt.|
|[uninitialized_default_construct](../standard-library/memory-functions.md#uninitialized_default_construct)|Kurzformen `uninitialized_default_construct` -Methode.|
|[uninitialized_default_construct_n](../standard-library/memory-functions.md#uninitialized_default_construct_n)|Kurzformen `uninitialized_construct` -Methode.|
|[uninitialized_fill](../standard-library/memory-functions.md#uninitialized_fill)|Objekte eines angegebenen Werts werden in einen nicht initialisierten Zielbereich kopiert.|
|[uninitialized_fill_n](../standard-library/memory-functions.md#uninitialized_fill_n)|Objekte einer angegebenen Anzahl von Elementen werden in einen nicht initialisierten Zielbereich kopiert.|
|[uninitialized_move](../standard-library/memory-functions.md#uninitialized_move)|Kurzformen `uninitialized_move` -Methode.|
|[uninitialized_move_n](../standard-library/memory-functions.md#uninitialized_move_n)|Kurzformen `uninitialized_move` -Methode.|
|[uninitialized_value_construct](../standard-library/memory-functions.md#uninitialized_value_construct)|Kurzformen `uninitialized_value_construct` -Methode.|
|[uninitialized_value_construct_n](../standard-library/memory-functions.md#uninitialized_value_construct_n)|Kurzformen `uninitialized_value_construct` -Methode.|
|[uses_allocator_v](../standard-library/memory-functions.md#uses_allocator_v)||

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator!=](../standard-library/memory-operators.md#op_neq)|Es wird auf Ungleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.|
|[operator==](../standard-library/memory-operators.md#op_eq_eq)|Es wird auf Gleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.|
|[operator>=](../standard-library/memory-operators.md#op_gt_eq)|Es wird darauf getestet, dass Zuweisungsobjekt größer als oder gleich einem zweiten Zuweisungsobjekt einer bestimmten Klasse ist.|
|[operator<](../standard-library/memory-operators.md#op_lt)|Es wird getestet, ob ein Objekt kleiner als ein zweites Objekt einer bestimmten Klasse ist.|
|[operator\<=](../standard-library/memory-operators.md#op_gt_eq)|Es wird darauf getestet, dass ein Objekt kleiner als oder gleich einem zweiten Objekt einer bestimmten Klasse ist.|
|[operator>](../standard-library/memory-operators.md#op_gt)|Es wird getestet, ob ein Objekt größer als ein zweites Objekt einer bestimmten Klasse ist.|
|[operator<<](../standard-library/memory-operators.md#op_lt_lt)|`shared_ptr`-Einfüger|

### <a name="classes"></a>Klassen

|||
|-|-|
|[allocator](../standard-library/allocator-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das die Speicherbelegung und -freigabe für Objektarrays des Typs **Type** verwaltet.|
|[allocator_traits](../standard-library/allocator-traits-class.md)|Beschreibt ein Objekt, das alle Informationen bestimmt, die für einen zuweisungsfähigen Container erforderlich ist.|
|[auto_ptr](../standard-library/auto-ptr-class.md)|Die Vorlagen Klasse beschreibt ein Objekt, das einen Zeiger auf ein zugeordneter Objekt vom Typ **Type** <strong>\*</strong> speichert, das sicherstellt, dass das Objekt, auf das es verweist, gelöscht wird, wenn das einschließende auto_ptr zerstört wird.|
|[bad_weak_ptr](../standard-library/bad-weak-ptr-class.md)|Meldet eine ungültige weak_ptr-Ausnahme.|
|[enabled_shared_from_this](../standard-library/enable-shared-from-this-class.md)|Hilft bei der Erstellung von `shared_ptr`.|
|[pointer_traits](../standard-library/pointer-traits-struct.md)|Stellt Informationen bereit, die für ein Objekt der Vorlagenklasse `allocator_traits` erforderlich sind, um eine Zuweisung mit Zeigertyp `Ptr` zu beschreiben.|
|[raw_storage_iterator](../standard-library/raw-storage-iterator-class.md)|Eine Adapterklasse, die bereitgestellt wird, um Algorithmen das Speichern ihrer Ergebnisse in nicht initialisiertem Speicher zu ermöglichen.|
|[shared_ptr](../standard-library/shared-ptr-class.md)|Umschließt einen intelligenten Zeiger mit Verweiszählung um ein dynamisch zugeordnetes Objekt.|
|[unique_ptr](../standard-library/unique-ptr-class.md)|Es wird ein Zeiger auf ein Objekt in Besitz gespeichert. Der Zeiger ist nicht im Besitz eines anderen `unique_ptr`-Elements. `unique_ptr` wird zerstört, wenn der Besitzer zerstört wird.|
|[weak_ptr](../standard-library/weak-ptr-class.md)|Umschließt einen schwach verknüpften Zeiger.|

### <a name="structures"></a>Strukturen

|||
|-|-|
|[allocator_arg_t](../standard-library/allocator-class.md#allocator_arg_t)||
|[default_delete](../standard-library/default-delete-struct.md)||
|Hashindizes|Stellt über Ladungen bereit, `unique_ptr` die `shared_ptr`speziell für und spezialisiert sind.|
|[owner_less](../standard-library/memory-functions.md#owner_less)|Ermöglicht Mischvergleiche, die auf Besitz basieren, freigegebener und schwacher Zeiger.|
|[uses_allocator](../standard-library/allocator-class.md#uses_allocator)||

### <a name="specializations"></a>Spezialisierungen

|||
|-|-|
|[allocator\<void>](../standard-library/allocator-void-class.md)|Eine Spezialisierung der Vorlagen Klassen Zuweisung zum Typ " **void**", die nur die Elementtypen definiert, die in diesem speziellen Kontext sinnvoll sind.|

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
