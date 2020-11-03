---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: 535cad057db406eaa48259288e34da6da4ed1cbb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210147"
---
# <span data-ttu-id="fb89a-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="fb89a-103">Start-Sleep</span></span>

## <span data-ttu-id="fb89a-104">概要</span><span class="sxs-lookup"><span data-stu-id="fb89a-104">SYNOPSIS</span></span>
<span data-ttu-id="fb89a-105">指定された期間、スクリプトまたはセッションでアクティビティを中断します。</span><span class="sxs-lookup"><span data-stu-id="fb89a-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="fb89a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="fb89a-106">SYNTAX</span></span>

### <span data-ttu-id="fb89a-107">秒 (既定値)</span><span class="sxs-lookup"><span data-stu-id="fb89a-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="fb89a-108">ミリ秒</span><span class="sxs-lookup"><span data-stu-id="fb89a-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="fb89a-109">Description</span><span class="sxs-lookup"><span data-stu-id="fb89a-109">DESCRIPTION</span></span>

<span data-ttu-id="fb89a-110">この `Start-Sleep` コマンドレットは、指定された期間、スクリプトまたはセッションでアクティビティを中断します。</span><span class="sxs-lookup"><span data-stu-id="fb89a-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="fb89a-111">操作が完了するのを待つ間、操作を繰り返す前の一時停止中など多くのタスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="fb89a-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="fb89a-112">例</span><span class="sxs-lookup"><span data-stu-id="fb89a-112">EXAMPLES</span></span>

### <span data-ttu-id="fb89a-113">例 1: すべてのコマンドを15秒間スリープする</span><span class="sxs-lookup"><span data-stu-id="fb89a-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="fb89a-114">例 2: すべてのコマンドを1.5 秒間スリープする</span><span class="sxs-lookup"><span data-stu-id="fb89a-114">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="fb89a-115">この例では、セッション内のすべてのコマンドを1秒間、または1秒間スリープ状態にします。</span><span class="sxs-lookup"><span data-stu-id="fb89a-115">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="fb89a-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="fb89a-116">PARAMETERS</span></span>

### <span data-ttu-id="fb89a-117">-ミリ秒</span><span class="sxs-lookup"><span data-stu-id="fb89a-117">-Milliseconds</span></span>

<span data-ttu-id="fb89a-118">リソースをスリープ状態にする時間をミリ秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89a-118">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="fb89a-119">パラメーターは **m** として省略できます。</span><span class="sxs-lookup"><span data-stu-id="fb89a-119">The parameter can be abbreviated as **m** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases: ms

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="fb89a-120">-秒</span><span class="sxs-lookup"><span data-stu-id="fb89a-120">-Seconds</span></span>

<span data-ttu-id="fb89a-121">リソースをスリープ状態にする時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="fb89a-121">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="fb89a-122">パラメーター名を省略することも、 **s** として省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb89a-122">You can omit the parameter name or you can abbreviate it as **s** .</span></span> <span data-ttu-id="fb89a-123">PowerShell 6.2.0 以降では、このパラメーターで小数値を受け取るようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb89a-123">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

```yaml
Type: System.Double
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="fb89a-124">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb89a-124">CommonParameters</span></span>

<span data-ttu-id="fb89a-125">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="fb89a-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="fb89a-126">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb89a-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="fb89a-127">入力</span><span class="sxs-lookup"><span data-stu-id="fb89a-127">INPUTS</span></span>

### <span data-ttu-id="fb89a-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="fb89a-128">System.Int32</span></span>

<span data-ttu-id="fb89a-129">パイプを使用して、秒数をにパイプすることができ `Start-Sleep` ます。</span><span class="sxs-lookup"><span data-stu-id="fb89a-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="fb89a-130">出力</span><span class="sxs-lookup"><span data-stu-id="fb89a-130">OUTPUTS</span></span>

### <span data-ttu-id="fb89a-131">なし</span><span class="sxs-lookup"><span data-stu-id="fb89a-131">None</span></span>

<span data-ttu-id="fb89a-132">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="fb89a-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="fb89a-133">注</span><span class="sxs-lookup"><span data-stu-id="fb89a-133">NOTES</span></span>

- <span data-ttu-id="fb89a-134">また、組み込みエイリアスであるを参照することもでき `Start-Sleep` `sleep` ます。</span><span class="sxs-lookup"><span data-stu-id="fb89a-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="fb89a-135">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb89a-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="fb89a-136">`Ctrl+C` から中断 `Start-Sleep` します。</span><span class="sxs-lookup"><span data-stu-id="fb89a-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="fb89a-137">`Ctrl+C` はから除外されません `[Threading.Thread]::Sleep` 。</span><span class="sxs-lookup"><span data-stu-id="fb89a-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="fb89a-138">詳細については、「 [Thread メソッド](/dotnet/api/system.threading.thread.sleep)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb89a-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="fb89a-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fb89a-139">RELATED LINKS</span></span>