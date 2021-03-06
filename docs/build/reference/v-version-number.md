---
title: /V (Versionsnummer)
ms.date: 11/04/2016
f1_keywords:
- /v
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
ms.openlocfilehash: 23c6ebfc0d67c6d00ed0e26d2e23806234cbb6af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463829"
---
# <a name="v-version-number"></a>/V (Versionsnummer)

Veraltet. Eine Zeichenfolge in der OBJ-Datei eingebettet.

## <a name="syntax"></a>Syntax

```
/Vstring
```

## <a name="arguments"></a>Argumente

*string*<br/>
Eine Zeichenfolge, die Angabe der Versionsnummer oder den Urheberrechtshinweis in einer OBJ-Datei eingebettet werden.

## <a name="remarks"></a>Hinweise

Die Bezeichnung der Stringcan eine .obj-Datei mit einer Versionsnummer oder Copyrightinformationen. Leerzeichen oder Tabulatorzeichen müssen in doppelte Anführungszeichen (") eingeschlossen werden, wenn sie einen Teil der Zeichenfolge sind. Ein umgekehrter Schrägstrich (\\) müssen vor keine doppelten Anführungszeichen stehen, wenn sie einen Teil der Zeichenfolge sind. Ein Leerzeichen zwischen **/v** und `string` ist optional.

Sie können auch [Kommentar (C/C++)](../../preprocessor/comment-c-cpp.md) mit dem Compiler Comment-Type-Argument, um den Namen und die Version des Compilers in der OBJ-Datei abzulegen.

Die **/v** Option ist ab Visual Studio 2005; veraltet. **/V** wurde in erster Linie verwendet, um das Erstellen von virtuellen Gerätetreibern (VxDs) zu unterstützen, und Erstellen von VxDs wird vom Visual C++-Toolset nicht mehr unterstützt. Eine Liste der Ersetzte Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)