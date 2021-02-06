---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: e4d06fdd1d5a616c24a4dd7bec10ea4dadea4062
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601011"
---
# <span data-ttu-id="2fc76-102">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="2fc76-102">Start-Sleep</span></span>

## <span data-ttu-id="2fc76-103">概要</span><span class="sxs-lookup"><span data-stu-id="2fc76-103">SYNOPSIS</span></span>
<span data-ttu-id="2fc76-104">指定された期間、スクリプトまたはセッションでアクティビティを中断します。</span><span class="sxs-lookup"><span data-stu-id="2fc76-104">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="2fc76-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2fc76-105">SYNTAX</span></span>

### <span data-ttu-id="2fc76-106">秒 (既定値)</span><span class="sxs-lookup"><span data-stu-id="2fc76-106">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="2fc76-107">ミリ秒</span><span class="sxs-lookup"><span data-stu-id="2fc76-107">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="2fc76-108">Description</span><span class="sxs-lookup"><span data-stu-id="2fc76-108">DESCRIPTION</span></span>

<span data-ttu-id="2fc76-109">この `Start-Sleep` コマンドレットは、指定された期間、スクリプトまたはセッションでアクティビティを中断します。</span><span class="sxs-lookup"><span data-stu-id="2fc76-109">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="2fc76-110">操作が完了するのを待つ間、操作を繰り返す前の一時停止中など多くのタスクに使用できます。</span><span class="sxs-lookup"><span data-stu-id="2fc76-110">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="2fc76-111">例</span><span class="sxs-lookup"><span data-stu-id="2fc76-111">EXAMPLES</span></span>

### <span data-ttu-id="2fc76-112">例 1: すべてのコマンドを15秒間スリープする</span><span class="sxs-lookup"><span data-stu-id="2fc76-112">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="2fc76-113">例 2: すべてのコマンドを1.5 秒間スリープする</span><span class="sxs-lookup"><span data-stu-id="2fc76-113">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="2fc76-114">この例では、セッション内のすべてのコマンドを1秒間、または1秒間スリープ状態にします。</span><span class="sxs-lookup"><span data-stu-id="2fc76-114">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="2fc76-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2fc76-115">PARAMETERS</span></span>

### <span data-ttu-id="2fc76-116">-ミリ秒</span><span class="sxs-lookup"><span data-stu-id="2fc76-116">-Milliseconds</span></span>

<span data-ttu-id="2fc76-117">リソースをスリープ状態にする時間をミリ秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="2fc76-117">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="2fc76-118">パラメーターは **m** として省略できます。</span><span class="sxs-lookup"><span data-stu-id="2fc76-118">The parameter can be abbreviated as **m**.</span></span>

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

### <span data-ttu-id="2fc76-119">-秒</span><span class="sxs-lookup"><span data-stu-id="2fc76-119">-Seconds</span></span>

<span data-ttu-id="2fc76-120">リソースをスリープ状態にする時間を秒単位で指定します。</span><span class="sxs-lookup"><span data-stu-id="2fc76-120">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="2fc76-121">パラメーター名を省略することも、 **s** として省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="2fc76-121">You can omit the parameter name or you can abbreviate it as **s**.</span></span> <span data-ttu-id="2fc76-122">PowerShell 6.2.0 以降では、このパラメーターで小数値を受け取るようになりました。</span><span class="sxs-lookup"><span data-stu-id="2fc76-122">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

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

### <span data-ttu-id="2fc76-123">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2fc76-123">CommonParameters</span></span>

<span data-ttu-id="2fc76-124">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2fc76-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2fc76-125">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc76-125">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="2fc76-126">入力</span><span class="sxs-lookup"><span data-stu-id="2fc76-126">INPUTS</span></span>

### <span data-ttu-id="2fc76-127">System.Int32</span><span class="sxs-lookup"><span data-stu-id="2fc76-127">System.Int32</span></span>

<span data-ttu-id="2fc76-128">パイプを使用して、秒数をにパイプすることができ `Start-Sleep` ます。</span><span class="sxs-lookup"><span data-stu-id="2fc76-128">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="2fc76-129">出力</span><span class="sxs-lookup"><span data-stu-id="2fc76-129">OUTPUTS</span></span>

### <span data-ttu-id="2fc76-130">なし</span><span class="sxs-lookup"><span data-stu-id="2fc76-130">None</span></span>

<span data-ttu-id="2fc76-131">このコマンドレットによる戻り値はありません。</span><span class="sxs-lookup"><span data-stu-id="2fc76-131">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="2fc76-132">注</span><span class="sxs-lookup"><span data-stu-id="2fc76-132">NOTES</span></span>

- <span data-ttu-id="2fc76-133">また、組み込みエイリアスであるを参照することもでき `Start-Sleep` `sleep` ます。</span><span class="sxs-lookup"><span data-stu-id="2fc76-133">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="2fc76-134">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc76-134">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="2fc76-135">`Ctrl+C` から中断 `Start-Sleep` します。</span><span class="sxs-lookup"><span data-stu-id="2fc76-135">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="2fc76-136">`Ctrl+C` はから除外されません `[Threading.Thread]::Sleep` 。</span><span class="sxs-lookup"><span data-stu-id="2fc76-136">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="2fc76-137">詳細については、「 [Thread メソッド](/dotnet/api/system.threading.thread.sleep)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2fc76-137">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="2fc76-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2fc76-138">RELATED LINKS</span></span>

