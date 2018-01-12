---
title: Compilerfehler Fehler C3446 | Microsoft Docs
ms.custom: 
ms.date: 07/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3446
dev_langs: C++
helpviewer_keywords: C3445
ms.assetid: 33064548-24e4-46f1-beb1-476e3c3b3fbf
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 590f9b4012c7a00cb73a61b0d275ff9c5ee9cf9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3446"></a>Compilerfehler Fehler C3446  
  
>"*Klasse*': eine Standard-Memberinitialisierer ist nicht zulässig, für einen Member einer Wertklasse  
  
In Visual Studio 2015 und früher, ließ der Compiler einen Standardmember-Initialisierer für einen Member einer Wertklasse zu, ignorierte diesen aber. Standardinitialisierung einer Wertklasse initialisiert die Elemente immer auf null; ein Standardkonstruktor ist nicht zulässig. In Visual Studio 2017 lösen Standardmember-Initialisierer einen Compilerfehler aus, wie im folgenden Beispiel gezeigt:

## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3446 in Visual Studio 2017 und höher:  
  
```cpp  
// C3446.cpp  
value struct V
{
       int i = 0; // error C3446: 'V::i': a default member initializer  
                  // is not allowed for a member of a value class
       int j {0}; // C3446           
};
```  
  
Um den Fehler zu beheben, entfernen Sie den Initialisierer:  
  
```cpp  
// C3446b.cpp  
value struct V
{
       int i;  
       int j;
};
```  
  