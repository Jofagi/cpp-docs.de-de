---
title: Compilerfehler C2792
ms.date: 11/04/2016
f1_keywords:
- C2792
helpviewer_keywords:
- C2792
ms.assetid: 392cf748-4f5e-4e62-a364-3118d5658408
ms.openlocfilehash: 40047cb557fba49f94e5c4e42f172cbcd999c65a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492755"
---
# <a name="compiler-error-c2792"></a>Compilerfehler C2792

"super": Dieses Schlüsselwort muss folgen "::"

Das einzige Token, das ausführen kann, dass Sie das Schlüsselwort `__super` ist `::`.

Im folgende Beispiel wird die C2792 generiert:

```
// C2792.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super.();   // C2792

      // try the following line instead
      // __super::mf();
   }
};
```