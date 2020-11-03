---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: 7d57e7cff0dc3ca0eff36dbe38e240efdd324060
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213931"
---
# <span data-ttu-id="5c49f-103">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="5c49f-103">Get-TraceSource</span></span>

## <span data-ttu-id="5c49f-104">概要</span><span class="sxs-lookup"><span data-stu-id="5c49f-104">SYNOPSIS</span></span>
<span data-ttu-id="5c49f-105">トレース用にインストルメント化された PowerShell コンポーネントを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c49f-105">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="5c49f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5c49f-106">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="5c49f-107">Description</span><span class="sxs-lookup"><span data-stu-id="5c49f-107">DESCRIPTION</span></span>

<span data-ttu-id="5c49f-108">**Get TraceSource** コマンドレットは、現在使用されている PowerShell コンポーネントのトレースソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c49f-108">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="5c49f-109">データを使用して、トレースできる PowerShell コンポーネントを決定できます。</span><span class="sxs-lookup"><span data-stu-id="5c49f-109">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="5c49f-110">トレースを行うと、コンポーネントは、内部処理の各手順について詳細なメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="5c49f-110">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="5c49f-111">開発者は、トレース データを使用して、データ フロー、プログラム実行、およびエラーを監視できます。</span><span class="sxs-lookup"><span data-stu-id="5c49f-111">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="5c49f-112">トレースコマンドレットは、PowerShell 開発者向けに設計されていますが、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c49f-112">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="5c49f-113">例</span><span class="sxs-lookup"><span data-stu-id="5c49f-113">EXAMPLES</span></span>

### <span data-ttu-id="5c49f-114">例 1: 名前でトレースソースを取得する</span><span class="sxs-lookup"><span data-stu-id="5c49f-114">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="5c49f-115">このコマンドは、プロバイダーを含む名前を持つすべてのトレースソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c49f-115">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="5c49f-116">例 2: すべてのトレースソースを取得する</span><span class="sxs-lookup"><span data-stu-id="5c49f-116">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="5c49f-117">このコマンドは、トレース可能なすべての PowerShell コンポーネントを取得します。</span><span class="sxs-lookup"><span data-stu-id="5c49f-117">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="5c49f-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5c49f-118">PARAMETERS</span></span>

### <span data-ttu-id="5c49f-119">-Name</span><span class="sxs-lookup"><span data-stu-id="5c49f-119">-Name</span></span>

<span data-ttu-id="5c49f-120">取得するトレースソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="5c49f-120">Specifies the trace sources to get.</span></span>
<span data-ttu-id="5c49f-121">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c49f-121">Wildcards are permitted.</span></span>
<span data-ttu-id="5c49f-122">パラメーター *名は省略可能です。*</span><span class="sxs-lookup"><span data-stu-id="5c49f-122">The parameter name *Name* is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="5c49f-123">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5c49f-123">CommonParameters</span></span>

<span data-ttu-id="5c49f-124">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5c49f-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5c49f-125">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c49f-125">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5c49f-126">入力</span><span class="sxs-lookup"><span data-stu-id="5c49f-126">INPUTS</span></span>

### <span data-ttu-id="5c49f-127">System.String</span><span class="sxs-lookup"><span data-stu-id="5c49f-127">System.String</span></span>

<span data-ttu-id="5c49f-128">パイプを使用してトレースソースの名前を含む文字列を **取得** することができます。</span><span class="sxs-lookup"><span data-stu-id="5c49f-128">You can pipe a string that contains the name of a trace source to **Get-TraceSource** .</span></span>

## <span data-ttu-id="5c49f-129">出力</span><span class="sxs-lookup"><span data-stu-id="5c49f-129">OUTPUTS</span></span>

### <span data-ttu-id="5c49f-130">System.management.automation.pstracesource (システム管理)</span><span class="sxs-lookup"><span data-stu-id="5c49f-130">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="5c49f-131">**Get TraceSource** は、トレースソースを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5c49f-131">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="5c49f-132">注</span><span class="sxs-lookup"><span data-stu-id="5c49f-132">NOTES</span></span>

## <span data-ttu-id="5c49f-133">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5c49f-133">RELATED LINKS</span></span>

[<span data-ttu-id="5c49f-134">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="5c49f-134">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="5c49f-135">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="5c49f-135">Trace-Command</span></span>](Trace-Command.md)
