---
title: 'Gewusst wie: Anzeigen von Befehlsinformationen in der Statusleiste'
ms.date: 11/04/2016
helpviewer_keywords:
- prompts [MFC]
- displaying command status [MFC]
- status bars [MFC], message area
- status bars [MFC], displaying command information
ms.assetid: de895cbe-61ee-46bf-9787-76b247527d6d
ms.openlocfilehash: 6da45edf611d70920340d8f9a9c2fd8de5cc0307
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654102"
---
# <a name="how-to-display-command-information-in-the-status-bar"></a>Gewusst wie: Anzeigen von Befehlsinformationen in der Statusleiste

Wenn Sie den Assistenten zum Erstellen des Grundgerüsts Ihrer Anwendung ausführen, können Sie eine Symbolleiste und Statusleiste unterstützen. Nur eine Option im Anwendungs-Assistenten unterstützt. Wenn eine Statusleiste vorhanden ist, stellt der Anwendung automatisch hilfreiche Hinweise, wie der Benutzer den Zeiger auf Elemente in den Menüs richtet. Die Anwendung zeigt automatisch eine eingabeaufforderungs-Zeichenfolge in der Statusleiste angezeigt, wenn das Menüelement markiert ist. Z. B. wenn der Benutzer den Mauszeiger auf Bewegen der **Ausschneiden** Befehl die **bearbeiten** im Menü die Statusleiste möglicherweise "Schneidet die Auswahl und überträgt sie in der Zwischenablage" in den Bereich der Statusleiste angezeigt. Die Eingabeaufforderung hilft die Benutzer, die den Zweck des Menüelements zu verstehen. Dies funktioniert auch, wenn der Benutzer eine Symbolleisten-Schaltfläche klickt.

Sie können in dieser Hilfe mit der Statusleiste hinzufügen, durch die Definition des eingabeaufforderungs-Zeichenfolgen für Menüelemente, die Sie die Anwendung hinzu. Zu diesem Zweck geben Sie die eingabeaufforderungs-Zeichenfolgen, wenn Sie die Eigenschaften des Menüelements im Menü-Editor bearbeiten. Die Zeichenfolgen, die Sie definieren, werden in der Ressourcendatei der Anwendung gespeichert. Sie haben die gleichen IDs wie die Befehle, die sie erläutern.

Standardmäßig fügt der Anwendungs-Assistent **AFX_IDS_IDLEMESSAGE**, die ID für eine "Ready" Standardnachricht, die angezeigt wird, wenn das Programm auf neue Nachrichten wartet. Wenn Sie die Option kontextbezogene Hilfe im Anwendungs-Assistenten angeben, wird die Nachricht geändert auf "Hilfe, F1 drücken."

## <a name="see-also"></a>Siehe auch

[Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

