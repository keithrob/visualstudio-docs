---
title: "Visual Basic-Specific IntelliSense"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-general
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 4dec8753-05e5-4f74-b304-5f8c4ed8723b
caps.latest.revision: 10
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
# Visual Basic-Specific IntelliSense
The Visual Basic source code editor offers the following IntelliSense features:  
  
-   Syntax tips  
  
     Syntax tips display the syntax of the statement that you are typing. This is useful for statements such as [Declare](../Topic/Declare%20Statement.md).  
  
## Automatic Completion  
  
-   Completion on various keywords  
  
     For example, if you type `goto` and a space, IntelliSense will display a list of the defined labels in a drop-down menu. Other supported keywords include `Exit`, `Implements`, `Option`, and `Declare`.  
  
-   Completion on `Enum` and `Boolean`  
  
     When a statement will refer to a member of an enumeration, IntelliSense will display a list of the members of the `Enum`. When a statement will refer to a `Boolean`, IntelliSense will display a true-false drop-down menu.  
  
 Completion can be turned off by default by deselecting **Auto list members** from the **General** property page in the **Visual Basic** folder.  
  
 You can manually invoke completion by invoking List Members, Complete Word, or ALT+RIGHT ARROW. For more information, see [Using IntelliSense](../VS_IDE/Using-IntelliSense.md).  
  
## IntelliSense in Zone  
 IntelliSense in Zone assists Visual Basic developers who need to deploy applications through ClickOnce and are constrained to partial trust settings. This feature:  
  
-   Enables you to choose the permissions the application will run with.  
  
-   Display APIs in the chosen Zone as available in List Members, and display APIs that require additional permissions as unavailable.  
  
 For more information, see [Code Access Security for ClickOnce Applications](../VS_IDE/Code-Access-Security-for-ClickOnce-Applications.md).  
  
## See Also  
 [Using IntelliSense](../VS_IDE/Using-IntelliSense.md)