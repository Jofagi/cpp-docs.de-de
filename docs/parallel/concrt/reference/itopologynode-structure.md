---
title: ITopologyNode-Struktur
ms.date: 11/04/2016
f1_keywords:
- ITopologyNode
- CONCRTRM/concurrency::ITopologyNode
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetExecutionResourceCount
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetFirstExecutionResource
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetId
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNext
- CONCRTRM/concurrency::ITopologyNode::ITopologyNode::GetNumaNode
helpviewer_keywords:
- ITopologyNode structure
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
ms.openlocfilehash: 4f880e3c44cd9f301aa65d45500ed7f1d1725bc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636656"
---
# <a name="itopologynode-structure"></a>ITopologyNode-Struktur

Eine Schnittstelle für einen vom Ressourcen-Manager definierten Topologieknoten. Ein Knoten enthält mindestens eine Ausführungsressource.

## <a name="syntax"></a>Syntax

```
struct ITopologyNode;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Itopologynode:: Getexecutionresourcecount](#getexecutionresourcecount)|Gibt die Anzahl der Ressourcen zur Ausführung unter diesem Knoten gruppiert.|
|[Itopologynode:: Getfirstexecutionresource](#getfirstexecutionresource)|Gibt die erste Ausführungsressource unter diesem Knoten in einer Reihenfolge gruppiert.|
|[ITopologyNode::GetId](#getid)|Gibt zurück, der Ressourcen-Manager, eindeutiger Bezeichner für diesen Knoten.|
|[Itopologynode:: GetNext](#getnext)|Gibt eine Schnittstelle auf den nächsten topologieknoten in der Reihenfolge der Enumeration zurück.|
|[Itopologynode:: Getnumanode](#getnumanode)|Gibt die von Windows zugewiesene NUMA-Knotenzahl zurück, zu der dieser Ressource-Manager-Knoten gehört.|

## <a name="remarks"></a>Hinweise

Diese Schnittstelle wird in der Regel verwendet, um die Topologie des Systems führen, als vom Ressourcen-Manager überwacht.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ITopologyNode`

## <a name="requirements"></a>Anforderungen

**Header:** concrtrm.h

**Namespace:** Parallelität

##  <a name="getexecutionresourcecount"></a>  Itopologynode:: Getexecutionresourcecount-Methode

Gibt die Anzahl der Ressourcen zur Ausführung unter diesem Knoten gruppiert.

```
virtual unsigned int GetExecutionResourceCount() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Ressourcen zur Ausführung unter diesem Knoten gruppiert.

##  <a name="getfirstexecutionresource"></a>  Itopologynode:: Getfirstexecutionresource-Methode

Gibt die erste Ausführungsressource unter diesem Knoten in einer Reihenfolge gruppiert.

```
virtual ITopologyExecutionResource *GetFirstExecutionResource() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Die erste Ausführungsressource, die unter diesem Knoten in der Reihenfolge der gruppiert werden.

##  <a name="getid"></a>  Itopologynode:: GetID-Methode

Gibt zurück, der Ressourcen-Manager, eindeutiger Bezeichner für diesen Knoten.

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Der Resource Manager Eindeutiger Bezeichner für diesen Knoten.

### <a name="remarks"></a>Hinweise

Die Concurrency Runtime stellt Hardwarethreads auf dem System in Gruppen von Prozessorknoten dar. Knoten werden in der Regel von der Hardwaretopologie des Systems abgeleitet. Beispielsweise können alle Prozessoren auf einem bestimmten Socket oder einen bestimmten NUMA-Knoten zu dem gleichen Prozessorknoten gehören. Der Ressourcen-Manager weist eine eindeutige Bezeichner auf diese Knoten beginnend mit `0` bis zu und einschließlich `nodeCount - 1`, wobei `nodeCount` stellt die Gesamtzahl der Prozessorknoten auf dem System.

Die Anzahl der Knoten erhalten Sie von der Funktion [GetProcessorNodeCount](concurrency-namespace-functions.md).

##  <a name="getnext"></a>  Itopologynode:: GetNext-Methode

Gibt eine Schnittstelle auf den nächsten topologieknoten in der Reihenfolge der Enumeration zurück.

```
virtual ITopologyNode *GetNext() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Eine Schnittstelle zu den nächsten Knoten in der Reihenfolge der Enumeration. Wenn die Reihenfolge der Systemtopologie keine weiteren Knoten vorhanden sind, gibt diese Methode den Wert `NULL`.

##  <a name="getnumanode"></a>  Itopologynode:: Getnumanode-Methode

Gibt die von Windows zugewiesene NUMA-Knotenzahl zurück, zu der dieser Ressource-Manager-Knoten gehört.

```
virtual unsigned long GetNumaNode() const = 0;
```

### <a name="return-value"></a>Rückgabewert

Die von Windows zugewiesene NUMA-Knotenzahl, zu der dieser Ressource-Manager-Knoten gehört.

### <a name="remarks"></a>Hinweise

Ein Threadproxy, der auf einem virtuellen Prozessorstamm ausgeführt wird, der zu diesem Knoten gehört, verfügt über Affinität zu mindestens der NUMA-Knotenebene für den NUMA-Knoten, der von dieser Methode zurückgegeben wird.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
