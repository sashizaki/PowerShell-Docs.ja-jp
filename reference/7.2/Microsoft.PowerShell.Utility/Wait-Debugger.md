---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-debugger?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Debugger
ms.openlocfilehash: a2ef114a43a63b18f5dc2d28acf7cbc0de8392bd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602403"
---
# <span data-ttu-id="2e061-102">Wait-Debugger</span><span class="sxs-lookup"><span data-stu-id="2e061-102">Wait-Debugger</span></span>

## <span data-ttu-id="2e061-103">概要</span><span class="sxs-lookup"><span data-stu-id="2e061-103">SYNOPSIS</span></span>
<span data-ttu-id="2e061-104">スクリプト内の次のステートメントを実行する前に、デバッガー内のスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="2e061-104">Stops a script in the debugger before running the next statement in the script.</span></span>

## <span data-ttu-id="2e061-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2e061-105">SYNTAX</span></span>

```
Wait-Debugger [<CommonParameters>]
```

## <span data-ttu-id="2e061-106">Description</span><span class="sxs-lookup"><span data-stu-id="2e061-106">DESCRIPTION</span></span>

<span data-ttu-id="2e061-107">コマンドレットの直後の時点で PowerShell スクリプト実行エンジンを停止 `Wait-Debugger` し、デバッガーがアタッチされるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="2e061-107">Stops the PowerShell script execution engine at the point immediately after the `Wait-Debugger` cmdlet and waits for a debugger to be attached.</span></span> <span data-ttu-id="2e061-108">これは、DSC リソースでを使用するのと似てい `Enable-RunspaceDebug -BreakAll` ますが、スクリプト内の特定のポイントでは中断します。</span><span class="sxs-lookup"><span data-stu-id="2e061-108">This is similar to using `Enable-RunspaceDebug -BreakAll` in a DSC resource but breaks at a specific point in the script.</span></span>

> [!CAUTION]
> <span data-ttu-id="2e061-109">完了後に行を削除するようにしてください `Wait-Debugger` 。</span><span class="sxs-lookup"><span data-stu-id="2e061-109">Make sure you remove the `Wait-Debugger` lines after you are done.</span></span> <span data-ttu-id="2e061-110">実行中のスクリプトは、で停止したときにハングしているように見え `Wait-Debugger` ます。</span><span class="sxs-lookup"><span data-stu-id="2e061-110">A running script appears to be hung when it is stopped at a `Wait-Debugger`.</span></span>

## <span data-ttu-id="2e061-111">例</span><span class="sxs-lookup"><span data-stu-id="2e061-111">EXAMPLES</span></span>

### <span data-ttu-id="2e061-112">例 1: デバッグ用のブレークポイントを挿入する</span><span class="sxs-lookup"><span data-stu-id="2e061-112">Example 1: Insert breakpoint for debugging</span></span>

```
[DscResource()]
class FileResource
{
    [DscProperty(Key)]
    [string] $Path

    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    [DscProperty(Mandatory)]
    [string] $SourcePath

    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime


    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if ($this.ensure -eq [Ensure]::Present)
        {
            if (! $fileExists)
            {
               $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    [bool] Test()
    {
        $present = Test-Path -LiteralPath $this.Path

        if ($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
        {
            return (! $present)
        }
    }

    [FileResource] Get()
    {
        $present = Test-Path -Path $this.Path

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }

        return $this
    }

    [void] CopyFile()
    {
        # Testing only - Remove before deployment!
        Wait-Debugger

        if (! (Test-Path -LiteralPath $this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose "Copying $($this.SourcePath) to $($this.Path)"

        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <span data-ttu-id="2e061-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2e061-113">PARAMETERS</span></span>

### <span data-ttu-id="2e061-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2e061-114">CommonParameters</span></span>

<span data-ttu-id="2e061-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2e061-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2e061-116">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e061-116">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2e061-117">入力</span><span class="sxs-lookup"><span data-stu-id="2e061-117">INPUTS</span></span>

### <span data-ttu-id="2e061-118">なし</span><span class="sxs-lookup"><span data-stu-id="2e061-118">None</span></span>

## <span data-ttu-id="2e061-119">出力</span><span class="sxs-lookup"><span data-stu-id="2e061-119">OUTPUTS</span></span>

### <span data-ttu-id="2e061-120">なし</span><span class="sxs-lookup"><span data-stu-id="2e061-120">None</span></span>

## <span data-ttu-id="2e061-121">注</span><span class="sxs-lookup"><span data-stu-id="2e061-121">NOTES</span></span>

## <span data-ttu-id="2e061-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2e061-122">RELATED LINKS</span></span>

[<span data-ttu-id="2e061-123">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="2e061-123">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)

