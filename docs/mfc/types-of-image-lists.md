---
title: Bildlistenarten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- lists [MFC], image
- image lists [MFC], types of
- CImageList class [MFC], types
ms.assetid: bee5e7c3-78f5-4037-a136-9c50d67cdee5
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 84a2118978d5ebd722d4fe56cdeec2aa0f74a94e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-image-lists"></a>Bildlistenarten
Es gibt zwei Arten von Bildlisten ([CImageList](../mfc/reference/cimagelist-class.md)): nicht maskierte und maskierte. Eine "nicht maskierte Bildliste" besteht aus einer Farbbitmap, die ein oder mehrere Abbilder enthält. Eine "maskierte Bildliste" besteht aus zwei Bitmaps gleicher Größe. Die erste ist eine Farbbitmap, die die Bilder enthält, und die zweite ist eine monochrome Bitmap, die eine Reihe von Masken enthält – eine für jedes Bild in der ersten Bitmap.  
  
 Eine der Überladungen der der **erstellen** Member-Funktion akzeptiert ein Flag zur Angabe, und zwar unabhängig davon, ob die Bildliste maskiert wird. (Andere Überladungen erstellen maskierten Bildlisten.)  
  
 Wenn ein nicht maskierten Bild gezeichnet wird, wird es einfach in den Ziel-Gerätekontext kopiert; Es wird also über die vorhandenen Hintergrundfarbe des Gerätekontexts gezeichnet. Wenn ein maskiertes Bild gezeichnet wird, werden die Bits des Bilds mit den Bit der Maske, erzeugt in der Regel transparente Bereiche in der Bitmap, in dem die Hintergrundfarbe des Zielgerätekontexts durchscheint, kombiniert. Sie können mehrere zeichnungsarten beim Zeichnen eines maskierten Bildes angeben. Beispielsweise können Sie angeben, dass das Bild blinkt, um ein ausgewähltes Objekt anzugeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CImageList](../mfc/using-cimagelist.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
