---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: b6111929a2995432ff92758ce8b014f38882792f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211760"
---
# <span data-ttu-id="0311f-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="0311f-103">Start-Sleep</span></span>

## <span data-ttu-id="0311f-104">概要</span><span class="sxs-lookup"><span data-stu-id="0311f-104">SYNOPSIS</span></span>
<span data-ttu-id="0311f-105">指定された期間、スクリプトまたはセッションでアクティビティを中断します。</span><span class="sxs-lookup"><span data-stu-id="0311f-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="0311f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0311f-106">SYNTAX</span></span>

### <span data-ttu-id="0311f-107">秒 (既定値)</span><span class="sxs-lookup"><span data-stu-id="0311f-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="0311f-108">ミリ秒</span><span class="sxs-lookup"><span data-stu-id="0311f-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="0311f-109">Description</span><span class="sxs-lookup"><span data-stu-id="0311f-109">DESCRIPTION</span></span>

<span data-ttu-id="0311f-110">この `Start-Sleep` コマンドレットは、指定された期間、スクリプトまたはセッションでアクティビティを中断します。</span><span class="sxs-lookup"><span data-stu-id="0311f-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="0311f-111">操作が完了するのを待つ間、操作を繰り返す前の一時停止中など多くのタスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="0311f-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="0311f-112">例</span><span class="sxs-lookup"><span data-stu-id="0311f-112">EXAMPLES</span></span>

### <span data-ttu-id="0311f-113">例 1: すべてのコマンドを15秒間スリープする</span><span class="sxs-lookup"><span data-stu-id="0311f-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="0311f-114">例 2: すべてのコマンドを1.5 秒間スリープする</span><span class="sxs-lookup"><span data-stu-id="0311f-114">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="0311f-115">この例では、セッション内のすべてのコマンドを1秒間、または1秒間スリープ状態にします。</span><span class="sxs-lookup"><span data-stu-id="0311f-115">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="0311f-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0311f-116">PARAMETERS</span></span>

### <span data-ttu-id="0311f-117">-ミリ秒</span><span class="sxs-lookup"><span data-stu-id="0311f-117">-Milliseconds</span></span>

<span data-ttu-id="0311f-118">リソースをスリープ状態にする時間をミリ秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="0311f-118">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="0311f-119">パラメーターは **m** として省略できます。</span><span class="sxs-lookup"><span data-stu-id="0311f-119">The parameter can be abbreviated as **m** .</span></span>

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

### <span data-ttu-id="0311f-120">-秒</span><span class="sxs-lookup"><span data-stu-id="0311f-120">-Seconds</span></span>

<span data-ttu-id="0311f-121">リソースをスリープ状態にする時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="0311f-121">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="0311f-122">パラメーター名を省略することも、 **s** として省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="0311f-122">You can omit the parameter name or you can abbreviate it as **s** .</span></span> <span data-ttu-id="0311f-123">PowerShell 6.2.0 以降では、このパラメーターで小数値を受け取るようになりました。</span><span class="sxs-lookup"><span data-stu-id="0311f-123">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

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

### <span data-ttu-id="0311f-124">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="0311f-124">CommonParameters</span></span>

<span data-ttu-id="0311f-125">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="0311f-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0311f-126">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0311f-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="0311f-127">入力</span><span class="sxs-lookup"><span data-stu-id="0311f-127">INPUTS</span></span>

### <span data-ttu-id="0311f-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="0311f-128">System.Int32</span></span>

<span data-ttu-id="0311f-129">パイプを使用して、秒数をにパイプすることができ `Start-Sleep` ます。</span><span class="sxs-lookup"><span data-stu-id="0311f-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="0311f-130">出力</span><span class="sxs-lookup"><span data-stu-id="0311f-130">OUTPUTS</span></span>

### <span data-ttu-id="0311f-131">なし</span><span class="sxs-lookup"><span data-stu-id="0311f-131">None</span></span>

<span data-ttu-id="0311f-132">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="0311f-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="0311f-133">注</span><span class="sxs-lookup"><span data-stu-id="0311f-133">NOTES</span></span>

- <span data-ttu-id="0311f-134">また、組み込みエイリアスであるを参照することもでき `Start-Sleep` `sleep` ます。</span><span class="sxs-lookup"><span data-stu-id="0311f-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="0311f-135">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0311f-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="0311f-136">`Ctrl+C` から中断 `Start-Sleep` します。</span><span class="sxs-lookup"><span data-stu-id="0311f-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="0311f-137">`Ctrl+C` はから除外されません `[Threading.Thread]::Sleep` 。</span><span class="sxs-lookup"><span data-stu-id="0311f-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="0311f-138">詳細については、「 [Thread メソッド](/dotnet/api/system.threading.thread.sleep)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0311f-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="0311f-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="0311f-139">RELATED LINKS</span></span>

