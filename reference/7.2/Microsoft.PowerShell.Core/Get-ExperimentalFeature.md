---
external help file: System.Management.Automation.dll-Help.xml
Module Name: Microsoft.PowerShell.Core
ms.date: 01/26/2021
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/get-experimentalfeature?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ExperimentalFeature
ms.openlocfilehash: aad634bb0a917d418aa9c7fa295a53fda280b8a3
ms.sourcegitcommit: 11880ca974fe2df308191c9f6dcdfe0b89c2dc67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "99601999"
---
# <span data-ttu-id="6ea99-102">Get-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="6ea99-102">Get-ExperimentalFeature</span></span>

## <span data-ttu-id="6ea99-103">概要</span><span class="sxs-lookup"><span data-stu-id="6ea99-103">SYNOPSIS</span></span>
<span data-ttu-id="6ea99-104">試験的な機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="6ea99-104">Gets experimental features.</span></span>

## <span data-ttu-id="6ea99-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6ea99-105">SYNTAX</span></span>

```
Get-ExperimentalFeature [[-Name] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="6ea99-106">Description</span><span class="sxs-lookup"><span data-stu-id="6ea99-106">DESCRIPTION</span></span>

<span data-ttu-id="6ea99-107">`Get-ExperimentalFeature`コマンドレットは、PowerShell によって検出されたすべての試験的な機能を返します。</span><span class="sxs-lookup"><span data-stu-id="6ea99-107">The `Get-ExperimentalFeature` cmdlet returns all experimental features discovered by PowerShell.</span></span>
<span data-ttu-id="6ea99-108">試験的な機能は、モジュールまたは PowerShell エンジンから取得できます。</span><span class="sxs-lookup"><span data-stu-id="6ea99-108">Experimental features can come from modules or the PowerShell engine.</span></span> <span data-ttu-id="6ea99-109">試験的な機能を使用すると、ユーザーは新しい機能を安全にテストし、(通常は GitHub 経由で) フィードバックを提供する前に、設計が完了したと見なされ、変更が重大な変更になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6ea99-109">Experimental features allow users to safely test new features and provide feedback (typically via GitHub) before the design is considered complete and any changes can become a breaking change.</span></span>

## <span data-ttu-id="6ea99-110">例</span><span class="sxs-lookup"><span data-stu-id="6ea99-110">EXAMPLES</span></span>

### <span data-ttu-id="6ea99-111">例 1</span><span class="sxs-lookup"><span data-stu-id="6ea99-111">Example 1</span></span>

<span data-ttu-id="6ea99-112">現在登録されている試験的な機能とその現在の状態の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="6ea99-112">Gets the list of currently registered experimental features and their current state.</span></span>

```powershell
Get-ExperimentalFeature
```

```Output
Name                         Enabled Source      Description
----                         ------- ------      -----------
PSImplicitRemotingBatching   False PSEngine      Batch implicit remoting proxy commands to improve performance
```

## <span data-ttu-id="6ea99-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6ea99-113">PARAMETERS</span></span>

### <span data-ttu-id="6ea99-114">-Name</span><span class="sxs-lookup"><span data-stu-id="6ea99-114">-Name</span></span>

<span data-ttu-id="6ea99-115">返される特定の実験的な機能の名前または名前。</span><span class="sxs-lookup"><span data-stu-id="6ea99-115">Name or names of specific experimental features to return.</span></span>

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

### <span data-ttu-id="6ea99-116">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="6ea99-116">CommonParameters</span></span>

<span data-ttu-id="6ea99-117">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="6ea99-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6ea99-118">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6ea99-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6ea99-119">入力</span><span class="sxs-lookup"><span data-stu-id="6ea99-119">INPUTS</span></span>

### <span data-ttu-id="6ea99-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="6ea99-120">System.String[]</span></span>

<span data-ttu-id="6ea99-121">返される試験的な機能の名前または名前。</span><span class="sxs-lookup"><span data-stu-id="6ea99-121">Name or names of experimental features to return.</span></span>

## <span data-ttu-id="6ea99-122">出力</span><span class="sxs-lookup"><span data-stu-id="6ea99-122">OUTPUTS</span></span>

### <span data-ttu-id="6ea99-123">ExperimentalFeature (システム管理)</span><span class="sxs-lookup"><span data-stu-id="6ea99-123">System.Management.Automation.ExperimentalFeature</span></span>

<span data-ttu-id="6ea99-124">名前が指定されていない場合は、要求された名前またはすべての試験的な機能に一致するインスタンスを返します。</span><span class="sxs-lookup"><span data-stu-id="6ea99-124">Returns instances that match the requested names or all experimental features if no name is specified.</span></span>

## <span data-ttu-id="6ea99-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="6ea99-125">RELATED LINKS</span></span>

[<span data-ttu-id="6ea99-126">Disable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="6ea99-126">Disable-ExperimentalFeature</span></span>](Disable-ExperimentalFeature.md)

[<span data-ttu-id="6ea99-127">Enable-ExperimentalFeature</span><span class="sxs-lookup"><span data-stu-id="6ea99-127">Enable-ExperimentalFeature</span></span>](Enable-ExperimentalFeature.md)
