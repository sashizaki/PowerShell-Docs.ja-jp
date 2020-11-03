---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 03/01/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: 2d91c36c6fd6d2e1281fdadf95c3b83e27c36f60
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93217723"
---
# <span data-ttu-id="a10ef-102">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a10ef-102">Get-ExperimentalFeature</span></span>

## <span data-ttu-id="a10ef-103">概要</span><span class="sxs-lookup"><span data-stu-id="a10ef-103">SYNOPSIS</span></span>
<span data-ttu-id="a10ef-104">試験的な機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="a10ef-104">Gets experimental features.</span></span>

## <span data-ttu-id="a10ef-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a10ef-105">SYNTAX</span></span>

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="a10ef-106">Description</span><span class="sxs-lookup"><span data-stu-id="a10ef-106">DESCRIPTION</span></span>

<span data-ttu-id="a10ef-107">`Get-ExperimentalFeature`コマンドレットは、PowerShell によって検出されたすべての試験的な機能を返します。</span><span class="sxs-lookup"><span data-stu-id="a10ef-107">The `Get-ExperimentalFeature` cmdlet returns all experimental features discovered by PowerShell.</span></span>
<span data-ttu-id="a10ef-108">試験的な機能は、モジュールまたは PowerShell エンジンから取得できます。</span><span class="sxs-lookup"><span data-stu-id="a10ef-108">Experimental features can come from modules or the PowerShell engine.</span></span> <span data-ttu-id="a10ef-109">試験的な機能を使用すると、ユーザーは新しい機能を安全にテストし、(通常は GitHub 経由で) フィードバックを提供する前に、設計が完了したと見なされ、変更が重大な変更になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a10ef-109">Experimental features allow users to safely test new features and provide feedback (typically via GitHub) before the design is considered complete and any changes can become a breaking change.</span></span>

## <span data-ttu-id="a10ef-110">例</span><span class="sxs-lookup"><span data-stu-id="a10ef-110">EXAMPLES</span></span>

### <span data-ttu-id="a10ef-111">例 1</span><span class="sxs-lookup"><span data-stu-id="a10ef-111">Example 1</span></span>

<span data-ttu-id="a10ef-112">現在登録されている試験的な機能とその現在の状態の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="a10ef-112">Gets the list of currently registered experimental features and their current state.</span></span>

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## <span data-ttu-id="a10ef-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a10ef-113">PARAMETERS</span></span>

### <span data-ttu-id="a10ef-114">-Name</span><span class="sxs-lookup"><span data-stu-id="a10ef-114">-Name</span></span>

<span data-ttu-id="a10ef-115">返される特定の実験的な機能の名前または名前。</span><span class="sxs-lookup"><span data-stu-id="a10ef-115">Name or names of specific experimental features to return.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a10ef-116">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a10ef-116">CommonParameters</span></span>

<span data-ttu-id="a10ef-117">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a10ef-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a10ef-118">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a10ef-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a10ef-119">入力</span><span class="sxs-lookup"><span data-stu-id="a10ef-119">INPUTS</span></span>

### <span data-ttu-id="a10ef-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="a10ef-120">System.String[]</span></span>

<span data-ttu-id="a10ef-121">返される試験的な機能の名前または名前。</span><span class="sxs-lookup"><span data-stu-id="a10ef-121">Name or names of experimental features to return.</span></span>

## <span data-ttu-id="a10ef-122">出力</span><span class="sxs-lookup"><span data-stu-id="a10ef-122">OUTPUTS</span></span>

### <span data-ttu-id="a10ef-123">ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a10ef-123">ExperimentalFeature</span></span>

<span data-ttu-id="a10ef-124">名前が指定されていない場合は、要求された名前またはすべての試験的な機能に一致するインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="a10ef-124">Returns instances that match the requested names or all experimental features if no name is specified.</span></span>

## <span data-ttu-id="a10ef-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a10ef-125">RELATED LINKS</span></span>

[<span data-ttu-id="a10ef-126">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a10ef-126">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="a10ef-127">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="a10ef-127">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)

