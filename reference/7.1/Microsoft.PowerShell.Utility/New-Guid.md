---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Guid
ms.openlocfilehash: 2a289500020f069231023fbabaa5401ee0759697
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209292"
---
# <span data-ttu-id="d72e9-103">New-Guid</span><span class="sxs-lookup"><span data-stu-id="d72e9-103">New-Guid</span></span>

## <span data-ttu-id="d72e9-104">概要</span><span class="sxs-lookup"><span data-stu-id="d72e9-104">SYNOPSIS</span></span>
<span data-ttu-id="d72e9-105">GUID を作成します。</span><span class="sxs-lookup"><span data-stu-id="d72e9-105">Creates a GUID.</span></span>

## <span data-ttu-id="d72e9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d72e9-106">SYNTAX</span></span>

```
New-Guid [<CommonParameters>]
```

## <span data-ttu-id="d72e9-107">Description</span><span class="sxs-lookup"><span data-stu-id="d72e9-107">DESCRIPTION</span></span>

<span data-ttu-id="d72e9-108">**新しい guid** コマンドレットは、ランダムなグローバル一意識別子 (guid) を作成します。</span><span class="sxs-lookup"><span data-stu-id="d72e9-108">The **New-Guid** cmdlet creates a random globally unique identifier (GUID).</span></span>
<span data-ttu-id="d72e9-109">スクリプトで一意の ID が必要な場合は、必要に応じて GUID を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d72e9-109">If you need a unique ID in a script, you can create a GUID, as needed.</span></span>

## <span data-ttu-id="d72e9-110">例</span><span class="sxs-lookup"><span data-stu-id="d72e9-110">EXAMPLES</span></span>

### <span data-ttu-id="d72e9-111">例 1: GUID を作成する</span><span class="sxs-lookup"><span data-stu-id="d72e9-111">Example 1: Create a GUID</span></span>

```
PS C:\> New-Guid
Guid
----
0352cf0f-2e7a-4aee-801d-7f27f8344c77
```

<span data-ttu-id="d72e9-112">このコマンドは、ランダムな GUID を作成します。</span><span class="sxs-lookup"><span data-stu-id="d72e9-112">This command creates a random GUID.</span></span>
<span data-ttu-id="d72e9-113">または、このコマンドレットの出力を変数に格納して、スクリプト内の他の場所で使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d72e9-113">Alternatively, you could store the output of this cmdlet in a variable to use elsewhere in a script.</span></span>

## <span data-ttu-id="d72e9-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d72e9-114">PARAMETERS</span></span>

### <span data-ttu-id="d72e9-115">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d72e9-115">CommonParameters</span></span>

<span data-ttu-id="d72e9-116">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d72e9-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d72e9-117">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d72e9-117">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d72e9-118">入力</span><span class="sxs-lookup"><span data-stu-id="d72e9-118">INPUTS</span></span>

## <span data-ttu-id="d72e9-119">出力</span><span class="sxs-lookup"><span data-stu-id="d72e9-119">OUTPUTS</span></span>

### <span data-ttu-id="d72e9-120">System.Guid</span><span class="sxs-lookup"><span data-stu-id="d72e9-120">System.Guid</span></span>

<span data-ttu-id="d72e9-121">このコマンドレットは、GUID を返します。</span><span class="sxs-lookup"><span data-stu-id="d72e9-121">This cmdlet returns a GUID.</span></span>

## <span data-ttu-id="d72e9-122">注</span><span class="sxs-lookup"><span data-stu-id="d72e9-122">NOTES</span></span>

## <span data-ttu-id="d72e9-123">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d72e9-123">RELATED LINKS</span></span>

