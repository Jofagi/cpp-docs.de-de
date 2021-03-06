---
title: Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente (C++)
ms.date: 06/28/2018
helpviewer_keywords:
- Dialog Editor [C++], adding event handlers to controls
- controls [C++], event handlers
- dialog box controls [C++], events
- event handlers, for dialog box controls
ms.assetid: f9c70f24-ea6f-44df-82eb-78a2deaee769
ms.openlocfilehash: e6539b7e0f8ab4d0b1b60ecfbd80685473534316
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487177"
---
# <a name="adding-event-handlers-for-dialog-box-controls-c"></a>Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente (C++)

Für Project-Dialogfelder, die bereits von einer Klasse zugeordnet sind, können Sie nutzen einige Verknüpfungen bei der Erstellung von Ereignishandlern. Sie können schnell einen Handler für das Standardereignis des Steuerelements Benachrichtigung oder für eine relevante Windows-Meldung erstellen.

### <a name="to-create-a-handler-for-the-default-control-notification-event"></a>Um einen Handler für das Standardereignis des Steuerelements Benachrichtigung zu erstellen.

1. Doppelklicken Sie auf das Steuerelement. Die **Text** -Editor wird geöffnet.

2. Hinzufügen des Steuerelements Handlercode für Benachrichtigungen in der **Text** Editor.

### <a name="to-create-a-handler-for-any-applicable-windows-message"></a>So erstellen Sie einen Ereignishandler für eine relevante Windows-Meldung

1. Klicken Sie auf das Steuerelement für das Benachrichtigungsereignis verarbeitet werden sollen.

2. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), klicken Sie auf die **Steuerelementereignisse** Schaltfläche, um die Liste der allgemeinen Windows-Ereignisse, die dem Steuerelement zugeordnete anzuzeigen. Z. B. der Standard **OK** Schaltfläche der **zu** Dialogfeld werden die folgenden Benachrichtigungsereignisse aufgelistet:

   - BN_CLICKED

   - BN_DOUBLECLICKED

   - BN_KILLFOCUS

   - BN_SETFOCUS

   > [!NOTE]
   > Alternativ können Sie das Dialogfeld "auswählen", und klicken Sie auf die **Steuerelementereignisse** Schaltfläche, um die Liste der allgemeinen Windows-Ereignisse für alle Steuerelemente im Dialogfeld anzuzeigen.

3. In der **Eigenschaften** , klicken Sie auf der rechten Spalte neben der zu behandelnden Ereignisses, und wählen Sie dann den vorgeschlagenen Namen Benachrichtigungsereignis (z. B. `OnBnClickedOK` BN_CLICKED behandelt).

   > [!NOTE]
   > Alternativ können Sie einen Ereignishandlernamen Ihrer Wahl, statt die Auswahl der standardmäßigen Ereignishandlernamen bereitstellen.

   Nachdem Sie das Ereignis ausgewählt haben, öffnet Visual Studio die **Text-Editor** und den Ereignishandler Code angezeigt. Beispielsweise wird der folgende Code hinzugefügt, für den standardmäßigen `OnBnClickedOK`:

    ```cpp
    void CAboutDlg::OnBnClickedOk(void)
    {
        // TODO: Add your control notification handler code here
    }
    ```

Wenn Sie verwenden möchten, fügen den Ereignishandler auf eine Klasse als diejenige implementieren Sie das Dialogfeld, verwenden Sie die [Ereignishandler-Assistent](../ide/event-handler-wizard.md). Weitere Informationen finden Sie unter [Hinzufügen eines Ereignishandlers](../ide/adding-an-event-handler-visual-cpp.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Standardereignisse für Steuerelemente](../windows/default-control-events.md)<br/>
[Definieren von Membervariablen für Dialogfeld-Steuerelemente](../windows/defining-member-variables-for-dialog-controls.md)<br/>
[Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)<br/>
[Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)<br/>
[Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)<br/>
[Adding a Member Variable (Hinzufügen einer Membervariablen)](../ide/adding-a-member-variable-visual-cpp.md)<br/>
[Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)<br/>
[MFC Message Handler (MFC-Meldungshandler)](../mfc/reference/adding-an-mfc-message-handler.md)