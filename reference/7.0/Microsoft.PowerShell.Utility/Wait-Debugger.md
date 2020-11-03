---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-debugger?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Debugger
ms.openlocfilehash: f1488f65cf5ce48efe9d6459952653ff6570aa25
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209352"
---
# <span data-ttu-id="8b454-103">Wait-Debugger</span><span class="sxs-lookup"><span data-stu-id="8b454-103">Wait-Debugger</span></span>

## <span data-ttu-id="8b454-104">概要</span><span class="sxs-lookup"><span data-stu-id="8b454-104">SYNOPSIS</span></span>
<span data-ttu-id="8b454-105">スクリプト内の次のステートメントを実行する前に、デバッガー内のスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="8b454-105">Stops a script in the debugger before running the next statement in the script.</span></span>

## <span data-ttu-id="8b454-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8b454-106">SYNTAX</span></span>

```
Wait-Debugger [<CommonParameters>]
```

## <span data-ttu-id="8b454-107">Description</span><span class="sxs-lookup"><span data-stu-id="8b454-107">DESCRIPTION</span></span>

<span data-ttu-id="8b454-108">コマンドレットの直後の時点で PowerShell スクリプト実行エンジンを停止 `Wait-Debugger` し、デバッガーがアタッチされるまで待機します。</span><span class="sxs-lookup"><span data-stu-id="8b454-108">Stops the PowerShell script execution engine at the point immediately after the `Wait-Debugger` cmdlet and waits for a debugger to be attached.</span></span> <span data-ttu-id="8b454-109">これは、DSC リソースでを使用するのと似てい `Enable-RunspaceDebug -BreakAll` ますが、スクリプト内の特定のポイントでは中断します。</span><span class="sxs-lookup"><span data-stu-id="8b454-109">This is similar to using `Enable-RunspaceDebug -BreakAll` in a DSC resource but breaks at a specific point in the script.</span></span>

> [!CAUTION]
> <span data-ttu-id="8b454-110">完了後に行を削除するようにしてください `Wait-Debugger` 。</span><span class="sxs-lookup"><span data-stu-id="8b454-110">Make sure you remove the `Wait-Debugger` lines after you are done.</span></span> <span data-ttu-id="8b454-111">実行中のスクリプトは、で停止したときにハングしているように見え `Wait-Debugger` ます。</span><span class="sxs-lookup"><span data-stu-id="8b454-111">A running script appears to be hung when it is stopped at a `Wait-Debugger`.</span></span>

## <span data-ttu-id="8b454-112">例</span><span class="sxs-lookup"><span data-stu-id="8b454-112">EXAMPLES</span></span>

### <span data-ttu-id="8b454-113">例 1: デバッグ用のブレークポイントを挿入する</span><span class="sxs-lookup"><span data-stu-id="8b454-113">Example 1: Insert breakpoint for debugging</span></span>

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

## <span data-ttu-id="8b454-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8b454-114">PARAMETERS</span></span>

### <span data-ttu-id="8b454-115">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8b454-115">CommonParameters</span></span>

<span data-ttu-id="8b454-116">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8b454-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8b454-117">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b454-117">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="8b454-118">入力</span><span class="sxs-lookup"><span data-stu-id="8b454-118">INPUTS</span></span>

### <span data-ttu-id="8b454-119">なし</span><span class="sxs-lookup"><span data-stu-id="8b454-119">None</span></span>

## <span data-ttu-id="8b454-120">出力</span><span class="sxs-lookup"><span data-stu-id="8b454-120">OUTPUTS</span></span>

### <span data-ttu-id="8b454-121">なし</span><span class="sxs-lookup"><span data-stu-id="8b454-121">None</span></span>

## <span data-ttu-id="8b454-122">注</span><span class="sxs-lookup"><span data-stu-id="8b454-122">NOTES</span></span>

## <span data-ttu-id="8b454-123">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8b454-123">RELATED LINKS</span></span>

[<span data-ttu-id="8b454-124">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="8b454-124">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)