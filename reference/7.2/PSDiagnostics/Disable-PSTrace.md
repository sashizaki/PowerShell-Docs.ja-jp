---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/disable-pstrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSTrace
ms.openlocfilehash: 0e246a0e3737f4ed693ed31096fc76e878a4af54
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600813"
---
# <span data-ttu-id="1c712-102">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="1c712-102">Disable-PSTrace</span></span>

## <span data-ttu-id="1c712-103">概要</span><span class="sxs-lookup"><span data-stu-id="1c712-103">SYNOPSIS</span></span>
<span data-ttu-id="1c712-104">Microsoft Windows PowerShell イベントプロバイダーのログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1c712-104">Disables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="1c712-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1c712-105">SYNTAX</span></span>

```
Disable-PSTrace [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="1c712-106">Description</span><span class="sxs-lookup"><span data-stu-id="1c712-106">DESCRIPTION</span></span>

<span data-ttu-id="1c712-107">このコマンドレットは、Microsoft Windows PowerShell イベントプロバイダーの操作および分析イベントログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1c712-107">This cmdlet disables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="1c712-108">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c712-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="1c712-109">例</span><span class="sxs-lookup"><span data-stu-id="1c712-109">EXAMPLES</span></span>

### <span data-ttu-id="1c712-110">例 1: PowerShell の分析イベントログを無効にする</span><span class="sxs-lookup"><span data-stu-id="1c712-110">Example 1: Disable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="1c712-111">次の例では、Microsoft Windows PowerShell プロバイダーの分析イベントログのみを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1c712-111">The following example disables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Disable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="1c712-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1c712-112">PARAMETERS</span></span>

### <span data-ttu-id="1c712-113">-分析のみ</span><span class="sxs-lookup"><span data-stu-id="1c712-113">-AnalyticOnly</span></span>

<span data-ttu-id="1c712-114">このパラメーターを使用すると、コマンドレットは、Microsoft Windows PowerShell プロバイダーの分析イベントログを無効にします。</span><span class="sxs-lookup"><span data-stu-id="1c712-114">When this parameter is used, the cmdlet disables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="1c712-115">操作イベントログは変更されません。</span><span class="sxs-lookup"><span data-stu-id="1c712-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="1c712-116">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1c712-116">CommonParameters</span></span>
<span data-ttu-id="1c712-117">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="1c712-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1c712-118">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c712-118">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1c712-119">入力</span><span class="sxs-lookup"><span data-stu-id="1c712-119">INPUTS</span></span>

### <span data-ttu-id="1c712-120">なし</span><span class="sxs-lookup"><span data-stu-id="1c712-120">None</span></span>

## <span data-ttu-id="1c712-121">出力</span><span class="sxs-lookup"><span data-stu-id="1c712-121">OUTPUTS</span></span>

### <span data-ttu-id="1c712-122">なし</span><span class="sxs-lookup"><span data-stu-id="1c712-122">None</span></span>

## <span data-ttu-id="1c712-123">注</span><span class="sxs-lookup"><span data-stu-id="1c712-123">NOTES</span></span>

<span data-ttu-id="1c712-124">このコマンドレットは `Get-LogProperties` 、 `Set-LogProperties` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1c712-124">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="1c712-125">このコマンドレットは、管理者特権の PowerShell セッションから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c712-125">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="1c712-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1c712-126">RELATED LINKS</span></span>

[<span data-ttu-id="1c712-127">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="1c712-127">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="1c712-128">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="1c712-128">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="1c712-129">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="1c712-129">Enable-PSTrace</span></span>](Enable-PSTrace.md)

