---
title: /CGTHREADS (Compilerthreads)
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: 1c459604d90b23953bbf3f250708c393fa78277d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495107"
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (Compilerthreads)

Legt die Anzahl von cl.exe-Threads zur Verwendung für die Optimierung und Codegenerierung fest, wenn die Link-Zeitcodegenerierung angegeben ist.

## <a name="syntax"></a>Syntax

```
/CGTHREADS:[1-8]
```

## <a name="arguments"></a>Argumente

*Anzahl*<br/>
Die maximale Anzahl von Threads zur Verwendung für cl.exe, im Bereich von 1 bis 8.

## <a name="remarks"></a>Hinweise

Die **/cgthreads** Option gibt die maximale Anzahl von Threads cl.exe verwendet parallel an, für die Optimierung und codegenerierung Phasen der Kompilierung verwendet, wenn die Link-Time code Generation (["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md)) ist angegeben. Standardmäßig verwendet cl.exe vier Threads, als ob **/CGTHREADS:4** wurden angegeben. Wenn mehr Prozessorkerne verfügbar sind, kann ein höherer `number`-Wert die Builderstellung beschleunigen.

Für einen Build können mehrere Stufen der Parallelität angegeben werden. Der msbuild.exe-Switch **maxcpucount** gibt die Anzahl der MSBuild-Prozesse, die parallel ausgeführt werden können. Die [/MP (erstellen mit mehreren Prozessen)](../../build/reference/mp-build-with-multiple-processes.md) -Compilerflag gibt die Anzahl der cl.exe-Prozesse, die die Quelldateien gleichzeitig zu kompilieren. Die [/cgthreads](../../build/reference/cgthreads-code-generation-threads.md) Compileroption gibt die Anzahl der Threads, die von jedem cl.exe-Prozess verwendet. Da der Prozessor nur so viele Threads gleichzeitig ausführen kann, wie Prozessorkerne vorhanden sind, ist es nicht sinnvoll, größere Werte für all diese Optionen gleichzeitig anzugeben. Das kann sogar kontraproduktiv sein. Weitere Informationen zum Erstellen von Projekten parallel, finden Sie unter [Erstellen von mehreren Projekten gleichzeitig](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften**, **Linker** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Ändern der **zusätzliche Optionen** Eigenschaft sollen **/cgthreads:**`number`, wobei `number` ist ein Wert von 1 bis 8, und wählen Sie dann **OK**.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Linkeroptionen](../../build/reference/linker-options.md)<br/>
[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)