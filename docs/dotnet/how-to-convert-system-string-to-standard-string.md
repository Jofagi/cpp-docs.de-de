---
title: 'Gewusst wie: Konvertieren von System::String zu Standardzeichenfolge'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, converting System::String to standard string
- string conversion, System::String
ms.assetid: 79e2537e-d4eb-459f-9506-0e738045b59e
ms.openlocfilehash: fafd23cb9dec25c742e040fad0793c38bd092322
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473229"
---
# <a name="how-to-convert-systemstring-to-standard-string"></a>Gewusst wie: Konvertieren von System::String zu Standardzeichenfolge

Sie können einen <xref:System.String> in `std::string` oder `std::wstring` konvertieren, ohne `PtrToStringChars` in Vcclr.h zu verwenden.

## <a name="example"></a>Beispiel

```
// convert_system_string.cpp
// compile with: /clr
#include <string>
#include <iostream>
using namespace std;
using namespace System;

void MarshalString ( String ^ s, string& os ) {
   using namespace Runtime::InteropServices;
   const char* chars =
      (const char*)(Marshal::StringToHGlobalAnsi(s)).ToPointer();
   os = chars;
   Marshal::FreeHGlobal(IntPtr((void*)chars));
}

void MarshalString ( String ^ s, wstring& os ) {
   using namespace Runtime::InteropServices;
   const wchar_t* chars =
      (const wchar_t*)(Marshal::StringToHGlobalUni(s)).ToPointer();
   os = chars;
   Marshal::FreeHGlobal(IntPtr((void*)chars));
}

int main() {
   string a = "test";
   wstring b = L"test2";
   String ^ c = gcnew String("abcd");

   cout << a << endl;
   MarshalString(c, a);
   c = "efgh";
   MarshalString(c, b);
   cout << a << endl;
   wcout << b << endl;
}
```

```Output
test
abcd
efgh
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)