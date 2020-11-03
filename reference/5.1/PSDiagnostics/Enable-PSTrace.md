---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 9abc91086d42ec7b813695e241820947f7fb0acc
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213544"
---
# <span data-ttu-id="463c6-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="463c6-102">Enable-PSTrace</span></span>

## <span data-ttu-id="463c6-103">概要</span><span class="sxs-lookup"><span data-stu-id="463c6-103">SYNOPSIS</span></span>
<span data-ttu-id="463c6-104">Microsoft Windows PowerShell イベントプロバイダーのログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="463c6-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="463c6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="463c6-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly]
```

## <span data-ttu-id="463c6-106">Description</span><span class="sxs-lookup"><span data-stu-id="463c6-106">DESCRIPTION</span></span>

<span data-ttu-id="463c6-107">このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを有効にします。</span><span class="sxs-lookup"><span data-stu-id="463c6-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="463c6-108">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463c6-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="463c6-109">例</span><span class="sxs-lookup"><span data-stu-id="463c6-109">EXAMPLES</span></span>

### <span data-ttu-id="463c6-110">例 1: PowerShell の分析イベントログを有効にする</span><span class="sxs-lookup"><span data-stu-id="463c6-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="463c6-111">次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを有効にします。</span><span class="sxs-lookup"><span data-stu-id="463c6-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="463c6-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="463c6-112">PARAMETERS</span></span>

### <span data-ttu-id="463c6-113">-分析のみ</span><span class="sxs-lookup"><span data-stu-id="463c6-113">-AnalyticOnly</span></span>

<span data-ttu-id="463c6-114">このパラメーターを使用すると、コマンドレットによって、Microsoft Windows PowerShell プロバイダーの分析イベントログが有効になります。</span><span class="sxs-lookup"><span data-stu-id="463c6-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="463c6-115">操作イベントログは変更されません。</span><span class="sxs-lookup"><span data-stu-id="463c6-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="463c6-116">-Force</span><span class="sxs-lookup"><span data-stu-id="463c6-116">-Force</span></span>

<span data-ttu-id="463c6-117">プロンプトを表示せずに変更を強制するために使用します。</span><span class="sxs-lookup"><span data-stu-id="463c6-117">Used to force the change without prompting.</span></span>

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

## <span data-ttu-id="463c6-118">入力</span><span class="sxs-lookup"><span data-stu-id="463c6-118">INPUTS</span></span>

### <span data-ttu-id="463c6-119">なし</span><span class="sxs-lookup"><span data-stu-id="463c6-119">None</span></span>

## <span data-ttu-id="463c6-120">出力</span><span class="sxs-lookup"><span data-stu-id="463c6-120">OUTPUTS</span></span>

### <span data-ttu-id="463c6-121">System.Object</span><span class="sxs-lookup"><span data-stu-id="463c6-121">System.Object</span></span>

## <span data-ttu-id="463c6-122">注</span><span class="sxs-lookup"><span data-stu-id="463c6-122">NOTES</span></span>

<span data-ttu-id="463c6-123">このコマンドレットは `Get-LogProperties` 、 `Set-LogProperties` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="463c6-123">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="463c6-124">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="463c6-124">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="463c6-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="463c6-125">RELATED LINKS</span></span>

[<span data-ttu-id="463c6-126">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="463c6-126">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="463c6-127">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="463c6-127">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="463c6-128">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="463c6-128">Disable-PSTrace</span></span>](Disable-PSTrace.md)
