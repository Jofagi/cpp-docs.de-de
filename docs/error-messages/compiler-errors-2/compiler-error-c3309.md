---
title: Compilerfehler C3309
ms.date: 11/04/2016
f1_keywords:
- C3309
helpviewer_keywords:
- C3309
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
ms.openlocfilehash: e66aa31982b018670684c8f12b05ba6f7347cd87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598145"
---
# <a name="compiler-error-c3309"></a>Compilerfehler C3309

"macro_name": Ein Modulname kann kein Makro oder Schlüsselwort sein

Der Wert, den Sie an die name-Eigenschaft des Modulattributs übergeben, darf kein Symbol für den zu erweiternden Präprozessor sein; es muss ein Zeichenfolgenliteral sein.

Im folgenden Beispiel wird C3309 generiert:

```
// C3309.cpp
#define NAME MyModule
[module(name="NAME")];   // C3309
// Try the following line instead
// [module(name="MyModule")];
[coclass]
class MyClass {
public:
   void MyFunc();
};

int main() {
}
```