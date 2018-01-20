---
title: '&lt;utility&gt; | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <utility>
dev_langs: C++
helpviewer_keywords: utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cbb348ec11c9c4f832c993ad1e4799c8a39aad2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ltutilitygt"></a>&lt;utility&gt;
Definiert Typen, Funktionen und Operatoren einer C++-Standardbibliothek, mit denen Paare von Objekten erstellt und verwaltet werden können. Solche Paare von Objekten sind immer dann nützlich, wenn zwei Objekte so behandelt werden müssen, als wären sie ein Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
#include <utility>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Paare werden häufig in der C++-Standardbibliothek verwendet. Sie sind sowohl als Argumente als auch als Rückgabewerte für verschiedene Funktionen sowie als Elementtypen für Container wie [map-Klasse](../standard-library/map-class.md) und [multimap-Klasse](../standard-library/multimap-class.md) erforderlich. Der \<utility>-Header wird automatisch von \<map> eingefügt, damit deren Typelemente für Schlüssel/Wert-Paare einfacher zu verwalten sind.  
  
### <a name="classes"></a>Klassen  
  
|||  
|-|-|  
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Eine Klasse, die den Typ eines `pair`-Elements umschließt.|  
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Eine Klasse, die eine `pair`-Elementanzahl umschließt.|  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[forward](../standard-library/utility-functions.md#forward)|Verhindert durch perfektes Weiterleiten, dass der Referenztyp (entweder `lvalue` oder `rvalue`) des Arguments verdeckt wird.|  
|[get](../standard-library/utility-functions.md#get)|Eine Funktion, die ein Element aus einem `pair`-Objekt abruft.|  
|[make_pair](../standard-library/utility-functions.md#make_pair)|Eine Vorlagenhilfsfunktion, die zum Erstellen von Objekten des Typs `pair` verwendet wird, wobei die Komponententypen auf den Datentypen basieren, die als Parameter übergeben werden.|  
|[move](../standard-library/utility-functions.md#move)|Gibt das als Eingabe übergebene Argument als einen `rvalue`-Verweis zurück.|  
|[swap](../standard-library/utility-functions.md#swap)|Tauscht die Elemente zweier `pair`-Objekte.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator!=](../standard-library/utility-operators.md#op_neq)|Testet, ob das pair-Objekt links vom Operator ungleich dem pair-Objekt rechts vom Operator ist.|  
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|Testet, ob das pair-Objekt links vom Operator gleich dem pair-Objekt rechts vom Operator ist.|  
|[operator<](../standard-library/utility-operators.md#op_lt)|Testet, ob das pair-Objekt links vom Operator kleiner als das pair-Objekt rechts vom Operator ist.|  
|[operator\<=](../standard-library/utility-operators.md#op_gt_eq)|Testet, ob das pair-Objekt links vom Operator kleiner gleich dem pair-Objekt rechts vom Operator ist.|  
|[operator>](../standard-library/utility-operators.md#op_gt)|Testet, ob das pair-Objekt links vom Operator größer als das pair-Objekt rechts vom Operator ist.|  
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|Testet, ob das pair-Objekt links vom Operator größer gleich dem pair-Objekt rechts vom Operator ist.|  
  
### <a name="structs"></a>Strukturen  
  
|||  
|-|-|  
|[identity](../standard-library/identity-structure.md)||  
|[pair](../standard-library/pair-structure.md)|Ein Typ, der die Möglichkeit bietet, zwei Objekte als ein einzelnes Objekt zu behandeln.|  
  
## <a name="see-also"></a>Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)


