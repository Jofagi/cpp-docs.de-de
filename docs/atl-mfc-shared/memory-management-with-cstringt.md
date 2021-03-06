---
title: Speicherverwaltung mit CStringT
ms.date: 11/04/2016
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
ms.openlocfilehash: f45aac11f0c42aecf8c72cf6f7d1630d50b780f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598018"
---
# <a name="memory-management-with-cstringt"></a>Speicherverwaltung mit CStringT

Klasse [CStringT](../atl-mfc-shared/reference/cstringt-class.md) ist eine Vorlagenklasse, die zum Bearbeiten von Zeichenfolgen mit variabler Länge verwendet. Der Arbeitsspeicher zum Speichern dieser Zeichenfolgen reserviert und freigegeben, die über einen Zeichenfolge-Manager-Objekt verknüpft ist, wobei jede Instanz von `CStringT`. MFC und ATL bieten standardmäßig Instanziierungen von `CStringT`namens `CString`, `CStringA`, und `CStringW`, das Bearbeiten von Zeichenfolgen, die von verschiedenen Zeichentypen. Diese Typen mit Zeichen sind vom Typ TCHAR **Char**, und `wchar_t`bzw. Diese Standard-Zeichenfolgen-Datentypen verwenden einen Zeichenfolge-Manager, der Arbeitsspeicher von den Prozessheap (in ATL) oder dem CRT-Heap (in MFC) zuweist. In vielen Anwendungen reicht diese Speicherbelegungsschema. Verwenden Sie jedoch für Code, sodass rechenintensive von Zeichenfolgen (oder Multithreadcode), die die Standard-Speicher-Manager nicht optimal ausgeführt werden können. In diesem Thema wird beschrieben, wie zum Überschreiben des Standardverhalten für die Verwaltung von Arbeitsspeicher von `CStringT`, erstellen Zuweisungen speziell für die aktuelle Aufgabe optimiert.

- [Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (grundlegende Methode)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)

- [Vermeiden von Heapkonflikten](../atl-mfc-shared/avoidance-of-heap-contention.md)

- [Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (fortgeschrittene Methode)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)

- [CFixedStringT: Beispiel eines benutzerdefinierten Zeichenfolgenmanagers](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)

## <a name="see-also"></a>Siehe auch

[CustomString-Beispiel](../visual-cpp-samples.md)

