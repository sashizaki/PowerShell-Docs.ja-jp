---
description: PowerShell プロバイダーで使用できるように設計されたコマンドレットの一覧を示します。
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 1f023c5a66265f561ef6644afdc45cd0149f35b7
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605195"
---
# <a name="about-core-commands"></a><span data-ttu-id="dea6c-103">コアコマンドについて</span><span class="sxs-lookup"><span data-stu-id="dea6c-103">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="dea6c-104">概要</span><span class="sxs-lookup"><span data-stu-id="dea6c-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="dea6c-105">PowerShell プロバイダーで使用できるように設計されたコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="dea6c-105">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="dea6c-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="dea6c-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="dea6c-107">PowerShell には、PowerShell プロバイダーによって公開されるデータストア内の項目を管理するために特に設計された一連のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="dea6c-107">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="dea6c-108">これらのコマンドレットを同じ方法で使用して、プロバイダーが使用できるようにするさまざまな種類のデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="dea6c-108">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="dea6c-109">プロバイダーの詳細については、「get-help about_providers」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="dea6c-109">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="dea6c-110">たとえば、Get-ChildItem コマンドレットを使用して、ファイルシステムディレクトリ内のファイル、レジストリキーの下にあるキー、または書き込んだりダウンロードしたプロバイダーによって公開されている項目を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="dea6c-110">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="dea6c-111">プロバイダーで使用するように設計されている PowerShell コマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="dea6c-111">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="dea6c-112">Get-childitem コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea6c-112">ChildItem cmdlets</span></span>

- <span data-ttu-id="dea6c-113">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="dea6c-113">Get-ChildItem</span></span>

<span data-ttu-id="dea6c-114">コンテンツのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea6c-114">Content cmdlets</span></span>

- <span data-ttu-id="dea6c-115">Add-Content</span><span class="sxs-lookup"><span data-stu-id="dea6c-115">Add-Content</span></span>
- <span data-ttu-id="dea6c-116">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="dea6c-116">Clear-Content</span></span>
- <span data-ttu-id="dea6c-117">Get-Content</span><span class="sxs-lookup"><span data-stu-id="dea6c-117">Get-Content</span></span>
- <span data-ttu-id="dea6c-118">Set-Content</span><span class="sxs-lookup"><span data-stu-id="dea6c-118">Set-Content</span></span>

<span data-ttu-id="dea6c-119">項目のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea6c-119">Item cmdlets</span></span>

- <span data-ttu-id="dea6c-120">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-120">Clear-Item</span></span>
- <span data-ttu-id="dea6c-121">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-121">Copy-Item</span></span>
- <span data-ttu-id="dea6c-122">Get-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-122">Get-Item</span></span>
- <span data-ttu-id="dea6c-123">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-123">Invoke-Item</span></span>
- <span data-ttu-id="dea6c-124">Move-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-124">Move-Item</span></span>
- <span data-ttu-id="dea6c-125">New-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-125">New-Item</span></span>
- <span data-ttu-id="dea6c-126">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-126">Remove-Item</span></span>
- <span data-ttu-id="dea6c-127">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-127">Rename-Item</span></span>
- <span data-ttu-id="dea6c-128">Set-Item</span><span class="sxs-lookup"><span data-stu-id="dea6c-128">Set-Item</span></span>

<span data-ttu-id="dea6c-129">Get-itemproperty コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea6c-129">ItemProperty cmdlets</span></span>

- <span data-ttu-id="dea6c-130">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea6c-130">Clear-ItemProperty</span></span>
- <span data-ttu-id="dea6c-131">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea6c-131">Copy-ItemProperty</span></span>
- <span data-ttu-id="dea6c-132">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea6c-132">Get-ItemProperty</span></span>
- <span data-ttu-id="dea6c-133">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea6c-133">Move-ItemProperty</span></span>
- <span data-ttu-id="dea6c-134">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea6c-134">New-ItemProperty</span></span>
- <span data-ttu-id="dea6c-135">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea6c-135">Remove-ItemProperty</span></span>
- <span data-ttu-id="dea6c-136">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea6c-136">Rename-ItemProperty</span></span>
- <span data-ttu-id="dea6c-137">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="dea6c-137">Set-ItemProperty</span></span>

<span data-ttu-id="dea6c-138">Location コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea6c-138">Location cmdlets</span></span>

- <span data-ttu-id="dea6c-139">Get-Location</span><span class="sxs-lookup"><span data-stu-id="dea6c-139">Get-Location</span></span>
- <span data-ttu-id="dea6c-140">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="dea6c-140">Pop-Location</span></span>
- <span data-ttu-id="dea6c-141">Push-Location</span><span class="sxs-lookup"><span data-stu-id="dea6c-141">Push-Location</span></span>
- <span data-ttu-id="dea6c-142">Set-Location</span><span class="sxs-lookup"><span data-stu-id="dea6c-142">Set-Location</span></span>

<span data-ttu-id="dea6c-143">Path コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea6c-143">Path cmdlets</span></span>

- <span data-ttu-id="dea6c-144">Join-Path</span><span class="sxs-lookup"><span data-stu-id="dea6c-144">Join-Path</span></span>
- <span data-ttu-id="dea6c-145">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="dea6c-145">Convert-Path</span></span>
- <span data-ttu-id="dea6c-146">Split-Path</span><span class="sxs-lookup"><span data-stu-id="dea6c-146">Split-Path</span></span>
- <span data-ttu-id="dea6c-147">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="dea6c-147">Resolve-Path</span></span>
- <span data-ttu-id="dea6c-148">Test-Path</span><span class="sxs-lookup"><span data-stu-id="dea6c-148">Test-Path</span></span>

<span data-ttu-id="dea6c-149">PSDrive コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea6c-149">PSDrive cmdlets</span></span>

- <span data-ttu-id="dea6c-150">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="dea6c-150">Get-PSDrive</span></span>
- <span data-ttu-id="dea6c-151">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="dea6c-151">New-PSDrive</span></span>
- <span data-ttu-id="dea6c-152">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="dea6c-152">Remove-PSDrive</span></span>

<span data-ttu-id="dea6c-153">PSProvider コマンドレット</span><span class="sxs-lookup"><span data-stu-id="dea6c-153">PSProvider cmdlets</span></span>

- <span data-ttu-id="dea6c-154">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="dea6c-154">Get-PSProvider</span></span>

<span data-ttu-id="dea6c-155">コマンドレットの詳細については、「」と入力 `get-help <cmdlet-name>` してください。</span><span class="sxs-lookup"><span data-stu-id="dea6c-155">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dea6c-156">関連項目</span><span class="sxs-lookup"><span data-stu-id="dea6c-156">SEE ALSO</span></span>

[<span data-ttu-id="dea6c-157">about_Providers</span><span class="sxs-lookup"><span data-stu-id="dea6c-157">about_Providers</span></span>](about_Providers.md)

