---
title: ATL-Operatoren
ms.date: 11/04/2016
helpviewer_keywords:
- operators [ATL]
ms.assetid: 58ccd252-2869-45ee-8a5c-3ca40ee7f8a2
ms.openlocfilehash: 361b0316e27ee06c64b3ed5e11c6aab10210596f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476257"
---
# <a name="atl-operators"></a>ATL-Operatoren

Dieser Abschnitt enthält die Referenzthemen für die globalen ATL-Operatoren.

|Operator|Beschreibung|
|--------------|-----------------|
|[operator ==](#operator_eq_eq)|Vergleicht zwei `CSid` Objekte oder `SID` -Strukturen auf Gleichheit.|
|[Operator! =](#operator_neq)|Vergleicht zwei `CSid` Objekte oder `SID` -Strukturen auf Ungleichheit.|
|[Operator <](#operator_lt)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für C++-Standardbibliothek-Kompatibilität).|
|[operator >](#operator_gt)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als die `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für C++-Standardbibliothek-Kompatibilität).|
|[operator <=](#operator_lt__eq)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für C++-Standardbibliothek-Kompatibilität).|
|[operator >=](#operator_gt__eq)|Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für C++-Standardbibliothek-Kompatibilität).|

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h.

##  <a name="operator_eq_eq"></a>  Operator ==

Vergleicht `CSid` Objekte oder `SID` -Strukturen auf Gleichheit (Sicherheits-ID).

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.

*RS*<br/>
Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Objekte gleich sind, FALSE, wenn sie nicht gleich sind.

##  <a name="operator_neq"></a>  Operator! =

Vergleicht `CSid` Objekte oder `SID` (Sicherheits-ID) der Strukturen auf Ungleichheit.

```
bool operator==(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.

*RS*<br/>
Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt TRUE zurück, wenn die Objekte nicht gleich "false", wenn sie gleich sind.

##  <a name="operator_lt"></a>  Operator <

Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für C++-Standardbibliothek-Kompatibilität).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.

*RS*<br/>
Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Adresse des der *Lhs* Objekt ist kleiner als die Adresse der *RS* Objekt, "false" andernfalls.

### <a name="remarks"></a>Hinweise

Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` -Struktur und wird implementiert, um die Kompatibilität mit C++-Standardbibliothek-Auflistungsklassen.

##  <a name="operator_gt"></a>  Operator >

Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als die `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für C++-Standardbibliothek-Kompatibilität).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.

*RS*<br/>
Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Adresse des der *Lhs* ist größer als die Adresse der *RS*"false" andernfalls.

### <a name="remarks"></a>Hinweise

Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` -Struktur und wird implementiert, um die Kompatibilität mit C++-Standardbibliothek-Auflistungsklassen.

##  <a name="operator_lt__eq"></a>  Operator < =

Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist kleiner als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für C++-Standardbibliothek-Kompatibilität).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.

*RS*<br/>
Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Adresse der *Lhs* ist kleiner als oder gleich der Adresse des der *RS*"false" andernfalls.

### <a name="remarks"></a>Hinweise

Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` -Struktur und wird implementiert, um die Kompatibilität mit C++-Standardbibliothek-Auflistungsklassen.

##  <a name="operator_gt__eq"></a>  Operator > =

Testet, ob die `CSid` Objekt oder `SID` Struktur auf der linken Seite des Operators ist größer als oder gleich der `CSid` Objekt oder `SID` Struktur auf der rechten Seite (für C++-Standardbibliothek-Kompatibilität).

```
bool operator<(const CSid& lhs, const CSid& rhs) throw();
```

### <a name="parameters"></a>Parameter

*LHS*<br/>
Die erste `CSid` Objekt oder `SID` zu vergleichende Struktur.

*RS*<br/>
Die zweite `CSid` Objekt oder `SID` zu vergleichende Struktur.

### <a name="return-value"></a>Rückgabewert

Gibt "true" zurück, wenn die Adresse des der *Lhs* ist größer als oder gleich auf die Adresse der *RS*"false" andernfalls.

### <a name="remarks"></a>Hinweise

Dieser Operator bezieht sich auf die Adresse der `CSid` Objekt oder `SID` -Struktur und wird implementiert, um die Kompatibilität mit C++-Standardbibliothek-Auflistungsklassen.

