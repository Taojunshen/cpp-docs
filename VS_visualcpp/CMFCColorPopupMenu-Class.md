---
title: "CMFCColorPopupMenu Class"
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
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
caps.latest.revision: 15
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
# CMFCColorPopupMenu Class
Represents a pop-up menu that users use to select colors in a document or application.  
  
## Syntax  
  
```  
class CMFCColorPopupMenu : public CMFCPopupMenu  
```  
  
## Members  
  
### Public Constructors  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu__cmfccolorpopupmenu)|Constructs a `CMFCColorPopupMenu` object.|  
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|Destructor.|  
  
### Public Methods  
  
|||  
|-|-|  
|Name|Description|  
|[CMFCColorPopupMenu::CreateTearOffBar](#cmfccolorpopupmenu__createtearoffbar)|Creates a dockable tear-off color bar. (Overrides [CMFCPopupMenu::CreateTearOffBar](../VS_visualcpp/CMFCPopupMenu-Class.md#cmfcpopupmenu__createtearoffbar).)|  
|[CMFCColorPopupMenu::GetMenuBar](#cmfccolorpopupmenu__getmenubar)|Returns the [CMFCPopupMenuBar](../VS_visualcpp/CMFCPopupMenuBar-Class.md) that is embedded inside the pop-up menu. (Overrides [CMFCPopupMenu::GetMenuBar](../VS_visualcpp/CMFCPopupMenu-Class.md#cmfcpopupmenu__getmenubar).)|  
|`CMFCColorPopupMenu::GetThisClass`|Used by the framework to obtain a pointer to the [CRuntimeClass](../VS_visualcpp/CRuntimeClass-Structure.md) object that is associated with this class type.|  
|[CMFCColorPopupMenu::SetPropList](#cmfccolorpopupmenu__setproplist)|Sets the property grid control object of the embedded `CMFCColorBar` object.|  
  
### Data Members  
  
|||  
|-|-|  
|Name|Description|  
|`m_bEnabledInCustomizeMode`|A Boolean value that determines whether to show the color bar.|  
|`m_wndColorBar`|The `CMFCColorBar` object that provides color selection.|  
  
### Remarks  
 This class inherits the pop-up menu functionality of the `CMFCPopupMenu` class and manages a `CMFCColorBar` object that provides color selection. When the toolbar framework is in customization mode and the `m_bEnabledInCustomizeMode` member is set to `FALSE`, the color bar object is not shown. For more information about customization mode, see [CMFCToolBar::IsCustomizeMode](../VS_visualcpp/CMFCToolBar-Class.md#cmfctoolbar__iscustomizemode)  
  
 For more information about `CMFCColorBar`, see [CMFCColorBar Class](../VS_visualcpp/CMFCColorBar-Class.md).  
  
## Inheritance Hierarchy  
 [CObject](../VS_visualcpp/CObject-Class.md)  
  
 [CCmdTarget](../VS_visualcpp/CCmdTarget-Class.md)  
  
 [CWnd](../VS_visualcpp/CWnd-Class.md)  
  
 [CFrameWnd](../VS_visualcpp/CFrameWnd-Class.md)  
  
 [CMiniFrameWnd](../VS_visualcpp/CMiniFrameWnd-Class.md)  
  
 [CMFCPopupMenu](../VS_visualcpp/CMFCPopupMenu-Class.md)  
  
 [CMFCColorPopupMenu](../VS_visualcpp/CMFCColorPopupMenu-Class.md)  
  
## Requirements  
 **Header:** afxcolorpopupmenu.h  
  
##  <a name="cmfccolorpopupmenu__cmfccolorpopupmenu"></a>  CMFCColorPopupMenu::CMFCColorPopupMenu  
 Constructs a `CMFCColorPopupMenu` object.  
  
```  
CMFCColorPopupMenu(  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    int nHorzDockRows,  
    int nVertDockColumns,  
    COLORREF colorAutomatic,  
    UINT uiCommandID,  
    BOOL bStdColorDlg = FALSE);  
  
CMFCColorPopupMenu(  
    CMFCColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic );  
  
CMFCColorPopupMenu(  
    CMFCRibbonColorButton* pParentBtn,  
    const CArray<COLORREF, COLORREF>& colors,  
    COLORREF color,  
    LPCTSTR lpszAutoColor,  
    LPCTSTR lpszOtherColor,  
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,  
    int nColumns,  
    COLORREF colorAutomatic,  
    UINT nID );  
```  
  
### Parameters  
 [in] `colors`  
 An array of colors that the framework displays on the pop-up menu.  
  
 [in] `color`  
 The default selected color.  
  
 [in] `lpszAutoColor`  
 The text label of the *automatic* (default) color button, or `NULL`.  
  
 The standard label for the automatic button is **Automatic**.  
  
 [in] `lpszOtherColor`  
 The text label of the *other* button, which displays more color choices, or `NULL`.  
  
 The standard label for the other button is **More Colors...**.  
  
 [in] `lpszDocColors`  
 The text label of the document colors button. The document colors palette lists all the colors that the document currently uses.  
  
 [in] `lstDocColors`  
 A list of colors that the document currently uses.  
  
 [in] `nColumns`  
 The number of columns that the array of colors has.  
  
 [in] `nHorzDockRows`  
 The number of rows that the color bar has when it is docked horizontally.  
  
 [in] `nVertDockColumns`  
 The number of columns that the color bar has when it is docked vertically.  
  
 [in] `colorAutomatic`  
 The default color that the framework applies when you click the automatic button.  
  
 [in] `uiCommandID`  
 The color bar control command ID.  
  
 [in] `bStdColorDlg`  
 A Boolean that indicates whether to show the standard system color dialog box or the [CMFCColorDialog](../VS_visualcpp/CMFCColorDialog-Class.md) dialog box.  
  
 [in] `pParentBtn`  
 A pointer to a parent button.  
  
 [in] `nID`  
 The command ID.  
  
### Remarks  
 Each overloaded constructor sets the `m_bEnabledInCustomizeMode` member to `FALSE`.  
  
### Example  
 The following example demonstrates how to construct a `CMFCColorPopupMenu` object.  
  
 [!CODE [NVC_MFC_RibbonApp#34](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_RibbonApp#34)]  
  
##  <a name="cmfccolorpopupmenu__createtearoffbar"></a>  CMFCColorPopupMenu::CreateTearOffBar  
 Creates a dockable tear-off color bar.  
  
```  
virtual CPane* CreateTearOffBar(  
    CFrameWnd* pWndMain,  
    UINT uiID,  
    LPCTSTR lpszName );  
```  
  
### Parameters  
  
|||  
|-|-|  
|Parameter|Description|  
|[in] `pWndMain`|Pointer to the parent window of the tear-off bar.|  
|[in] `uiID`|The command ID of the tear-off bar.|  
|[in] `lpszName`|The window text of the tear-off bar.|  
  
### Return Value  
 A pointer to the new tear-off control bar object.  
  
### Remarks  
 This method creates a [CMFCColorBar Class](../VS_visualcpp/CMFCColorBar-Class.md) object and casts it to a [CPane Class](../VS_visualcpp/CPane-Class.md) pointer. You can cast this value back to a [CMFCColorBar Class](../VS_visualcpp/CMFCColorBar-Class.md) pointer by using one of the casting macros described in [Type Casting of MFC Class Objects](../VS_visualcpp/Type-Casting-of-MFC-Class-Objects.md).  
  
##  <a name="cmfccolorpopupmenu__getmenubar"></a>  CMFCColorPopupMenu::GetMenuBar  
 Returns the [CMFCPopupMenuBar](../VS_visualcpp/CMFCPopupMenuBar-Class.md) that is embedded inside the pop-up menu.  
  
```  
virtual CMFCPopupMenuBar* GetMenuBar();  
```  
  
### Return Value  
 A pointer to the embedded `CMFCPopupMenuBar`.  
  
### Remarks  
 The color pop-up menu has an embedded [CMFCPopupMenuBar Class](../VS_visualcpp/CMFCPopupMenuBar-Class.md) object. Override this method in a derived class if your application uses a different embedded type.  
  
##  <a name="cmfccolorpopupmenu__setproplist"></a>  CMFCColorPopupMenu::SetPropList  
 Sets the property grid control object of the embedded `CMFCColorBar` object.  
  
```  
void SetPropList( CMFCPropertyGridCtrl* pWndList );  
```  
  
### Parameters  
 [in] `pWndList`  
 Pointer to a property grid control object.  
  
## See Also  
 [Hierarchy Chart](../VS_visualcpp/Hierarchy-Chart.md)   
 [Classes](../VS_visualcpp/MFC-Classes.md)