---
title: Verwenden von Bildlisten in einem erweiterten Kombinationsfeld-Steuerelement
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], combo boxes
- extended combo boxes [MFC], images
- images [MFC], combo box items
ms.assetid: dfff25fe-af70-47a2-8032-3901d1e6842d
ms.openlocfilehash: 38f51205eea7220f0efbc2d8821fcb2b423e0add
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504598"
---
# <a name="using-image-lists-in-an-extended-combo-box-control"></a>Verwenden von Bildlisten in einem erweiterten Kombinationsfeld-Steuerelement

Die Hauptfunktion von erweiterten Kombinationsfeld-Steuerelementen ist die Möglichkeit, einzelne Elemente in einem Kombinationsfeld-Steuerelement-Images aus einer Bildliste zugeordnet werden soll. Jedes Element kann auf drei verschiedene Bilder anzuzeigen: eine für den ausgewählten Zustand, eine für die nicht ausgewählten Zustand und das dritte für ein Overlaybild.

Das folgende Verfahren verknüpft eine Bildliste mit einem erweiterten Kombinationsfeld-Steuerelement:

### <a name="to-associate-an-image-list-with-an-extended-combo-box-control"></a>Zuordnen eine Bildliste mit einem erweiterten Kombinationsfeld-Steuerelement

1. Erstellen Sie eine neue Bildliste (oder verwenden Sie ein vorhandene Image List-Objekt), mit der [CImageList](../mfc/reference/cimagelist-class.md) Konstruktor und den resultierenden Zeiger speichern.

1. Initialisieren Sie das neue Image List-Objekt durch Aufrufen [CImageList:: Create](../mfc/reference/cimagelist-class.md#create). Der folgende Code ist ein Beispiel für diesen Aufruf.

   [!code-cpp[NVC_MFCControlLadenDialog#10](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_1.cpp)]

1. Fügen Sie optionale Bilder für jeden möglichen Status: ausgewählte oder nicht ausgewählt und ein Overlay. Der folgende Code fügt drei vordefinierte Images.

   [!code-cpp[NVC_MFCControlLadenDialog#11](../mfc/codesnippet/cpp/using-image-lists-in-an-extended-combo-box-control_2.cpp)]

1. Ordnen Sie die Bildliste mit dem Steuerelement mit einem Aufruf von [CComboBoxEx:: SetImageList](../mfc/reference/ccomboboxex-class.md#setimagelist).

Sobald die Bildliste mit dem Steuerelement zugeordnet wurde, können Sie die Images, die jedes Element für die drei möglichen Zuständen verwendet wird, einzeln angeben. Weitere Informationen finden Sie unter [Festlegen der Bilder für ein einzelnes Element](../mfc/setting-the-images-for-an-individual-item.md).

## <a name="see-also"></a>Siehe auch

[Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)

