---
title: Compilerfehler C2318
ms.date: 11/04/2016
f1_keywords:
- C2318
helpviewer_keywords:
- C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
ms.openlocfilehash: a68a333c9cb817a653597acb011dfbb9291c4d0e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615767"
---
# <a name="compiler-error-c2318"></a>Compilerfehler C2318

Kein try-Block mit diesem catch-Handler verbunden

Es ist ein `catch` -Handler definiert, vor diesem ist aber kein `try` -Block angegeben.

Im folgenden Beispiel wird C2318 generiert:

```
// C2318.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   // no try block
   catch( int ) {}   // C2318
}
```

Mögliche Lösung:

```
// C2318b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try{}
   catch( int ) {}
}
```