---
ms.date: 09/20/2019
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC Log リソース
ms.openlocfilehash: a1b7bf44fbaf36a3adaf0666e9f0a754fa3f6ee1
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71954669"
---
# <a name="dsc-log-resource"></a><span data-ttu-id="6ff3c-103">DSC Log リソース</span><span class="sxs-lookup"><span data-stu-id="6ff3c-103">DSC Log Resource</span></span>

> <span data-ttu-id="6ff3c-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="6ff3c-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="6ff3c-105">Windows PowerShell Desired State Configuration (DSC) の **Log** リソースは、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを書き込むためのメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-105">The **Log** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to write messages to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ff3c-106">構文</span><span class="sxs-lookup"><span data-stu-id="6ff3c-106">Syntax</span></span>

```Syntax
Log [string] #ResourceName
{
    Message = [string]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

> [!NOTE]
> <span data-ttu-id="6ff3c-107">既定では、DSC の操作ログのみが有効になります。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-107">By default only the Operational logs for DSC are enabled.</span></span> <span data-ttu-id="6ff3c-108">分析ログを利用または表示するには、最初にそれを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-108">Before the Analytic log will be available or visible, it must be enabled.</span></span> <span data-ttu-id="6ff3c-109">詳細については、「[DSC イベント ログの場所](../../../troubleshooting/troubleshooting.md#where-are-dsc-event-logs)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-109">For more information, see [Where are DSC Event Logs?](../../../troubleshooting/troubleshooting.md#where-are-dsc-event-logs).</span></span>

## <a name="properties"></a><span data-ttu-id="6ff3c-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6ff3c-110">Properties</span></span>

|<span data-ttu-id="6ff3c-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6ff3c-111">Property</span></span> |<span data-ttu-id="6ff3c-112">説明</span><span class="sxs-lookup"><span data-stu-id="6ff3c-112">Description</span></span> |
|---|---|
|<span data-ttu-id="6ff3c-113">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6ff3c-113">Message</span></span> |<span data-ttu-id="6ff3c-114">Microsoft-Windows-Desired State Configuration/Analytic イベント ログに書き込むメッセージを示します。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-114">Indicates the message you want to write to the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="6ff3c-115">共通プロパティ</span><span class="sxs-lookup"><span data-stu-id="6ff3c-115">Common properties</span></span>

|<span data-ttu-id="6ff3c-116">プロパティ</span><span class="sxs-lookup"><span data-stu-id="6ff3c-116">Property</span></span> |<span data-ttu-id="6ff3c-117">説明</span><span class="sxs-lookup"><span data-stu-id="6ff3c-117">Description</span></span> |
|---|---|
|<span data-ttu-id="6ff3c-118">DependsOn</span><span class="sxs-lookup"><span data-stu-id="6ff3c-118">DependsOn</span></span> |<span data-ttu-id="6ff3c-119">このリソースを構成する前に、他のリソースの構成を実行する必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-119">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="6ff3c-120">たとえば、最初に実行するリソース構成スクリプト ブロックの ID が ResourceName で、そのタイプが ResourceType である場合、このプロパティを使用する構文は `DependsOn = "[ResourceType]ResourceName"` になります。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-120">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="6ff3c-121">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="6ff3c-121">PsDscRunAsCredential</span></span> |<span data-ttu-id="6ff3c-122">リソース全体を実行するための資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-122">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="6ff3c-123">**PsDscRunAsCredential** という共通プロパティは、他の資格情報という文脈の中であらゆる DSC リソースを実行するために WMF 5.0 で追加されました。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-123">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="6ff3c-124">詳細については、「[DSC リソースに対して資格情報を使用する](../../../configurations/runasuser.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-124">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="6ff3c-125">例</span><span class="sxs-lookup"><span data-stu-id="6ff3c-125">Example</span></span>

<span data-ttu-id="6ff3c-126">次の例では、Microsoft-Windows-Desired State Configuration/Analytic イベント ログにメッセージを含める方法を示します。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-126">The following example shows how to include a message in the Microsoft-Windows-Desired State Configuration/Analytic event log.</span></span>

> [!NOTE]
> <span data-ttu-id="6ff3c-127">このリソースが構成されている状態で [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) を実行すると、常に **$false** が返されます。</span><span class="sxs-lookup"><span data-stu-id="6ff3c-127">If you run [Test-DscConfiguration](https://technet.microsoft.com/en-us/library/dn407382.aspx) with this resource configured, it will always return **$false**.</span></span>

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