---
title: Requestedit (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requestedit
helpviewer_keywords:
- requestedit attribute
ms.assetid: b3c24790-3c4a-4646-8722-03d7b51172ee
ms.openlocfilehash: 27e6190cbb5908d46150acb758e2b4d5efaff1bb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611588"
---
# <a name="requestedit"></a>requestedit

Gibt an, dass die Eigenschaft unterstützt die `OnRequestEdit` Benachrichtigung.

## <a name="syntax"></a>Syntax

```cpp
[requestedit]
```

## <a name="remarks"></a>Hinweise

Die **Requestedit** C++-Attribut hat die gleiche Funktionalität wie die [Requestedit](/windows/desktop/Midl/requestedit) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](bindable.md) für ein Beispiel für die Verwendung von **Requestedit**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[Datenmemberattribute](data-member-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)