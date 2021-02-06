---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/29/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pswsmancombinedtrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSWSManCombinedTrace
ms.openlocfilehash: ef333edaa091e96df11a8288e9b16f133614c1e0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601216"
---
# <span data-ttu-id="f5f16-102">Enable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="f5f16-102">Enable-PSWSManCombinedTrace</span></span>

## <span data-ttu-id="f5f16-103">概要</span><span class="sxs-lookup"><span data-stu-id="f5f16-103">SYNOPSIS</span></span>
<span data-ttu-id="f5f16-104">WSMan プロバイダーと PowerShell プロバイダーが有効になっている状態で、ログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="f5f16-104">Start a logging session with the WSMan and PowerShell providers enabled.</span></span>

## <span data-ttu-id="f5f16-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f5f16-105">SYNTAX</span></span>

```
Enable-PSWSManCombinedTrace [-DoNotOverwriteExistingTrace] [<CommonParameters>]
```

## <span data-ttu-id="f5f16-106">Description</span><span class="sxs-lookup"><span data-stu-id="f5f16-106">DESCRIPTION</span></span>

<span data-ttu-id="f5f16-107">このコマンドレットは、次の PowerShell プロバイダーが有効になっているログセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="f5f16-107">This cmdlet starts a logging session with the following PowerShell providers enabled:</span></span>

- <span data-ttu-id="f5f16-108">Microsoft-Windows-PowerShell</span><span class="sxs-lookup"><span data-stu-id="f5f16-108">Microsoft-Windows-PowerShell</span></span>
- <span data-ttu-id="f5f16-109">Microsoft-Windows-WinRM</span><span class="sxs-lookup"><span data-stu-id="f5f16-109">Microsoft-Windows-WinRM</span></span>

<span data-ttu-id="f5f16-110">セッションの名前は ' PSTrace ' です。</span><span class="sxs-lookup"><span data-stu-id="f5f16-110">The session is named 'PSTrace'.</span></span>

<span data-ttu-id="f5f16-111">このコマンドレットは、コマンドレットを使用し `Start-Trace` ます。</span><span class="sxs-lookup"><span data-stu-id="f5f16-111">This cmdlet uses the `Start-Trace` cmdlet.</span></span>

<span data-ttu-id="f5f16-112">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f5f16-112">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="f5f16-113">例</span><span class="sxs-lookup"><span data-stu-id="f5f16-113">EXAMPLES</span></span>

### <span data-ttu-id="f5f16-114">例 1: 結合されたログセッションを開始する</span><span class="sxs-lookup"><span data-stu-id="f5f16-114">Example 1: Start a combined logging session</span></span>

```powershell
Enable-PSWSManCombinedTrace
```

## <span data-ttu-id="f5f16-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f5f16-115">PARAMETERS</span></span>

### <span data-ttu-id="f5f16-116">-DoNotOverwriteExistingTrace</span><span class="sxs-lookup"><span data-stu-id="f5f16-116">-DoNotOverwriteExistingTrace</span></span>

<span data-ttu-id="f5f16-117">既定では、イベントは "$pshome \Traces\PSTrace.etl" に書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="f5f16-117">By default, the events are written to "$pshome\Traces\PSTrace.etl".</span></span> <span data-ttu-id="f5f16-118">このパラメーターを使用すると、コマンドレットによって一意のファイル名 "$pshome \Traces\ PSTrace_ {guid} .etl" が作成されます。</span><span class="sxs-lookup"><span data-stu-id="f5f16-118">When this parameter is used, the cmdlet creates a unique filename: "$pshome\Traces\PSTrace_{guid}.etl"</span></span>

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

### <span data-ttu-id="f5f16-119">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f5f16-119">CommonParameters</span></span>

<span data-ttu-id="f5f16-120">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f5f16-120">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f5f16-121">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f5f16-121">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f5f16-122">入力</span><span class="sxs-lookup"><span data-stu-id="f5f16-122">INPUTS</span></span>

### <span data-ttu-id="f5f16-123">なし</span><span class="sxs-lookup"><span data-stu-id="f5f16-123">None</span></span>

## <span data-ttu-id="f5f16-124">出力</span><span class="sxs-lookup"><span data-stu-id="f5f16-124">OUTPUTS</span></span>

### <span data-ttu-id="f5f16-125">なし</span><span class="sxs-lookup"><span data-stu-id="f5f16-125">None</span></span>

## <span data-ttu-id="f5f16-126">注</span><span class="sxs-lookup"><span data-stu-id="f5f16-126">NOTES</span></span>

## <span data-ttu-id="f5f16-127">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f5f16-127">RELATED LINKS</span></span>

[<span data-ttu-id="f5f16-128">イベントのトレース</span><span class="sxs-lookup"><span data-stu-id="f5f16-128">Event Tracing</span></span>](/windows/desktop/ETW/event-tracing-portal)

[<span data-ttu-id="f5f16-129">Start-Trace</span><span class="sxs-lookup"><span data-stu-id="f5f16-129">Start-Trace</span></span>](start-trace.md)

[<span data-ttu-id="f5f16-130">Disable-PSWSManCombinedTrace</span><span class="sxs-lookup"><span data-stu-id="f5f16-130">Disable-PSWSManCombinedTrace</span></span>](Disable-PSWSManCombinedTrace.md)

