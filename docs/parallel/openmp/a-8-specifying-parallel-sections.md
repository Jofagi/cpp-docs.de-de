---
title: A.8   Angeben von parallelen Abschnitten
ms.date: 11/04/2016
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
ms.openlocfilehash: 81eaed920e77b23052ac58c2d0e18fee83c00565
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461437"
---
# <a name="a8---specifying-parallel-sections"></a>A.8   Angeben von parallelen Abschnitten

Im folgenden Beispiel (für [Abschnitt 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) auf 14) Funktionen *x-Achse enthält*, *Yaxis*, und *Zaxis* gleichzeitig ausgeführt werden können. Die erste `section` Richtlinie ist optional.  Beachten Sie, dass alle `section` Anweisungen müssen in der lexikalischen Wertebereich angezeigt werden die `parallel sections` zu erstellen.

```
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```