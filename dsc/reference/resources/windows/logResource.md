---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Log リソース
ms.openlocfilehash: 1f94a2d847a4ef63f81e2fb83d1a0f76f5677b09
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047641"
---
# <a name="dsc-log-resource"></a><span data-ttu-id="79629-103">DSC Log リソース</span><span class="sxs-lookup"><span data-stu-id="79629-103">DSC Log Resource</span></span>

> <span data-ttu-id="79629-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0_</span><span class="sxs-lookup"><span data-stu-id="79629-104">_Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0_</span></span>

<span data-ttu-id="79629-105">Windows PowerShell Desired State Configuration (DSC) の __Log__ リソースは、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを書き込むためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="79629-105">The __Log__ resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to write messages to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

```
Syntax

Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
}
```

> [!NOTE]
> <span data-ttu-id="79629-106">既定では、DSC の操作ログのみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="79629-106">By default only the Operational logs for DSC are enabled.</span></span> <span data-ttu-id="79629-107">分析ログを利用または表示するには、最初にそれを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="79629-107">Before the Analytic log will be available or visible, it must be enabled.</span></span> <span data-ttu-id="79629-108">詳細については、「[DSC イベント ログの場所](../../../troubleshooting/troubleshooting.md#where-are-dsc-event-logs)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="79629-108">For more information, see [Where are DSC Event Logs?](../../../troubleshooting/troubleshooting.md#where-are-dsc-event-logs).</span></span>

## <a name="properties"></a><span data-ttu-id="79629-109">プロパティ</span><span class="sxs-lookup"><span data-stu-id="79629-109">Properties</span></span>

| <span data-ttu-id="79629-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="79629-110">Property</span></span> | <span data-ttu-id="79629-111">説明</span><span class="sxs-lookup"><span data-stu-id="79629-111">Description</span></span> |
| --- | --- |
| <span data-ttu-id="79629-112">メッセージ</span><span class="sxs-lookup"><span data-stu-id="79629-112">Message</span></span>| <span data-ttu-id="79629-113">Microsoft-Windows-Desired State Configuration/Analytic イベント ログに書き込むメッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="79629-113">Indicates the message you want to write to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>|
| <span data-ttu-id="79629-114">DependsOn</span><span class="sxs-lookup"><span data-stu-id="79629-114">DependsOn</span></span> | <span data-ttu-id="79629-115">このログ メッセージが書き込まれる前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="79629-115">Indicates that the configuration of another resource must run before this log message gets written.</span></span> <span data-ttu-id="79629-116">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が **ResourceName** で、そのタイプが **ResourceType** である場合、このプロパティを使用する構文は `DependsOn = '[ResourceType]ResourceName'` になります。</span><span class="sxs-lookup"><span data-stu-id="79629-116">For example, if the ID of the resource configuration script block that you want to run first is **ResourceName** and its type is **ResourceType**, the syntax for using this property is `DependsOn = '[ResourceType]ResourceName'`.</span></span>|

## <a name="example"></a><span data-ttu-id="79629-117">例</span><span class="sxs-lookup"><span data-stu-id="79629-117">Example</span></span>

<span data-ttu-id="79629-118">次の例では、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを含める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79629-118">The following example shows how to include a message in the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

> [!NOTE]
> <span data-ttu-id="79629-119">このリソースが構成されている状態で [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) を実行すると、常に **$false** が返されます。</span><span class="sxs-lookup"><span data-stu-id="79629-119">If you run [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) with this resource configured, it will always return **$false**.</span></span>

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
