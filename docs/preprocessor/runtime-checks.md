---
title: runtime_checks
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: 38df7ccc384830bb547c11e1a3d5458a1298574c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547367"
---
# <a name="runtimechecks"></a>runtime_checks
Dient der Deaktivierung oder Wiederherstellung der [/RTC](../build/reference/rtc-run-time-error-checks.md) -Einstellungen.

## <a name="syntax"></a>Syntax

```
#pragma runtime_checks( "[runtime_checks]", {restore | off} )
```

## <a name="remarks"></a>Hinweise

Sie können nur Laufzeitüberprüfungen aktivieren, die mit einer Compileroption aktiviert wurden. Angenommen, Sie nicht angeben `/RTCs`Angabe `#pragma runtime_checks( "s", restore)` wird die Überprüfung der Stapelrahmen nicht aktiviert.

Das **runtime_checks** -Pragma muss außerhalb der Funktion angezeigt werden und tritt für die erste definierte Funktion in Kraft, nachdem das Pragma sichtbar ist. Die Argumente *restore* und *off* schalten die in **runtime_checks** angegebenen Optionen ein oder aus.

Die Option **runtime_checks** kann leer sein oder mehrere Parameter aus der folgenden Tabelle enthalten.

### <a name="parameters-of-the-runtimechecks-pragma"></a>Parameter des runtime_checks-Pragmas

|Parameter|Typ der Laufzeitüberprüfung|
|--------------------|-----------------------------|
|*s*|Aktiviert die Überprüfung des Stapels (Frames).|
|*c*|Meldet die Zuweisung eines Werts zu einem kleineren Datentyp, der zu einem Datenverlust führt.|
|*n*|Zeigt an, wenn eine Variable verwendet wird, bevor sie definiert ist.|

Hierbei handelt es sich um dieselben Buchstaben verwendet werden, mit der `/RTC` -Compileroption. Zum Beispiel:

```
#pragma runtime_checks( "sc", restore )
```

Verwenden des **runtime_checks** -Pragmas mit einer leeren Zeichenfolge (**""**) ist eine besondere Form der Direktive:

- Wenn Sie den Parameter *off* verwenden, werden die in der vorstehenden Tabelle aufgeführten Laufzeitfehlerüberprüfungen deaktiviert.

- Bei Verwendung der *wiederherstellen* Parameter, die Laufzeitfehler-Überprüfungen auf die zurückgesetzt, die Sie angegeben haben, mit der `/RTC` -Compileroption.

```
#pragma runtime_checks( "", off )
.
.
.
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)