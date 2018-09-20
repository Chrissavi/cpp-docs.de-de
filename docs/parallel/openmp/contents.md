---
title: Inhalt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b7858099-7d7f-4cd9-9fa0-fba4832f2dd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0ed7dd48d496042cb48a8c8054226ec8892ffbc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432762"
---
# <a name="contents"></a>Inhalt

[1. Einführung](../../parallel/openmp/1-introduction.md)

[1.1 Geltungsbereich](../../parallel/openmp/1-1-scope.md)

[1.2. Begriffsdefinition](../../parallel/openmp/1-2-definition-of-terms.md)

[1.3 Ausführungsmodell](../../parallel/openmp/1-3-execution-model.md)

[1.4 Konformität](../../parallel/openmp/1-4-compliance.md)

[1.5 Normative Verweise](../../parallel/openmp/1-5-normative-references.md)

[1.6 Organisation](../../parallel/openmp/1-6-organization.md)

[2. Direktiven](../../parallel/openmp/2-directives.md)

[2.1 Direktivenformat](../../parallel/openmp/2-1-directive-format.md)

[2.2 Bedingte Kompilierung](../../parallel/openmp/2-2-conditional-compilation.md)

[2.3 parallel-Konstrukt](../../parallel/openmp/2-3-parallel-construct.md)

[2.4 Arbeitsteilungskonstrukte](../../parallel/openmp/2-4-work-sharing-constructs.md)

[2.4.1 for-Konstrukt](../../parallel/openmp/2-4-1-for-construct.md)

[2.4.2 sections-Konstrukt](../../parallel/openmp/2-4-2-sections-construct.md)

[2.4.3 single-Konstrukt](../../parallel/openmp/2-4-3-single-construct.md)

[2.5 Kombinierte parallele Arbeitsteilungskonstrukte](../../parallel/openmp/2-5-combined-parallel-work-sharing-constructs.md)

[2.5.1 parallel for-Konstrukt](../../parallel/openmp/2-5-1-parallel-for-construct.md)

[2.5.2 parallel sections-Konstrukt](../../parallel/openmp/2-5-2-parallel-sections-construct.md)

[2.6 Master- und Synchronisierungsdirektiven](../../parallel/openmp/2-6-master-and-synchronization-directives.md)

[2.6.1 master-Konstrukt](../../parallel/openmp/2-6-1-master-construct.md)

[2.6.2 critical-Konstrukt](../../parallel/openmp/2-6-2-critical-construct.md)

[2.6.3 barrier-Direktive](../../parallel/openmp/2-6-3-barrier-directive.md)

[2.6.4 atomic-Konstrukt](../../parallel/openmp/2-6-4-atomic-construct.md)

[2.6.5 flush-Direktive](../../parallel/openmp/2-6-5-flush-directive.md)

[2.6.6 ordered-Konstrukt](../../parallel/openmp/2-6-6-ordered-construct.md)

[2.7 Datenumgebung](../../parallel/openmp/2-7-data-environment.md)

[2.7.1 threadprivate-Direktive](../../parallel/openmp/2-7-1-threadprivate-directive.md)

[2.7.2 Datenfreigabe-Attributklauseln](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md)

[2.7.2.1 private](../../parallel/openmp/2-7-2-1-private.md)

[2.7.2.2 firstprivate](../../parallel/openmp/2-7-2-2-firstprivate.md)

[2.7.2.3 lastprivate](../../parallel/openmp/2-7-2-3-lastprivate.md)

[2.7.2.4 shared](../../parallel/openmp/2-7-2-4-shared.md)

[2.7.2.5 default](../../parallel/openmp/2-7-2-5-default.md)

[2.7.2.6 reduction](../../parallel/openmp/2-7-2-6-reduction.md)

[2.7.2.7 copyin](../../parallel/openmp/2-7-2-7-copyin.md)

[2.7.2.8 copyprivate](../../parallel/openmp/2-7-2-8-copyprivate.md)

[2.8 Direktivenbindung](../../parallel/openmp/2-8-directive-binding.md)

[2.9 Schachtelung von Anweisungen](../../parallel/openmp/2-9-directive-nesting.md)

[3. Funktionen der Laufzeitbibliothek](../../parallel/openmp/3-run-time-library-functions.md)

[3.1 Ausführungsumgebungsfunktionen](../../parallel/openmp/3-1-execution-environment-functions.md)

[3.1.1 omp_set_num_threads-Funktion](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)

[3.1.2 omp_get_num_threads-Funktion](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md)

[3.1.3 omp_get_max_threads-Funktion](../../parallel/openmp/3-1-3-omp-get-max-threads-function.md)

[3.1.4 omp_get_thread_num-Funktion](../../parallel/openmp/3-1-4-omp-get-thread-num-function.md)

[3.1.5 omp_get_num_procs-Funktion](../../parallel/openmp/3-1-5-omp-get-num-procs-function.md)

[3.1.6 omp_in_parallel-Funktion](../../parallel/openmp/3-1-6-omp-in-parallel-function.md)

[3.1.7 omp_set_dynamic-Funktion](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)

[3.1.8 omp_get_dynamic-Funktion](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md)

[3.1.9 omp_set_nested-Funktion](../../parallel/openmp/3-1-9-omp-set-nested-function.md)

[3.1.10 omp_get_nested-Funktion](../../parallel/openmp/3-1-10-omp-get-nested-function.md)

[3.2 Lock-Funktionen](../../parallel/openmp/3-2-lock-functions.md)

[3.2.1 omp_init_lock- und omp_init_nest_lock-Funktionen](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)

[3.2.2 omp_destroy_lock- und omp_destroy_nest_lock-Funktionen](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)

[3.2.3 omp_set_lock- und omp_set_nest_lock-Funktionen](../../parallel/openmp/3-2-3-omp-set-lock-and-omp-set-nest-lock-functions.md)

[3.2.4 omp_unset_lock- und omp_unset_nest_lock-Funktionen](../../parallel/openmp/3-2-4-omp-unset-lock-and-omp-unset-nest-lock-functions.md)

[3.2.5 omp_test_lock- und omp_test_nest_lock-Funktionen](../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md)

[3.3 Routinen zur zeitlichen Steuerung](../../parallel/openmp/3-3-timing-routines.md)

[3.3.1 omp_get_wtime-Funktion](../../parallel/openmp/3-3-1-omp-get-wtime-function.md)

[3.3.2 omp_get_wtick-Funktion](../../parallel/openmp/3-3-2-omp-get-wtick-function.md)

[4. Umgebungsvariablen](../../parallel/openmp/4-environment-variables.md)

[4.1 OMP_SCHEDULE](../../parallel/openmp/4-1-omp-schedule.md)

[4.2 OMP_NUM_THREADS](../../parallel/openmp/4-2-omp-num-threads.md)

[4.3 OMP_DYNAMIC](../../parallel/openmp/4-3-omp-dynamic.md)

[4.4 OMP_NESTED](../../parallel/openmp/4-4-omp-nested.md)

[A. Beispiele](../../parallel/openmp/a-examples.md)

[A. 1 parallele Ausführung einer einfachen Schleife](../../parallel/openmp/a-1-executing-a-simple-loop-in-parallel.md)

[A. 2 angeben der bedingten Kompilierung](../../parallel/openmp/a-2-specifying-conditional-compilation.md)

[A. 3 Verwenden von parallelen Bereichen](../../parallel/openmp/a-3-using-parallel-regions.md)

[A. 4 verwenden der Nowait-Klausel](../../parallel/openmp/a-4-using-the-nowait-clause.md)

[A. 5 Verwenden der critical-Direktive](../../parallel/openmp/a-5-using-the-critical-directive.md)

[A. 6 Verwenden der Lastprivate-Klausel](../../parallel/openmp/a-6-using-the-lastprivate-clause.md)

[A. 7 Verwenden der Reduction-Klausel](../../parallel/openmp/a-7-using-the-reduction-clause.md)

[A. 8 angeben von parallelen Abschnitten](../../parallel/openmp/a-8-specifying-parallel-sections.md)

[A. 9 Verwenden einzelner Direktiven](../../parallel/openmp/a-9-using-single-directives.md)

[A. 10 angeben der sequenziellen Reihenfolge](../../parallel/openmp/a-10-specifying-sequential-ordering.md)

[A. 11 angeben einer festgelegten Anzahl von Threads](../../parallel/openmp/a-11-specifying-a-fixed-number-of-threads.md)

[A. 12 verwenden der atomic-Direktive](../../parallel/openmp/a-12-using-the-atomic-directive.md)

[A. 13 Verwenden der flush-Direktive mit einer Liste](../../parallel/openmp/a-13-using-the-flush-directive-with-a-list.md)

[A. 14 verwenden der flush-Direktive ohne eine Liste](../../parallel/openmp/a-14-using-the-flush-directive-without-a-list.md)

[A. 15 Ermitteln der Anzahl der verwendeten Threads](../../parallel/openmp/a-15-determining-the-number-of-threads-used.md)

[A. 16 Verwenden von Sperren](../../parallel/openmp/a-16-using-locks.md)

[A. 17 Verwenden von schachtelbaren Sperren](../../parallel/openmp/a-17-using-nestable-locks.md)

[A. 18 geschachtelte for-Direktiven](../../parallel/openmp/a-18-nested-for-directives.md)

[19 Beispiele für falsche Verschachtelung von Arbeit sharing-Direktiven arbeitsteilungsdirektiven](../../parallel/openmp/a-19-examples-showing-incorrect-nesting-of-work-sharing-directives.md)

[A. 20 Bindung von Barrier-Direktiven](../../parallel/openmp/a-20-binding-of-barrier-directives.md)

[A. 21 Bereichsauswahl für Variablen mit der private-Klausel](../../parallel/openmp/a-21-scoping-variables-with-the-private-clause.md)

[A. 22 Verwenden der default(None)-Klausel](../../parallel/openmp/a-22-using-the-default-none-clause.md)

[A. 23 Beispiele für die ordered-Direktive](../../parallel/openmp/a-23-examples-of-the-ordered-directive.md)

[A. 24 Beispiel für die private-Klausel](../../parallel/openmp/a-24-example-of-the-private-clause.md)

[25 Beispiele der Copyprivate-Klausel-Attribut der Daten-datenattributklausel](../../parallel/openmp/a-25-examples-of-the-copyprivate-data-attribute-clause.md)

[A. 26 verwenden der Threadprivate-Direktive](../../parallel/openmp/a-26-using-the-threadprivate-directive.md)

[A. 27 Verwenden von C99-Arrays variabler Länge](../../parallel/openmp/a-27-use-of-c99-variable-length-arrays.md)

[A. 28 verwenden der Num_threads-Klausel](../../parallel/openmp/a-28-use-of-num-threads-clause.md)

[A.29 mit der Arbeit innerhalb eines critical-Konstrukts](../../parallel/openmp/a-29-use-of-work-sharing-constructs-inside-a-critical-construct.md)

[A. 30 verwenden der erneuten Privatisierung](../../parallel/openmp/a-30-use-of-reprivatization.md)

[A. 31 threadsichere Lock-Funktionen](../../parallel/openmp/a-31-thread-safe-lock-functions.md)

[B. Stubs für Funktionen der Laufzeitbibliothek](../../parallel/openmp/b-stubs-for-run-time-library-functions.md)

[C. OpenMP C- und C++-Grammatik](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md)

[C.1 Notation](../../parallel/openmp/c-1-notation.md)

[C.2 Regeln](../../parallel/openmp/c-2-rules.md)

[D. Verwenden der schedule-Klausel](../../parallel/openmp/d-using-the-schedule-clause.md)

[E. Durch die Implementierung definiertes Verhalten in OpenMP C/C++](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md)

[F. Neue Funktionen und Erläuterungen in Version 2.0](../../parallel/openmp/f-new-features-and-clarifications-in-version-2-0.md)

## <a name="see-also"></a>Siehe auch

[C und C++-Anwendungsprogrammierschnittstelle](../../parallel/openmp/openmp-c-and-cpp-application-program-interface.md)