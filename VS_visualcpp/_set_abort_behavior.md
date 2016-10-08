---
title: "_set_abort_behavior"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
  - C
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
apiname: 
  - _set_abort_behavior
apilocation: 
  - msvcrt.dll
  - msvcr80.dll
  - msvcr90.dll
  - msvcr100.dll
  - msvcr100_clr0400.dll
  - msvcr110.dll
  - msvcr110_clr0400.dll
  - msvcr120.dll
  - msvcr120_clr0400.dll
  - ucrtbase.dll
  - api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
ms.assetid: 43918766-e4ba-4b1f-80e8-1a4a910cd452
caps.latest.revision: 24
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# _set_abort_behavior
Specifies the action to be taken when a program is abnormally terminated.  
  
> [!NOTE]
>  Do not use the `abort` function to shut down a Windows 8.x Store app, except in testing or debugging scenarios. Programmatic or UI ways to close a Windows 8.x Store app are not permitted according to the [Windows 8 app certification requirements](http://go.microsoft.com/fwlink/?LinkId=262889). For more information, see [Application lifecycle (Windows Store apps)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Syntax  
  
```  
unsigned int _set_abort_behavior(  
   unsigned int flags,  
   unsigned int mask  
);  
```  
  
#### Parameters  
 [in] `flags`  
 New value of the `abort` flags.  
  
 [in] `mask`  
 Mask for the `abort` flags bits to set.  
  
## Return Value  
 The old value of the flags.  
  
## Remarks  
 There are two `abort` flags: `_WRITE_ABORT_MSG` and `_CALL_REPORTFAULT`. `_WRITE_ABORT_MSG` determines whether a helpful text message is printed when a program is abnormally terminated. The message states that the application has called the `abort` function. The default behavior is to print the message. `_CALL_REPORTFAULT`, if set, specifies that a Watson crash dump is generated and reported when `abort` is called. By default, crash dump reporting is enabled in non-DEBUG builds.  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`_set_abort_behavior`|<stdlib.h>|  
  
 For more compatibility information, see [Compatibility](../VS_visualcpp/Compatibility.md).  
  
## Example  
  
```c  
  
      // crt_set_abort_behavior.c  
// compile with: /TC  
#include <stdlib.h>  
  
int main()  
{  
   printf("Suppressing the abort message. If successful, this message"  
          " will be the only output.\n");  
   // Suppress the abort message  
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);  
   abort();  
}  
```  
  
 **Suppressing the abort message. If successful, this message will be the only output.**   
## See Also  
 [abort](../VS_visualcpp/abort.md)