---
title: Compilerfehler C3804
ms.date: 11/04/2016
f1_keywords:
- C3804
helpviewer_keywords:
- C3804
ms.assetid: 7c4cda28-ec96-4d04-937b-36dbd9944722
ms.openlocfilehash: e83380696aca3d6d45c235925b830bef9e3061a3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544585"
---
# <a name="compiler-error-c3804"></a>Compilerfehler C3804

'Property_accessor': die Zugriffsmethoden eine Eigenschaft müssen entweder werden alle statisch oder alle nicht statischen

Wenn Sie eine nicht triviale Eigenschaft zu definieren, werden die Accessorfunktionen können entweder statisch oder -Instanz, aber nicht beides.

Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md) .

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C3804 generiert.

```
// C3804.cpp
// compile with: /c /clr
ref struct A {

   property int i {
      static int get() {}
      void set(int i) {}
   }   // C3804 error

   // OK
   property int j {
      int get() { return 0; }
      void set(int i) {}
   }

   property int k {
      static int get() { return 0; }
      static void set(int i) {}
   }
};
```