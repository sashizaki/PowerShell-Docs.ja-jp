---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Log リソース
ms.openlocfilehash: 50fd6cd31ba426108830fcf124a767318060a95d
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39268434"
---
# <a name="dsc-log-resource"></a>DSC Log リソース

_適用対象: Windows PowerShell 4.0、Windows PowerShell 5.0_

Windows PowerShell Desired State Configuration (DSC) の __Log__ リソースは、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを書き込むためのメカニズムを備えています。

```
Syntax

Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
}
```

> [!NOTE]
> 既定では、DSC の操作ログのみが有効になります。 分析ログを利用または表示するには、最初にそれを有効にする必要があります。 詳細については、「[DSC イベント ログの場所](troubleshooting.md#where-are-dsc-event-logs)」をご覧ください。

## <a name="properties"></a>プロパティ

| プロパティ | 説明 |
| --- | --- |
| メッセージ| Microsoft-Windows-Desired State Configuration/Analytic イベント ログに書き込むメッセージを示します。|
| DependsOn | このログ メッセージが書き込まれる前に、他のリソースの構成を実行する必要があることを示します。 たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = '[ResourceType]ResourceName'` になります。|

## <a name="example"></a>例

次の例では、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを含める方法を示します。

> [!NOTE]
> このリソースが構成されている状態で [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) を実行すると、常に **$false** が返されます。

```powershell
Configuration logResourceTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node localhost
    {
        Log LogExample
        {
            Message = 'This message will appear in the Microsoft-Windows-Desired State Configuration/Analytic event log.'
        }
    }
}
```