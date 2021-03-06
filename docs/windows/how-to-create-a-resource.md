---
title: 'Vorgehensweise: Erstellen einer Ressource (C++)'
ms.date: 11/04/2016
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
ms.openlocfilehash: 75f7f722b354e60b86abdeb9a3f9a01469aefcf8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513691"
---
# <a name="how-to-create-a-resource"></a>Gewusst wie: Erstellen einer Ressource

> [!NOTE]
> **Ressourcenansicht** wird in Express-Editionen nicht unterstützt.

### <a name="to-create-a-new-resource-in-resource-view"></a>So erstellen Sie eine neue Ressource in der Ressourcenansicht

1. Mit dem Schwerpunkt auf die RC-Datei in [Ressourcenansicht](../windows/resource-view-window.md), klicken Sie auf die **bearbeiten** Menü, und wählen Sie **Ressource hinzufügen** (oder mit der rechten Maustaste in der RC-Datei **Ressourcenansicht** , und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md)den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.

### <a name="to-create-a-new-resource-in-solution-explorer"></a>So erstellen Sie eine neue Ressource im Projektmappen-Explorer

1. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektordner, und wählen Sie **Hinzufügen**aus. Klicken Sie dann im Kontextmenü auf **Ressource hinzufügen** .

   Wenn im Projekt noch keine RC-Datei vorhanden ist, wird mit diesem Schritt eine erstellt. Anschließend können Sie diesen Schritt wiederholen, um der neuen RC-Datei spezifische Ressourcentypen hinzuzufügen.

2. Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md)den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.

### <a name="to-create-a-new-resource-in-class-view"></a>So erstellen Sie eine neue Ressource in der Klassenansicht

1. Klicken Sie in der [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code)mit der rechten Maustaste auf die Klasse, und wählen Sie **Hinzufügen**aus. Klicken Sie dann im Kontextmenü auf **Ressource hinzufügen** .

2. Wählen Sie im [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md)den Ressourcentyp aus, den Sie dem Projekt hinzufügen möchten.

### <a name="to-create-a-new-resource-from-the-project-menu"></a>So erstellen Sie eine neue Ressource über das Menü "Projekt"

1. Wählen Sie im Menü **Projekt** den Befehl **Ressource hinzufügen**aus.

Wenn Sie eine neue Ressource erstellen, Visual C++ weist einen eindeutigen Namen, z. B. `IDD_Dialog1`. Sie können diese Ressourcen-ID anpassen, indem Sie die Ressourceneigenschaften entweder im zugehörigen Ressourcen-Editor oder im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)bearbeiten.

Eine Ressource kann entweder als neue Standardressource (die auf keiner Vorlage basiert) oder als Ressource erstellt werden, die von einer [Vorlage](../windows/how-to-use-resource-templates.md)erstellt wurde.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Add Resource Dialog Box](../windows/add-resource-dialog-box.md)