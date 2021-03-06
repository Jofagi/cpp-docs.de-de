---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Methoden'
ms.date: 09/12/2018
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
ms.openlocfilehash: 1e47e45efe27c9562cf8500f8941bcf0e259448a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585028"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Methoden

Eine vordefinierte Methode unterscheidet sich von einer benutzerdefinierten Methode, da er bereits von der Klasse implementiert wird [COleControl](../mfc/reference/colecontrol-class.md). Z. B. `COleControl` enthält eine vordefinierte Memberfunktion, die die Refresh-Methode für das Steuerelement unterstützt. Die Dispatch-Eintrag für die Zuordnung für diese Methode ist DISP_STOCKFUNC_REFRESH.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

`COleControl` unterstützt zwei vordefinierte Methoden: DoClick und aktualisieren. Aktualisierung wird aufgerufen, durch Benutzer des Steuerelements, um die Darstellung des Steuerelements sofort zu aktualisieren. DoClick wird aufgerufen, um das Auslösen des Steuerelements auf Ereignis.

|Methode|Dispatch-Zuordnungseintrag|Kommentar|
|------------|------------------------|-------------|
|`DoClick`|**DISP_STOCKPROP_DOCLICK)**|Löst ein Click-Ereignis.|
|`Refresh`|**DISP_STOCKPROP_REFRESH)**|Sofort aktualisiert die Darstellung des Steuerelements.|

##  <a name="_core_adding_a_stock_method_using_classwizard"></a> Hinzufügen einer Methode mithilfe der Methode Assistent zum Hinzufügen von

Das Hinzufügen einer Methode ist einfach mit der [Assistenten zum Hinzufügen von Methoden](../ide/add-method-wizard.md). Das folgende Verfahren veranschaulicht das Hinzufügen der Refresh-Methode an ein Steuerelement mit dem MFC-ActiveX-Steuerelement-Assistenten erstellt.

#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>Die vordefinierte Refresh-Methode, die mithilfe des Assistenten zum Hinzufügen einer Methode hinzufügen

1. Laden Sie das Steuerelementprojekt.

1. Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.

1. Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Methode hinzufügen**.

   Dies öffnet den Assistenten zum Hinzufügen einer Methode.

1. In der **Methodenname** auf **aktualisieren**.

1. Klicken Sie auf **Fertig stellen**.

##  <a name="_core_classwizard_changes_for_stock_methods"></a> Hinzufügen von Assistenten Änderungen für die vordefinierten Methoden

Da die vordefinierte Refresh-Methode von der Basisklasse des Steuerelements unterstützt wird die **Assistenten zum Hinzufügen von Methoden** ändert sich nicht auf die Sie in der Klassendeklaration des Steuerelements in keiner Weise. Es fügt einen Eintrag für die Methode, die in die Dispatchzuordnung des Steuerelements und seiner. IDL-Datei. Die folgende Zeile des Steuerelements Dispatchzuordnung, befindet sich in seiner Implementierung hinzugefügt (. CPP)-Datei:

[!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]

Dies stellt die Refresh-Methode des Steuerelements-Benutzern zur Verfügung.

Die folgende Zeile wird des Steuerelements hinzugefügt. IDL-Datei:

[!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]

Diese Zeile weist der Refresh-Methode zu eine bestimmte ID-Nummer.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

