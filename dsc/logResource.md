---
title:   DSC Log リソース 
ms.date:  2016-05-16
keywords:  powershell,DSC
description:  
ms.topic:  article
author:  eslesar
manager:  dongill
ms.prod:  powershell
---

# DSC Log リソース 

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) の __Log__ リソースは、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを書き込むためのメカニズムを備えています。

```
Syntax

Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
}
```

## プロパティ
|  プロパティ  |  説明   | 
|---|---| 
| メッセージ| Microsoft-Windows-Desired State Configuration/Analytic イベント ログに書き込むメッセージを示します。| 
| DependsOn | このログ メッセージが書き込まれる前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。| 

## 例

次の例では、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを含める方法を示します。

> **注**: このリソースが構成されている状態で [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) を実行すると、常に **$false** が返されます。

```powershell 
Log LogExample
{
    Message = "This message will appear in the Microsoft-Windows-Desired State Configuration/Analytic event log."
} 
```



<!--HONumber=May16_HO3-->


