---
title: "LABEL (MASM)"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "Label"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LABEL directive"
ms.assetid: 39ec44e8-91e6-4f3c-8cf0-b66479974e42
caps.latest.revision: 7
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# LABEL (MASM)
Creates a new label by assigning the current location-counter value and the given `type` to *name*.  
  
## Syntax  
  
```  
  
      name LABEL type  
name LABEL [[NEAR | FAR | PROC]] PTR [[type]]   
```  
  
## See Also  
 [Directives Reference](../intrinsics/directives-reference.md)