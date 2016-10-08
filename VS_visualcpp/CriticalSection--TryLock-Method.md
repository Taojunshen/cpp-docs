---
title: "CriticalSection::TryLock Method"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: reference
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
caps.latest.revision: 3
manager: ghogen
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# CriticalSection::TryLock Method
Attempts to enter a critical section without blocking. If the call is successful, the calling thread takes ownership of the critical section.  
  
## Syntax  
  
```  
SyncLock TryLock();  
  
static SyncLock TryLock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### Parameters  
 `cs`  
 A user-specified critical section object.  
  
## Return Value  
 A nonzero value if the critical section is successfully entered or the current thread already owns the critical section. Zero if another thread already owns the critical section.  
  
## Remarks  
 The first **TryLock** function affects the current critical section object. The second **TryLock** function affects a user-specified critical section.  
  
## Requirements  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## See Also  
 [CriticalSection Class](../VS_visualcpp/CriticalSection-Class.md)