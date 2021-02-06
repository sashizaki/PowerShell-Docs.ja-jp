---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 908a43506bfbff964cfbdd8eea270b1fa42c3e77
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601393"
---
# <span data-ttu-id="b8475-102">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b8475-102">Unregister-PSRepository</span></span>

## <span data-ttu-id="b8475-103">概要</span><span class="sxs-lookup"><span data-stu-id="b8475-103">SYNOPSIS</span></span>
<span data-ttu-id="b8475-104">リポジトリの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="b8475-104">Unregisters a repository.</span></span>

## <span data-ttu-id="b8475-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b8475-105">SYNTAX</span></span>

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## <span data-ttu-id="b8475-106">Description</span><span class="sxs-lookup"><span data-stu-id="b8475-106">DESCRIPTION</span></span>

<span data-ttu-id="b8475-107">`Unregister-PSRepository`コマンドレットは、現在のユーザーのリポジトリを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="b8475-107">The `Unregister-PSRepository` cmdlet unregisters a repository for the current user.</span></span>

## <span data-ttu-id="b8475-108">例</span><span class="sxs-lookup"><span data-stu-id="b8475-108">EXAMPLES</span></span>

### <span data-ttu-id="b8475-109">例 1: リポジトリの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="b8475-109">Example 1: Unregister a repository</span></span>

<span data-ttu-id="b8475-110">この例では、myNuGetSource という名前のリポジトリを登録解除します。</span><span class="sxs-lookup"><span data-stu-id="b8475-110">This example unregisters the repository named myNuGetSource.</span></span>

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### <span data-ttu-id="b8475-111">例 2: すべてのリポジトリの登録を解除する</span><span class="sxs-lookup"><span data-stu-id="b8475-111">Example 2: Unregister all repositories</span></span>

<span data-ttu-id="b8475-112">この例では `Get-PSRepository` 、を使用して登録されているすべてのリポジトリを取得し、パイプライン演算子を使用してそれらをに渡して、登録を `Unregister-PSRepository` 解除します。</span><span class="sxs-lookup"><span data-stu-id="b8475-112">This example uses `Get-PSRepository` to get all registered repositories, and uses the pipeline operator to pass them to `Unregister-PSRepository` to unregister them.</span></span>

```powershell
Get-PSRepository | Unregister-PSRepository
```

## <span data-ttu-id="b8475-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b8475-113">PARAMETERS</span></span>

### <span data-ttu-id="b8475-114">-Name</span><span class="sxs-lookup"><span data-stu-id="b8475-114">-Name</span></span>

<span data-ttu-id="b8475-115">削除するリポジトリの名前の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b8475-115">Specifies an array of names of the repositories to remove.</span></span>

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

### <span data-ttu-id="b8475-116">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b8475-116">CommonParameters</span></span>

<span data-ttu-id="b8475-117">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b8475-117">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b8475-118">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b8475-118">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b8475-119">入力</span><span class="sxs-lookup"><span data-stu-id="b8475-119">INPUTS</span></span>

### <span data-ttu-id="b8475-120">System.String[]</span><span class="sxs-lookup"><span data-stu-id="b8475-120">System.String[]</span></span>

## <span data-ttu-id="b8475-121">出力</span><span class="sxs-lookup"><span data-stu-id="b8475-121">OUTPUTS</span></span>

### <span data-ttu-id="b8475-122">System.Object</span><span class="sxs-lookup"><span data-stu-id="b8475-122">System.Object</span></span>

## <span data-ttu-id="b8475-123">注</span><span class="sxs-lookup"><span data-stu-id="b8475-123">NOTES</span></span>

## <span data-ttu-id="b8475-124">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b8475-124">RELATED LINKS</span></span>

[<span data-ttu-id="b8475-125">Get-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b8475-125">Get-PSRepository</span></span>](Get-PSRepository.md)

[<span data-ttu-id="b8475-126">Register-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b8475-126">Register-PSRepository</span></span>](Register-PSRepository.md)

[<span data-ttu-id="b8475-127">Set-PSRepository</span><span class="sxs-lookup"><span data-stu-id="b8475-127">Set-PSRepository</span></span>](Set-PSRepository.md)
