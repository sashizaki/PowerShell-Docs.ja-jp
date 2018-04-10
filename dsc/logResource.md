---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Log リソース
ms.openlocfilehash: f1a528767508d4a0e7f0ea2e58fd27a6a4d7ec75
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="dsc-log-resource"></a><span data-ttu-id="970ca-103">DSC Log リソース</span><span class="sxs-lookup"><span data-stu-id="970ca-103">DSC Log Resource</span></span>

> <span data-ttu-id="970ca-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="970ca-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="970ca-105">Windows PowerShell Desired State Configuration (DSC) の __Log__ リソースは、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを書き込むためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="970ca-105">The __Log__ resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to write messages to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

```
Syntax

Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
}
```

<span data-ttu-id="970ca-106">注: 既定では、DSC の操作ログのみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="970ca-106">NOTE: By default only the Operational logs for DSC are enabled.</span></span>
<span data-ttu-id="970ca-107">分析ログを利用または表示するには、最初にそれを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="970ca-107">Before the Analytic log will be available or visible, it must be enabled.</span></span>
<span data-ttu-id="970ca-108">次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="970ca-108">See the following article.</span></span>

[<span data-ttu-id="970ca-109">DSC イベント ログの場所</span><span class="sxs-lookup"><span data-stu-id="970ca-109">Where are DSC Event Logs?</span></span>](https://msdn.microsoft.com/en-us/powershell/dsc/troubleshooting#where-are-dsc-event-logs)

## <a name="properties"></a><span data-ttu-id="970ca-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="970ca-110">Properties</span></span>
|  <span data-ttu-id="970ca-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="970ca-111">Property</span></span>  |  <span data-ttu-id="970ca-112">説明</span><span class="sxs-lookup"><span data-stu-id="970ca-112">Description</span></span>   |
|---|---|
| <span data-ttu-id="970ca-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="970ca-113">Message</span></span>| <span data-ttu-id="970ca-114">Microsoft-Windows-Desired State Configuration/Analytic イベント ログに書き込むメッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="970ca-114">Indicates the message you want to write to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>|
| <span data-ttu-id="970ca-115">DependsOn</span><span class="sxs-lookup"><span data-stu-id="970ca-115">DependsOn</span></span> | <span data-ttu-id="970ca-116">このログ メッセージが書き込まれる前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="970ca-116">Indicates that the configuration of another resource must run before this log message gets written.</span></span> <span data-ttu-id="970ca-117">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が __ResourceName__ で、そのタイプが __ResourceType__ である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="970ca-117">For example, if the ID of the resource configuration script block that you want to run first is __ResourceName__ and its type is __ResourceType__, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span>|

## <a name="example"></a><span data-ttu-id="970ca-118">例</span><span class="sxs-lookup"><span data-stu-id="970ca-118">Example</span></span>

<span data-ttu-id="970ca-119">次の例では、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを含める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="970ca-119">The following example shows how to include a message in the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

> <span data-ttu-id="970ca-120">**注**: このリソースが構成されている状態で [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) を実行すると、常に **$false** が返されます。</span><span class="sxs-lookup"><span data-stu-id="970ca-120">**Note**: if you run [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) with this resource configured, it will always return **$false**.</span></span>

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