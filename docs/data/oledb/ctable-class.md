---
title: CTable-Klasse
ms.date: 11/04/2016
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
ms.openlocfilehash: 7605d78a140a0f5353a16b9e22d5d618d29ff327
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556682"
---
# <a name="ctable-class"></a>CTable-Klasse

Bietet eine Möglichkeit, direkt auf ein einfaches Rowset (ohne Parameter) zuzugreifen.

## <a name="syntax"></a>Syntax

```cpp
template <class TAccessor = CNoAccessor,
            template <typename T> class TRowset = CRowset>
class CTable :
   public CAccessorRowset <TAccessor, TRowset>
```

### <a name="parameters"></a>Parameter

*TAccessor*<br/>
Ein Accessor-Klasse.

*TRowset*<br/>
Eine Rowset-Klasse.

## <a name="requirements"></a>Anforderungen

**Header:** atldbcli.h

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[Öffnen](#open)|Öffnet die Tabelle.|

## <a name="remarks"></a>Hinweise

Finden Sie unter [CCommand](../../data/oledb/ccommand-class.md) Informationen zum Ausführen eines Befehls in ein Rowset zugreifen.

## <a name="open"></a> CTable:: Open

Öffnet die Tabelle.

### <a name="syntax"></a>Syntax

```cpp
HRESULT Open(const CSession& session,
   LPCWSTR wszTableName,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();

HRESULT Open(const CSession& session,
   LPCSTR szTableName,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();

HRESULT Open(const CSession& session,
   DBID& dbid,
   DBPROPSET* pPropSet = NULL,
   ULONG ulPropSets = 0) throw ();
```

#### <a name="parameters"></a>Parameter

*Sitzung*<br/>
[in] Die Sitzung, für die in der Tabelle geöffnet wird.

*wszTableName*<br/>
[in] Der Name der Tabelle zu öffnen, werden als Unicode-Zeichenfolge übergeben.

*szTableName*<br/>
[in] Der Name der Tabelle zu öffnen, werden als eine ANSI-Zeichenfolge übergeben.

*dbid*<br/>
[in] Die `DBID` der Tabelle zu öffnen.

*pPropSet*<br/>
[in] Ein Zeiger auf ein Array von [DBPROPSET](https://docs.microsoft.com/previous-versions/windows/desktop/ms714367(v=vs.85)) Strukturen, die Eigenschaften und Werte festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](https://docs.microsoft.com/previous-versions/windows/desktop/ms713696(v=vs.85)) in die *OLE DB-Programmierreferenz* in das Windows SDK. Der Standardwert NULL gibt an, keine Eigenschaften.

*ulPropSets*<br/>
[in] Die Anzahl der [DBPROPSET](https://docs.microsoft.com/previous-versions/windows/desktop/ms714367(v=vs.85)) Strukturen zu übergeben, der *DBPROPSET* Argument.

### <a name="return-value"></a>Rückgabewert

Ein standard-HRESULT.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [IOpenRowset:: OPENROWSET](https://docs.microsoft.com/previous-versions/windows/desktop/ms716724(v=vs.85)) in die *OLE DB-Programmierreferenz*.

## <a name="see-also"></a>Siehe auch

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)