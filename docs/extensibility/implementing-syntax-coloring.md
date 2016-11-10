---
title: "Implementing Syntax Coloring"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "syntax coloring, implementing"
  - "editors [Visual Studio SDK], colorizing text"
  - "text, colorizing in editors"
ms.assetid: 96e762ca-efd0-41e7-8958-fda4897c8c7a
caps.latest.revision: 20
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
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
# Implementing Syntax Coloring
When the language service provides syntax colorization, the parser converts a line of text into an array of colorable items and returns token types corresponding to these colorable items. The parser should return token types that belong to a list of colorable items. [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] displays each colorable item in the code window according to the attributes assigned by the colorizer object to the appropriate token type.  
  
 [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] does not specify a parser interface, and parser implementation is completely up to you. However, a default parser implementation is provided in the Visual Studio Language Package project. For managed code, the managed package framework (MPF) provides complete support for colorizing text.  
  
 Legacy language services are implemented as part of a VSPackage, but the newer way to implement language service features is to use MEF extensions. To find out more about the new way to implement syntax coloring, see [Walkthrough: Highlighting Text](../extensibility/walkthrough--highlighting-text.md).  
  
> [!NOTE]
>  We recommend that you begin to use the new editor API as soon as possible. This will improve the performance of your language service and let you take advantage of new editor features.  
  
## Steps Followed by an Editor to Colorize Text  
  
1.  The editor gets the colorizer by calling the \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo.GetColorizer*> method on the \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLanguageInfo> object.  
  
2.  The editor calls the \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.GetStateMaintenanceFlag*> method to determine whether the colorizer needs the state of each line to be maintained outside the colorizer.  
  
3.  If the colorizer requires the state to be maintained outside the colorizer, the editor calls the \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.GetStartState*> method to get the state of the first line.  
  
4.  For each line in the buffer, the editor calls the \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine*> method, which performs the following steps:  
  
    1.  The line of text is passed to a scanner to convert the text into tokens. Each token specifies the token text and the token type.  
  
    2.  The token type is converted into an index into a colorable items list.  
  
    3.  The token information is used to fill in an array such that each element of the array corresponds to a character in the line. The values stored in the array are the indexes into the colorable items list.  
  
    4.  The state at the end of the line is returned for each line.  
  
5.  If the colorizer requires the state to be maintained, the editor caches the state for that line.  
  
6.  The editor renders the line of text using the information returned from the \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine*> method. This requires the following steps:  
  
    1.  For each character in the line, get the colorable item index.  
  
    2.  If using the default colorable items, access the editor's colorable items list.  
  
    3.  Otherwise, call the language service's \<xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems.GetColorableItem*> method to obtain a colorable item.  
  
    4.  Use the information in the colorable item to render the text into the display.  
  
## Managed Package Framework Colorizer  
 The managed package framework (MPF) provides all the classes that are required to implement a colorizer. Your language service class should inherit the \<xref:Microsoft.VisualStudio.Package.LanguageService> class and implement the required methods. You must supply a scanner and parser by implementing the \<xref:Microsoft.VisualStudio.Package.IScanner> interface, and return an instance of that interface from the \<xref:Microsoft.VisualStudio.Package.LanguageService.GetScanner*> method (one of the methods that must be implemented in the \<xref:Microsoft.VisualStudio.Package.LanguageService> class). For more information, see [Syntax Colorizing in a Legacy Language Service](../extensibility/syntax-colorizing-in-a-legacy-language-service.md).  
  
## See Also  
 [How to: Use Built-In Colorable Items](../extensibility/how-to--use-built-in-colorable-items.md)   
 [Custom Colorable Items](../extensibility/custom-colorable-items.md)   
 [Developing a Legacy Language Service](../extensibility/developing-a-legacy-language-service.md)   
 [Syntax Colorizing in a Legacy Language Service](../extensibility/syntax-colorizing-in-a-legacy-language-service.md)