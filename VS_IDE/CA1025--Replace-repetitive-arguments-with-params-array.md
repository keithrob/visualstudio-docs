---
title: "CA1025: Replace repetitive arguments with params array"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-devops-test
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f009b340-dea3-4459-8fe1-2143aa8b5d0b
caps.latest.revision: 14
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
# CA1025: Replace repetitive arguments with params array
|||  
|-|-|  
|TypeName|ReplaceRepetitiveArgumentsWithParamsArray|  
|CheckId|CA1025|  
|Category|Microsoft.Design|  
|Breaking Change|Non-breaking|  
  
## Cause  
 A public or protected method in a public type has more than three parameters, and its last three parameters are the same type.  
  
## Rule Description  
 Use a parameter array instead of repeated arguments when the exact number of arguments is unknown and the variable arguments are the same type, or can be passed as the same type. For example, the <xref:System.Console.WriteLine?qualifyHint=False> method provides a general-purpose overload that uses a parameter array to accept any number of <xref:System.Object?qualifyHint=False> arguments.  
  
## How to Fix Violations  
 To fix a violation of this rule, replace the repeated arguments with a parameter array.  
  
## When to Suppress Warnings  
 It is always safe to suppress a warning from this rule; however, this design might cause usability issues.  
  
## Example  
 The following example shows a type that violates this rule.  
  
 [!CODE [FxCop.Design.RepeatArgs#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Design.RepeatArgs#1)]