---
title: 'Vorgehensweise: Öffnen eine Ressourcenskriptdatei außerhalb eines C++-Projekts (eigenständig)'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
ms.openlocfilehash: 43b245c1d19e7468a9433473eb49dc970316eba5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529076"
---
# <a name="how-to-open-a-resource-script-file-outside-of-a-c-project-standalone"></a>Vorgehensweise: Öffnen eine Ressourcenskriptdatei außerhalb eines C++-Projekts (eigenständig)

Sie können Ressourcen in einer RC-Datei anzeigen, ohne dass ein Projekt geöffnet sein muss. Die RC-Datei wird geöffnet, in einem Dokumentfenster geöffnet, anstatt in der [Ressourcenansicht](../windows/resource-view-window.md) Fenster (wie dies der Fall ist, wenn die Datei innerhalb eines Projekts geöffnet ist).

> [!NOTE]
> Dies ist eine wichtige Unterscheidung, da einige Befehle nur verfügbar sind, wenn die Datei eigenständig (außerhalb eines Projekts) geöffnet wird. Beispielsweise Sie können nur eine Datei speichern in einem anderen Format oder als einen anderen Dateinamen an, wenn die Datei außerhalb eines Projekts geöffnet wird (die **speichern** Befehl ist nicht verfügbar, wenn eine Datei innerhalb eines Projekts geöffnet ist).

### <a name="to-open-an-rc-file-outside-a-project"></a>Öffnen einer RC-Datei außerhalb eines Projekts

1. Von der **Datei** Menü wählen **öffnen**, klicken Sie dann auf **Datei**.

2. In der **geöffnete Datei** Dialogfeld navigieren Sie zur Ressourcenskriptdatei, die Sie verwenden möchten, anzeigen, markieren Sie die Datei, und klicken Sie auf **öffnen**.

   > [!NOTE]
   > Wenn Sie das Projekt zuerst öffnen (**Datei**, **öffnen**, **Projekt**), einige Befehle werden nicht zur Verfügung. Eine Datei „eigenständig“ zu öffnen, bedeutet, sie zu öffnen, ohne erst das Projekt zu laden.

Öffnen und Anzeigen der Ressourcendatei im Textformat vorliegen, finden Sie unter [Bearbeiten einer Ressourcenskriptdatei (.rc) Datei](../windows/how-to-open-a-resource-script-file-in-text-format.md).

### <a name="to-open-multiple-rc-files-outside-a-project"></a>Öffnen mehrerer RC-Dateien außerhalb eines Projekts

1. Öffnen Sie beide Ressourcendateien eigenständig. Öffnen Sie z. B. `Source1.rc` und `Source2.rc`.

   1. Von der **Datei** Menü wählen **öffnen**, klicken Sie dann auf **Datei**.

   2. In der **Datei öffnen** Dialogfeld navigieren Sie zu den ersten Ressourcenskriptdatei, die Sie öffnen möchten (`Source1.rc`), markieren Sie die Datei, und klicken Sie auf **öffnen**.

   3. Wiederholen Sie den vorherigen Schritt zum Öffnen der zweiten RC-Datei (`Source2.rc`).

       Die RC-Dateien sind nun in separaten Dokumentfenstern geöffnet.

2. Wenn beide RC-Dateien geöffnet sind, ordnen Sie die Fenster so an, dass sie gleichzeitig angezeigt werden:

   - Von der **Fenster** Menü wählen **neue horizontale Registerkartengruppe** oder **neue vertikale Registerkartengruppe**.

       \- oder –

   - Mit der rechten Maustaste eine der RC-Dateien, und wählen Sie **neue horizontale Registerkartengruppe** oder **neue vertikale Registerkartengruppe** aus dem Kontextmenü.

> [!NOTE]
> Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)