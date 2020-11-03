---
description: PowerShell プロバイダーで使用できるように設計されたコマンドレットの一覧を示します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 5c784518ae30108813d32497f654198e7d10b379
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220731"
---
# <a name="about-core-commands"></a><span data-ttu-id="f7325-104">コアコマンドについて</span><span class="sxs-lookup"><span data-stu-id="f7325-104">About Core Commands</span></span>

## <a name="short-description"></a><span data-ttu-id="f7325-105">概要</span><span class="sxs-lookup"><span data-stu-id="f7325-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f7325-106">PowerShell プロバイダーで使用できるように設計されたコマンドレットの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f7325-106">Lists the cmdlets that are designed for use with PowerShell providers.</span></span>

## <a name="long-description"></a><span data-ttu-id="f7325-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="f7325-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="f7325-108">PowerShell には、PowerShell プロバイダーによって公開されるデータストア内の項目を管理するために特に設計された一連のコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f7325-108">PowerShell includes a set of cmdlets that are specifically designed to manage the items in the data stores that are exposed by PowerShell providers.</span></span>
<span data-ttu-id="f7325-109">これらのコマンドレットを同じ方法で使用して、プロバイダーが使用できるようにするさまざまな種類のデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="f7325-109">You can use these cmdlets in the same ways to manage all the different types of data that the providers make available to you.</span></span> <span data-ttu-id="f7325-110">プロバイダーの詳細については、「get-help about_providers」と入力してください。</span><span class="sxs-lookup"><span data-stu-id="f7325-110">For more information about providers, type "get-help about_providers".</span></span>

<span data-ttu-id="f7325-111">たとえば、Get-ChildItem コマンドレットを使用して、ファイルシステムディレクトリ内のファイル、レジストリキーの下にあるキー、または書き込んだりダウンロードしたプロバイダーによって公開されている項目を一覧表示できます。</span><span class="sxs-lookup"><span data-stu-id="f7325-111">For example, you can use the Get-ChildItem cmdlet to list the files in a file system directory, the keys under a registry key, or the items that are exposed by a provider that you write or download.</span></span>

<span data-ttu-id="f7325-112">プロバイダーで使用するように設計されている PowerShell コマンドレットの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f7325-112">The following is a list of the PowerShell cmdlets that are designed for use with providers:</span></span>

<span data-ttu-id="f7325-113">Get-childitem コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7325-113">ChildItem cmdlets</span></span>

- <span data-ttu-id="f7325-114">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="f7325-114">Get-ChildItem</span></span>

<span data-ttu-id="f7325-115">コンテンツのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7325-115">Content cmdlets</span></span>

- <span data-ttu-id="f7325-116">Add-Content</span><span class="sxs-lookup"><span data-stu-id="f7325-116">Add-Content</span></span>
- <span data-ttu-id="f7325-117">Clear-Content</span><span class="sxs-lookup"><span data-stu-id="f7325-117">Clear-Content</span></span>
- <span data-ttu-id="f7325-118">Get-Content</span><span class="sxs-lookup"><span data-stu-id="f7325-118">Get-Content</span></span>
- <span data-ttu-id="f7325-119">Set-Content</span><span class="sxs-lookup"><span data-stu-id="f7325-119">Set-Content</span></span>

<span data-ttu-id="f7325-120">項目のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7325-120">Item cmdlets</span></span>

- <span data-ttu-id="f7325-121">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-121">Clear-Item</span></span>
- <span data-ttu-id="f7325-122">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-122">Copy-Item</span></span>
- <span data-ttu-id="f7325-123">Get-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-123">Get-Item</span></span>
- <span data-ttu-id="f7325-124">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-124">Invoke-Item</span></span>
- <span data-ttu-id="f7325-125">Move-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-125">Move-Item</span></span>
- <span data-ttu-id="f7325-126">New-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-126">New-Item</span></span>
- <span data-ttu-id="f7325-127">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-127">Remove-Item</span></span>
- <span data-ttu-id="f7325-128">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-128">Rename-Item</span></span>
- <span data-ttu-id="f7325-129">Set-Item</span><span class="sxs-lookup"><span data-stu-id="f7325-129">Set-Item</span></span>

<span data-ttu-id="f7325-130">Get-itemproperty コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7325-130">ItemProperty cmdlets</span></span>

- <span data-ttu-id="f7325-131">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f7325-131">Clear-ItemProperty</span></span>
- <span data-ttu-id="f7325-132">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f7325-132">Copy-ItemProperty</span></span>
- <span data-ttu-id="f7325-133">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f7325-133">Get-ItemProperty</span></span>
- <span data-ttu-id="f7325-134">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f7325-134">Move-ItemProperty</span></span>
- <span data-ttu-id="f7325-135">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f7325-135">New-ItemProperty</span></span>
- <span data-ttu-id="f7325-136">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f7325-136">Remove-ItemProperty</span></span>
- <span data-ttu-id="f7325-137">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f7325-137">Rename-ItemProperty</span></span>
- <span data-ttu-id="f7325-138">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="f7325-138">Set-ItemProperty</span></span>

<span data-ttu-id="f7325-139">Location コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7325-139">Location cmdlets</span></span>

- <span data-ttu-id="f7325-140">Get-Location</span><span class="sxs-lookup"><span data-stu-id="f7325-140">Get-Location</span></span>
- <span data-ttu-id="f7325-141">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="f7325-141">Pop-Location</span></span>
- <span data-ttu-id="f7325-142">Push-Location</span><span class="sxs-lookup"><span data-stu-id="f7325-142">Push-Location</span></span>
- <span data-ttu-id="f7325-143">Set-Location</span><span class="sxs-lookup"><span data-stu-id="f7325-143">Set-Location</span></span>

<span data-ttu-id="f7325-144">Path コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7325-144">Path cmdlets</span></span>

- <span data-ttu-id="f7325-145">Join-Path</span><span class="sxs-lookup"><span data-stu-id="f7325-145">Join-Path</span></span>
- <span data-ttu-id="f7325-146">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="f7325-146">Convert-Path</span></span>
- <span data-ttu-id="f7325-147">Split-Path</span><span class="sxs-lookup"><span data-stu-id="f7325-147">Split-Path</span></span>
- <span data-ttu-id="f7325-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="f7325-148">Resolve-Path</span></span>
- <span data-ttu-id="f7325-149">Test-Path</span><span class="sxs-lookup"><span data-stu-id="f7325-149">Test-Path</span></span>

<span data-ttu-id="f7325-150">PSDrive コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7325-150">PSDrive cmdlets</span></span>

- <span data-ttu-id="f7325-151">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f7325-151">Get-PSDrive</span></span>
- <span data-ttu-id="f7325-152">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f7325-152">New-PSDrive</span></span>
- <span data-ttu-id="f7325-153">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="f7325-153">Remove-PSDrive</span></span>

<span data-ttu-id="f7325-154">PSProvider コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f7325-154">PSProvider cmdlets</span></span>

- <span data-ttu-id="f7325-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="f7325-155">Get-PSProvider</span></span>

<span data-ttu-id="f7325-156">コマンドレットの詳細については、「」と入力 `get-help <cmdlet-name>` してください。</span><span class="sxs-lookup"><span data-stu-id="f7325-156">For more information about a cmdlet, type `get-help <cmdlet-name>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7325-157">関連項目</span><span class="sxs-lookup"><span data-stu-id="f7325-157">SEE ALSO</span></span>

[<span data-ttu-id="f7325-158">about_Providers</span><span class="sxs-lookup"><span data-stu-id="f7325-158">about_Providers</span></span>](about_Providers.md)