---
title: CElementTraits-Klasse
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 4951f5b87efbff83f39badba5f3e1041a15d8c6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480756"
---
# <a name="celementtraits-class"></a>CElementTraits-Klasse

Diese Klasse wird von Auflistungsklassen verwendet, verschieben, kopieren, Vergleich und Hashvorgängen Methoden und Funktionen bereit.

## <a name="syntax"></a>Syntax

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ der Daten in der Auflistung gespeichert werden.

## <a name="remarks"></a>Hinweise

Diese Klasse stellt statische Standard-Funktionen und Methoden für das Verschieben, kopieren, vergleichen und hashing in ein Klassenobjekt Auflistung gespeicherten Elementen an. `CElementTraits` als Standardanbieter dieser Vorgänge angegeben ist, durch die Auflistungsklassen [CAtlArray](../../atl/reference/catlarray-class.md), [CAtlList](../../atl/reference/catllist-class.md), [CRBMap](../../atl/reference/crbmap-class.md), [CRBMultiMap](../../atl/reference/crbmultimap-class.md), und [CRBTree](../../atl/reference/crbtree-class.md).

Die standardimplementierungen ist ausreichend für einfache Datentypen, aber wenn die Auflistungsklassen verwendet werden, um komplexe Objekte speichern, die Funktionen und Methoden müssen überschrieben werden von benutzerdefinierten Implementierungen.

Weitere Informationen finden Sie unter [ATL-Auflistungsklassen](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Anforderungen

**Header:** atlcoll.h

## <a name="see-also"></a>Siehe auch

[CDefaultElementTraits-Klasse](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
