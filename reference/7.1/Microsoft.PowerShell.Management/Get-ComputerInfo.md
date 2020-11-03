---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: c8f24d7b020a75bae121c054550c8aed2c55074f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217651"
---
# <span data-ttu-id="aae24-103">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="aae24-103">Get-ComputerInfo</span></span>

## <span data-ttu-id="aae24-104">概要</span><span class="sxs-lookup"><span data-stu-id="aae24-104">SYNOPSIS</span></span>
<span data-ttu-id="aae24-105">システムおよびオペレーティングシステムのプロパティの統合オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="aae24-105">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="aae24-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="aae24-106">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="aae24-107">Description</span><span class="sxs-lookup"><span data-stu-id="aae24-107">DESCRIPTION</span></span>

<span data-ttu-id="aae24-108">`Get-ComputerInfo`コマンドレットは、システムとオペレーティングシステムのプロパティの統合オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="aae24-108">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="aae24-109">このコマンドレットは、Windows PowerShell 5.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="aae24-109">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="aae24-110">例</span><span class="sxs-lookup"><span data-stu-id="aae24-110">EXAMPLES</span></span>

### <span data-ttu-id="aae24-111">例 1: すべてのコンピューターのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="aae24-111">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="aae24-112">このコマンドは、すべてのシステムおよびオペレーティングシステムのプロパティをコンピューターから取得します。</span><span class="sxs-lookup"><span data-stu-id="aae24-112">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="aae24-113">例 2: すべてのコンピューターのオペレーティングシステムのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="aae24-113">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="aae24-114">このコマンドは、すべてのオペレーティングシステムのプロパティをコンピューターから取得します。</span><span class="sxs-lookup"><span data-stu-id="aae24-114">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="aae24-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="aae24-115">PARAMETERS</span></span>

### <span data-ttu-id="aae24-116">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="aae24-116">-Property</span></span>

<span data-ttu-id="aae24-117">このコマンドレットによって表示されるコンピュータープロパティを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="aae24-117">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

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

### <span data-ttu-id="aae24-118">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="aae24-118">CommonParameters</span></span>

<span data-ttu-id="aae24-119">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="aae24-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="aae24-120">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aae24-120">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="aae24-121">入力</span><span class="sxs-lookup"><span data-stu-id="aae24-121">INPUTS</span></span>

### <span data-ttu-id="aae24-122">System.String[]</span><span class="sxs-lookup"><span data-stu-id="aae24-122">System.String[]</span></span>

## <span data-ttu-id="aae24-123">出力</span><span class="sxs-lookup"><span data-stu-id="aae24-123">OUTPUTS</span></span>

### <span data-ttu-id="aae24-124">Microsoft. PowerShell. 管理. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="aae24-124">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="aae24-125">注</span><span class="sxs-lookup"><span data-stu-id="aae24-125">NOTES</span></span>

## <span data-ttu-id="aae24-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="aae24-126">RELATED LINKS</span></span>

