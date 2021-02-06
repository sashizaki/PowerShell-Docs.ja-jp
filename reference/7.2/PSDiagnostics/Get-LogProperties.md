---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: f532dd3ff46f14348437de531e80e94b192b13e8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599918"
---
# <span data-ttu-id="8a7ec-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="8a7ec-102">Get-LogProperties</span></span>

## <span data-ttu-id="8a7ec-103">概要</span><span class="sxs-lookup"><span data-stu-id="8a7ec-103">SYNOPSIS</span></span>
<span data-ttu-id="8a7ec-104">Windows イベントログのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="8a7ec-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="8a7ec-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8a7ec-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## <span data-ttu-id="8a7ec-106">Description</span><span class="sxs-lookup"><span data-stu-id="8a7ec-106">DESCRIPTION</span></span>

<span data-ttu-id="8a7ec-107">このコマンドレットは、Windows イベントログの構成設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="8a7ec-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="8a7ec-108">このコマンドレットは、コマンドレットとコマンドレットによって使用され `Enable-PSTrace` `Disable-PSTrace` ます。</span><span class="sxs-lookup"><span data-stu-id="8a7ec-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="8a7ec-109">例</span><span class="sxs-lookup"><span data-stu-id="8a7ec-109">EXAMPLES</span></span>

### <span data-ttu-id="8a7ec-110">例 1: Windows PowerShell イベントログの構成設定を取得する</span><span class="sxs-lookup"><span data-stu-id="8a7ec-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

```powershell
Get-LogProperties 'Windows PowerShell'
```

```Output
Name       : Windows PowerShell
Enabled    : True
Type       : Admin
Retention  : False
AutoBackup : False
MaxLogSize : 15728640
```

## <span data-ttu-id="8a7ec-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8a7ec-111">PARAMETERS</span></span>

### <span data-ttu-id="8a7ec-112">-Name</span><span class="sxs-lookup"><span data-stu-id="8a7ec-112">-Name</span></span>

<span data-ttu-id="8a7ec-113">イベントプロバイダーの名前。</span><span class="sxs-lookup"><span data-stu-id="8a7ec-113">The name of the event provider.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="8a7ec-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a7ec-114">CommonParameters</span></span>

<span data-ttu-id="8a7ec-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="8a7ec-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="8a7ec-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a7ec-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="8a7ec-117">入力</span><span class="sxs-lookup"><span data-stu-id="8a7ec-117">INPUTS</span></span>

### <span data-ttu-id="8a7ec-118">System.String</span><span class="sxs-lookup"><span data-stu-id="8a7ec-118">System.String</span></span>

## <span data-ttu-id="8a7ec-119">出力</span><span class="sxs-lookup"><span data-stu-id="8a7ec-119">OUTPUTS</span></span>

### <span data-ttu-id="8a7ec-120">Microsoft. 診断. LogDetails</span><span class="sxs-lookup"><span data-stu-id="8a7ec-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="8a7ec-121">**Psdiagnostics** モジュールは、 **logdetails** クラスを名前空間に追加し `Microsoft.PowerShell.Diagnostics` ます。</span><span class="sxs-lookup"><span data-stu-id="8a7ec-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="8a7ec-122">注</span><span class="sxs-lookup"><span data-stu-id="8a7ec-122">NOTES</span></span>

## <span data-ttu-id="8a7ec-123">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8a7ec-123">RELATED LINKS</span></span>

[<span data-ttu-id="8a7ec-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="8a7ec-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="8a7ec-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="8a7ec-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="8a7ec-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="8a7ec-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)

