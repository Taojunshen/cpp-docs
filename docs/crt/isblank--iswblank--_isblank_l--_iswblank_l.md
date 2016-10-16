---
title: "isblank, iswblank, _isblank_l, _iswblank_l"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "isblank"
  - "_isblank_l"
  - "iswblank"
  - "_iswblank_l"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-string-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_iswblank_l"
  - "isblank"
  - "_istblank_l"
  - "_istblank"
  - "_isblank_l"
  - "iswblank"
dev_langs: 
  - "C++"
ms.assetid: 33ce96c0-f387-411a-8283-c3d2a69e56bd
caps.latest.revision: 4
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
# isblank, iswblank, _isblank_l, _iswblank_l
Determines whether an integer represents a blank character.  
  
## Syntax  
  
```  
int isblank(  
   int c   
);  
int iswblank(  
   wint_t c   
);  
int _isblank_l(  
   int c,  
   _locale_t locale  
);  
int _iswblank_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### Parameters  
 `c`  
 Integer to test.  
  
 `locale`  
 Locale to use.  
  
## Return Value  
 Each of these routines returns nonzero if `c` is a particular representation of a space or horizontal tab character, or is one of a locale-specific set of characters that are used to separate words within a line of text. `isblank` returns a nonzero value if `c` is a space character (0x20) or horizontal tab character (0x09). The result of the test condition for the `isblank` functions depends on the `LC_CTYPE` category setting of the locale; for more information, see [setlocale, _wsetlocale](../crt/setlocale--_wsetlocale.md). The versions of these functions that do not have the `_l` suffix use the current locale for any locale-dependent behavior; the versions that do have the `_l` suffix are identical except that they use the locale that's passed in instead. For more information, see [Locale](../crt/locale.md).  
  
 `iswblank` returns a nonzero value if `c` is a wide character that corresponds to a standard space or horizontal tab character.  
  
 The behavior of `isblank` and `_isblank_l` is undefined if `c` is not EOF or in the range 0 through 0xFF, inclusive. When a debug CRT library is used and `c` is not one of these values, the functions raise an assertion.  
  
### Generic-Text Routine Mappings  
  
|TCHAR.H routine|_UNICODE & _MBCS not defined|_MBCS defined|_UNICODE defined|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istblank`|`isblank`|[_ismbcblank](../crt/8e0a5f47-ba64-4411-92a3-3c525d16e3be.md)|`iswblank`|  
|`_istblank_l`|`_isblank_l`|[_ismbcblank_l](../crt/8e0a5f47-ba64-4411-92a3-3c525d16e3be.md)|`_iswblank_l`|  
  
## Requirements  
  
|Routine|Required header|  
|-------------|---------------------|  
|`isblank`|\<ctype.h>|  
|`iswblank`|\<ctype.h> or \<wchar.h>|  
|`_isblank_l`|\<ctype.h>|  
|`_iswblank_l`|\<ctype.h> or \<wchar.h>|  
  
 For additional compatibility information, see [Compatibility](../crt/compatibility.md).  
  
## .NET Framework Equivalent  
 [System::Char::IsWhiteSpace](https://msdn.microsoft.com/en-us/library/system.char.iswhitespace.aspx)  
  
## See Also  
 [Character Classification](../crt/character-classification.md)   
 [Locale](../crt/locale.md)   
 [is, isw Routines](../crt/is--isw-routines.md)