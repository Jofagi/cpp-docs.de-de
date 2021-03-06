---
title: interior_ptr (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- stdcli::language::interior_ptr
- interior_ptr_cpp
- interior_ptr
helpviewer_keywords:
- interior_ptr keyword [C++]
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
ms.openlocfilehash: 05ae4aeba3761ccb0abeb8c3722d9ddf932bee5a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443081"
---
# <a name="interiorptr-ccli"></a>interior_ptr (C++/CLI)

Ein *innerer Zeiger* deklariert einen Zeiger auf die in einen Verweistyp handelt, aber nicht auf das Objekt selbst. Ein innerer Zeiger kann mit Verweis-Handle, Werttyp, geschachtelte Typhandle, Member eines verwalteten Typs oder auf ein Element eines verwalteten Arrays verweisen.

## <a name="all-runtimes"></a>Alle Laufzeiten

(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.)

## <a name="windows-runtime"></a>Windows-Runtime

(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows-Runtime gelten.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

Im folgenden Syntaxbeispiel wird veranschaulicht, einen inneren Zeiger.

### <a name="syntax"></a>Syntax

```cpp
cli::interior_ptr<cv_qualifier type> var = &initializer;
```

### <a name="parameters"></a>Parameter

*cv_qualifier*<br/>
**const** oder **flüchtige** Qualifizierer.

*Typ*<br/>
Der Typ des *Initialisierer*.

*var*<br/>
Der Name des der **Interior_ptr** Variable.

*initializer*<br/>
Ein Member eines Verweistyps, Element eines verwalteten Arrays oder jedes andere Objekt, das Sie in einen systemeigenen Zeiger zuweisen können.

### <a name="remarks"></a>Hinweise

Ein systemeigenen Zeiger kann nicht aus, um ein Element als seine Änderungen am Speicherort auf dem verwalteten Heap, nachzuverfolgen, die führt durch den Garbage Collector Instanzen eines Objekts verschieben. In der Reihenfolge für einen Zeiger, um ordnungsgemäß auf die Instanz zu verweisen muss die Runtime den Zeiger auf das Objekt neu positioniert zu aktualisieren.

Ein **Interior_ptr** eine Obermenge der Funktionen der einen systemeigenen Zeiger darstellt.  Aus diesem Grund Elemente, die in einen systemeigenen Zeiger zugewiesen werden, kann auch zugewiesen werden ein **Interior_ptr**.  Ein innerer Zeiger ist zulässig, um den gleichen Satz von Vorgängen wie systemeigene Zeiger, einschließlich Vergleich und Zeigerarithmetik auszuführen.

Ein innerer Zeiger kann nur auf dem Stapel deklariert werden.  Ein innerer Zeiger kann nicht als Member einer Klasse deklariert werden.

Da innere Zeigern nur auf dem Stapel vorhanden sind, ergibt das Übernehmen der Adresse einen inneren Zeiger einen nicht verwalteten Zeiger.

**Interior_ptr** verfügt über eine implizite Konvertierung in **"bool"**, wodurch für die Verwendung in bedingten Anweisungen.

Informationen dazu, wie einen inneren Zeiger deklariert, die in ein Objekt verweist, die auf dem Heap der Garbage Collection nicht verschoben werden können, finden Sie unter [Pin_ptr](../windows/pin-ptr-cpp-cli.md).

**Interior_ptr** befindet sich in der Cli-Namespace.  Finden Sie unter [Platform-, Default- und Cli-Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) für Weitere Informationen.

Weitere Informationen zu inneren Zeigern finden Sie unter

- [Vorgehensweise: Deklarieren und Verwenden von inneren Zeigern und verwalteten Arrays (C++/CLI)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)

- [Vorgehensweise: Deklarieren von Werttypen mit dem interior_ptr-Schlüsselwort (C++/CLI)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)

- [Vorgehensweise: Überladen von Funktionen mit inneren und nativen Zeigern (C++/CLI)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)

- [Vorgehensweise: Deklarieren von inneren Zeigern mit dem const-Schlüsselwort (C++/CLI)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt, wie Sie deklarieren und Verwenden eines inneren Zeigers in einen Verweistyp handelt.

```cpp
// interior_ptr.cpp
// compile with: /clr
using namespace System;

ref class MyClass {
public:
   int data;
};

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   h_MyClass->data = 1;
   Console::WriteLine(h_MyClass->data);

   interior_ptr<int> p = &(h_MyClass->data);
   *p = 2;
   Console::WriteLine(h_MyClass->data);

   // alternatively
   interior_ptr<MyClass ^> p2 = &h_MyClass;
   (*p2)->data = 3;
   Console::WriteLine((*p2)->data);
}
```

```Output
1
2
3
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)