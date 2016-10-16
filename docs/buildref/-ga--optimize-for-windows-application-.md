---
title: "-GA (Optimize for Windows Application)"
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
  - "VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication"
  - "/ga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GA compiler option [C++]"
  - "GA compiler option [C++]"
  - "-GA compiler option [C++]"
  - "Optimize for Windows compiler options"
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
caps.latest.revision: 10
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
# /GA (Optimize for Windows Application)
Results in more efficient code for an .exe file for accessing thread-local storage (TLS) variables.  
  
## Syntax  
  
```  
/GA  
```  
  
## Remarks  
 **/GA** speeds access to data declared with [__declspec(thread)](../cpp/__declspec.md) in a Windows-based program. When this option is set, the [__tls_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) macro is assumed to be 0.  
  
 Using **/GA** for a DLL can result in bad code generation.  
  
### To set this compiler option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box. For details, see [How to: Open Project Property Pages](../notintoc/how-to--open-project-property-pages.md).  
  
2.  Click the **C/C++** folder.  
  
3.  Click the **Command Line** property page.  
  
4.  Type the compiler option in the **Additional Options** box.  
  
### To set this compiler option programmatically  
  
-   See \<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## See Also  
 [Compiler Options](../buildref/compiler-options.md)   
 [Setting Compiler Options](../buildref/setting-compiler-options.md)