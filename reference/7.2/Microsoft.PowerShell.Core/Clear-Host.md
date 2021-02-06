---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/clear-host?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-Host
ms.openlocfilehash: de7dc6027653db063311bd34e1282e3cb5294e92
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600590"
---
# <span data-ttu-id="5d6cc-102">Clear-Host</span><span class="sxs-lookup"><span data-stu-id="5d6cc-102">Clear-Host</span></span>

## <span data-ttu-id="5d6cc-103">概要</span><span class="sxs-lookup"><span data-stu-id="5d6cc-103">SYNOPSIS</span></span>

<span data-ttu-id="5d6cc-104">ホスト プログラムの表示を消去します。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-104">Clears the display in the host program.</span></span>

## <span data-ttu-id="5d6cc-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5d6cc-105">SYNTAX</span></span>

```
Clear-Host [<CommonParameters>]
```

## <span data-ttu-id="5d6cc-106">Description</span><span class="sxs-lookup"><span data-stu-id="5d6cc-106">DESCRIPTION</span></span>

<span data-ttu-id="5d6cc-107">関数は、 `Clear-Host` 蓄積されたコマンドや出力を含む、現在の表示からすべてのテキストを削除します。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-107">The `Clear-Host` function removes all text from the current display, including commands and output that might have accumulated.</span></span> <span data-ttu-id="5d6cc-108">完了すると、コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-108">When complete, it displays the command prompt.</span></span> <span data-ttu-id="5d6cc-109">関数名またはそのエイリアスであるを使用でき `cls` ます。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-109">You can use the function name or its alias, `cls`.</span></span>

<span data-ttu-id="5d6cc-110">`Clear-Host` 現在のディスプレイのみに影響します。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-110">`Clear-Host` affects only the current display.</span></span> <span data-ttu-id="5d6cc-111">保存した結果を削除したり、セッションから項目を削除したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-111">It does not delete saved results or remove any items from the session.</span></span> <span data-ttu-id="5d6cc-112">変数や関数など、セッション固有項目はこの関数で削除されません。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-112">Session-specific items, such as variables and functions, are not affected by this function.</span></span>

<span data-ttu-id="5d6cc-113">関数の動作は `Clear-Host` ホストプログラムによって決まるため、ホストプログラムによって動作が `Clear-Host` 異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-113">Because the behavior of the `Clear-Host` function is determined by the host program, `Clear-Host` might work differently in different host programs.</span></span>

## <span data-ttu-id="5d6cc-114">例</span><span class="sxs-lookup"><span data-stu-id="5d6cc-114">EXAMPLES</span></span>

### <span data-ttu-id="5d6cc-115">例 1</span><span class="sxs-lookup"><span data-stu-id="5d6cc-115">Example 1</span></span>

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

<span data-ttu-id="5d6cc-116">このコマンドは `cls` 、の別名 `Clear-Host` を使用して、現在の表示をクリアします。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-116">This command uses the `cls` alias of `Clear-Host` to clear the current display.</span></span>

## <span data-ttu-id="5d6cc-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5d6cc-117">PARAMETERS</span></span>

### <span data-ttu-id="5d6cc-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d6cc-118">CommonParameters</span></span>
<span data-ttu-id="5d6cc-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5d6cc-120">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5d6cc-121">入力</span><span class="sxs-lookup"><span data-stu-id="5d6cc-121">INPUTS</span></span>

### <span data-ttu-id="5d6cc-122">なし</span><span class="sxs-lookup"><span data-stu-id="5d6cc-122">None</span></span>

<span data-ttu-id="5d6cc-123">入力をにパイプすることはできません `Clear-Host` 。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-123">You cannot pipe input to `Clear-Host`.</span></span>

## <span data-ttu-id="5d6cc-124">出力</span><span class="sxs-lookup"><span data-stu-id="5d6cc-124">OUTPUTS</span></span>

### <span data-ttu-id="5d6cc-125">なし</span><span class="sxs-lookup"><span data-stu-id="5d6cc-125">None</span></span>

<span data-ttu-id="5d6cc-126">`Clear-Host` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-126">`Clear-Host` does not generate any output</span></span>

## <span data-ttu-id="5d6cc-127">注</span><span class="sxs-lookup"><span data-stu-id="5d6cc-127">NOTES</span></span>

<span data-ttu-id="5d6cc-128">`Clear-Host` は、高度な関数ではなく、単純な関数です。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-128">`Clear-Host` is a simple function, not an advanced function.</span></span> <span data-ttu-id="5d6cc-129">そのため、コマンドで **Debug** などの共通パラメーターを使用することはできません `Clear-Host` 。</span><span class="sxs-lookup"><span data-stu-id="5d6cc-129">As such, you cannot use common parameters, such as **Debug**, in a `Clear-Host` command.</span></span>

## <span data-ttu-id="5d6cc-130">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5d6cc-130">RELATED LINKS</span></span>

[<span data-ttu-id="5d6cc-131">Get-Host</span><span class="sxs-lookup"><span data-stu-id="5d6cc-131">Get-Host</span></span>](../Microsoft.PowerShell.Utility/Get-Host.md)

[<span data-ttu-id="5d6cc-132">Out-Host</span><span class="sxs-lookup"><span data-stu-id="5d6cc-132">Out-Host</span></span>](Out-Host.md)

[<span data-ttu-id="5d6cc-133">Read-Host</span><span class="sxs-lookup"><span data-stu-id="5d6cc-133">Read-Host</span></span>](../Microsoft.PowerShell.Utility/Read-Host.md)

[<span data-ttu-id="5d6cc-134">Write-Host</span><span class="sxs-lookup"><span data-stu-id="5d6cc-134">Write-Host</span></span>](../Microsoft.PowerShell.Utility/Write-Host.md)

