---
title: Bearbeiten einer Zeichenfolge in einer Versionsinformationsressource (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.version
helpviewer_keywords:
- version information resources [C++]
- resources [C++], editing version information
ms.assetid: d3a7d4e4-7d31-47c2-902c-f50b8404ba4f
ms.openlocfilehash: 75d41444d685b067b57aa78aee944ee005da5d3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476426"
---
# <a name="editing-a-string-in-a-version-information-resource-c"></a>Bearbeiten einer Zeichenfolge in einer Versionsinformationsressource (C++)

### <a name="to-edit-a-string-in-a-version-information-resource"></a>So bearbeiten Sie eine Zeichenfolge in einer Versionsinformationsressource

1. Klicken Sie ein Mal auf das Element, um es auszuwählen, und dann noch ein Mal, um mit der Bearbeitung zu beginnen. Nehmen Sie die Änderungen direkt in die **Versionsinformationen** Tabelle oder in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Die vorgenommenen Änderungen werden an beiden Orten berücksichtigt.

   > [!NOTE]
   > Beim Bearbeiten der `FILEFLAGS` -Schlüssel in der **Versionsinformationen** -Editor, Sie werden bemerken Sie nicht Festlegen der **Debuggen**, **Private Build**, oder **spezielle Erstellen Sie** Eigenschaften (in der **Eigenschaften** Fenster) für RC-Dateien:

   - Die **Versionsinformationen** legt die **Debuggen** Eigenschaft mit einer `#ifdef` im Ressourcenskript, basierend auf den `_DEBUG` build-Flag.

   - Wenn die `Private Build` Schlüssel besitzt eine **Wert** legen Sie in der **Versionsinformationen** Tabelle, die entsprechende **Private Build** Eigenschaft (in der **Eigenschaften**  Fenster) für die `FILEFLAGS` Schlüssel **"true"**. Wenn der **Wert** leer ist, ist die Eigenschaft **False**. Ebenso der **Special Build** Schlüssel (in der **Versionsinformationen** Tabelle) gebunden ist, um die **Special Build** -Eigenschaft für die `FILEFLAGS` Schlüssel.

Sie können die Informationssequenz des Zeichenfolgenblocks sortieren, indem Sie entweder auf den Spaltenkopf „Schlüssel“ oder den Spaltenkopf „Wert“ klicken. Mithilfe dieser Überschriften können die Informationen automatisch in der ausgewählten Reihenfolge neu angeordnet werden.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Versionsinfo-Editor](../windows/version-information-editor.md)<br/>
[Versionsinformationen (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)