---
title: error_condition-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- system_error/std::error_condition
- system_error/std::error_condition::value_type
- system_error/std::error_condition::assign
- system_error/std::error_condition::category
- system_error/std::error_condition::clear
- system_error/std::error_condition::message
- system_error/std::error_condition::operator bool
dev_langs: C++
helpviewer_keywords:
- std::error_condition
- std::error_condition::value_type
- std::error_condition::assign
- std::error_condition::category
- std::error_condition::clear
- std::error_condition::message
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eaf36a6f078fd41eee75788a2adbbb5efed7f5d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="errorcondition-class"></a>error_condition-Klasse
Stellt benutzerdefinierte Fehlercodes dar.  
  
## <a name="syntax"></a>Syntax  
  
```
class error_condition;
```  
  
## <a name="remarks"></a>Hinweise  
 Ein Objekt vom Typ `error_condition` enthält einen Fehlercodewert und einen Zeiger auf ein Objekt, das eine [category (Kategorie)](../standard-library/error-category-class.md) von Fehlercodes darstellt, die für berichtete benutzerdefinierte Fehlercodes verwendet werden.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[error_condition](#error_condition)|Konstruiert ein Objekt vom Typ `error_condition`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[value_type](#value_type)|Ein Typ, der den gespeicherten Fehlercodewert darstellt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[assign](#assign)|Weist einen Fehlercodewert und die Kategorie an eine Fehlerbedingung zurück.|  
|[category](#category)|Gibt die Fehlerkategorie zurück.|  
|[clear](#clear)|Löscht den Fehlercodewert und die Kategorie.|  
|[message](#message)|Gibt den Namen des Fehlercodes zurück.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator==](#op_eq_eq)|Prüft auf Gleichheit zwischen `error_condition`-Objekten.|  
|[operator!=](#op_neq)|Prüft auf Ungleichheit zwischen `error_condition`-Objekten.|  
|[operator<](#op_lt)|Testet, ob das `error_condition`-Objekt kleiner ist als das `error_code`-Objekt, das für den Vergleich übergeben wurde.|  
|[operator=](#op_eq)|Weist dem `error_condition`-Objekt einen neuen Enumerationswert zu.|  
|[operator bool](#op_bool)|Wandelt eine Variable vom Typ `error_condition` um.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<system_error>  
  
 **Namespace:** std  
  
##  <a name="assign"></a> error_condition::assign  
 Weist einen Fehlercodewert und die Kategorie an eine Fehlerbedingung zurück.  
  
```
void assign(value_type val, const error_category& _Cat);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`val`|Der Fehlercodewert, der in `error_code` gespeichert werden soll.|  
|`_Cat`|Die Fehlerkategorie, die in `error_code` gespeichert werden soll.|  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Funktion speichert `val` als Fehlercodewert und einen Zeiger auf `_Cat`.  
  
##  <a name="category"></a> error_condition::category  
 Gibt die Fehlerkategorie zurück.  
  
```
const error_category& category() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf die gespeicherte Fehlerkategorie.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="clear"></a> error_condition::clear  
 Löscht den Fehlercodewert und die Kategorie.  
  
```
clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion speichert einen Fehlercodewert „Null“ und einen Zeiger auf das Objekt [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
##  <a name="error_condition"></a> error_condition::error_condition  
 Konstruiert ein Objekt vom Typ `error_condition`.  
  
```
error_condition();

error_condition(value_type val, const error_category& _Cat);

template <class _Enum>
error_condition(_Enum _Errcode,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_code>::type* = 0);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`val`|Der Fehlercodewert, der in `error_condition` gespeichert werden soll.|  
|`_Cat`|Die Fehlerkategorie, die in `error_condition` gespeichert werden soll.|  
|`_Errcode`|Der Enumerationswert, der in `error_condition` gespeichert werden soll.|  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor speichert einen Fehlercodewert „Null“ und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category).  
  
 Der zweite Konstruktor speichert `val` als Fehlercodewert und einen Zeiger auf [error_category](http://msdn.microsoft.com/en-us/6fe57a15-63a1-4e79-8af4-6738e43e19c8).  
  
 Im dritten Konstruktor wird `(value_type)_Errcode` als Fehlercodewert und ein Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category) gespeichert.  
  
##  <a name="message"></a> error_condition::message  
 Gibt den Namen des Fehlercodes zurück.  
  
```
string message() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `string`, der den Namen des Fehlercodes darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion gibt `category().message(value())` zurück.  
  
##  <a name="op_eq_eq"></a> error_condition::operator==  
 Prüft auf Gleichheit zwischen `error_condition`-Objekten.  
  
```
bool operator==(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Die Objekte, die auf Gleichheit getestet werden sollen.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Objekte gleich sind; **FALSE**, wenn die Objekte nicht gleich sind.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `category() == right.category() && value == right.value()`zurück.  
  
##  <a name="op_neq"></a> error_condition::operator!=  
 Prüft auf Ungleichheit zwischen `error_condition`-Objekten.  
  
```
bool operator!=(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Das Objekt, das auf Ungleichheit geprüft werden soll.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das Objekt `error_condition` nicht dem Objekt `error_condition` entspricht, das an `right` übergeben wird; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `!(*this == right)`zurück.  
  
##  <a name="op_lt"></a> error_condition::operator&lt;  
 Testet, ob das `error_condition`-Objekt kleiner ist als das `error_code`-Objekt, das für den Vergleich übergeben wurde.  
  
```
bool operator<(const error_condition& right) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`right`|Das zu vergleichende `error_condition`-Objekt.|  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn das Objekt, das an `error_condition` übergeben wird, kleiner ist als das an `error_condition` übergebene Objekt; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator gibt `category() < right.category() || category() == right.category() && value < right.value()` zurück.  
  
##  <a name="op_eq"></a> error_condition::operator=  
 Weist dem `error_condition`-Objekt einen neuen Enumerationswert zu.  
  
```
template <class _Enum>
error_condition(_Enum error,
    typename enable_if<is_error_condition_enum<_Enum>::value,
    error_condition>::type&
 operator=(Enum _Errcode);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Errcode`|Der Enumerationswert, der dem `error_condition`-Objekt zugewiesen wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das `error_condition`-Objekt, dem der neue Enumerationswert durch die Memberfunktion zugewiesen wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator speichert `(value_type)error` als Fehlercodewert und einen Zeiger auf [generic_category](../standard-library/system-error-functions.md#generic_category). Er gibt `*this` zurück.  
  
##  <a name="op_bool"></a> error_condition::operator bool  
 Wandelt eine Variable vom Typ `error_condition` um.  
  
```
explicit operator bool() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der boolesche Wert des Objekts `error_condition`.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator gibt einen Wert zurück, der zu `true` konvertiert werden kann, allerdings nur wenn [value](#value) nicht null entspricht. Der Rückgabetyp kann nur zu `bool` konvertiert werden, nicht zu `void *` oder zu anderen bekannten skalaren Typen.  
  
##  <a name="value"></a> error_condition::value  
 Gibt den gespeicherten Fehlercodewert zurück.  
  
```
value_type value() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der gespeicherte Fehlercodewert vom Typ [value_type](#value_type).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="value_type"></a> error_condition::value_type  
 Ein Typ, der den gespeicherten Fehlercodewert darstellt.  
  
```
typedef int value_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Typdefinition ist ein Synonym für `int`.  
  
## <a name="see-also"></a>Siehe auch  
 [error_category-Klasse](../standard-library/error-category-class.md)   
 [<system_error>](../standard-library/system-error.md)


