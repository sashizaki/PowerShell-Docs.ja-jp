---
ms.date: 08/03/2020
keywords: powershell,コマンドレット
title: 付録 1 - 互換性のあるエイリアス
description: PowerShell には、UNIX と cmd.exe のユーザーが使い慣れたコマンドを使用できるようにするさまざまなエイリアスがあります。
ms.openlocfilehash: 8cbbd5a358de9018fcb5c840e711cd76f7a9a353
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500744"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="15bdc-104">付録 1 - 互換性のあるエイリアス</span><span class="sxs-lookup"><span data-stu-id="15bdc-104">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="15bdc-105">PowerShell には、 **UNIX** と **cmd.exe** のユーザーが使い慣れたコマンドを使用できるようにするさまざまなエイリアスがあります。</span><span class="sxs-lookup"><span data-stu-id="15bdc-105">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="15bdc-106">そのコマンドと、それに関連する PowerShell コマンドレットおよび PowerShell エイリアスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="15bdc-106">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|            <span data-ttu-id="15bdc-107">cmd.exe コマンド</span><span class="sxs-lookup"><span data-stu-id="15bdc-107">cmd.exe command</span></span>            | <span data-ttu-id="15bdc-108">UNIX コマンド</span><span class="sxs-lookup"><span data-stu-id="15bdc-108">UNIX command</span></span> | <span data-ttu-id="15bdc-109">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="15bdc-109">PowerShell cmdlet</span></span> | <span data-ttu-id="15bdc-110">PowerShell エイリアス</span><span class="sxs-lookup"><span data-stu-id="15bdc-110">PowerShell alias</span></span> |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| <span data-ttu-id="15bdc-111">**cd** 、 **chdir**</span><span class="sxs-lookup"><span data-stu-id="15bdc-111">**cd** , **chdir**</span></span>                     | <span data-ttu-id="15bdc-112">**cd**</span><span class="sxs-lookup"><span data-stu-id="15bdc-112">**cd**</span></span>       | `Set-Location`    | `sl`             |
| <span data-ttu-id="15bdc-113">**cls**</span><span class="sxs-lookup"><span data-stu-id="15bdc-113">**cls**</span></span>                               | <span data-ttu-id="15bdc-114">**オフ**</span><span class="sxs-lookup"><span data-stu-id="15bdc-114">**clear**</span></span>    | `Clear-Host`      | `cls`            |
| <span data-ttu-id="15bdc-115">**copy**</span><span class="sxs-lookup"><span data-stu-id="15bdc-115">**copy**</span></span>                              | <span data-ttu-id="15bdc-116">**cp**</span><span class="sxs-lookup"><span data-stu-id="15bdc-116">**cp**</span></span>       | `Copy-Item`       | `cpi`            |
| <span data-ttu-id="15bdc-117">**del** 、 **erase** 、 **rd** 、 **rmdir**</span><span class="sxs-lookup"><span data-stu-id="15bdc-117">**del** , **erase** , **rd** , **rmdir**</span></span> | <span data-ttu-id="15bdc-118">**rm**</span><span class="sxs-lookup"><span data-stu-id="15bdc-118">**rm**</span></span>       | `Remove-Item`     | `ri`             |
| <span data-ttu-id="15bdc-119">**dir**</span><span class="sxs-lookup"><span data-stu-id="15bdc-119">**dir**</span></span>                               | <span data-ttu-id="15bdc-120">**ls**</span><span class="sxs-lookup"><span data-stu-id="15bdc-120">**ls**</span></span>       | `Get-ChildItem`   | `gci`            |
| <span data-ttu-id="15bdc-121">**echo**</span><span class="sxs-lookup"><span data-stu-id="15bdc-121">**echo**</span></span>                              | <span data-ttu-id="15bdc-122">**echo**</span><span class="sxs-lookup"><span data-stu-id="15bdc-122">**echo**</span></span>     | `Write-Output`    | `write`          |
| <span data-ttu-id="15bdc-123">**md**</span><span class="sxs-lookup"><span data-stu-id="15bdc-123">**md**</span></span>                                | <span data-ttu-id="15bdc-124">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="15bdc-124">**mkdir**</span></span>    | `New-Item`        | `ni`             |
| <span data-ttu-id="15bdc-125">**move**</span><span class="sxs-lookup"><span data-stu-id="15bdc-125">**move**</span></span>                              | <span data-ttu-id="15bdc-126">**mv**</span><span class="sxs-lookup"><span data-stu-id="15bdc-126">**mv**</span></span>       | `Move-Item`       | `mi`             |
| <span data-ttu-id="15bdc-127">**popd**</span><span class="sxs-lookup"><span data-stu-id="15bdc-127">**popd**</span></span>                              | <span data-ttu-id="15bdc-128">**popd**</span><span class="sxs-lookup"><span data-stu-id="15bdc-128">**popd**</span></span>     | `Pop-Location`    | `popd`           |
| <span data-ttu-id="15bdc-129">**pushd**</span><span class="sxs-lookup"><span data-stu-id="15bdc-129">**pushd**</span></span>                             | <span data-ttu-id="15bdc-130">**pushd**</span><span class="sxs-lookup"><span data-stu-id="15bdc-130">**pushd**</span></span>    | `Push-Location`   | `pushd`          |
| <span data-ttu-id="15bdc-131">**ren**</span><span class="sxs-lookup"><span data-stu-id="15bdc-131">**ren**</span></span>                               | <span data-ttu-id="15bdc-132">**mv**</span><span class="sxs-lookup"><span data-stu-id="15bdc-132">**mv**</span></span>       | `Rename-Item`     | `rni`            |
| <span data-ttu-id="15bdc-133">**type**</span><span class="sxs-lookup"><span data-stu-id="15bdc-133">**type**</span></span>                              | <span data-ttu-id="15bdc-134">**cat**</span><span class="sxs-lookup"><span data-stu-id="15bdc-134">**cat**</span></span>      | `Get-Content`     | `gc`             |

<span data-ttu-id="15bdc-135">PowerShell エイリアスを検索するには、[Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="15bdc-135">To find the PowerShell aliases, use the [Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) cmdlet.</span></span> <span data-ttu-id="15bdc-136">コマンドレットのエイリアスを表示するには、 **Definition** パラメーターを使用して、コマンドレット名を指定します。</span><span class="sxs-lookup"><span data-stu-id="15bdc-136">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="15bdc-137">または、エイリアスのコマンドレット名を検索するには、 **Name** パラメーターを使用して、エイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="15bdc-137">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
