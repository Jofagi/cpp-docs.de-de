---
title: /ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verknüpfen)
ms.date: 11/04/2016
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
ms.openlocfilehash: 7c1d78758e43bf8e0c2c281c495c81e9f62b36e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473904"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verknüpfen)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Die Ressourcendatei von .NET Framework, die Sie mit der Assembly verknüpfen möchten

## <a name="remarks"></a>Hinweise

Die/ASSEMBLYLINKRESOURCE-Option erstellt einen Link zu einer .NET Framework-Ressource in der Ausgabedatei an. die Ressourcendatei wird nicht in der Ausgabedatei platziert. [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) bettet eine Ressourcendatei in die Ausgabedatei.

Verknüpfte Ressourcen sind öffentlich in der Assembly, wenn der Linker erstellt.

/ ASSEMBLYLINKRESOURCE erfordert, dass die Kompilierung ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md); [/Ln](../../build/reference/ln-create-msil-module.md) oder [/noAssembly](../../build/reference/noassembly-create-a-msil-module.md) ist mit/ASSEMBLYLINKRESOURCE nicht zulässig.

Wenn *Filename* ist eine .NET Framework-Ressourcendatei erstellt haben, z. B. durch [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der **System.Resources** Namespace. Weitere Informationen finden Sie unter [System.Resources.ResourceManager](https://msdn.microsoft.com/library/system.resources.resourcemanager.aspx). Verwenden Sie für alle anderen Ressourcen die **GetManifestResource** \* Methoden in der **System.Reflection.Assembly** Klasse, um Zugriff auf die Ressource zur Laufzeit.

*FileName* kann einem beliebigen Dateiformat sein. Beispielsweise empfiehlt es sich um eine systemeigene DLL Teil der Assembly zu machen, damit es im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly zugegriffen werden kann.

Andere Optionen des Linkers, die Generierung der Zielassembly betreffen sind:

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Option in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)