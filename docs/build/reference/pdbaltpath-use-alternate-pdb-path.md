---
title: /PDBALTPATH (Use Alternate PDB Path)
ms.date: 11/04/2016
f1_keywords:
- /pdbaltpath
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
ms.openlocfilehash: dd7bdc8d161e92eedf4856fcd28d9f9f1ac781b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551098"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (Use Alternate PDB Path)

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>Argumente

*pdb_file_name*<br/>
Der Pfad und der Dateiname für die .pdb-Datei.

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Option, um einen alternativen Speicherort für die Programmdatenbankdatei (.pdb) in einer kompilierten Binärdatei bereitzustellen. Normalerweise zeichnet der Linker den Speicherort der .pdb-Dateien in den Binärdateien auf, die er produziert. Sie können diese Option verwenden, um einen anderen Pfad und Dateinamen für die .pdb-Datei bereitzustellen. Die mit /PDBALTPATH bereitgestellten Informationen ändern weder den Standort noch den Namen der tatsächlichen .pdb-Datei, sondern sie ändern die Informationen, die der Linker in die Binärdatei schreibt. Damit können Sie einen Pfad bereitstellen, der unabhängig von der Dateistruktur des Buildcomputers ist. Zwei typische Verwendungszwecke für die Option ist die Bereitstellung eines Netzwerkpfads oder einer Datei, die keine Pfadinformationen hat.

Der Wert des *Pdb_file_name* kann eine beliebige Zeichenfolge, die eine Umgebungsvariable sein oder **%_PDB%**. Der Linker erweitert eine Umgebungsvariable, wie z. B. **%SystemRoot%**, auf den Wert. Der Linker definiert die Umgebungsvariablen **%_PDB%** und **%_EXT%**. **%_PDB%** wird auf den Namen der tatsächlichen .pdb-Datei ohne Pfadinformationen erweitert und **%_EXT%** ist die Erweiterung der generierten ausführbaren Datei.

## <a name="see-also"></a>Siehe auch

[DUMPBIN-Optionen](../../build/reference/dumpbin-options.md)<br/>
[/PDBPATH](../../build/reference/pdbpath.md)