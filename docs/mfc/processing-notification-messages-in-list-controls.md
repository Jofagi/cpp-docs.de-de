---
title: Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen
ms.date: 11/04/2016
helpviewer_keywords:
- processing notifications [MFC]
- CListCtrl class [MFC], processing notifications
ms.assetid: 1f0e296e-d2a3-48fc-ae38-51d7fb096f51
ms.openlocfilehash: 427abe5259334588b566656abd70acf22b923809
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490089"
---
# <a name="processing-notification-messages-in-list-controls"></a>Verarbeiten von Benachrichtigungsmeldungen in Listensteuerelementen

Wenn Benutzer auf die Spaltenüberschriften klicken, ziehen Sie Symbole, Bearbeiten von Bezeichnungen und So weiter, das Strukturelement-Steuerelement ([CListCtrl](../mfc/reference/clistctrl-class.md)) sendet benachrichtigungsmeldungen an das übergeordnete Fenster. Behandeln Sie diese Nachrichten, wenn Sie darauf reagieren möchten. Z. B. wenn der Benutzer auf eine Spaltenüberschrift klickt, empfiehlt zum Sortieren der Elemente, die basierend auf dem Inhalt dieser Spalte, wie Microsoft Outlook.

Prozess WM_NOTIFY-Meldungen im Listensteuerelement in Ihrer Klasse Ansichts- oder Dialogfeldobjekt. Verwenden Sie das Fenster "Eigenschaften" zum Erstellen einer [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) Handlerfunktion mit einer Switch-Anweisung basierend auf der Nachricht behandelt wird.

Eine Liste mit den Benachrichtigungen, die einem Steuerelement an das übergeordnete Fenster senden kann, finden Sie unter [Liste Ansicht Steuerelementverweis](/windows/desktop/Controls/list-view-control-reference) im Windows SDK.

## <a name="see-also"></a>Siehe auch

[Verwenden von CListCtrl](../mfc/using-clistctrl.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

