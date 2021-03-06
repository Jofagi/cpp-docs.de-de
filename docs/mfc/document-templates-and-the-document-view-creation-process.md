---
title: Dokumentvorlagen und der Dokument-/-Erstellungsvorgang
ms.date: 11/19/2018
helpviewer_keywords:
- icons, for multiple document templates
- document templates [MFC], and views
- document/view architecture [MFC], creating document/view
- single document template
- MFC, document templates
- multiple document template
- CDocTemplate class [MFC]
- templates [MFC], document templates
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
ms.openlocfilehash: 29575166a188b0691465bef0a72810d2e3d97624
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52174882"
---
# <a name="document-templates-and-the-documentview-creation-process"></a>Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten

Zum Verwalten komplexen Prozess, der Erstellen von Dokumenten mit ihren zugehörigen Ansichten und Rahmenfenster das Framework verwendet zwei Dokumentvorlagenklassen: [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) für SDI-Anwendungen und [CMultiDocTemplate ](../mfc/reference/cmultidoctemplate-class.md) für MDI-Anwendungen. Ein `CSingleDocTemplate` erstellen und speichern Sie ein Dokument eines bestimmten Typs zu einem Zeitpunkt. Ein `CMultiDocTemplate` behält eine Liste der vielen geöffneten Dokumente eines bestimmten Typs.

Einige Anwendungen unterstützen mehrere Dokumenttypen. Eine Anwendung kann z. B. Textdokumente und Dokumente mit Grafiken unterstützen. Wenn der Benutzer den neuen Befehl im Menü Datei auswählt, zeigt ein Dialogfeld in einer solchen Anwendung eine Liste der neuen Dokumenttypen zu öffnen. Für jeden unterstützten Dokumenttyp verwendet die Anwendung ein individuelles Dokument Template-Objekt. Die folgende Abbildung veranschaulicht die Konfiguration des MDI-Anwendung, die unterstützt zwei Typen von Dokumenten und mehrere offene Dokumente anzeigt.

![MDI-Anwendung mit zwei Dokumenttypen](../mfc/media/vc387h1.gif "MDI-Anwendung mit zwei Dokumenttypen") <br/>
MDI-Anwendung mit zwei Dokumenttypen

Dokumentvorlagen erstellt und verwaltet werden, durch das-Objekt. Einer der wesentlichen Aufgaben ausgeführt, während Ihrer Anwendungsverzeichnis `InitInstance` Funktion besteht darin, eine oder mehrere Dokumentvorlagen des entsprechenden Typs zu erstellen. Dieses Feature finden Sie im [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md). Das Anwendungsobjekt speichert einen Zeiger auf jede Dokumentvorlage in der Vorlagenliste und stellt eine Schnittstelle für das Hinzufügen von Dokumentvorlagen.

Wenn Sie zwei oder mehr Dokumenttypen unterstützen müssen, müssen Sie einen zusätzlichen Aufruf hinzufügen [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) für jeden Dokumenttyp.

Ein Symbol wird für jede Dokumentvorlage basierend auf seiner Position in der Anwendung des Dokumentvorlagen registriert. Die Reihenfolge der Dokumentationsvorlagen richtet sich nach der Reihenfolge, werden sie durch Aufrufe hinzugefügt `AddDocTemplate`. MFC wird davon ausgegangen, dass die erste Symbol-Ressource in der Anwendung ist das Symbol der Anwendung, die nächste Symbolressource ist das erste Dokumentsymbol, und So weiter.

Beispielsweise ist eine Dokumentvorlage, die dritte von drei für die Anwendung. Wenn in der Anwendung am Index 3 Symbolressource vorhanden ist, wird das Symbol für die Dokumentvorlage verwendet. Wenn dies nicht der Fall ist, wird das Symbol am Index 0 als Standardwert verwendet.

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)<br/>
[Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)<br/>
[Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)<br/>
[Beziehungen zwischen MFC-Objekten](../mfc/relationships-among-mfc-objects.md)<br/>
[Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

