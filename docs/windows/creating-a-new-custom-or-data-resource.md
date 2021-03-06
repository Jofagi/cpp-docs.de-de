---
title: Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.binary
helpviewer_keywords:
- custom resources [C++]
- data resources [C++]
- resources [C++], creating
ms.assetid: 9918bf96-38fa-43a1-a384-572f95d84950
ms.openlocfilehash: 7b4044921a26e572c53e1a070611c78323d3ca1e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590475"
---
# <a name="creating-a-new-custom-or-data-resource-c"></a>Erstellen einer neuen benutzerdefinierten Ressource oder Datenressource (C++)

Sie können eine neue benutzerdefinierte oder Datenressource erstellen, indem Sie die Ressource in einer separaten Datei mit der normalen Syntax von Ressourcenskriptdateien (RC), und klicken Sie dann die Datei einschließen, mit der rechten Maustaste in das Projekt im platzieren **Projektmappen-Explorer** und auf **Ressource umfasst** im Kontextmenü auf.

### <a name="to-create-a-new-custom-or-data-resource"></a>So erstellen Sie eine neue benutzerdefinierte oder Datenressource

1. [Erstellen Sie eine RC-Datei](../windows/how-to-create-a-resource-script-file.md) , die die benutzerdefinierte oder Datenressource enthält.

   Sie können benutzerdefinierte Daten in einer RC-Datei als in Anführungszeichen eingeschlossene nullterminierte Zeichenfolgen oder als ganze Zahlen im dezimalen, hexadezimalen oder oktalen Format eingeben.

2. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf die RC-Datei Ihres Projekts, und klicken Sie dann im Kontextmenü auf **Ressourcenincludes** .

3. In der **Kompilierzeitdirektiven** geben eine `#include` -Anweisung, die den Namen der Datei mit der benutzerdefinierten Ressource enthält. Zum Beispiel:

    ```cpp
    #include mydata.rc
    ```

   Achten Sie auf die korrekte Syntax und Rechtschreibung Ihrer Eingaben. Der Inhalt des Felds **Kompilierzeitdirektiven** wird in die Ressourcenskriptdatei genau so eingefügt, wie sie ihn eingegeben haben.

4. Klicken Sie auf **OK** , um Ihre Änderungen aufzuzeichnen.

Eine weitere Möglichkeit zum Erstellen einer benutzerdefinierten Ressource ist das Importieren einer externen Datei als benutzerdefinierte Ressource. Weitere Informationen finden Sie unter [Importieren und Exportieren von Ressourcen](../windows/how-to-import-and-export-resources.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Binary Editor](binary-editor.md)