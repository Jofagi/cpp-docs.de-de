---
title: Handle für Objekt (^) (C++ / CLI und C++ / CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
ms.openlocfilehash: 6f61a6b95ba8f9a059606376696fd1d8d64030db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625731"
---
# <a name="handle-to-object-operator---ccli-and-ccx"></a>Handle für Objekt (^) (C++ / CLI und C++ / CX)

Die *handledeklarator* (`^`, ausgesprochen "hat"), modifiziert den [Spezifizierer](../cpp/overview-of-declarators.md) so, dass das deklarierte Objekt automatisch gelöscht werden sollen, wenn das System feststellt, dass das Objekt ist nicht mehr zugegriffen werden kann.

## <a name="accessing-the-declared-object"></a>Zugreifen auf das deklarierte Objekt

Eine Variable, die mit dem Handledeklarator deklariert wird, verhält sich wie ein Zeiger auf das Objekt. Allerdings verweist die Variable auf das gesamte Objekt, kann also nicht auf einen Member des Objekts verweisen, und unterstützt keine Zeigerarithmetik. Verwenden Sie den Dereferenzierungsoperator (`*`), um auf das Objekt zuzugreifen, und den Pfeil-Memberzugriffsoperator (`->`), um auf einen Member des Objekts zuzugreifen.

## <a name="windows-runtime"></a>Windows-Runtime

Der Compiler verwendet die COM *verweiszählung* Mechanismus, um zu bestimmen, ob das Objekt nicht mehr verwendet wird und gelöscht werden kann. Dies ist möglich, da es sich bei einem Objekt, das von einer Windows Runtime-Schnittstelle abgeleitet wird, um ein COM-Objekt handelt. Der Verweiszähler wird inkrementiert, wenn das Objekt erstellt oder kopiert wird, und dekrementiert, wenn das Objekt auf NULL festgelegt wird oder den gültigen Bereichs verlässt. Wenn der Verweiszähler den Wert 0 erreicht, wird das Objekt automatisch und sofort gelöscht.

Der Vorteil des Handledeklarators ist, dass Sie in COM den Verweiszählerwert für ein Objekt nicht mehr explizit verwalten müssen, was ein langwieriger und fehleranfälliger Prozess ist. Dabei müssen Sie alle AddRef()- bzw. Release()-Methoden des Objekts aufrufen, um den Verweiszähler zu inkrementieren bzw. zu dekrementieren. Wenn Sie ein Objekt mit dem handledeklarator deklarieren, generiert der Compiler jedoch Code, der den Verweiszähler automatisch anpasst.

Informationen dazu, wie ein Objekt instanziieren, finden Sie unter [Ref neue](../windows/ref-new-gcnew-cpp-component-extensions.md).

## <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

Das System verwendet die CLR *Garbage Collector* Mechanismus, um zu bestimmen, ob das Objekt nicht mehr verwendet wird und gelöscht werden kann. Die Common Language Runtime verwaltet einen Heap, auf dem sie Objekten Arbeitsspeicher zuordnet, und verwendet im Programm verwaltete Verweise (Variablen), die den Speicherort von Objekten auf dem Heap angeben. Wenn ein Objekt nicht mehr verwendet wird, wird der Arbeitsspeicher freigegeben, den das Objekt auf dem Heap belegt. In regelmäßigen Abständen komprimiert der Garbage Collector den Heap, damit der freigegebene Arbeitsspeicher optimal verwendet werden kann. Das Komprimieren des Heaps kann Objekte auf dem Heap verschieben das erklärt die Speicherorte, die von den verwalteten verweisen bezeichnet. Deshalb berücksichtigt der Garbage Collector die Positionen in allen verwalteten Verweisen und aktualisiert sie automatisch, damit sie weiterhin die aktuellen Positionen der Objekte auf dem Heap angeben.

Weil aber systemeigene C++-Zeiger (`*`) und Verweise (`&`) keine verwalteten Verweise sind, kann der Garbage Collector die Adressen, auf die sie zeigen, nicht automatisch aktualisieren. Zur Umgehung dieses Problems verwenden Sie den Handledeklarator, um für eine Variable festzulegen, dass sie vom Garbage Collector verwaltet und automatisch aktualisiert werden soll.

Weitere Informationen finden Sie unter [wie: Deklarieren Sie in systemeigenen Typen behandelt](../dotnet/how-to-declare-handles-in-native-types.md).

### <a name="examples"></a>Beispiele

Dieses Beispiel zeigt, wie eine Instanz eines Referenztyps auf dem verwalteten Heap erstellt wird.  In diesem Beispiel wird außerdem gezeigt, dass Sie ein Handle mit einem anderen initialisieren können, wodurch Sie zwei Verweise auf dasselbe Objekt auf dem verwaltetem Heap mit Garbage Collection erhalten. Beachten Sie, dass diese Zuweisung ["nullptr"](../windows/nullptr-cpp-component-extensions.md) zu einem Handle markiert nicht das Objekt für die Garbagecollection.

```cpp
// mcppv2_handle.cpp
// compile with: /clr
ref class MyClass {
public:
   MyClass() : i(){}
   int i;
   void Test() {
      i++;
      System::Console::WriteLine(i);
   }
};

int main() {
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass->Test();

   MyClass ^ p_MyClass2;
   p_MyClass2 = p_MyClass;

   p_MyClass = nullptr;
   p_MyClass2->Test();
}
```

```Output
1
2
```

Das folgende Beispiel zeigt, wie ein Handle für ein Objekt auf dem verwalteten Heap deklariert wird, wobei der Objekttyp ein geschachtelter Werttyp ist. Das Beispiel zeigt auch, wie Sie den Werttyp des geschachtelten Objekts abrufen.

```cpp
// mcppv2_handle_2.cpp
// compile with: /clr
using namespace System;

void Test(Object^ o) {
   Int32^ i = dynamic_cast<Int32^>(o);

   if(i)
      Console::WriteLine(i);
   else
      Console::WriteLine("Not a boxed int");
}

int main() {
   String^ str = "test";
   Test(str);

   int n = 100;
   Test(n);
}
```

```Output
Not a boxed int
100
```

Dieses Beispiel zeigt, dass das allgemeine C++-Idiom zur Anwendung mit einer `void*` Zeiger auf ein beliebiges Objekt verweisen, wird durch ersetzt `Object^`, die ein Handle einer beliebigen Reference-Klasse enthalten kann. Es zeigt auch, dass sämtliche Typen, auch Arrays und Delegaten, in ein Objekthandle konvertiert werden können.

```cpp
// mcppv2_handle_3.cpp
// compile with: /clr
using namespace System;
using namespace System::Collections;
public delegate void MyDel();
ref class MyClass {
public:
   void Test() {}
};

void Test(Object ^ x) {
   Console::WriteLine("Type is {0}", x->GetType());
}

int main() {
   // handle to Object can hold any ref type
   Object ^ h_MyClass = gcnew MyClass;

   ArrayList ^ arr = gcnew ArrayList();
   arr->Add(gcnew MyClass);

   h_MyClass = dynamic_cast<MyClass ^>(arr[0]);
   Test(arr);

   Int32 ^ bi = 1;
   Test(bi);

   MyClass ^ h_MyClass2 = gcnew MyClass;

   MyDel^ DelInst = gcnew MyDel(h_MyClass2, &MyClass::Test);
   Test(DelInst);
}
```

```Output
Type is System.Collections.ArrayList

Type is System.Int32

Type is MyDel
```

Dieses Beispiel zeigt, dass ein Handle dereferenzierbar ist, und dass auf einen Member mit einem dereferenzierten Handle zugegriffen werden kann.

```cpp
// mcppv2_handle_4.cpp
// compile with: /clr
using namespace System;
value struct DataCollection {
private:
   int Size;
   array<String^>^ x;

public:
   DataCollection(int i) : Size(i) {
      x = gcnew array<String^>(Size);
      for (int i = 0 ; i < Size ; i++)
         x[i] = i.ToString();
   }

   void f(int Item) {
      if (Item >= Size)
      {
         System::Console::WriteLine("Cannot access array element {0}, size is {1}", Item, Size);
         return;
      }
      else
         System::Console::WriteLine("Array value: {0}", x[Item]);
   }
};

void f(DataCollection y, int Item) {
   y.f(Item);
}

int main() {
   DataCollection ^ a = gcnew DataCollection(10);
   f(*a, 7);   // dereference a handle, return handle's object
   (*a).f(11);   // access member via dereferenced handle
}
```

```Output
Array value: 7

Cannot access array element 11, size is 10
```

Dieses Beispiel zeigt, dass die ein systemeigenen Verweises (`&`) kann nicht gebunden werden ein **Int** Member eines verwalteten Typs, als die **Int** kann in Heaps mit Garbage collection gespeichert werden, und native Verweise nicht nachverfolgt. objektverschiebung im verwalteten Heap. Zur Behebung dieses Problems können Sie eine lokale Variable verwenden, oder ändern Sie `&` in `%`, um einen Nachverfolgungsverweis zu erhalten.

```cpp
// mcppv2_handle_5.cpp
// compile with: /clr
ref struct A {
   void Test(unsigned int &){}
   void Test2(unsigned int %){}
   unsigned int i;
};

int main() {
   A a;
   a.i = 9;
   a.Test(a.i);   // C2664
   a.Test2(a.i);   // OK

   unsigned int j = 0;
   a.Test(j);   // OK
}
```

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)<br/>
[Nachverfolgungsverweisoperator](../windows/tracking-reference-operator-cpp-component-extensions.md)
