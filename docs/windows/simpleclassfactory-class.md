---
title: SimpleClassFactory-Klasse
ms.date: 09/7/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
helpviewer_keywords:
- Microsoft::WRL::SimpleClassFactory class
- Microsoft::WRL::SimpleClassFactory::CreateInstance method
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
ms.openlocfilehash: e73c4cc8088fb5200ae2ae76dcbed773db76863b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500580"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory-Klasse

Stellt einen grundlegenden Mechanismus zum Erstellen einer Basisklasse bereit.

## <a name="syntax"></a>Syntax

```cpp
template<typename Base>
class SimpleClassFactory : public ClassFactory<>;
```

### <a name="parameters"></a>Parameter

*Basis*<br/>
Eine Basisklasse.

## <a name="remarks"></a>Hinweise

Die Basisklasse muss einen Standardkonstruktor bereitstellen.

Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit `SimpleClassFactory` mit der [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) Makro.

`ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[SimpleClassFactory::CreateInstance-Methode](#createinstance)|Erstellt eine Instanz der angegebenen Schnittstelle.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ClassFactory`

`SimpleClassFactory`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="createinstance"></a>Simpleclassfactory:: CreateInstance-Methode

Erstellt eine Instanz der angegebenen Schnittstelle.

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

#### <a name="parameters"></a>Parameter

*pUnkOuter*<br/>
Muss `nullptr`ist, andernfalls CLASS_E_NOAGGREGATION zurückgegeben wird.

SimpleClassFactory unterstützt keine Aggregation. Wenn der Aggregation unterstützt wurden, und das zu erstellende Objekt war Teil einer Aggregatfunktion gehört, *pUnkOuter* wäre ein Zeiger auf das steuernde `IUnknown` Schnittstelle des Aggregats.

*riid*<br/>
Schnittstellen-ID des Objekts zu erstellen.

*ppvObject*<br/>
Wenn dieser Vorgang abgeschlossen ist, Zeiger auf eine Instanz des Objekts gemäß der *Riid* Parameter.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Wenn `__WRL_STRICT__` wird definiert, ein Assert-Fehler wird ausgegeben, wenn die Klassenvorlagenparameter angegebene Basisklasse abgeleitet ist nicht [RuntimeClass](../windows/runtimeclass-class.md), oder ist nicht konfiguriert, mit dem ClassicCom oder WinRtClassicComMix [ RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumerationswert.
