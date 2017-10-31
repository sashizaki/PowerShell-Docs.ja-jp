---
title: Windows Management Framework (WMF)
ms.date: 2017-02-14
keywords: "PowerShell、WMF"
description: 
ms.topic: article
author: keithb
manager: dongill
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: 749dd8b19592cb5f40a5aed32d28edeb5cb2dfc9
ms.sourcegitcommit: bb2c52577a519c0599a0b3c961f749fe0df70a45
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="windows-management-framework"></a><span data-ttu-id="738f6-103">Windows Management Framework</span><span class="sxs-lookup"><span data-stu-id="738f6-103">Windows Management Framework</span></span>

<span data-ttu-id="738f6-104">Windows Management Framework (WMF) は配信メカニズムであり、さまざまな種類の Windows や Windows Server に一貫した管理インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="738f6-104">Windows Management Framework (WMF) is the delivery mechanism that provides a consistent management interface across the various flavors of Windows and Windows Server.</span></span>
<span data-ttu-id="738f6-105">WMF をインストールすると、お客様はご利用の環境で OS をシームレスにミックスし、相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="738f6-105">With the installation of WMF, customers get a seamless way to interoperate between mixes of OSes in their environment.</span></span>
<span data-ttu-id="738f6-106">WMF は一部の Windows や Windows Server の管理機能を更新します。以前のバージョンの Windows と Windows Server でインストールできます (通常、2 つ下のバージョンまで)。</span><span class="sxs-lookup"><span data-stu-id="738f6-106">WMF makes the updates to management functionality, in a given release of Windows and Windows Server, available for installation on lower versions (typically, 2 lower versions) of Windows and Windows Server.</span></span>

<span data-ttu-id="738f6-107">WMF をインストールすると、次の機能が追加または更新されます。</span><span class="sxs-lookup"><span data-stu-id="738f6-107">WMF installation adds and/or updates the following features:</span></span>

- <span data-ttu-id="738f6-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="738f6-108">Windows PowerShell</span></span>
- <span data-ttu-id="738f6-109">Windows PowerShell Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="738f6-109">Windows PowerShell Desired State Configuration (DSC)</span></span>
- <span data-ttu-id="738f6-110">Windows PowerShell Integrated Script Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="738f6-110">Windows PowerShell Integrated Script Environment (ISE)</span></span>
- <span data-ttu-id="738f6-111">Windows リモート管理 (WinRM)</span><span class="sxs-lookup"><span data-stu-id="738f6-111">Windows Remote Management (WinRM)</span></span>
- <span data-ttu-id="738f6-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="738f6-112">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="738f6-113">Windows PowerShell Web サービス (Management OData IIS 拡張機能)</span><span class="sxs-lookup"><span data-stu-id="738f6-113">Windows PowerShell Web Services (Management OData IIS Extension)</span></span>
- <span data-ttu-id="738f6-114">ソフトウェア インベントリ ログ (SIL)</span><span class="sxs-lookup"><span data-stu-id="738f6-114">Software Inventory Logging (SIL)</span></span>
- <span data-ttu-id="738f6-115">Server Manager CIM Provider</span><span class="sxs-lookup"><span data-stu-id="738f6-115">Server Manager CIM Provider</span></span>

## <a name="wmf-release-notes"></a><span data-ttu-id="738f6-116">WMF リリース ノート</span><span class="sxs-lookup"><span data-stu-id="738f6-116">WMF Release Notes</span></span>

<span data-ttu-id="738f6-117">PowerShell と特定の WMF のその他のコンポーネントのさまざまな拡張に関する詳細については、下のリンクにアクセスし、リリース ノートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="738f6-117">To learn about various enhancements in PowerShell and other components of a given WMF, please refer to the links below to review the release notes:</span></span>

- [<span data-ttu-id="738f6-118">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="738f6-118">WMF 5.1</span></span>](5.1/release-notes.md)
- [<span data-ttu-id="738f6-119">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="738f6-119">WMF 5.0</span></span>](5.0/releasenotes.md)
- [<span data-ttu-id="738f6-120">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="738f6-120">WMF 4.0</span></span>](https://download.microsoft.com/download/3/D/6/3D61D262-8549-4769-A660-230B67E15B25/Windows%20Management%20Framework%204%200%20Release%20Notes.docx)
- [<span data-ttu-id="738f6-121">WMF 3.0</span><span class="sxs-lookup"><span data-stu-id="738f6-121">WMF 3.0</span></span>](https://download.microsoft.com/download/E/7/6/E76850B8-DA6E-4FF5-8CCE-A24FC513FD16/WMF%203%20Release%20Notes.docx)

## <a name="wmf-availability-across-windows-operating-systems"></a><span data-ttu-id="738f6-122">Windows オペレーティング システム全体の WMF 可用性</span><span class="sxs-lookup"><span data-stu-id="738f6-122">WMF Availability Across Windows Operating Systems</span></span>

| <span data-ttu-id="738f6-123">オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="738f6-123">Operating System Version</span></span> | [<span data-ttu-id="738f6-124">WMF 5.1</span><span class="sxs-lookup"><span data-stu-id="738f6-124">WMF 5.1</span></span>](https://aka.ms/wmf51download) | [<span data-ttu-id="738f6-125">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="738f6-125">WMF 5.0</span></span>](https://aka.ms/wmf5download) | [<span data-ttu-id="738f6-126">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="738f6-126">WMF 4.0</span></span>](https://aka.ms/wmf4download) |  [<span data-ttu-id="738f6-127">WMF 3.0</span><span class="sxs-lookup"><span data-stu-id="738f6-127">WMF 3.0</span></span>](https://aka.ms/wmf3download) | [<span data-ttu-id="738f6-128">WMF 2.0</span><span class="sxs-lookup"><span data-stu-id="738f6-128">WMF 2.0</span></span>](https://aka.ms/wmf2download) |
| ------------------------ | ----------- | ----------- | ----------- | ------------ |  ------------- |
| <span data-ttu-id="738f6-129">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="738f6-129">Windows Server 2016</span></span> | <span data-ttu-id="738f6-130">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-130">Ships in-box</span></span> |  |  |  |  |
| <span data-ttu-id="738f6-131">Windows 10</span><span class="sxs-lookup"><span data-stu-id="738f6-131">Windows 10</span></span> | <span data-ttu-id="738f6-132">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-132">Ships in-box</span></span> | <span data-ttu-id="738f6-133">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-133">Ships in-box</span></span>  | | | |  
| <span data-ttu-id="738f6-134">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="738f6-134">Windows Server 2012 R2</span></span>| <span data-ttu-id="738f6-135">可</span><span class="sxs-lookup"><span data-stu-id="738f6-135">Yes</span></span> | <span data-ttu-id="738f6-136">可</span><span class="sxs-lookup"><span data-stu-id="738f6-136">Yes</span></span> | <span data-ttu-id="738f6-137">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-137">Ships in-box</span></span> |  |  |
| <span data-ttu-id="738f6-138">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="738f6-138">Windows 8.1</span></span> | <span data-ttu-id="738f6-139">可</span><span class="sxs-lookup"><span data-stu-id="738f6-139">Yes</span></span> | <span data-ttu-id="738f6-140">可</span><span class="sxs-lookup"><span data-stu-id="738f6-140">Yes</span></span> |  <span data-ttu-id="738f6-141">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-141">Ships in-box</span></span> |  |  |
| <span data-ttu-id="738f6-142">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="738f6-142">Windows Server 2012</span></span> | <span data-ttu-id="738f6-143">可</span><span class="sxs-lookup"><span data-stu-id="738f6-143">Yes</span></span> | <span data-ttu-id="738f6-144">可</span><span class="sxs-lookup"><span data-stu-id="738f6-144">Yes</span></span> | <span data-ttu-id="738f6-145">可</span><span class="sxs-lookup"><span data-stu-id="738f6-145">Yes</span></span> |  <span data-ttu-id="738f6-146">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-146">Ships in-box</span></span> | |
| <span data-ttu-id="738f6-147">Windows 8</span><span class="sxs-lookup"><span data-stu-id="738f6-147">Windows 8</span></span> |  |  |  | <span data-ttu-id="738f6-148">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-148">Ships in-box</span></span> | |
| <span data-ttu-id="738f6-149">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="738f6-149">Windows Server 2008 R2 SP1</span></span> | <span data-ttu-id="738f6-150">可</span><span class="sxs-lookup"><span data-stu-id="738f6-150">Yes</span></span> | <span data-ttu-id="738f6-151">可</span><span class="sxs-lookup"><span data-stu-id="738f6-151">Yes</span></span> | <span data-ttu-id="738f6-152">可</span><span class="sxs-lookup"><span data-stu-id="738f6-152">Yes</span></span> |  <span data-ttu-id="738f6-153">可</span><span class="sxs-lookup"><span data-stu-id="738f6-153">Yes</span></span>| <span data-ttu-id="738f6-154">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-154">Ships in-box</span></span> |
| <span data-ttu-id="738f6-155">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="738f6-155">Windows 7 SP1</span></span>  | <span data-ttu-id="738f6-156">可</span><span class="sxs-lookup"><span data-stu-id="738f6-156">Yes</span></span> | <span data-ttu-id="738f6-157">可</span><span class="sxs-lookup"><span data-stu-id="738f6-157">Yes</span></span> | <span data-ttu-id="738f6-158">可</span><span class="sxs-lookup"><span data-stu-id="738f6-158">Yes</span></span> | <span data-ttu-id="738f6-159">可</span><span class="sxs-lookup"><span data-stu-id="738f6-159">Yes</span></span> | <span data-ttu-id="738f6-160">出荷時にインストール済み</span><span class="sxs-lookup"><span data-stu-id="738f6-160">Ships in-box</span></span> |
| <span data-ttu-id="738f6-161">Windows Server 2008 SP2</span><span class="sxs-lookup"><span data-stu-id="738f6-161">Windows Server 2008 SP2</span></span> | | | | <span data-ttu-id="738f6-162">可</span><span class="sxs-lookup"><span data-stu-id="738f6-162">Yes</span></span> | <span data-ttu-id="738f6-163">可</span><span class="sxs-lookup"><span data-stu-id="738f6-163">Yes</span></span> |
| <span data-ttu-id="738f6-164">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="738f6-164">Windows Vista</span></span> | | | | | <span data-ttu-id="738f6-165">可</span><span class="sxs-lookup"><span data-stu-id="738f6-165">Yes</span></span> |
| <span data-ttu-id="738f6-166">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="738f6-166">Windows Server 2003</span></span>| | | |  | <span data-ttu-id="738f6-167">可</span><span class="sxs-lookup"><span data-stu-id="738f6-167">Yes</span></span> |
| <span data-ttu-id="738f6-168">Windows XP</span><span class="sxs-lookup"><span data-stu-id="738f6-168">Windows XP</span></span> | | | |  | <span data-ttu-id="738f6-169">可</span><span class="sxs-lookup"><span data-stu-id="738f6-169">Yes</span></span> |

<span data-ttu-id="738f6-170">**"出荷時にインストール済み"**: `specified WMF` の機能は、示されているバージョンの Windows および Windows Server に付属しています。</span><span class="sxs-lookup"><span data-stu-id="738f6-170">**"Ships in-box"**: The features of the `specified WMF` were shipped in the indicated version of  Windows and Windows Server.</span></span>
<span data-ttu-id="738f6-171">したがって、示されているオペレーティング システムのバージョンには、`specified WMF` をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="738f6-171">Hence, the `specified WMF` doesn't need to be installed on the indicated operating system versions.</span></span>
