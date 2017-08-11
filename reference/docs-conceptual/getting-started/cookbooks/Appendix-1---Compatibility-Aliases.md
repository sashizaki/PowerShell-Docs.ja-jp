---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "付録 1 - 互換性のあるエイリアス"
ms.assetid: 96ad921e-1a57-463e-8e60-424faf8b6ef8
ms.openlocfilehash: d789139ef80d4208b56e0b2930f04f824a00537d
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="appendix-1---compatibility-aliases"></a><span data-ttu-id="87554-103">付録 1 - 互換性のあるエイリアス</span><span class="sxs-lookup"><span data-stu-id="87554-103">Appendix 1 - Compatibility Aliases</span></span>
<span data-ttu-id="87554-104">Windows PowerShell には、UNIX と Cmd のユーザーが使い慣れたコマンド名を Windows PowerShell でも使用できるようにするいくつかの移行エイリアスがあります。</span><span class="sxs-lookup"><span data-stu-id="87554-104">Windows PowerShell has several transition aliases that allow UNIX and Cmd users to use familiar command names in Windows PowerShell.</span></span> <span data-ttu-id="87554-105">最も一般的なエイリアスについて、対応する Windows PowerShell コマンド、および Windows PowerShell の標準エイリアス (存在する場合) と共に以下の表にまとめました。</span><span class="sxs-lookup"><span data-stu-id="87554-105">The most common aliases are shown in the table below, along with the Windows PowerShell command behind the alias and the standard Windows PowerShell alias if one exists.</span></span>

<span data-ttu-id="87554-106">エイリアスに対応する Windows PowerShell コマンドは、Windows PowerShell から Get-Alias コマンドレットを使用して検索できます。</span><span class="sxs-lookup"><span data-stu-id="87554-106">You can find the Windows PowerShell command that any alias points to from within Windows PowerShell by using the Get-Alias cmdlet.</span></span> <span data-ttu-id="87554-107">たとえば、**get-alias cls** と入力します。</span><span class="sxs-lookup"><span data-stu-id="87554-107">For example, type **get-alias cls**.</span></span>

```
CommandType     Name                            Definition
-----------     ----                            ----------
Alias           cls                             Clear-Host
```

|<span data-ttu-id="87554-108">CMD コマンド</span><span class="sxs-lookup"><span data-stu-id="87554-108">CMD Command</span></span>|<span data-ttu-id="87554-109">UNIX コマンド</span><span class="sxs-lookup"><span data-stu-id="87554-109">UNIX Command</span></span>|<span data-ttu-id="87554-110">PS コマンド</span><span class="sxs-lookup"><span data-stu-id="87554-110">PS Command</span></span>|<span data-ttu-id="87554-111">PS エイリアス</span><span class="sxs-lookup"><span data-stu-id="87554-111">PS Alias</span></span>|
|---------------|----------------|--------------|------------|
|<span data-ttu-id="87554-112">**dir**</span><span class="sxs-lookup"><span data-stu-id="87554-112">**dir**</span></span>|<span data-ttu-id="87554-113">**ls**</span><span class="sxs-lookup"><span data-stu-id="87554-113">**ls**</span></span>|<span data-ttu-id="87554-114">**Get-ChildItem**</span><span class="sxs-lookup"><span data-stu-id="87554-114">**Get-ChildItem**</span></span>|<span data-ttu-id="87554-115">**gci**</span><span class="sxs-lookup"><span data-stu-id="87554-115">**gci**</span></span>|
|<span data-ttu-id="87554-116">**cls**</span><span class="sxs-lookup"><span data-stu-id="87554-116">**cls**</span></span>|<span data-ttu-id="87554-117">**clear**</span><span class="sxs-lookup"><span data-stu-id="87554-117">**clear**</span></span>|<span data-ttu-id="87554-118">**Clear-Host** (関数)</span><span class="sxs-lookup"><span data-stu-id="87554-118">**Clear-Host** (function)</span></span>|<span data-ttu-id="87554-119">**cls**</span><span class="sxs-lookup"><span data-stu-id="87554-119">**cls**</span></span>|
|<span data-ttu-id="87554-120">**del、erase、rmdir**</span><span class="sxs-lookup"><span data-stu-id="87554-120">**del, erase, rmdir**</span></span>|<span data-ttu-id="87554-121">**rm**</span><span class="sxs-lookup"><span data-stu-id="87554-121">**rm**</span></span>|<span data-ttu-id="87554-122">**Remove-Item**</span><span class="sxs-lookup"><span data-stu-id="87554-122">**Remove-Item**</span></span>|<span data-ttu-id="87554-123">**ri**</span><span class="sxs-lookup"><span data-stu-id="87554-123">**ri**</span></span>|
|<span data-ttu-id="87554-124">**copy**</span><span class="sxs-lookup"><span data-stu-id="87554-124">**copy**</span></span>|<span data-ttu-id="87554-125">**cp**</span><span class="sxs-lookup"><span data-stu-id="87554-125">**cp**</span></span>|<span data-ttu-id="87554-126">**Copy-Item**</span><span class="sxs-lookup"><span data-stu-id="87554-126">**Copy-Item**</span></span>|<span data-ttu-id="87554-127">**ci**</span><span class="sxs-lookup"><span data-stu-id="87554-127">**ci**</span></span>|
|<span data-ttu-id="87554-128">**move**</span><span class="sxs-lookup"><span data-stu-id="87554-128">**move**</span></span>|<span data-ttu-id="87554-129">**mv**</span><span class="sxs-lookup"><span data-stu-id="87554-129">**mv**</span></span>|<span data-ttu-id="87554-130">**Move-Item**</span><span class="sxs-lookup"><span data-stu-id="87554-130">**Move-Item**</span></span>|<span data-ttu-id="87554-131">**mi**</span><span class="sxs-lookup"><span data-stu-id="87554-131">**mi**</span></span>|
|<span data-ttu-id="87554-132">**rename**</span><span class="sxs-lookup"><span data-stu-id="87554-132">**rename**</span></span>|<span data-ttu-id="87554-133">**mv**</span><span class="sxs-lookup"><span data-stu-id="87554-133">**mv**</span></span>|<span data-ttu-id="87554-134">**Rename-Item**</span><span class="sxs-lookup"><span data-stu-id="87554-134">**Rename-Item**</span></span>|<span data-ttu-id="87554-135">**rni**</span><span class="sxs-lookup"><span data-stu-id="87554-135">**rni**</span></span>|
|<span data-ttu-id="87554-136">**type**</span><span class="sxs-lookup"><span data-stu-id="87554-136">**type**</span></span>|<span data-ttu-id="87554-137">**cat**</span><span class="sxs-lookup"><span data-stu-id="87554-137">**cat**</span></span>|<span data-ttu-id="87554-138">**Get-Content**</span><span class="sxs-lookup"><span data-stu-id="87554-138">**Get-Content**</span></span>|<span data-ttu-id="87554-139">**gc**</span><span class="sxs-lookup"><span data-stu-id="87554-139">**gc**</span></span>|
|<span data-ttu-id="87554-140">**cd**</span><span class="sxs-lookup"><span data-stu-id="87554-140">**cd**</span></span>|<span data-ttu-id="87554-141">**cd**</span><span class="sxs-lookup"><span data-stu-id="87554-141">**cd**</span></span>|<span data-ttu-id="87554-142">**Set-Location**</span><span class="sxs-lookup"><span data-stu-id="87554-142">**Set-Location**</span></span>|<span data-ttu-id="87554-143">**sl**</span><span class="sxs-lookup"><span data-stu-id="87554-143">**sl**</span></span>|
|<span data-ttu-id="87554-144">**md**</span><span class="sxs-lookup"><span data-stu-id="87554-144">**md**</span></span>|<span data-ttu-id="87554-145">**mkdir**</span><span class="sxs-lookup"><span data-stu-id="87554-145">**mkdir**</span></span>|<span data-ttu-id="87554-146">**New-Item**</span><span class="sxs-lookup"><span data-stu-id="87554-146">**New-Item**</span></span>|<span data-ttu-id="87554-147">**ni**</span><span class="sxs-lookup"><span data-stu-id="87554-147">**ni**</span></span>|
|<span data-ttu-id="87554-148">**pushd**</span><span class="sxs-lookup"><span data-stu-id="87554-148">**pushd**</span></span>|<span data-ttu-id="87554-149">**pushd**</span><span class="sxs-lookup"><span data-stu-id="87554-149">**pushd**</span></span>|<span data-ttu-id="87554-150">**Push-Location**</span><span class="sxs-lookup"><span data-stu-id="87554-150">**Push-Location**</span></span>|<span data-ttu-id="87554-151">**pushd**</span><span class="sxs-lookup"><span data-stu-id="87554-151">**pushd**</span></span>|
|<span data-ttu-id="87554-152">**popd**</span><span class="sxs-lookup"><span data-stu-id="87554-152">**popd**</span></span>|<span data-ttu-id="87554-153">**popd**</span><span class="sxs-lookup"><span data-stu-id="87554-153">**popd**</span></span>|<span data-ttu-id="87554-154">**Pop-Location**</span><span class="sxs-lookup"><span data-stu-id="87554-154">**Pop-Location**</span></span>|<span data-ttu-id="87554-155">**popd**</span><span class="sxs-lookup"><span data-stu-id="87554-155">**popd**</span></span>|
