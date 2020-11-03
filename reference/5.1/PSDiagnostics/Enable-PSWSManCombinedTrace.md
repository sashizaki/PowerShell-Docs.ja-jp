---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: f67b5d9fe8da48cca5fd4ec7d2056a4702d3ff16
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213539"
---
# <span data-ttu-id="2d348-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="2d348-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="2d348-104">概要</span><span class="sxs-lookup"><span data-stu-id="2d348-104">SYNOPSIS</span></span>
<span data-ttu-id="2d348-105">WSMan プロバイダーと PowerShell プロバイダーが有効になっている状態で、ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="2d348-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="2d348-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="2d348-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="2d348-107">Description</span><span class="sxs-lookup"><span data-stu-id="2d348-107">DESCRIPTION</span></span>

<span data-ttu-id="2d348-108">このコマンドレットは、次の PowerShell プロバイダーが有効になっているログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="2d348-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="2d348-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d348-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="2d348-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="2d348-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="2d348-111">セッションの名前は ' PSTrace ' です。</span><span class="sxs-lookup"><span data-stu-id="2d348-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="2d348-112">このコマンドレットは、コマンドレットを使用し `Start-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="2d348-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="2d348-113">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d348-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="2d348-114">例</span><span class="sxs-lookup"><span data-stu-id="2d348-114">EXAMPLES</span></span>

### <span data-ttu-id="2d348-115">例 1: 結合されたログセッションを開始する</span><span class="sxs-lookup"><span data-stu-id="2d348-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="2d348-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="2d348-116">PARAMETERS</span></span>

### <span data-ttu-id="2d348-117">-DoNotOverwriteExistingTrace</span><span class="sxs-lookup"><span data-stu-id="2d348-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="2d348-118">既定では、イベントは "$pshome \Traces\PSTrace.etl" に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="2d348-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="2d348-119">このパラメーターを使用すると、コマンドレットによって一意のファイル名 "$pshome \Traces\ PSTrace_ {guid} .etl" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="2d348-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="2d348-120">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="2d348-120">CommonParameters</span></span>

<span data-ttu-id="2d348-121">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="2d348-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="2d348-122">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d348-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="2d348-123">入力</span><span class="sxs-lookup"><span data-stu-id="2d348-123">INPUTS</span></span>

### <span data-ttu-id="2d348-124">なし</span><span class="sxs-lookup"><span data-stu-id="2d348-124">None</span></span>

## <span data-ttu-id="2d348-125">出力</span><span class="sxs-lookup"><span data-stu-id="2d348-125">OUTPUTS</span></span>

### <span data-ttu-id="2d348-126">System.Object</span><span class="sxs-lookup"><span data-stu-id="2d348-126">System.Object</span></span>

## <span data-ttu-id="2d348-127">注</span><span class="sxs-lookup"><span data-stu-id="2d348-127">NOTES</span></span>

## <span data-ttu-id="2d348-128">関連リンク</span><span class="sxs-lookup"><span data-stu-id="2d348-128">RELATED LINKS</span></span>

[<span data-ttu-id="2d348-129">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="2d348-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="2d348-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="2d348-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="2d348-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="2d348-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)
