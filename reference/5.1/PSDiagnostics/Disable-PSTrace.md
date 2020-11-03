---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: fc58e0bcfdd0b4ee7c7ee383b44f7d7f428c34c0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213563"
---
# <span data-ttu-id="5879e-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="5879e-102">Disable-PSTrace</span></span>

## <span data-ttu-id="5879e-103">概要</span><span class="sxs-lookup"><span data-stu-id="5879e-103">SYNOPSIS</span></span>
<span data-ttu-id="5879e-104">Microsoft Windows PowerShell イベントプロバイダーのログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5879e-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="5879e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5879e-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="5879e-106">Description</span><span class="sxs-lookup"><span data-stu-id="5879e-106">DESCRIPTION</span></span>

<span data-ttu-id="5879e-107">このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5879e-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="5879e-108">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5879e-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="5879e-109">例</span><span class="sxs-lookup"><span data-stu-id="5879e-109">EXAMPLES</span></span>

### <span data-ttu-id="5879e-110">例 1: PowerShell の分析イベントログを無効にする</span><span class="sxs-lookup"><span data-stu-id="5879e-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="5879e-111">次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5879e-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="5879e-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5879e-112">PARAMETERS</span></span>

### <span data-ttu-id="5879e-113">-分析のみ</span><span class="sxs-lookup"><span data-stu-id="5879e-113">-AnalyticOnly</span></span>

<span data-ttu-id="5879e-114">このパラメーターを使用すると、コマンドレットは、Microsoft Windows PowerShell プロバイダーの分析イベントログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="5879e-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="5879e-115">操作イベントログは変更されません。</span><span class="sxs-lookup"><span data-stu-id="5879e-115">The Operational event log is not changed.</span></span>

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

## <span data-ttu-id="5879e-116">入力</span><span class="sxs-lookup"><span data-stu-id="5879e-116">INPUTS</span></span>

### <span data-ttu-id="5879e-117">なし</span><span class="sxs-lookup"><span data-stu-id="5879e-117">None</span></span>

## <span data-ttu-id="5879e-118">出力</span><span class="sxs-lookup"><span data-stu-id="5879e-118">OUTPUTS</span></span>

### <span data-ttu-id="5879e-119">System.Object</span><span class="sxs-lookup"><span data-stu-id="5879e-119">System.Object</span></span>

## <span data-ttu-id="5879e-120">注</span><span class="sxs-lookup"><span data-stu-id="5879e-120">NOTES</span></span>

<span data-ttu-id="5879e-121">このコマンドレットは `Get-LogProperties` 、 `Set-LogProperties` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5879e-121">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="5879e-122">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5879e-122">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="5879e-123">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5879e-123">RELATED LINKS</span></span>

[<span data-ttu-id="5879e-124">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="5879e-124">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="5879e-125">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="5879e-125">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="5879e-126">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="5879e-126">Enable-PSTrace</span></span>](Enable-PSTrace.md)
