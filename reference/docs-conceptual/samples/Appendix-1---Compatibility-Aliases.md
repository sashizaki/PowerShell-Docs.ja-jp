---
ms.date: 09/09/2019
keywords: powershell,コマンドレット
title: 付録 1 - 互換性のあるエイリアス
ms.openlocfilehash: 2351fdf23711fe1417f7e3fc3cca5b642d5a59fc
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "70848167"
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="1bc23-103">付録 1 - 互換性のあるエイリアス</span><span class="sxs-lookup"><span data-stu-id="1bc23-103">Appendix 1 - Compatibility Aliases</span></span>

<span data-ttu-id="1bc23-104">PowerShell には、**UNIX** と **cmd.exe** のユーザーが使い慣れたコマンドを使用できるようにするさまざまなエイリアスがあります。</span><span class="sxs-lookup"><span data-stu-id="1bc23-104">PowerShell has several aliases that allow **UNIX** and **cmd.exe** users to use familiar commands.</span></span>
<span data-ttu-id="1bc23-105">そのコマンドと、それに関連する PowerShell コマンドレットおよび PowerShell エイリアスを次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="1bc23-105">The commands and their related PowerShell cmdlet and PowerShell alias are shown in the following table:</span></span>

|<span data-ttu-id="1bc23-106">cmd.exe コマンド</span><span class="sxs-lookup"><span data-stu-id="1bc23-106">cmd.exe command</span></span>|<span data-ttu-id="1bc23-107">UNIX コマンド</span><span class="sxs-lookup"><span data-stu-id="1bc23-107">UNIX command</span></span>|<span data-ttu-id="1bc23-108">PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="1bc23-108">PowerShell cmdlet</span></span>|<span data-ttu-id="1bc23-109">PowerShell エイリアス</span><span class="sxs-lookup"><span data-stu-id="1bc23-109">PowerShell alias</span></span>|
|---------------|----------------|--------------|------------|
|<span data-ttu-id="1bc23-110">**cls**</span><span class="sxs-lookup"><span data-stu-id="1bc23-110">**cls**</span></span>|<span data-ttu-id="1bc23-111">**オフ**</span><span class="sxs-lookup"><span data-stu-id="1bc23-111">**clear**</span></span>|<span data-ttu-id="1bc23-112">`Clear-Host` (関数)</span><span class="sxs-lookup"><span data-stu-id="1bc23-112">`Clear-Host` (function)</span></span>|`cls`|
|<span data-ttu-id="1bc23-113">**copy**</span><span class="sxs-lookup"><span data-stu-id="1bc23-113">**copy**</span></span>|<span data-ttu-id="1bc23-114">**cp**</span><span class="sxs-lookup"><span data-stu-id="1bc23-114">**cp**</span></span>|`Copy-Item`|`cpi`|
|<span data-ttu-id="1bc23-115">**dir**</span><span class="sxs-lookup"><span data-stu-id="1bc23-115">**dir**</span></span>|<span data-ttu-id="1bc23-116">**ls**</span><span class="sxs-lookup"><span data-stu-id="1bc23-116">**ls**</span></span>|`Get-ChildItem`|`gci`|
|<span data-ttu-id="1bc23-117">**type**</span><span class="sxs-lookup"><span data-stu-id="1bc23-117">**type**</span></span>|<span data-ttu-id="1bc23-118">**cat**</span><span class="sxs-lookup"><span data-stu-id="1bc23-118">**cat**</span></span>|`Get-Content`|`gc`|
|<span data-ttu-id="1bc23-119">**move**</span><span class="sxs-lookup"><span data-stu-id="1bc23-119">**move**</span></span>|<span data-ttu-id="1bc23-120">**mv**</span><span class="sxs-lookup"><span data-stu-id="1bc23-120">**mv**</span></span>|`Move-Item`|`mi`|
|<span data-ttu-id="1bc23-121">**md**</span><span class="sxs-lookup"><span data-stu-id="1bc23-121">**md**</span></span>|<span data-ttu-id="1bc23-122">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="1bc23-122">**mkdir**</span></span>|`New-Item`|`ni`|
|<span data-ttu-id="1bc23-123">**pushd**</span><span class="sxs-lookup"><span data-stu-id="1bc23-123">**pushd**</span></span>|<span data-ttu-id="1bc23-124">**pushd**</span><span class="sxs-lookup"><span data-stu-id="1bc23-124">**pushd**</span></span>|`Push-Location`|`pushd`|
|<span data-ttu-id="1bc23-125">**popd**</span><span class="sxs-lookup"><span data-stu-id="1bc23-125">**popd**</span></span>|<span data-ttu-id="1bc23-126">**popd**</span><span class="sxs-lookup"><span data-stu-id="1bc23-126">**popd**</span></span>|`Pop-Location`|`popd`|
|<span data-ttu-id="1bc23-127">**del**、**erase**、**rd**、**rmdir**</span><span class="sxs-lookup"><span data-stu-id="1bc23-127">**del**, **erase**, **rd**, **rmdir**</span></span>|<span data-ttu-id="1bc23-128">**rm**</span><span class="sxs-lookup"><span data-stu-id="1bc23-128">**rm**</span></span>|`Remove-Item`|`ri`|
|<span data-ttu-id="1bc23-129">**ren**</span><span class="sxs-lookup"><span data-stu-id="1bc23-129">**ren**</span></span>|<span data-ttu-id="1bc23-130">**mv**</span><span class="sxs-lookup"><span data-stu-id="1bc23-130">**mv**</span></span>|`Rename-Item`|`rni`|
|<span data-ttu-id="1bc23-131">**cd**、**chdir**</span><span class="sxs-lookup"><span data-stu-id="1bc23-131">**cd**, **chdir**</span></span>|<span data-ttu-id="1bc23-132">**cd**</span><span class="sxs-lookup"><span data-stu-id="1bc23-132">**cd**</span></span>|`Set-Location`|`sl`|

<span data-ttu-id="1bc23-133">PowerShell エイリアスを検索するには、[Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1bc23-133">To find the PowerShell aliases, use the [Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) cmdlet.</span></span> <span data-ttu-id="1bc23-134">コマンドレットのエイリアスを表示するには、**Definition** パラメーターを使用して、コマンドレット名を指定します。</span><span class="sxs-lookup"><span data-stu-id="1bc23-134">To display a cmdlet's aliases, use the **Definition** parameter and specify the cmdlet name.</span></span>
<span data-ttu-id="1bc23-135">または、エイリアスのコマンドレット名を検索するには、**Name** パラメーターを使用して、エイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1bc23-135">Or, to find an alias's cmdlet name, use the **Name** parameter and specify the alias.</span></span>

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
