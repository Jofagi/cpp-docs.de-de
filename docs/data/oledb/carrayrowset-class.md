---
title: CArrayRowset-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
- ATL::CArrayRowset::CArrayRowset
- CArrayRowset.CArrayRowset
- ATL.CArrayRowset.CArrayRowset
- ATL.CArrayRowset<TAccessor>.CArrayRowset
- CArrayRowset::CArrayRowset
- CArrayRowset
- CArrayRowset<TAccessor>::CArrayRowset
- ATL::CArrayRowset<TAccessor>::CArrayRowset
- CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset::Snapshot
- Snapshot
- CArrayRowset<TAccessor>::Snapshot
- ATL.CArrayRowset.Snapshot
- ATL.CArrayRowset<TAccessor>.Snapshot
- ATL::CArrayRowset<TAccessor>::Snapshot
- CArrayRowset::Snapshot
- CArrayRowset.Snapshot
- CArrayRowset::operator[]
- CArrayRowset.operator[]
- ATL::CArrayRowset::m_nRowsRead
- ATL::CArrayRowset<TAccessor>::m_nRowsRead
- CArrayRowset<TAccessor>::m_nRowsRead
- ATL.CArrayRowset<TAccessor>.m_nRowsRead
- CArrayRowset.m_nRowsRead
- m_nRowsRead
- ATL.CArrayRowset.m_nRowsRead
- CArrayRowset::m_nRowsRead
helpviewer_keywords:
- CArrayRowset class
- CArrayRowset class, constructor
- Snapshot method
- operator [], arrays
- '[] operator'
- operator[], arrays
- m_nRowsRead
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
ms.openlocfilehash: 0a867f80f3be685b3c45c8645d6441732acf5851
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330982"
---
# <a name="carrayrowset-class"></a>CArrayRowset-Klasse

Greift auf die Elemente eines Rowsets mit Arraysyntax.

## <a name="syntax"></a>Syntax

```cpp
template < class TAccessor >
class CArrayRowset :
   public CVirtualBuffer <TAccessor>,
   protected CBulkRowset <TAccessor>
```

### <a name="parameters"></a>Parameter

*TAccessor*<br/>
Der Typ der Accessor-Klasse, die Sie auf das Rowset verwenden möchten.

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CArrayRowset](#carrayrowset)|Konstruktor.|
|[Snapshot](#snapshot)|Liest das gesamte Rowset in den Speicher an.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[Operator&#91;&#93;](#operator)|Greift auf ein Element des Rowsets.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[CArrayRowset::m_nRowsRead](#nrowsread)|Die Anzahl der Zeilen, die bereits gelesen.|

## <a name="carrayrowset"></a> CArrayRowset:: CArrayRowset

Erstellt ein neues `CArrayRowset`-Objekt.

### <a name="syntax"></a>Syntax

```cpp
CArrayRowset(int nMax = 100000);
```

#### <a name="parameters"></a>Parameter

*nmax.*<br/>
[in] Maximale Anzahl von Zeilen im Rowset.

## <a name="snapshot"></a> CArrayRowset:: Snapshot

Liest das gesamte Rowset in den Speicher, erstellen ein Bild oder eine Momentaufnahme davon.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Snapshot() throw();
```

## <a name="operator"></a> CArrayRowset:: Operator

Stellt arrayähnlichen Syntax für den Zugriff auf eine Zeile im Rowset bereit.

### <a name="syntax"></a>Syntax

```cpp
TAccessor & operator[](int nrow);
```

#### <a name="parameters"></a>Parameter

*TAccessor*<br/>
Auf Vorlagen basierenden Parameter, der den Typ des Accessors gespeichert, in dem Rowset angibt.

*Funktionen "nrow"*<br/>
[in] Anzahl von der Zeile (Arrayelement), die Sie zugreifen möchten.

### <a name="return-value"></a>Rückgabewert

Der Inhalt der die angeforderte Zeile.

### <a name="remarks"></a>Hinweise

Wenn *Funktionen "nrow"* überschreitet die Anzahl der Zeilen im Rowset, wird eine Ausnahme ausgelöst.

## <a name="nrowsread"></a> CArrayRowset:: M_nrowsread

Enthält die Anzahl der Zeilen im Rowset, die bereits gelesen wurden.

### <a name="syntax"></a>Syntax

```cpp
ULONG m_nRowsRead;
```

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CRowset-Klasse](../../data/oledb/crowset-class.md)