---
title: /LN (Erstellen eines MSIL-Moduls)
ms.date: 11/04/2016
f1_keywords:
- /LN
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
ms.openlocfilehash: d8253dacbfa57f84a3eee05ffa0f8f9879f6b009
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536928"
---
# <a name="ln-create-msil-module"></a>/LN (Erstellen eines MSIL-Moduls)

Legt fest, dass ein Assemblymanifest nicht in die Ausgabedatei eingefügt wird.

## <a name="syntax"></a>Syntax

```
/LN
```

## <a name="remarks"></a>Hinweise

In der Standardeinstellung **/ln** ist nicht aktiv (ein Assemblymanifest wird in die Ausgabedatei eingefügt).

Wenn **/ln** verwendet wird, eines der [/CLR (Common Language Runtime Compilation)](../../build/reference/clr-common-language-runtime-compilation.md) Optionen müssen auch verwendet werden.

Ein verwaltetes Programm, das keine Assemblymetadaten im Manifest aufweist, wird ein Modul aufgerufen. Bei der Kompilierung mit [/c (Kompilieren ohne Verknüpfen)](../../build/reference/c-compile-without-linking.md) und **/ln**, geben Sie [/NOASSEMBLY (MSIL-Modul erstellen)](../../build/reference/noassembly-create-a-msil-module.md) in der Linkerphase ein, um die Ausgabedatei zu erstellen.

Möglicherweise möchten die Module zu erstellen, wenn ein komponentenbasierter Ansatz zum Erstellen von Assemblys werden sollen.  D. h. können Typen erstellen und diese in Module kompilieren.  Anschließend können Sie eine Assembly über ein oder mehrere Module generieren.  Weitere Informationen zum Erstellen von Assemblys aus Modulen finden Sie unter [NETMODULE-Dateien als Linkereingabe](../../build/reference/netmodule-files-as-linker-input.md) oder [Al.exe (Assembly Linker)](/dotnet/framework/tools/al-exe-assembly-linker).

Die standarddateierweiterung für ein Modul ist "netmodule".

In Visual C++-Versionen vor Visual C++ 2005, ein Modul erstellt wurde, mit **/CLR: noAssembly**.

Visual C++-Linker NETMODULE-Dateien als Eingabe akzeptiert und die vom Linker generierte Ausgabedatei ist eine Assembly oder eine NETMODULE-Datei mit keine Abhängigkeit zur Laufzeit auf die NETMODULE-Dateien, die an den Linker eingegeben wurden.  Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

- Geben Sie [/NOASSEMBLY (MSIL-Modul erstellen)](../../build/reference/noassembly-create-a-msil-module.md) in der Linkerphase ein, um die Ausgabedatei zu erstellen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Diese Compileroption kann nicht programmgesteuert geändert werden.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)