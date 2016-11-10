---
title: "Type arguments for extension method &#39;&lt;methodName&gt;&#39; defined in &#39;&lt;typeName&gt;&#39; could not be inferred from the delegate &#39;&lt;delagateName&gt;&#39;"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 2bb9ca8d-7293-40e9-9285-e20b8254b3af
caps.latest.revision: 7
manager: douge
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
# Type arguments for extension method &#39;&lt;methodName&gt;&#39; defined in &#39;&lt;typeName&gt;&#39; could not be inferred from the delegate &#39;&lt;delagateName&gt;&#39;
An assignment statement uses `AddressOf` to assign the address of a generic extension method to a delegate, but it does not supply any type arguments to the extension method.  
  
 Normally, when you invoke a generic method, you supply a type argument for each type parameter that the generic method defines. If you do not supply any type arguments, the compiler attempts to infer the types to be passed to the type parameters. If the context does not provide enough information for the compiler to infer the types, an error is generated.  
  
 **Error ID:** BC36581  
  
### To correct this error  
  
-   In the `AddressOf` expression, specify the type arguments for the extension method.  
  
## See Also  
 [Generic Types in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [AddressOf Operator](../Topic/AddressOf%20Operator%20\(Visual%20Basic\).md)   
 [Generic Procedures in Visual Basic](../Topic/Generic%20Procedures%20in%20Visual%20Basic.md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Extension Methods](../Topic/Extension%20Methods%20\(Visual%20Basic\).md)