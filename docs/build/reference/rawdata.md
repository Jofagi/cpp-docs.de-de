---
title: /RAWDATA
ms.date: 11/04/2016
f1_keywords:
- /rawdata
helpviewer_keywords:
- RAWDATA dumpbin option
- raw data
- -RAWDATA dumpbin option
- /RAWDATA dumpbin option
ms.assetid: 41cba845-5e1f-415e-9fe4-604a52235983
ms.openlocfilehash: 91fa1e26ca159f23c848efc6bf46afdea2a8bc52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621480"
---
# <a name="rawdata"></a>/RAWDATA

```
/RAWDATA[:{1|2|4|8|NONE[,number]]
```

## <a name="remarks"></a>Hinweise

Diese Option zeigt die unformatierten Inhalt jedes Abschnitts in der Datei. Die Argumente zum Steuern der Anzeige, wie unten dargestellt:

|Argument|Ergebnis|
|--------------|------------|
|1|Der Standardwert. Inhalt wird angezeigt, in hexadezimale Bytes und auch als ASCII-Zeichen, wenn sie eine gedruckte Darstellung verfügen.|
|2|Inhalte werden als hexadezimale 2-Byte-Werte angezeigt.|
|4|Inhalte werden als hexadezimale 4-Byte-Werte angezeigt.|
|8|Inhalte werden als hexadezimale 8-Byte-Werte angezeigt.|
|KEINE|Rohdaten werden unterdrückt. Dieses Argument ist hilfreich, um die Ausgabe der steuern/ALL.|
|*Zahl*|Angezeigten Zeilen werden festgelegt, auf eine Breite, die enthält `number` Werte pro Zeile.|

Nur die [/Headers](../../build/reference/headers.md) DUMPBIN-Option ist verfügbar für die Verwendung in Dateien mit der ["/ GL"](../../build/reference/gl-whole-program-optimization.md) -Compileroption.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)