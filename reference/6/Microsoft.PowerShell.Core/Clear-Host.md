---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: ''
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-host?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Host
ms.openlocfilehash: 4c0732a8d1e40cdc584839db62f61a4e9f7b618c
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209119"
---
# <span data-ttu-id="46016-103">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="46016-103">Clear-Host</span></span>

## <span data-ttu-id="46016-104">概要</span><span class="sxs-lookup"><span data-stu-id="46016-104">SYNOPSIS</span></span>

<span data-ttu-id="46016-105">ホスト プログラムの表示を消去します。</span><span class="sxs-lookup"><span data-stu-id="46016-105">Clears the display in the host program.</span></span>

## <span data-ttu-id="46016-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="46016-106">SYNTAX</span></span>

```
Clear-Host [<CommonParameters>]
```

## <span data-ttu-id="46016-107">Description</span><span class="sxs-lookup"><span data-stu-id="46016-107">DESCRIPTION</span></span>

<span data-ttu-id="46016-108">関数は、 `Clear-Host` 蓄積されたコマンドや出力を含む、現在の表示からすべてのテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="46016-108">The `Clear-Host` function removes all text from the current display, including commands and output that might have accumulated.</span></span> <span data-ttu-id="46016-109">完了すると、コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="46016-109">When complete, it displays the command prompt.</span></span> <span data-ttu-id="46016-110">関数名またはそのエイリアスであるを使用でき `cls` ます。</span><span class="sxs-lookup"><span data-stu-id="46016-110">You can use the function name or its alias, `cls`.</span></span>

<span data-ttu-id="46016-111">`Clear-Host` 現在のディスプレイのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="46016-111">`Clear-Host` affects only the current display.</span></span> <span data-ttu-id="46016-112">保存した結果を削除したり、セッションから項目を削除したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="46016-112">It does not delete saved results or remove any items from the session.</span></span> <span data-ttu-id="46016-113">変数や関数など、セッション固有項目はこの関数で削除されません。</span><span class="sxs-lookup"><span data-stu-id="46016-113">Session-specific items, such as variables and functions, are not affected by this function.</span></span>

<span data-ttu-id="46016-114">関数の動作は `Clear-Host` ホストプログラムによって決まるため、ホストプログラムによって動作が `Clear-Host` 異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="46016-114">Because the behavior of the `Clear-Host` function is determined by the host program, `Clear-Host` might work differently in different host programs.</span></span>

## <span data-ttu-id="46016-115">例</span><span class="sxs-lookup"><span data-stu-id="46016-115">EXAMPLES</span></span>

### <span data-ttu-id="46016-116">例 1</span><span class="sxs-lookup"><span data-stu-id="46016-116">Example 1</span></span>

```
# Before

PS C:\> Get-Process

Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    843      33    14428      22556    99    17.41   1688 CcmExec
     44       6     2196       4964    52     0.23    692 conhost
    646      12     2332       4896    49     1.12    388 csrss
    189      11     2860       7084   114     0.66   2896 csrss
     78      11     1876       4008    42     0.22   4000 csrss
     76       7     1848       5064    54     0.08   1028 dwm
    610      41    23952      44048   208     4.40   2080 explorer
      0       0        0         24     0               0 Idle
    182      32     7692      15980    91     0.23   3056 LogonUI
    186      25     7832      16068    91     0.27   3996 LogonUI
   1272      32    11512      20432    58    25.07    548 lsass
    267      10     3536       6736    34     0.80    556 lsm
    137      17     3520       7472    61     0.05   1220 msdtc
    447      31    70316      84476   201 1,429.67    836 MsMpEng
    265      18     7136      15628   134     2.20   3544 msseces
    248      16     6476       4076    76     0.22   1592 NisSrv
    368      25    61312      65508   614     1.78    848 powershell
    101       8     2304       6624    70     0.64   3648 rdpclip
    258      15     6804      12156    50     2.65    536 services
...

PS C:\> cls
#After

PS C:>
```

<span data-ttu-id="46016-117">このコマンドは `cls` 、の別名 `Clear-Host` を使用して、現在の表示をクリアします。</span><span class="sxs-lookup"><span data-stu-id="46016-117">This command uses the `cls` alias of `Clear-Host` to clear the current display.</span></span>

## <span data-ttu-id="46016-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="46016-118">PARAMETERS</span></span>

### <span data-ttu-id="46016-119">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="46016-119">CommonParameters</span></span>
<span data-ttu-id="46016-120">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="46016-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="46016-121">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46016-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="46016-122">入力</span><span class="sxs-lookup"><span data-stu-id="46016-122">INPUTS</span></span>

### <span data-ttu-id="46016-123">なし</span><span class="sxs-lookup"><span data-stu-id="46016-123">None</span></span>

<span data-ttu-id="46016-124">入力をにパイプすることはできません `Clear-Host` 。</span><span class="sxs-lookup"><span data-stu-id="46016-124">You cannot pipe input to `Clear-Host`.</span></span>

## <span data-ttu-id="46016-125">出力</span><span class="sxs-lookup"><span data-stu-id="46016-125">OUTPUTS</span></span>

### <span data-ttu-id="46016-126">なし</span><span class="sxs-lookup"><span data-stu-id="46016-126">None</span></span>

<span data-ttu-id="46016-127">`Clear-Host` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="46016-127">`Clear-Host` does not generate any output</span></span>

## <span data-ttu-id="46016-128">注</span><span class="sxs-lookup"><span data-stu-id="46016-128">NOTES</span></span>

<span data-ttu-id="46016-129">`Clear-Host` は、高度な関数ではなく、単純な関数です。</span><span class="sxs-lookup"><span data-stu-id="46016-129">`Clear-Host` is a simple function, not an advanced function.</span></span> <span data-ttu-id="46016-130">そのため、コマンドで **Debug** などの共通パラメーターを使用することはできません `Clear-Host` 。</span><span class="sxs-lookup"><span data-stu-id="46016-130">As such, you cannot use common parameters, such as **Debug** , in a `Clear-Host` command.</span></span>

## <span data-ttu-id="46016-131">関連リンク</span><span class="sxs-lookup"><span data-stu-id="46016-131">RELATED LINKS</span></span>

[<span data-ttu-id="46016-132">Get-Host</span><span class="sxs-lookup"><span data-stu-id="46016-132">Get-Host</span></span>](../Microsoft.PowerShell.Utility/Get-Host.md)

[<span data-ttu-id="46016-133">Out-Host</span><span class="sxs-lookup"><span data-stu-id="46016-133">Out-Host</span></span>](Out-Host.md)

[<span data-ttu-id="46016-134">Read-Host</span><span class="sxs-lookup"><span data-stu-id="46016-134">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)

[<span data-ttu-id="46016-135">Write-Host</span><span class="sxs-lookup"><span data-stu-id="46016-135">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)
