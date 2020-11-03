---
external help file: PSModule-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 0d98d7bbb26d5a50542f0e125e912ea6333714c1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215179"
---
# <span data-ttu-id="b1346-103">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b1346-103">Unregister-PSRepository</span></span>

## <span data-ttu-id="b1346-104">概要</span><span class="sxs-lookup"><span data-stu-id="b1346-104">SYNOPSIS</span></span>
<span data-ttu-id="b1346-105">リポジトリの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="b1346-105">Unregisters a repository.</span></span>

## <span data-ttu-id="b1346-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b1346-106">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="b1346-107">Description</span><span class="sxs-lookup"><span data-stu-id="b1346-107">DESCRIPTION</span></span>

<span data-ttu-id="b1346-108">`Unregister-PSRepository`コマンドレットは、現在のユーザーのリポジトリを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="b1346-108">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="b1346-109">例</span><span class="sxs-lookup"><span data-stu-id="b1346-109">EXAMPLES</span></span>

### <span data-ttu-id="b1346-110">例 1: リポジトリの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="b1346-110">Example 1: Unregister a repository</span></span>

<span data-ttu-id="b1346-111">この例では、myNuGetSource という名前のリポジトリを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="b1346-111">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="b1346-112">例 2: すべてのリポジトリの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="b1346-112">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="b1346-113">この例では `Get-PSRepository` 、を使用して登録されているすべてのリポジトリを取得し、パイプライン演算子を使用してそれらをに渡して、登録を `Unregister-PSRepository` 解除します。</span><span class="sxs-lookup"><span data-stu-id="b1346-113">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="b1346-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b1346-114">PARAMETERS</span></span>

### <span data-ttu-id="b1346-115">-Name</span><span class="sxs-lookup"><span data-stu-id="b1346-115">-Name</span></span>

<span data-ttu-id="b1346-116">削除するリポジトリの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b1346-116">Specifies an array of names of the repositories to remove.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="b1346-117">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b1346-117">CommonParameters</span></span>

<span data-ttu-id="b1346-118">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b1346-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b1346-119">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1346-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b1346-120">入力</span><span class="sxs-lookup"><span data-stu-id="b1346-120">INPUTS</span></span>

### <span data-ttu-id="b1346-121">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b1346-121">System.String[]</span></span>

## <span data-ttu-id="b1346-122">出力</span><span class="sxs-lookup"><span data-stu-id="b1346-122">OUTPUTS</span></span>

### <span data-ttu-id="b1346-123">System.Object</span><span class="sxs-lookup"><span data-stu-id="b1346-123">System.Object</span></span>

## <span data-ttu-id="b1346-124">注</span><span class="sxs-lookup"><span data-stu-id="b1346-124">NOTES</span></span>

## <span data-ttu-id="b1346-125">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b1346-125">RELATED LINKS</span></span>

[<span data-ttu-id="b1346-126">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b1346-126">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="b1346-127">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b1346-127">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="b1346-128">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b1346-128">Set-PSRepository</span></span>](Set-PSRepository.md)