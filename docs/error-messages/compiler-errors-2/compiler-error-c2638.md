---
title: Compilerfehler C2638
ms.date: 11/04/2016
f1_keywords:
- C2638
helpviewer_keywords:
- C2638
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
ms.openlocfilehash: 0c4c1e73c97f51bb0e52a618829ffb0bed417a45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582775"
---
# <a name="compiler-error-c2638"></a>Compilerfehler C2638

"Bezeichner": __based-Modifizierer für Zeiger auf Member unzulässig

Die `__based` Modifizierer kann nicht für Zeiger auf Member verwendet werden.

Im folgende Beispiel wird die C2638 generiert:

```
// C2638.cpp
void *a;

class C {
public:
   int i;
   int j;
   int func();
};
int __based (a) C::* cpi = &C::i;  // C2638
int (__based (a) C::* cpf)() = &C::func; // c2638
```