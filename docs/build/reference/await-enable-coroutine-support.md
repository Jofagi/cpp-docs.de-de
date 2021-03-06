---
title: / await (coroutineunterstützung aktivieren)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: e3f7359b60e1ba22c2646cecfd35b827919ae033
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590431"
---
# <a name="await-enable-coroutine-support"></a>/ await (coroutineunterstützung aktivieren)

Verwenden der **"/ await"** -Compileroption verwenden, um die Compiler-Unterstützung für Coroutinen zu aktivieren.

## <a name="syntax"></a>Syntax

> "/ await"

## <a name="remarks"></a>Hinweise

Die **"/ await"** -Compileroption ermöglicht das Compiler-Unterstützung für C++-Coroutinen und die Schlüsselwörter **Co_await**, **Co_yield**, und **Co_return**. Diese Option ist standardmäßig deaktiviert. Weitere Informationen zur Unterstützung für Coroutinen in Visual Studio finden Sie unter den [Visual Studio-Team-Blog](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Weitere Informationen zu den standardmäßigen Vorschlag von Coroutinen, finden Sie unter [N4628 Arbeitsentwurf, technische Spezifikation für die C++-Erweiterungen für Coroutinen](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf).

Die **"/ await"** Option ist ab, die in Visual Studio 2015 verfügbar.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen des Projekts **Eigenschaftenseiten** Dialogfeld.

1. Unter **Konfigurationseigenschaften**, erweitern Sie die **C/C++-** Ordner, und wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **"/ await"** -Compileroption in der **zusätzliche Optionen** Feld. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
