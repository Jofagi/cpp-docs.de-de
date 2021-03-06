---
title: / Useprofile wurde (Verwendung von PGO-Daten mit LTCG)
ms.date: 03/14/2018
f1_keywords:
- USEPROFILE
ms.openlocfilehash: 4b780bed3b92b874f2bf18fb0235e8e2baf95ae9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550630"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/ Useprofile wurde (PGO im abgesicherten Threadmodus ausgeführt)

Diese Linkeroption zusammen mit [/LTCG (Link-zeitcodegenerierung](ltcg-link-time-code-generation.md) weist den Linker erstellen, indem Sie mithilfe von Trainingsdaten für die profilgesteuerte Optimierung (PGO).

## <a name="syntax"></a>Syntax

> **/ Useprofile wurde**[**:**{**AGGRESSIVES**|**PGD =**_Filename_}]

### <a name="arguments"></a>Argumente

**AGGRESSIVE**<br/>
Dieses optionale Argument gibt an, dass aggressive geschwindigkeitsoptimierungen während der Generierung von optimiertem Code verwendet werden soll.

**PGD**=*Dateiname*<br/>
Gibt einen Basisdateinamen für die PGD-Datei an. Standardmäßig verwendet der Linker den Basisdateinamen für ausführbare Datei mit der Erweiterung PGD.

## <a name="remarks"></a>Hinweise

Die **/USERPROFILE angegeben** Linkeroption dient zusammen mit **"/ LTCG"** generieren oder einen optimierten Build basierend auf der PGO-Trainingsdaten aktualisieren. Dies entspricht der veralteten **/LTCG: PGUPDATE** und **/LTCG: PGOPTIMIZE** Optionen.

Der optionale **AGGRESSIVES** Argument deaktiviert hinsichtlich der Größe Heuristik, um zu versuchen, die Geschwindigkeit zu optimieren. Dies kann in Optimierungen führen, die im Wesentlichen erhöhen Sie die Größe Ihrer ausführbaren Datei, und kann die resultierende Geschwindigkeit nicht erhöhen. Sie sollten ein Profil, und vergleichen Sie die Ergebnisse der Verwendung von und nicht mit **AGGRESSIVES**. Dieses Argument muss explizit angegeben werden; Es ist nicht standardmäßig aktiviert.

Die **PGD** Argument gibt einen optionalen Namen für die Schulung Daten PGD-Datei zu verwenden, entspricht der Vorgehensweise in [/genprofile oder/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md). Dies entspricht der veralteten **/PGD** wechseln. Standardmäßig oder wenn keine *Filename* angegeben wird, eine PGD-Datei, die den gleichen Basisnamen wie die ausführbare Datei verwendet wird.

Die **/USERPROFILE angegeben** Linkeroption ist neu in Visual Studio 2015.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Optimierung** Eigenschaftenseite.

1. In der **Link-Zeitcodegenerierung** Eigenschaft wählen **Link-Zeitcodegenerierung verwenden (/ LTCG)**.

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/USERPROFILE angegeben** Option und optionalen Argumenten in der **zusätzliche Optionen** Feld. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/ GENPROFILE und/fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profilgesteuerte Optimierungen](../../build/reference/profile-guided-optimizations.md)<br/>
[Umgebungsvariablen für profilgesteuerte Optimierungen](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
