---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: df7f9000cf66cebce83e3146cd5c95a7d1a78bf8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605190"
---
# <span data-ttu-id="5ded4-102">New-Guid</span><span class="sxs-lookup"><span data-stu-id="5ded4-102">New-Guid</span></span>

## <span data-ttu-id="5ded4-103">概要</span><span class="sxs-lookup"><span data-stu-id="5ded4-103">SYNOPSIS</span></span>
<span data-ttu-id="5ded4-104">GUID を作成します。</span><span class="sxs-lookup"><span data-stu-id="5ded4-104">Creates a GUID.</span></span>

## <span data-ttu-id="5ded4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5ded4-105">SYNTAX</span></span>

```
New-Guid [<CommonParameters>]
```

## <span data-ttu-id="5ded4-106">Description</span><span class="sxs-lookup"><span data-stu-id="5ded4-106">DESCRIPTION</span></span>

<span data-ttu-id="5ded4-107">**新しい guid** コマンドレットは、ランダムなグローバル一意識別子 (guid) を作成します。</span><span class="sxs-lookup"><span data-stu-id="5ded4-107">The **New-Guid** cmdlet creates a random globally unique identifier (GUID).</span></span>
<span data-ttu-id="5ded4-108">スクリプトで一意の ID が必要な場合は、必要に応じて GUID を作成できます。</span><span class="sxs-lookup"><span data-stu-id="5ded4-108">If you need a unique ID in a script, you can create a GUID, as needed.</span></span>

## <span data-ttu-id="5ded4-109">例</span><span class="sxs-lookup"><span data-stu-id="5ded4-109">EXAMPLES</span></span>

### <span data-ttu-id="5ded4-110">例 1: GUID を作成する</span><span class="sxs-lookup"><span data-stu-id="5ded4-110">Example 1: Create a GUID</span></span>

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

<span data-ttu-id="5ded4-111">このコマンドは、ランダムな GUID を作成します。</span><span class="sxs-lookup"><span data-stu-id="5ded4-111">This command creates a random GUID.</span></span>
<span data-ttu-id="5ded4-112">または、このコマンドレットの出力を変数に格納して、スクリプト内の他の場所で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ded4-112">Alternatively, you could store the output of this cmdlet in a variable to use elsewhere in a script.</span></span>

## <span data-ttu-id="5ded4-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5ded4-113">PARAMETERS</span></span>

### <span data-ttu-id="5ded4-114">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5ded4-114">CommonParameters</span></span>

<span data-ttu-id="5ded4-115">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5ded4-115">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5ded4-116">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ded4-116">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5ded4-117">入力</span><span class="sxs-lookup"><span data-stu-id="5ded4-117">INPUTS</span></span>

## <span data-ttu-id="5ded4-118">出力</span><span class="sxs-lookup"><span data-stu-id="5ded4-118">OUTPUTS</span></span>

### <span data-ttu-id="5ded4-119">System.Guid</span><span class="sxs-lookup"><span data-stu-id="5ded4-119">System.Guid</span></span>

<span data-ttu-id="5ded4-120">このコマンドレットは、GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="5ded4-120">This cmdlet returns a GUID.</span></span>

## <span data-ttu-id="5ded4-121">注</span><span class="sxs-lookup"><span data-stu-id="5ded4-121">NOTES</span></span>

## <span data-ttu-id="5ded4-122">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5ded4-122">RELATED LINKS</span></span>

