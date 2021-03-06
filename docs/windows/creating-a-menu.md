---
title: Erstellen eines Menüs (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.menu
helpviewer_keywords:
- mnemonics [C++], associating menu items
- menus [C++], associating commands with mnemonic keys
- menus [C++], creating
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
ms.openlocfilehash: b779e6b089410b818247471086fe987c37b1f36c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518555"
---
# <a name="creating-a-menu-c"></a>Erstellen eines Menüs (C++)

> [!NOTE]
> Die **Ressourcen-Fenster** ist in Express-Editionen nicht verfügbar.

### <a name="to-create-a-standard-menu"></a>So erstellen Sie ein Standardmenü

1. Klicken Sie im Menü **Ansicht** auf **Ressourcenansicht** und klicken Sie mit der rechten Maustaste auf die Überschrift **Menü** , und wählen Sie **Ressource hinzufügen**aus. Wählen Sie **Menü**aus.

2. Wählen Sie auf der Menüleiste das Feld **Neues Element** (das Rechteck mit dem Text "Hier eingeben") aus.

   ![Feld "Neues Element" im Menü-Editor](../windows/media/vcmenueditornewitembox.gif "VcMenuEditorNewItemBox")<br/>
   Feld "Neues Element"

3. Geben Sie einen Namen für das neue Menü ein, z. B. "Datei".

   Der eingegebene Text wird sowohl im **Menü** -Editor als auch im Feld **Beschriftung** im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)angezeigt. Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.

   Nachdem Sie das neue Menü in der Menüleiste benannt haben, rückt das Feld für das neue Menüelement nach rechts (damit ein weiteres Menü eingefügt werden kann). Unter dem ersten Menü wird ein weiteres Feld geöffnet, dem Sie Menübefehle hinzufügen können.

   ![Erweiterte neue Elementfeld](../windows/media/vcmenueditornewitemboxexpanded.gif "VcMenuEditorNewItemBoxExpanded")<br/>
   Feld "Neues Element", dessen Fokus nach der Eingabe des Menünamens versetzt wurde

   > [!NOTE]
   > Um ein einzelnes Element im Menü auf der Menüleiste zu erstellen, legen die **Popup** Eigenschaft **"false"**.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)