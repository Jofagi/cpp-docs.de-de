---
title: Makros und C++
ms.date: 11/04/2016
helpviewer_keywords:
- macros, C++
- macros
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
ms.openlocfilehash: cd5d1237bc025cceb25cc290509b929b595a215f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499891"
---
# <a name="macros-and-c"></a>Makros und C++
C++ bietet neue Funktionen, von denen einige die Funktionen ablösen, die vom ANSI-C-Präprozessor bereitgestellt werden. Diese neuen Funktionen erweitern die Typsicherheit und die Voraussagbarkeit der Sprache:

- In C++ können Objekte, die als deklariert **const** in Konstanten Ausdrücken verwendet werden können. Dadurch können Programme Konstanten deklarieren, die Typ- und Wertinformationen haben, und Enumerationen, die mit dem Debugger symbolisch angezeigt werden können. Die Verwendung der `#define`-Präprozessoranweisung zum Definieren von Konstanten ist weniger genau. Wird kein Speicher für reserviert eine **const** Objekt, wenn ein Ausdruck, der die Adresse wird im Programm gefunden wird.

- Funktionstypmakros werden von der C++-Inlinefunktion abgelöst. Im Vergleich zu Makros haben Inlinefunktionen folgende Vorteile:

    - Typsicherheit. Inlinefunktionen unterliegen derselben Typüberprüfung wie normale Funktionen. Makros sind nicht typsicher.

    - Korrekte Behandlung von Argumenten, die Nebeneffekte haben. Inlinefunktionen werten vor dem Eintreten in den Funktionstext die Ausdrücke aus, die als Argumente bereitgestellt werden. Daher ist es nicht möglich, dass ein Ausdruck mit Nebeneffekten unsicher ist.

Weitere Informationen zu Inlinefunktionen finden Sie unter [Inline __inline, \__forceinline](../cpp/inline-functions-cpp.md).

Aus Gründen der Abwärtskompatibilität werden alle Präprozessorfunktionen, die in ANSI C und in früheren C++-Spezifikationen vorhanden sind, für Microsoft C++ beibehalten.

## <a name="see-also"></a>Siehe auch

[Vordefinierte Makros](../preprocessor/predefined-macros.md)<br/>
[Makros (C/C++)](../preprocessor/macros-c-cpp.md)