---
title: __noop
ms.date: 11/04/2016
f1_keywords:
- __noop_cpp
- __noop
helpviewer_keywords:
- __noop keyword [C++]
ms.assetid: 81ac6e97-7bf8-496b-b3c4-fd02837573e5
ms.openlocfilehash: 074ab4c6ea51c8b3a2543d9b43248a8da37567cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613008"
---
# <a name="noop"></a>__noop

**Microsoft-spezifisch**

Die `__noop` systeminterne gibt an, dass eine Funktion, die ignoriert werden sollen und die Argumentliste analysiert werden, jedoch kein Code generiert werden, für die Argumente. Es dient zur Verwendung in globalen Debugfunktionen, die eine Variable Anzahl von Argumenten akzeptieren.

Der Compiler konvertiert die `__noop` systeminterne 0 zum Zeitpunkt der Kompilierung.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie verwenden können `__noop`.

```
// compiler_intrinsics__noop.cpp
// compile with or without /DDEBUG
#include <stdio.h>

#if DEBUG
   #define PRINT   printf_s
#else
   #define PRINT   __noop
#endif

int main() {
   PRINT("\nhello\n");
}
```

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)