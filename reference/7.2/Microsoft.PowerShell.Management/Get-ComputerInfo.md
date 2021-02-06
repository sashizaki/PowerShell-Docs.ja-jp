---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: abc820bd6f8f5c8cd8c6301aacee268c82161d7e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603048"
---
# <span data-ttu-id="09643-102">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="09643-102">Get-ComputerInfo</span></span>

## <span data-ttu-id="09643-103">概要</span><span class="sxs-lookup"><span data-stu-id="09643-103">SYNOPSIS</span></span>
<span data-ttu-id="09643-104">システムおよびオペレーティングシステムのプロパティの統合オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="09643-104">Gets a consolidated object of system and operating system properties.</span></span>

## <span data-ttu-id="09643-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="09643-105">SYNTAX</span></span>

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="09643-106">Description</span><span class="sxs-lookup"><span data-stu-id="09643-106">DESCRIPTION</span></span>

<span data-ttu-id="09643-107">`Get-ComputerInfo`コマンドレットは、システムとオペレーティングシステムのプロパティの統合オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="09643-107">The `Get-ComputerInfo` cmdlet gets a consolidated object of system and operating system properties.</span></span>
<span data-ttu-id="09643-108">このコマンドレットは、Windows PowerShell 5.1 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="09643-108">This cmdlet was introduced in Windows PowerShell 5.1.</span></span>

## <span data-ttu-id="09643-109">例</span><span class="sxs-lookup"><span data-stu-id="09643-109">EXAMPLES</span></span>

### <span data-ttu-id="09643-110">例 1: すべてのコンピューターのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="09643-110">Example 1: Get all computer properties</span></span>

```powershell
Get-ComputerInfo
```

<span data-ttu-id="09643-111">このコマンドは、すべてのシステムおよびオペレーティングシステムのプロパティをコンピューターから取得します。</span><span class="sxs-lookup"><span data-stu-id="09643-111">This command gets all system and operating system properties from the computer.</span></span>

### <span data-ttu-id="09643-112">例 2: すべてのコンピューターのオペレーティングシステムのプロパティを取得する</span><span class="sxs-lookup"><span data-stu-id="09643-112">Example 2: Get all computer operating system properties</span></span>

```powershell
Get-ComputerInfo -Property "os*"
```

<span data-ttu-id="09643-113">このコマンドは、すべてのオペレーティングシステムのプロパティをコンピューターから取得します。</span><span class="sxs-lookup"><span data-stu-id="09643-113">This command gets all operating system properties from the computer.</span></span>

## <span data-ttu-id="09643-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="09643-114">PARAMETERS</span></span>

### <span data-ttu-id="09643-115">-プロパティ</span><span class="sxs-lookup"><span data-stu-id="09643-115">-Property</span></span>

<span data-ttu-id="09643-116">このコマンドレットによって表示されるコンピュータープロパティを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="09643-116">Specifies, as a string array, the computer properties in which this cmdlet displays.</span></span>

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

### <span data-ttu-id="09643-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="09643-117">CommonParameters</span></span>

<span data-ttu-id="09643-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="09643-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="09643-119">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09643-119">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="09643-120">入力</span><span class="sxs-lookup"><span data-stu-id="09643-120">INPUTS</span></span>

### <span data-ttu-id="09643-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="09643-121">System.String[]</span></span>

## <span data-ttu-id="09643-122">出力</span><span class="sxs-lookup"><span data-stu-id="09643-122">OUTPUTS</span></span>

### <span data-ttu-id="09643-123">Microsoft. PowerShell. 管理. ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="09643-123">Microsoft.PowerShell.Management.ComputerInfo</span></span>

## <span data-ttu-id="09643-124">注</span><span class="sxs-lookup"><span data-stu-id="09643-124">NOTES</span></span>

<span data-ttu-id="09643-125">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="09643-125">This cmdlet is only available on Windows platforms.</span></span>

## <span data-ttu-id="09643-126">関連リンク</span><span class="sxs-lookup"><span data-stu-id="09643-126">RELATED LINKS</span></span>
