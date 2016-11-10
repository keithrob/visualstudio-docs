---
title: "How to: Debug an ActiveX Control"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - FSharp
  - VB
  - CSharp
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-debug
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: bbc02cf7-a7e6-44fe-99af-87a43e1d7251
caps.latest.revision: 16
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
# How to: Debug an ActiveX Control
> [!NOTE]
>  The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition. To change your settings, choose Import and Export Settings on the Tools menu. For more information, see [Customizing Development Settings in Visual Studio](assetId:///22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 To debug your ActiveX control, you must specify a container (executable) for the control to run in.  
  
### To specify a container for the debug session  
  
1.  In Solution Explorer, select the project.  
  
2.  From the **View** menu, choose **Property Pages**.  
  
3.  In the **Project Property Pages** dialog box, open the **Configuration Properties** folder, and select **Debugging**.  
  
4.  Under the **Debugging** category, locate the **Command** property.  
  
5.  Specify the path name for the container. For example, C:\Program Files\Internet Explorer\IEXPLORE.EXE.  
  
6.  If you specify Internet Explorer as the container and you are using Active Desktop, type `/new` in the **Command Arguments** box.  
  
7.  Click **OK**.  
  
     If you do not specify a container in the **Project Property Pages** dialog box, you can specify the container when you begin debugging. When you select an execution command to start debugging, the [Executable for Debugging Session Dialog Box](../VS_debugger/Executable-for-Debugging-Session-Dialog-Box.md) appears. Specify the path name of the container in the dialog box.  
  
## See Also  
 [ActiveX Controls](../Topic/ActiveX%20Controls.md)   
 [Testing Properties and Events with Test Container](../Topic/Testing%20Properties%20and%20Events%20with%20Test%20Container.md)   
 [COM and ActiveX Debugging](../VS_debugger/COM-and-ActiveX-Debugging.md)   
 [Debugging in Visual Studio](../VS_debugger/Debugging-in-Visual-Studio.md)