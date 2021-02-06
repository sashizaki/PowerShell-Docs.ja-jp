---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-tracesource?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-TraceSource
ms.openlocfilehash: c196d00359c9b20b5dc1fefc0ab2b94655703f6f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602781"
---
# <span data-ttu-id="2178a-102">Get-TraceSource</span><span class="sxs-lookup"><span data-stu-id="2178a-102">Get-TraceSource</span></span>

## <span data-ttu-id="2178a-103">概要</span><span class="sxs-lookup"><span data-stu-id="2178a-103">SYNOPSIS</span></span>
<span data-ttu-id="2178a-104">トレース用にインストルメント化された PowerShell コンポーネントを取得します。</span><span class="sxs-lookup"><span data-stu-id="2178a-104">Gets PowerShell components that are instrumented for tracing.</span></span>

## <span data-ttu-id="2178a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2178a-105">SYNTAX</span></span>

```
Get-TraceSource [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="2178a-106">Description</span><span class="sxs-lookup"><span data-stu-id="2178a-106">DESCRIPTION</span></span>

<span data-ttu-id="2178a-107">**Get TraceSource** コマンドレットは、現在使用されている PowerShell コンポーネントのトレースソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="2178a-107">The **Get-TraceSource** cmdlet gets the trace sources for PowerShell components that are currently in use.</span></span>
<span data-ttu-id="2178a-108">データを使用して、トレースできる PowerShell コンポーネントを決定できます。</span><span class="sxs-lookup"><span data-stu-id="2178a-108">You can use the data to determine which PowerShell components you can trace.</span></span>
<span data-ttu-id="2178a-109">トレースを行うと、コンポーネントは、内部処理の各手順について詳細なメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="2178a-109">When tracing, the component generates detailed messages about each step in its internal processing.</span></span>
<span data-ttu-id="2178a-110">開発者は、トレース データを使用して、データ フロー、プログラム実行、およびエラーを監視できます。</span><span class="sxs-lookup"><span data-stu-id="2178a-110">Developers use the trace data to monitor data flow, program execution, and errors.</span></span>

<span data-ttu-id="2178a-111">トレースコマンドレットは、PowerShell 開発者向けに設計されていますが、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="2178a-111">The tracing cmdlets were designed for PowerShell developers, but they are available to all users.</span></span>

## <span data-ttu-id="2178a-112">例</span><span class="sxs-lookup"><span data-stu-id="2178a-112">EXAMPLES</span></span>

### <span data-ttu-id="2178a-113">例 1: 名前でトレースソースを取得する</span><span class="sxs-lookup"><span data-stu-id="2178a-113">Example 1: Get trace sources by name</span></span>

```
PS C:\> Get-TraceSource -Name "*provider*"
```

<span data-ttu-id="2178a-114">このコマンドは、プロバイダーを含む名前を持つすべてのトレースソースを取得します。</span><span class="sxs-lookup"><span data-stu-id="2178a-114">This command gets all of the trace sources that have names that include provider.</span></span>

### <span data-ttu-id="2178a-115">例 2: すべてのトレースソースを取得する</span><span class="sxs-lookup"><span data-stu-id="2178a-115">Example 2: Get all trace sources</span></span>

```
PS C:\> Get-TraceSource
```

<span data-ttu-id="2178a-116">このコマンドは、トレース可能なすべての PowerShell コンポーネントを取得します。</span><span class="sxs-lookup"><span data-stu-id="2178a-116">This command gets all of the PowerShell components that can be traced.</span></span>

## <span data-ttu-id="2178a-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2178a-117">PARAMETERS</span></span>

### <span data-ttu-id="2178a-118">-Name</span><span class="sxs-lookup"><span data-stu-id="2178a-118">-Name</span></span>

<span data-ttu-id="2178a-119">取得するトレースソースを指定します。</span><span class="sxs-lookup"><span data-stu-id="2178a-119">Specifies the trace sources to get.</span></span>
<span data-ttu-id="2178a-120">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2178a-120">Wildcards are permitted.</span></span>
<span data-ttu-id="2178a-121">パラメーター *名は省略可能です。*</span><span class="sxs-lookup"><span data-stu-id="2178a-121">The parameter name *Name* is optional.</span></span>

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

### <span data-ttu-id="2178a-122">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2178a-122">CommonParameters</span></span>

<span data-ttu-id="2178a-123">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2178a-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2178a-124">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2178a-124">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2178a-125">入力</span><span class="sxs-lookup"><span data-stu-id="2178a-125">INPUTS</span></span>

### <span data-ttu-id="2178a-126">System.String</span><span class="sxs-lookup"><span data-stu-id="2178a-126">System.String</span></span>

<span data-ttu-id="2178a-127">パイプを使用してトレースソースの名前を含む文字列を **取得** することができます。</span><span class="sxs-lookup"><span data-stu-id="2178a-127">You can pipe a string that contains the name of a trace source to **Get-TraceSource**.</span></span>

## <span data-ttu-id="2178a-128">出力</span><span class="sxs-lookup"><span data-stu-id="2178a-128">OUTPUTS</span></span>

### <span data-ttu-id="2178a-129">System.management.automation.pstracesource (システム管理)</span><span class="sxs-lookup"><span data-stu-id="2178a-129">System.Management.Automation.PSTraceSource</span></span>

<span data-ttu-id="2178a-130">**Get TraceSource** は、トレースソースを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="2178a-130">**Get-TraceSource** returns objects that represent the trace sources.</span></span>

## <span data-ttu-id="2178a-131">注</span><span class="sxs-lookup"><span data-stu-id="2178a-131">NOTES</span></span>

## <span data-ttu-id="2178a-132">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2178a-132">RELATED LINKS</span></span>

[<span data-ttu-id="2178a-133">Set-TraceSource</span><span class="sxs-lookup"><span data-stu-id="2178a-133">Set-TraceSource</span></span>](Set-TraceSource.md)

[<span data-ttu-id="2178a-134">Trace-Command</span><span class="sxs-lookup"><span data-stu-id="2178a-134">Trace-Command</span></span>](Trace-Command.md)

