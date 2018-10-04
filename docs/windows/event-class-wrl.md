---
title: Event-Klasse (WRL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b28a6e9d30e7a31916582207901859045023ad66
ms.sourcegitcommit: d1527eb2d50156bf923f2a32ec3af9efc7fc4304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48250961"
---
# <a name="event-class-wrl"></a>Event-Klasse (WRL)

Stellt ein Ereignis dar.

## <a name="syntax"></a>Syntax

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                   | Beschreibung
---------------------- | ------------------------------------------------
[Event:: Event](#event) | Initialisiert eine neue Instanz der `Event`-Klasse.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                 | Beschreibung
------------------------------------ | ------------------------------------------------------------------------
[Event:: =](#operator-assign) | Weist dem angegebenen `Event` Verweis auf das aktuelle `Event` Instanz.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HandleT`

`Event`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="event"></a>Event:: Event

Initialisiert eine neue Instanz der `Event`-Klasse.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()  
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Handle für ein Ereignis. In der Standardeinstellung *h* wird initialisiert `nullptr`.

## <a name="operator-assign"></a>Event:: =

Weist dem angegebenen `Event` Verweis auf das aktuelle `Event` Instanz.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Ein Rvalue-Verweis auf ein `Event` Instanz.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf die aktuelle `Event` Instanz.