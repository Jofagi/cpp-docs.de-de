---
title: Drehen Sie Memberfunktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6f0abfd5803ea4b4d4b4478104790e0f56e5afc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="spin-button-member-functions"></a>Memberfunktionen für das Drehfeldsteuerelement
Es stehen mehrere Memberfunktionen für das Drehfeld-Steuerelement ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)). Verwenden Sie diese Funktionen so ändern Sie die folgenden Attribute für das Drehfeld.  
  
-   **Acceleration** können Sie die Rate, mit der die Position geändert wird, wenn der Benutzer die Pfeiltaste gedrückt hält, anpassen. Verwenden Sie zum Arbeiten mit Beschleunigung der [Memberfunktionen SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) und [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) Memberfunktionen.  
  
-   **Basis** können Sie ändern, der Base (10 oder 16) verwendet, um die Position in der Beschriftung des Buddy-Fensters angezeigt. Verwenden Sie zum Arbeiten mit der Basis der [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) und [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) Memberfunktionen.  
  
-   **Fenster Buddy** können Sie Buddy-Fensters dynamisch festlegen. Um abzufragen oder zu ändern, welche das Buddyfenster ist, verwenden die [Memberfunktionen GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) und [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) Memberfunktionen.  
  
-   **Position** können Sie Abfragen und Ändern der Position. Verwenden Sie zum Bearbeiten mit der Position der [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) und [Memberfunktion SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) Memberfunktionen. Da die Beschriftung des Buddysteuerelements möglicherweise geändert (z. B. im Fall, dass die Buddy ein Bearbeitungssteuerelement ist), `GetPos` Ruft die aktuelle Beschriftung ab und passt die Position entsprechend.  
  
-   **Bereich** können Sie die maximalen und minimalen Positionen für das Drehfeld ändern. Standardmäßig ist die maximale auf 0 festgelegt, und mindestens auf 100 festgelegt ist. Da das Standardmaximum kleiner als der minimale Standardwert handelt, die Aktionen der Pfeilschaltflächen Counter-intuitiven ist. In der Regel legen Sie den Bereich mit der [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) Memberfunktion. Um die Verwendung des Bereichs abzufragen [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)
