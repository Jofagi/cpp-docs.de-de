---
title: Übersicht über die Funktionen
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
ms.openlocfilehash: 3b2f2cfe5cd769b3cdaef002a970ad21c48162ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50557364"
---
# <a name="overview-of-functions"></a>Übersicht über die Funktionen

Funktionen müssen eine Definition aufweisen und sollten eine Deklaration enthalten, obwohl eine Definition als Deklaration verwendet werden kann, wenn die Deklaration vor dem Aufruf der Funktion angezeigt wird. Die Funktionsdefinition enthält den Funktionstext, also den Code, der beim Funktionsaufruf ausgeführt wird.

Eine Funktionsdeklaration legt den Namen, den Rückgabetyp und die Attribute einer Funktion fest, die an anderer Stelle im Programm definiert ist. Eine Funktionsdeklaration muss dem Aufruf der Funktion vorangestellt sein. Daher werden die Headerdateien, die die Deklarationen für die Laufzeitfunktionen enthalten, im Code vor dem Aufruf einer Laufzeitfunktion eingebunden. Sofern die Deklaration Informationen über die Art und Anzahl der Parameter enthält, ist die Deklaration ein Prototyp. Weitere Informationen finden Sie unter [Funktionsprototypen](../c-language/function-prototypes.md).

Der Compiler nutzt den Prototyp, um die Argumenttypen bei nachfolgenden Funktionsaufrufen mit den Funktionsparametern zu vergleichen und dann die Argumenttypen (falls notwendig) in die Parametertypen zu konvertieren.

Ein Funktionsaufruf übergibt die Ausführungssteuerung von der aufrufenden Funktion an die aufgerufene Funktion. Die Argumente, sofern vorhanden, werden nach Wert an die aufgerufene Funktion übergeben. Die Ausführung einer `return`-Anweisung in der aufgerufenen Funktion gibt die Steuerung und ggf. einen Wert an die aufrufende Funktion zurück.

## <a name="see-also"></a>Siehe auch

[Funktionen](../c-language/functions-c.md)