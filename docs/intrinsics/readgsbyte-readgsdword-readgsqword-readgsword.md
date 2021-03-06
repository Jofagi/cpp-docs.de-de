---
title: __readgsbyte, __readgsdword, __readgsqword, __readgsword
ms.date: 11/04/2016
f1_keywords:
- __readgsbyte
- __readgsdword
- __readgsqword
- __readgsword
helpviewer_keywords:
- __readgsword intrinsic
- __readgsdword intrinsic
- __readgsqword intrinsic
- __readgsbyte intrinsic
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
ms.openlocfilehash: 1bc6a3b2ef2d78e5b30ea36149ea691468c9b0ec
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51327511"
---
# <a name="readgsbyte-readgsdword-readgsqword-readgsword"></a>__readgsbyte, __readgsdword, __readgsqword, __readgsword

**Microsoft-spezifisch**

Lesen Sie Arbeitsspeicher von einem Speicherort, ein Offset relativ zum Beginn der GS-Segment angegeben wird.

## <a name="syntax"></a>Syntax

```
unsigned char __readgsbyte(
   unsigned long Offset
);
unsigned short __readgsword(
   unsigned long Offset
);
unsigned long __readgsdword(
   unsigned long Offset
);
unsigned __int64 __readgsqword(
   unsigned long Offset
);
```

#### <a name="parameters"></a>Parameter

*Offset*<br/>
[in] Der Offset vom Anfang des `GS` zum Lesen aus.

## <a name="return-value"></a>Rückgabewert

Der Speicherinhalt, der das Byte, Wort, Double oder Vierfachwort (wie durch den Namen der aufgerufenen Funktion angegeben wird) an der Position `GS:[Offset]`.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__readgsbyte`|x64|
|`__readgsdword`|x64|
|`__readgsqword`|x64|
|`__readgsword`|x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

Diese systeminternen Funktionen sind nur im Kernelmodus verfügbar, und die Routinen sind nur als systeminterne Funktionen verfügbar.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__writegsbyte, \__writegsdword, \__writegsqword, \__writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)<br/>
[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)