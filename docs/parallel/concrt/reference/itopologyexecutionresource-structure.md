---
title: ITopologyExecutionResource-Struktur
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: fa4d8978cbdb5cab36367138ffb607a722b6b91a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631074"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource-Struktur

Eine Schnittstelle zu einer vom Ressourcen-Manager definierten Ausführungsressource.

## <a name="syntax"></a>Syntax

```
struct ITopologyExecutionResource;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Itopologyexecutionresource:: GetID](#getid)|Gibt zurück, der Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.|
|[ITopologyExecutionResource::GetNext](#getnext)|Gibt eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge der zurück.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems führen, als vom Ressourcen-Manager überwacht.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ITopologyExecutionResource`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="getid"></a>  Itopologyexecutionresource:: GetID-Methode

Gibt zurück, der Ressourcen-Manager eindeutige Bezeichner für diese Ausführungsressource.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der Resource Manager Eindeutiger Bezeichner für diese Ausführungsressource.

##  <a name="getnext"></a>  Itopologyexecutionresource:: GetNext-Methode

Gibt eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge der zurück.

```
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine Schnittstelle zur nächsten Ausführungsressource Reihenfolge der. Wenn die Reihenfolge des Knotens, zu dem diese Ausführungsressource gehört, keine weiteren Knoten vorhanden sind, gibt diese Methode den Wert `NULL`.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
