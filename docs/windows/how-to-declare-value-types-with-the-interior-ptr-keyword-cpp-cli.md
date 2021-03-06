---
title: 'Gewusst wie: Deklarieren von Werttypen mit dem interior_ptr-Schlüsselwort (C++/CLI)'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
ms.openlocfilehash: 114d1bd3677537029f336f4de3675015f1725214
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612861"
---
# <a name="how-to-declare-value-types-with-the-interiorptr-keyword-ccli"></a>Gewusst wie: Deklarieren von Werttypen mit dem interior_ptr-Schlüsselwort (C++/CLI)

Ein **Interior_ptr** kann mit einem Werttyp verwendet werden.

> [!IMPORTANT]
> Diese Sprachfunktion wird unterstützt, indem die `/clr` -Compileroption verwenden, aber nicht von der `/ZW` -Compileroption.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Der folgende C++-/ c++ / CLI-Beispiel veranschaulicht, wie ein **Interior_ptr** mit einem Werttyp.

### <a name="code"></a>Code

```cpp
// interior_ptr_value_types.cpp
// compile with: /clr
value struct V {
   V(int i) : data(i){}
   int data;
};

int main() {
   V v(1);
   System::Console::WriteLine(v.data);

   // pointing to a value type
   interior_ptr<V> pv = &v;
   pv->data = 2;

   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);

   // pointing into a value type
   interior_ptr<int> pi = &v.data;
   *pi = 3;
   System::Console::WriteLine(*pi);
   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);
}
```

```Output
1
2
2
3
3
3
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

In einen Werttyp handelt die **dies** Zeiger Interior_ptr ergibt.

Im Text einer nicht statischen Memberfunktion eines Werttyps `V`, **dies** ist ein Ausdruck vom Typ `interior_ptr<V>` , deren Wert ist die Adresse des Objekts für die die Funktion aufgerufen wird.

### <a name="code"></a>Code

```cpp
// interior_ptr_value_types_this.cpp
// compile with: /clr /LD
value struct V {
   int data;
   void f() {
      interior_ptr<V> pv1 = this;
      // V* pv2 = this;   error
   }
};
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel zeigt, wie Sie mit der Address-of-Operator mit den statischen Membern.

Die Adresse eines statischen Members der Visual C++-Typ führt einen systemeigenen Zeiger.  Die Adresse eines statischen Wert Type-Elements ist ein verwalteter Zeiger auf, da Typmember Wert auf dem Runtime-Heap reserviert wird und vom Garbage Collector verschoben werden kann.

### <a name="code"></a>Code

```cpp
// interior_ptr_value_static.cpp
// compile with: /clr
using namespace System;
value struct V { int i; };

ref struct G {
   static V v = {22};
   static int i = 23;
   static String^ pS = "hello";
};

int main() {
   interior_ptr<int> p1 = &G::v.i;
   Console::WriteLine(*p1);

   interior_ptr<int> p2 = &G::i;
   Console::WriteLine(*p2);

   interior_ptr<String^> p3 = &G::pS;
   Console::WriteLine(*p3);
}
```

```Output
22
23
hello
```

## <a name="see-also"></a>Siehe auch

[interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)