---
ms.date: 07/08/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: 単一インスタンスの DSC リソースを記述する (ベスト プラクティス)
description: この記事では、構成で単一のインスタンスのみを許可する DSC リソースを定義するためのベスト プラクティスについて説明します。
ms.openlocfilehash: 4744136b5a733c86b517b239b2c37ce57a4246f7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662642"
---
# <a name="writing-a-single-instance-dsc-resource-best-practice"></a><span data-ttu-id="d918a-104">単一インスタンスの DSC リソースを記述する (ベスト プラクティス)</span><span class="sxs-lookup"><span data-stu-id="d918a-104">Writing a single-instance DSC resource (best practice)</span></span>

> [!NOTE]
> <span data-ttu-id="d918a-105">この記事では、構成で単一のインスタンスのみを許可する DSC リソースを定義するためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d918a-105">This article describes a best practice for defining a DSC resource that allows only a single instance in a configuration.</span></span> <span data-ttu-id="d918a-106">現在のところ、これを行う組み込みの DSC 機能はありません。</span><span class="sxs-lookup"><span data-stu-id="d918a-106">Currently, there is no built-in DSC feature to do this.</span></span> <span data-ttu-id="d918a-107">これは将来変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d918a-107">That might change in the future.</span></span>

<span data-ttu-id="d918a-108">構成の中で、1 つのリソースを複数回使用することを許可したくない状況があります。</span><span class="sxs-lookup"><span data-stu-id="d918a-108">There are situations where you don't want to allow a resource to be used multiple times in a configuration.</span></span> <span data-ttu-id="d918a-109">たとえば、[xTimeZone](https://github.com/PowerShell/xTimeZone) リソースの以前の実装では、構成がリソースを複数回呼び出し、各リソース ブロックに別々のタイム ゾーンを設定する可能性がありました。</span><span class="sxs-lookup"><span data-stu-id="d918a-109">For example, in a previous implementation of the [xTimeZone](https://github.com/PowerShell/xTimeZone) resource, a configuration could call the resource multiple times, setting the time zone to a different setting in each resource block:</span></span>

```powershell
Configuration SetTimeZone
{
    Param
    (
        [String[]]$NodeName = $env:COMPUTERNAME

    )

    Import-DSCResource -ModuleName xTimeZone


    Node $NodeName
    {
         xTimeZone TimeZoneExample
         {

            TimeZone = 'Eastern Standard Time'
         }

         xTimeZone TimeZoneExample2
         {

            TimeZone = 'Pacific Standard Time'

         }

    }
}
```

<span data-ttu-id="d918a-110">これは、DSC リソース キーの動作方法が原因でした。</span><span class="sxs-lookup"><span data-stu-id="d918a-110">This is because of the way DSC resource keys work.</span></span> <span data-ttu-id="d918a-111">1 つのリソースには、少なくとも 1 つのキー プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="d918a-111">A resource must have at least one key property.</span></span> <span data-ttu-id="d918a-112">キー プロパティのすべての値の組み合わせが一意であれば、リソースのインスタンスは一意とみなされます。</span><span class="sxs-lookup"><span data-stu-id="d918a-112">A resource instance is considered unique if the combination of the values of all of its key properties is unique.</span></span> <span data-ttu-id="d918a-113">リソースの以前の実装では、 [xTimeZone](https://github.com/PowerShell/xTimeZone) リソースには **TimeZone** プロパティしかなかったため、このプロパティをキーにする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="d918a-113">In its previous implementation, the [xTimeZone](https://github.com/PowerShell/xTimeZone) resource had only one property-- **TimeZone** , which was required to be a key.</span></span> <span data-ttu-id="d918a-114">このため、上記のような構成は、警告なしにコンパイルされ実行されました。</span><span class="sxs-lookup"><span data-stu-id="d918a-114">Because of this, a configuration such as the one above would compile and run without warning.</span></span> <span data-ttu-id="d918a-115">各 **xTimeZone** リソース ブロックは、一意とみなされます。</span><span class="sxs-lookup"><span data-stu-id="d918a-115">Each of the **xTimeZone** resource blocks is considered unique.</span></span> <span data-ttu-id="d918a-116">これにより、構成がノードに繰り返し適用され、タイムゾーンが何度も戻されたり進められたりしていました。</span><span class="sxs-lookup"><span data-stu-id="d918a-116">This would cause the configuration to be repeatedly applied to the node, cycling the timezone back and forth.</span></span>

<span data-ttu-id="d918a-117">構成がタイムゾーンを対象のノードに 1 回だけ設定されるようにするため、リソースは、2 番目のプロパティで、キー プロパティになる **IsSingleInstance** を追加するよう更新されることになっていました。</span><span class="sxs-lookup"><span data-stu-id="d918a-117">To ensure that a configuration could set the time zone for a target node only once, the resource was updated to add a second property, **IsSingleInstance** , that became the key property.</span></span> <span data-ttu-id="d918a-118">**IsSingleInstance** は、 **ValueMap** を使用して、単一の値 "Yes" に制限されていました。</span><span class="sxs-lookup"><span data-stu-id="d918a-118">The **IsSingleInstance** was limited to a single value, "Yes" by using a **ValueMap**.</span></span> <span data-ttu-id="d918a-119">リソースの以前の MOF スキーマは、次のようでした。</span><span class="sxs-lookup"><span data-stu-id="d918a-119">The old MOF schema for the resource was:</span></span>

```powershell
[ClassVersion("1.0.0.0"), FriendlyName("xTimeZone")]
class xTimeZone : OMI_BaseResource
{
    [Key, Description("Specifies the TimeZone.")] String TimeZone;
};
```

<span data-ttu-id="d918a-120">リソースの更新された MOF スキーマを、次に示します。</span><span class="sxs-lookup"><span data-stu-id="d918a-120">The updated MOF schema for the resource is:</span></span>

```powershell
[ClassVersion("1.0.0.0"), FriendlyName("xTimeZone")]
class xTimeZone : OMI_BaseResource
{
    [Key, Description("Specifies the resource is a single instance, the value must be 'Yes'"), ValueMap{"Yes"}, Values{"Yes"}] String IsSingleInstance;
    [Required, Description("Specifies the TimeZone.")] String TimeZone;
};
```

<span data-ttu-id="d918a-121">リソース スクリプトも、新しいパラメーターを使用するよう更新されました。</span><span class="sxs-lookup"><span data-stu-id="d918a-121">The resource script was also updated to use the new parameter.</span></span> <span data-ttu-id="d918a-122">リソース スクリプトがどのように変更されたかを次に示します。</span><span class="sxs-lookup"><span data-stu-id="d918a-122">Here how the resource script was changed:</span></span>

```powershell
function Get-TargetResource
{
    [CmdletBinding()]
    [OutputType([Hashtable])]
    param
    (
        [parameter(Mandatory = $true)]
        [ValidateSet('Yes')]
        [String]
        $IsSingleInstance,

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $TimeZone
    )

    #Get the current TimeZone
    $CurrentTimeZone = Get-TimeZone

    $returnValue = @{
        TimeZone = $CurrentTimeZone
        IsSingleInstance = 'Yes'
    }

    #Output the target resource
    $returnValue
}

function Set-TargetResource
{
    [CmdletBinding()]
    param
    (
        [parameter(Mandatory = $true)]
        [ValidateSet('Yes')]
        [String]
        $IsSingleInstance,

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $TimeZone
    )

    #Output the result of Get-TargetResource function.
    $CurrentTimeZone = Get-TimeZone

    Write-Verbose -Message "Replace the System Time Zone to $TimeZone"

    try
    {
        if($CurrentTimeZone -ne $TimeZone)
        {
            Write-Verbose -Verbose "Setting the TimeZone"
            Set-TimeZone -TimeZone $TimeZone
        }
        else
        {
            Write-Verbose -Verbose "TimeZone already set to $TimeZone"
        }
    }
    catch
    {
        $ErrorMsg = $_.Exception.Message
        Write-Verbose -Verbose $ErrorMsg
    }
}


function Test-TargetResource
{
    [CmdletBinding()]
    [OutputType([Boolean])]
    param
    (
        [parameter(Mandatory = $true)]
        [ValidateSet('Yes')]
        [String]
        $IsSingleInstance,

        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String]
        $TimeZone
    )

    #Output from Get-TargetResource
    $CurrentTimeZone = Get-TimeZone

    if($TimeZone -eq $CurrentTimeZone)
    {
        return $true
    }
    else
    {
        return $false
    }
}

Function Get-TimeZone {
    [CmdletBinding()]
    param()

    & tzutil.exe /g
}

Function Set-TimeZone {
    [CmdletBinding()]
    param(
        [Parameter(Mandatory=$true)]
        [System.String]
        $TimeZone
    )

    try
    {
        & tzutil.exe /s $TimeZone
    }
    catch
    {
        $ErrorMsg = $_.Exception.Message
        Write-Verbose $ErrorMsg
    }
}

Export-ModuleMember -Function *-TargetResource
```

<span data-ttu-id="d918a-123">**TimeZone** プロパティは、もはやキーではないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="d918a-123">Notice that the **TimeZone** property is no longer a key.</span></span> <span data-ttu-id="d918a-124">現在は、構成がタイム ゾーンの設定を 2 回試みる場合 (異なる **TimeZone** 値を指定した 2 つの異なる **xTimeZone** ブロックを使用)、構成をコンパイルしようとすると、次のようにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d918a-124">Now, if a configuration attempts to set the time zone twice (by using two different **xTimeZone** blocks with different **TimeZone** values), attempting to compile the configuration will cause an error:</span></span>

```Output
Test-ConflictingResources : A conflict was detected between resources '[xTimeZone]TimeZoneExample (::15::10::xTimeZone)' and
'[xTimeZone]TimeZoneExample2 (::22::10::xTimeZone)' in node 'CONTOSO-CLIENT'. Resources have identical key properties but there are differences in the
following non-key properties: 'TimeZone'. Values 'Eastern Standard Time' don't match values 'Pacific Standard Time'. Please update these property
values so that they are identical in both cases.
At line:271 char:9
+         Test-ConflictingResources $keywordName $canonicalizedValue $k ...
+         ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Write-Error], InvalidOperationException
    + FullyQualifiedErrorId : ConflictingDuplicateResource,Test-ConflictingResources
Errors occurred while processing configuration 'SetTimeZone'.
At C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\PSDesiredStateConfiguration.psm1:3705 char:5
+     throw $ErrorRecord
+     ~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (SetTimeZone:String) [], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessConfiguration
```
