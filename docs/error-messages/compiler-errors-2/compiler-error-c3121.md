---
title: Compilerfehler C3121
ms.date: 11/04/2016
f1_keywords:
- C3121
helpviewer_keywords:
- C3121
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
ms.openlocfilehash: cd8f23a3edbdee4dc4edc294494cb9d73cf6b998
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561394"
---
# <a name="compiler-error-c3121"></a>Compilerfehler C3121

GUID kann nicht für die Klasse 'Klassenname' geändert werden.

Sie haben versucht, ändern Sie die Klassen-ID mit [__declspec(uuid)](../../cpp/uuid-cpp.md).

Der folgende Code wird z. B. C3121 generiert:

```
// C3121.cpp
[emitidl];
[module(name="MyLibrary")];

[coclass, uuid="00000000-0000-0000-0000-111111111111"]
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121
{
};
int main()
{
}
```