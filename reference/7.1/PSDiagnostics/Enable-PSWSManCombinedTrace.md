---
external help file: PSDiagnostics-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: 0999c59ab2e27b066dc6afa0b21cce029a9419e1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93211699"
---
# <span data-ttu-id="e536b-103">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e536b-103">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="e536b-104">概要</span><span class="sxs-lookup"><span data-stu-id="e536b-104">SYNOPSIS</span></span>
<span data-ttu-id="e536b-105">WSMan プロバイダーと PowerShell プロバイダーが有効になっている状態で、ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e536b-105">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="e536b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e536b-106">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="e536b-107">Description</span><span class="sxs-lookup"><span data-stu-id="e536b-107">DESCRIPTION</span></span>

<span data-ttu-id="e536b-108">このコマンドレットは、次の PowerShell プロバイダーが有効になっているログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e536b-108">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="e536b-109">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="e536b-109">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="e536b-110">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="e536b-110">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="e536b-111">セッションの名前は ' PSTrace ' です。</span><span class="sxs-lookup"><span data-stu-id="e536b-111">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="e536b-112">このコマンドレットは、コマンドレットを使用し `Start-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="e536b-112">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="e536b-113">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e536b-113">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="e536b-114">例</span><span class="sxs-lookup"><span data-stu-id="e536b-114">EXAMPLES</span></span>

### <span data-ttu-id="e536b-115">例 1: 結合されたログセッションを開始する</span><span class="sxs-lookup"><span data-stu-id="e536b-115">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="e536b-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e536b-116">PARAMETERS</span></span>

### <span data-ttu-id="e536b-117">-DoNotOverwriteExistingTrace</span><span class="sxs-lookup"><span data-stu-id="e536b-117">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="e536b-118">既定では、イベントは "$pshome \Traces\PSTrace.etl" に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="e536b-118">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="e536b-119">このパラメーターを使用すると、コマンドレットによって一意のファイル名 "$pshome \Traces\ PSTrace_ {guid} .etl" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="e536b-119">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e536b-120">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e536b-120">CommonParameters</span></span>

<span data-ttu-id="e536b-121">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e536b-121">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e536b-122">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e536b-122">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e536b-123">入力</span><span class="sxs-lookup"><span data-stu-id="e536b-123">INPUTS</span></span>

### <span data-ttu-id="e536b-124">なし</span><span class="sxs-lookup"><span data-stu-id="e536b-124">None</span></span>

## <span data-ttu-id="e536b-125">出力</span><span class="sxs-lookup"><span data-stu-id="e536b-125">OUTPUTS</span></span>

### <span data-ttu-id="e536b-126">なし</span><span class="sxs-lookup"><span data-stu-id="e536b-126">None</span></span>

## <span data-ttu-id="e536b-127">注</span><span class="sxs-lookup"><span data-stu-id="e536b-127">NOTES</span></span>

## <span data-ttu-id="e536b-128">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e536b-128">RELATED LINKS</span></span>

[<span data-ttu-id="e536b-129">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="e536b-129">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="e536b-130">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="e536b-130">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="e536b-131">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="e536b-131">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

