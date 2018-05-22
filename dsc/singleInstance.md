---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 単一インスタンスの DSC リソースを記述する (ベスト プラクティス)
ms.openlocfilehash: 9494964b1b13eaa082ad5cbc279b4586bb7211cc
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="writing-a-single-instance-dsc-resource-best-practice"></a><span data-ttu-id="6d4d5-103">単一インスタンスの DSC リソースを記述する (ベスト プラクティス)</span><span class="sxs-lookup"><span data-stu-id="6d4d5-103">Writing a single-instance DSC resource (best practice)</span></span>

><span data-ttu-id="6d4d5-104">**注:** このトピックでは、構成で単一のインスタンスのみを許可する DSC リソースを定義するためのベスト プラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-104">**Note:** This topic describes a best practice for defining a DSC resource that allows only a single instance in a configuration.</span></span> <span data-ttu-id="6d4d5-105">現在のところ、これを行う組み込みの DSC 機能はありません。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-105">Currently, there is no built-in DSC feature to do this.</span></span> <span data-ttu-id="6d4d5-106">これは将来変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-106">That might change in the future.</span></span>

<span data-ttu-id="6d4d5-107">構成の中で、1 つのリソースを複数回使用することを許可したくない状況があります。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-107">There are situations where you don't want to allow a resource to be used multiple times in a configuration.</span></span> <span data-ttu-id="6d4d5-108">たとえば、[xTimeZone](https://github.com/PowerShell/xTimeZone) リソースの以前の実装では、構成がリソースを複数回呼び出し、各リソース ブロックに別々のタイム ゾーンを設定する可能性がありました。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-108">For example, in a previous implementation of the [xTimeZone](https://github.com/PowerShell/xTimeZone) resource, a configuration could call the resource multiple times, setting the time zone to a different setting in each resource block:</span></span>

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

<span data-ttu-id="6d4d5-109">これは、DSC リソース キーの動作方法が原因でした。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-109">This is because of the way DSC resource keys work.</span></span> <span data-ttu-id="6d4d5-110">1 つのリソースには、少なくとも 1 つのキー プロパティが必要です。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-110">A resource must have at least one key property.</span></span> <span data-ttu-id="6d4d5-111">キー プロパティのすべての値の組み合わせが一意であれば、リソースのインスタンスは一意とみなされます。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-111">A resource instance is considered unique if the combination of the values of all of its key properties is unique.</span></span> <span data-ttu-id="6d4d5-112">リソースの以前の実装では、[xTimeZone](https://github.com/PowerShell/xTimeZone) リソースには **TimeZone** プロパティしかなかったため、このプロパティをキーにする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-112">In its previous implementation, the [xTimeZone](https://github.com/PowerShell/xTimeZone) resource had only one property--**TimeZone**, which was required to be a key.</span></span> <span data-ttu-id="6d4d5-113">このため、上記のような構成は、警告なしにコンパイルされ実行されました。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-113">Because of this, a configuration such as the one above would compile and run without warning.</span></span> <span data-ttu-id="6d4d5-114">各 **xTimeZone** リソース ブロックは、一意とみなされます。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-114">Each of the **xTimeZone** resource blocks is considered unique.</span></span> <span data-ttu-id="6d4d5-115">これにより、構成がノードに繰り返し適用され、タイムゾーンが何度も戻されたり進められたりしていました。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-115">This would cause the configuration to be repeatedly applied to the node, cycling the timezone back and forth.</span></span>

<span data-ttu-id="6d4d5-116">構成がタイムゾーンを対象のノードに 1 回だけ設定されるようにするため、リソースは、2 番目のプロパティで、キー プロパティになる **IsSingleInstance** を追加するよう更新されることになっていました。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-116">To ensure that a configuration could set the time zone for a target node only once, the resource was updated to add a second property, **IsSingleInstance**, that became the key property.</span></span>
<span data-ttu-id="6d4d5-117">**IsSingleInstance** は、**ValueMap** を使用して、単一の値 "Yes" に制限されていました。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-117">The **IsSingleInstance** was limited to a single value, "Yes" by using a **ValueMap**.</span></span> <span data-ttu-id="6d4d5-118">リソースの以前の MOF スキーマは、次のようでした。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-118">The old MOF schema for the resource was:</span></span>

```powershell
[ClassVersion("1.0.0.0"), FriendlyName("xTimeZone")]
class xTimeZone : OMI_BaseResource
{
    [Key, Description("Specifies the TimeZone.")] String TimeZone;
};
```

<span data-ttu-id="6d4d5-119">リソースの更新された MOF スキーマを、次に示します。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-119">The updated MOF schema for the resource is:</span></span>

```powershell
[ClassVersion("1.0.0.0"), FriendlyName("xTimeZone")]
class xTimeZone : OMI_BaseResource
{
    [Key, Description("Specifies the resource is a single instance, the value must be 'Yes'"), ValueMap{"Yes"}, Values{"Yes"}] String IsSingleInstance;
    [Required, Description("Specifies the TimeZone.")] String TimeZone;
};
```

<span data-ttu-id="6d4d5-120">リソース スクリプトも、新しいパラメーターを使用するよう更新されました。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-120">The resource script was also updated to use the new parameter.</span></span> <span data-ttu-id="6d4d5-121">次に示すのは、以前のリソース スクリプトです。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-121">Here is the old resource script:</span></span>

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
    [CmdletBinding(SupportsShouldProcess=$true)]
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

    if($PSCmdlet.ShouldProcess("'$TimeZone'","Replace the System Time Zone"))
    {
        try
        {
            if($CurrentTimeZone -ne $TimeZone)
            {
                Write-Verbose -Verbose "Setting the TimeZone"
                Set-TimeZone -TimeZone $TimeZone}
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

<span data-ttu-id="6d4d5-122">**TimeZone** プロパティは、もはやキーではないことにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-122">Notice that the **TimeZone** property is no longer a key.</span></span> <span data-ttu-id="6d4d5-123">現在は、構成がタイム ゾーンの設定を 2 回試みる場合 (異なる **TimeZone** 値を指定した 2 つの異なる **xTimeZone** ブロックを使用)、構成をコンパイルしようとすると、次のようにエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6d4d5-123">Now, if a configuration attempts to set the time zone twice (by using two different **xTimeZone** blocks with different **TimeZone** values), attempting to compile the configuration will cause an error:</span></span>

```powershell
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