---
external help file: PSDiagnostics-help.xml
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/get-logproperties?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-LogProperties
ms.openlocfilehash: 63f9f644a81886dab498e46fce90d4ff2f7be91b
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217075"
---
# <span data-ttu-id="94db8-102">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="94db8-102">Get-LogProperties</span></span>

## <span data-ttu-id="94db8-103">概要</span><span class="sxs-lookup"><span data-stu-id="94db8-103">SYNOPSIS</span></span>
<span data-ttu-id="94db8-104">Windows イベントログのプロパティを取得します。</span><span class="sxs-lookup"><span data-stu-id="94db8-104">Retrieves the properties of a Windows event log.</span></span>

## <span data-ttu-id="94db8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="94db8-105">SYNTAX</span></span>

```
Get-LogProperties [-Name] <Object> [<CommonParameters>]
```

## <span data-ttu-id="94db8-106">Description</span><span class="sxs-lookup"><span data-stu-id="94db8-106">DESCRIPTION</span></span>

<span data-ttu-id="94db8-107">このコマンドレットは、Windows イベントログの構成設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="94db8-107">This cmdlet gets the configuration settings of a Windows event log.</span></span> <span data-ttu-id="94db8-108">このコマンドレットは、コマンドレットとコマンドレットによって使用され `Enable-PSTrace` `Disable-PSTrace` ます。</span><span class="sxs-lookup"><span data-stu-id="94db8-108">This cmdlet is used by the `Enable-PSTrace` and `Disable-PSTrace` cmdlets.</span></span>

## <span data-ttu-id="94db8-109">例</span><span class="sxs-lookup"><span data-stu-id="94db8-109">EXAMPLES</span></span>

### <span data-ttu-id="94db8-110">例 1: Windows PowerShell イベントログの構成設定を取得する</span><span class="sxs-lookup"><span data-stu-id="94db8-110">Example 1: Get the configuration settings of the Windows PowerShell event log</span></span>

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

## <span data-ttu-id="94db8-111">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="94db8-111">PARAMETERS</span></span>

### <span data-ttu-id="94db8-112">-Name</span><span class="sxs-lookup"><span data-stu-id="94db8-112">-Name</span></span>

<span data-ttu-id="94db8-113">イベントプロバイダーの名前。</span><span class="sxs-lookup"><span data-stu-id="94db8-113">The name of the event provider.</span></span>

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

### <span data-ttu-id="94db8-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="94db8-114">CommonParameters</span></span>

<span data-ttu-id="94db8-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="94db8-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="94db8-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94db8-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="94db8-117">入力</span><span class="sxs-lookup"><span data-stu-id="94db8-117">INPUTS</span></span>

### <span data-ttu-id="94db8-118">System.String</span><span class="sxs-lookup"><span data-stu-id="94db8-118">System.String</span></span>

## <span data-ttu-id="94db8-119">出力</span><span class="sxs-lookup"><span data-stu-id="94db8-119">OUTPUTS</span></span>

### <span data-ttu-id="94db8-120">Microsoft. 診断. LogDetails</span><span class="sxs-lookup"><span data-stu-id="94db8-120">Microsoft.PowerShell.Diagnostics.LogDetails</span></span>

<span data-ttu-id="94db8-121">**Psdiagnostics** モジュールは、 **logdetails** クラスを名前空間に追加し `Microsoft.PowerShell.Diagnostics` ます。</span><span class="sxs-lookup"><span data-stu-id="94db8-121">The **PSDiagnostics** module adds the **LogDetails** class to the `Microsoft.PowerShell.Diagnostics` namespace.</span></span>

## <span data-ttu-id="94db8-122">注</span><span class="sxs-lookup"><span data-stu-id="94db8-122">NOTES</span></span>

## <span data-ttu-id="94db8-123">関連リンク</span><span class="sxs-lookup"><span data-stu-id="94db8-123">RELATED LINKS</span></span>

[<span data-ttu-id="94db8-124">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="94db8-124">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="94db8-125">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="94db8-125">Enable-PSTrace</span></span>](Enable-PSTrace.md)

[<span data-ttu-id="94db8-126">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="94db8-126">Disable-PSTrace</span></span>](Disable-PSTrace.md)
