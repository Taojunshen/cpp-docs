---
title: "Creating the Header Control"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHeaderCtrl class, creating"
  - "header controls, creating"
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: 9
ms.author: "mblome"
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
# Creating the Header Control
The header control is not directly available in the dialog editor (although you can add a list control, which includes a header control).  
  
### To put a header control in a dialog box  
  
1.  Manually embed a member variable of type [CHeaderCtrl](../mfcref/cheaderctrl-class.md) in your dialog class.  
  
2.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md), create and set the styles for the `CHeaderCtrl`, position it, and display it.  
  
3.  Add items to the header control.  
  
4.  Use the Properties window to map handler functions in the dialog class for any header-control notification messages you need to handle (see [Mapping Messages to Functions](../mfcref/mapping-messages-to-functions.md)).  
  
### To put a header control in a view (not a CListView)  
  
1.  Embed a [CHeaderCtrl](../mfcref/cheaderctrl-class.md) object in your view class.  
  
2.  Style, position, and display the header control window in the view's [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md) member function.  
  
3.  Add items to the header control.  
  
4.  Use the Properties window to map handler functions in the view class for any header-control notification messages you need to handle (see [Mapping Messages to Functions](../mfcref/mapping-messages-to-functions.md)).  
  
 In either case, the embedded control object is created when the view or dialog object is created. Then you must call [CHeaderCtrl::Create](../Topic/CHeaderCtrl::Create.md) to create the control window. To position the control, call [CHeaderCtrl::Layout](../Topic/CHeaderCtrl::Layout.md) to determine the control's initial size and position and [SetWindowPos](../Topic/CWnd::SetWindowPos.md) to set the position you want. Then add items as described in [Adding Items to the Header Control](../mfc/adding-items-to-the-header-control.md).  
  
 For more information, see [Creating a Header Control](http://msdn.microsoft.com/library/windows/desktop/bb775238) in the [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## See Also  
 [Using CHeaderCtrl](../mfc/using-cheaderctrl.md)   
 [Controls](../mfc/controls--mfc-.md)