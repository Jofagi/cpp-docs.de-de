---
title: Windows-Laufzeit und verwaltete Vorlagen (C++ / CLI und C++ / CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- templates, with CLR types
ms.assetid: cf59d16b-5514-448b-9a95-e0b4fcb616a6
ms.openlocfilehash: cbd66f3ddf41602f7ed9a73f3a334bb86f1f3705
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471473"
---
# <a name="windows-runtime-and-managed-templates-ccli-and-ccx"></a>Windows-Laufzeit und verwaltete Vorlagen (C++ / CLI und C++ / CX)

Vorlagen können Sie einen Prototyp der einer Windows-Runtime oder der common Language Runtime-Typ definieren, und klicken Sie dann mithilfe von verschiedenen Vorlagentypparameter instanziieren Variationen dieses Typs.

## <a name="all-runtimes"></a>Alle Laufzeiten

Sie können Vorlagen von Werttypen oder Referenztypen erstellen.  Weitere Informationen zum Erstellen von Werttypen oder Referenztypen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).

Weitere Informationen zu Standard-c++-Klassenvorlagen, finden Sie unter [Klassenvorlagen](../cpp/class-templates.md).

## <a name="windows-runtime"></a>Windows-Runtime

(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows-Runtime gelten.)

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

Es gibt einige Einschränkungen für das Erstellen von Klassenvorlagen von verwalteten Typen, die in den folgenden Codebeispielen veranschaulicht werden.

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Es ist möglich, das Instanziieren eines generischen Typs mit einem verwalteten Typ Template-Parameter, aber eine verwaltete Vorlage mit einem generischen Typparameter für die Vorlage kann nicht instanziiert werden. Dies ist, da es sich bei generische Typen zur Laufzeit aufgelöst werden. Weitere Informationen finden Sie unter [Generika und Vorlagen (C++ / CLI)](../windows/generics-and-templates-visual-cpp.md).

```cpp
// managed_templates.cpp
// compile with: /clr /c

generic<class T>
ref class R;

template<class T>
ref class Z {
   // Instantiate a generic with a template parameter.
   R<T>^ r;    // OK
};

generic<class T>
ref class R {
   // Cannot instantiate a template with a generic parameter.
   Z<T>^ z;   // C3231
};
```

Ein generischer Typ oder Funktion kann nicht in einer Vorlage für verwaltete geschachtelt werden.

```cpp
// managed_templates_2.cpp
// compile with: /clr /c

template<class T> public ref class R {
   generic<class T> ref class W {};   // C2959
};
```

Kann nicht auf Vorlagen definiert, die in einer referenzierten Assembly mit C++ / CLI-Language-Syntax, aber Sie können mithilfe von Reflektion. Wenn Sie eine Vorlage nicht instanziiert wird, wird es nicht in den Metadaten ausgegeben. Wenn Sie eine Vorlage instanziiert wird, werden nur auf die verwiesen wird Member-Funktionen in den Metadaten angezeigt.

```cpp
// managed_templates_3.cpp
// compile with: /clr

// Will not appear in metadata.
template<class T> public ref class A {};

// Will appear in metadata as a specialized type.
template<class T> public ref class R {
public:
   // Test is referenced, will appear in metadata
   void Test() {}

   // Test2 is not referenced, will not appear in metadata
   void Test2() {}
};

// Will appear in metadata.
generic<class T> public ref class G { };

public ref class S { };

int main() {
   R<int>^ r = gcnew R<int>;
   r->Test();
}
```

Sie können die verwalteten Modifizierer einer Klasse in eine teilweise Spezialisierung oder eine explizite Spezialisierung einer Klassenvorlage ändern.

```cpp
// managed_templates_4.cpp
// compile with: /clr /c

// class template
// ref class
template <class T>
ref class A {};

// partial template specialization
// value type
template <class T>
value class A <T *> {};

// partial template specialization
// interface
template <class T>
interface class A<T%> {};

// explicit template specialization
// native class
template <>
class A <int> {};
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)