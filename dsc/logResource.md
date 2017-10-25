---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC Log リソース"
ms.openlocfilehash: 72c9c5a9b8e2a4ed4ce43cfd792572ce95b502b3
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="dsc-log-resource"></a>DSC Log リソース 

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

注: 既定では、DSC の操作ログのみが有効になります。
分析ログを利用または表示するには、最初にそれを有効にする必要があります。
次の記事を参照してください。

[DSC イベント ログの場所](https://msdn.microsoft.com/en-us/powershell/dsc/troubleshooting#where-are-dsc-event-logs)

## <a name="properties"></a>プロパティ
|  プロパティ  |  説明   | 
|---|---| 
| メッセージ| Microsoft-Windows-Desired State Configuration/Analytic イベント ログに書き込むメッセージを示します。| 
| DependsOn | このログ メッセージが書き込まれる前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。| 

## <a name="example"></a>例

次の例では、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを含める方法を示します。

> **注**: このリソースが構成されている状態で [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) を実行すると、常に **$false** が返されます。

```powershell 
Configuration logResourceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node localhost

    {
        Log LogExample
        {
            Message = "This message will appear in the Microsoft-Windows-Desired State Configuration/Analytic event log."
        }
    }
}
```

