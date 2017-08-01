---
title: Windows Management Framework (WMF)
ms.date: 2016-05-16
keywords: "PowerShell、WMF"
description: 
ms.topic: article
author: keithb
manager: dongill
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: eacd33d2a0a92977a3990132e23eef9871a7f0dc
ms.sourcegitcommit: c732e3ee6d2e0e9cd8c40105d6fbfd4d207b730d
ms.translationtype: HT
ms.contentlocale: ja-JP
---
# <a name="windows-management-framework"></a><span data-ttu-id="cceef-103">Windows Management Framework</span><span class="sxs-lookup"><span data-stu-id="cceef-103">Windows Management Framework</span></span>

<span data-ttu-id="cceef-104">Windows Management Framework (WMF) は配信メカニズムであり、さまざまな種類の Windows や Windows Server に一貫した管理インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cceef-104">Windows Management Framework (WMF) is the delivery mechanism that provides a consistent management interface across the various flavors of Windows and Windows Server.</span></span>
<span data-ttu-id="cceef-105">WMF をインストールすると、お客様はご利用の環境で OS をシームレスにミックスし、相互運用できます。</span><span class="sxs-lookup"><span data-stu-id="cceef-105">With the installation of WMF, customers get a seamless way to interoperate between mixes of OSes in their environment.</span></span>
<span data-ttu-id="cceef-106">WMF は一部の Windows や Windows Server の管理機能を更新します。以前のバージョンの Windows と Windows Server でインストールできます (通常、2 つ下のバージョンまで)。</span><span class="sxs-lookup"><span data-stu-id="cceef-106">WMF makes the updates to management functionality, in a given release of Windows and Windows Server, available for installation on lower versions (typically, 2 lower versions) of Windows and Windows Server.</span></span>

<span data-ttu-id="cceef-107">WMF をインストールすると、次の機能が追加または更新されます。</span><span class="sxs-lookup"><span data-stu-id="cceef-107">WMF installation adds and/or updates the following features:</span></span>

- <span data-ttu-id="cceef-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cceef-108">Windows PowerShell</span></span>
- <span data-ttu-id="cceef-109">Windows PowerShell Desired State Configuration (DSC)</span><span class="sxs-lookup"><span data-stu-id="cceef-109">Windows PowerShell Desired State Configuration (DSC)</span></span>
- <span data-ttu-id="cceef-110">Windows PowerShell Integrated Script Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="cceef-110">Windows PowerShell Integrated Script Environment (ISE)</span></span>
- <span data-ttu-id="cceef-111">Windows リモート管理 (WinRM)</span><span class="sxs-lookup"><span data-stu-id="cceef-111">Windows Remote Management (WinRM)</span></span>
- <span data-ttu-id="cceef-112">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="cceef-112">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="cceef-113">Windows PowerShell Web サービス (Management OData IIS 拡張機能)</span><span class="sxs-lookup"><span data-stu-id="cceef-113">Windows PowerShell Web Services (Management OData IIS Extension)</span></span>
- <span data-ttu-id="cceef-114">ソフトウェア インベントリ ログ (SIL)</span><span class="sxs-lookup"><span data-stu-id="cceef-114">Software Inventory Logging (SIL)</span></span>
- <span data-ttu-id="cceef-115">Server Manager CIM Provider</span><span class="sxs-lookup"><span data-stu-id="cceef-115">Server Manager CIM Provider</span></span>

## <a name="wmf-release-notes"></a><span data-ttu-id="cceef-116">WMF リリース ノート</span><span class="sxs-lookup"><span data-stu-id="cceef-116">WMF Release Notes</span></span>
<span data-ttu-id="cceef-117">PowerShell と特定の WMF のその他のコンポーネントのさまざまな拡張に関する詳細については、下のリンクにアクセスし、リリース ノートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cceef-117">To learn about various enhancements in PowerShell and other components of a given WMF, please refer to the links below to review the release notes:</span></span>


- [<span data-ttu-id="cceef-118">WMF 5.1 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="cceef-118">WMF 5.1 (Preview)</span></span>](5.1/release-notes.md)
- [<span data-ttu-id="cceef-119">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="cceef-119">WMF 5.0</span></span>](5.0/releasenotes.md)


## <a name="wmf-availability-across-windows-operating-systems"></a><span data-ttu-id="cceef-120">Windows オペレーティング システム全体の WMF 可用性</span><span class="sxs-lookup"><span data-stu-id="cceef-120">WMF Availability Across Windows Operating Systems</span></span>

><span data-ttu-id="cceef-121">TODO: 列ヘッダーの特定の WMF DLC にリンクを追加する</span><span class="sxs-lookup"><span data-stu-id="cceef-121">TODO: Add links to specific WMF DLC on the column header</span></span>

| <span data-ttu-id="cceef-122">オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="cceef-122">Operating System Version</span></span> | [<span data-ttu-id="cceef-123">WMF 5.1 プレビュー*</span><span class="sxs-lookup"><span data-stu-id="cceef-123">WMF 5.1 Preview*</span></span>]() | [<span data-ttu-id="cceef-124">WMF 5.0</span><span class="sxs-lookup"><span data-stu-id="cceef-124">WMF 5.0</span></span>]() | [<span data-ttu-id="cceef-125">WMF 4.0</span><span class="sxs-lookup"><span data-stu-id="cceef-125">WMF 4.0</span></span>]() |  [<span data-ttu-id="cceef-126">WMF 3.0</span><span class="sxs-lookup"><span data-stu-id="cceef-126">WMF 3.0</span></span>]() | [<span data-ttu-id="cceef-127">WMF (2.0)</span><span class="sxs-lookup"><span data-stu-id="cceef-127">WMF (2.0)</span></span>]() |
| ------------------------ | ----------- | ----------- | ----------- | ------------ |  ------------- |
| <span data-ttu-id="cceef-128">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="cceef-128">Windows Server 2016</span></span> | <span data-ttu-id="cceef-129">箱で出荷*</span><span class="sxs-lookup"><span data-stu-id="cceef-129">Ships in-box*</span></span> | <span data-ttu-id="cceef-130">箱で出荷*</span><span class="sxs-lookup"><span data-stu-id="cceef-130">Ships in-box*</span></span> |  |  |  |
| <span data-ttu-id="cceef-131">Windows 10</span><span class="sxs-lookup"><span data-stu-id="cceef-131">Windows 10</span></span> | <span data-ttu-id="cceef-132">箱で出荷*</span><span class="sxs-lookup"><span data-stu-id="cceef-132">Ships in-box*</span></span> | <span data-ttu-id="cceef-133">箱で出荷*</span><span class="sxs-lookup"><span data-stu-id="cceef-133">Ships in-box*</span></span>  | | | |  
| <span data-ttu-id="cceef-134">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="cceef-134">Windows Server 2012 R2</span></span>| <span data-ttu-id="cceef-135">??</span><span class="sxs-lookup"><span data-stu-id="cceef-135">??</span></span> | <span data-ttu-id="cceef-136">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-136">Yes</span></span> | <span data-ttu-id="cceef-137">箱で出荷</span><span class="sxs-lookup"><span data-stu-id="cceef-137">Ships in-box</span></span> |  |  |
| <span data-ttu-id="cceef-138">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="cceef-138">Windows 8.1</span></span> | <span data-ttu-id="cceef-139">??</span><span class="sxs-lookup"><span data-stu-id="cceef-139">??</span></span> | <span data-ttu-id="cceef-140">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-140">Yes</span></span> |  <span data-ttu-id="cceef-141">箱で出荷</span><span class="sxs-lookup"><span data-stu-id="cceef-141">Ships in-box</span></span> |  |  |
| <span data-ttu-id="cceef-142">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="cceef-142">Windows Server 2012</span></span> | <span data-ttu-id="cceef-143">??</span><span class="sxs-lookup"><span data-stu-id="cceef-143">??</span></span> | <span data-ttu-id="cceef-144">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-144">Yes</span></span> | <span data-ttu-id="cceef-145">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-145">Yes</span></span> |  <span data-ttu-id="cceef-146">箱で出荷</span><span class="sxs-lookup"><span data-stu-id="cceef-146">Ships in-box</span></span> | |
| <span data-ttu-id="cceef-147">Windows 8</span><span class="sxs-lookup"><span data-stu-id="cceef-147">Windows 8</span></span> |  |  |  | <span data-ttu-id="cceef-148">箱で出荷</span><span class="sxs-lookup"><span data-stu-id="cceef-148">Ships in-box</span></span> | |
| <span data-ttu-id="cceef-149">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="cceef-149">Windows Server 2008 R2 SP1</span></span> | <span data-ttu-id="cceef-150">??</span><span class="sxs-lookup"><span data-stu-id="cceef-150">??</span></span> | <span data-ttu-id="cceef-151">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-151">Yes</span></span> | <span data-ttu-id="cceef-152">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-152">Yes</span></span> |  <span data-ttu-id="cceef-153">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-153">Yes</span></span>| <span data-ttu-id="cceef-154">箱で出荷</span><span class="sxs-lookup"><span data-stu-id="cceef-154">Ships in-box</span></span> |
| <span data-ttu-id="cceef-155">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="cceef-155">Windows 7 SP1</span></span>  | <span data-ttu-id="cceef-156">??</span><span class="sxs-lookup"><span data-stu-id="cceef-156">??</span></span> | <span data-ttu-id="cceef-157">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-157">Yes</span></span> | <span data-ttu-id="cceef-158">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-158">Yes</span></span> | <span data-ttu-id="cceef-159">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-159">Yes</span></span> | <span data-ttu-id="cceef-160">箱で出荷</span><span class="sxs-lookup"><span data-stu-id="cceef-160">Ships in-box</span></span> |
| <span data-ttu-id="cceef-161">Windows Server 2008 SP2</span><span class="sxs-lookup"><span data-stu-id="cceef-161">Windows Server 2008 SP2</span></span> | | | | <span data-ttu-id="cceef-162">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-162">Yes</span></span> | <span data-ttu-id="cceef-163">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-163">Yes</span></span> |
| <span data-ttu-id="cceef-164">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="cceef-164">Windows Vista</span></span> | | | | | <span data-ttu-id="cceef-165">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-165">Yes</span></span> |
| <span data-ttu-id="cceef-166">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="cceef-166">Windows Server 2003</span></span>| | | |  | <span data-ttu-id="cceef-167">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-167">Yes</span></span> |
| <span data-ttu-id="cceef-168">Windows XP</span><span class="sxs-lookup"><span data-stu-id="cceef-168">Windows XP</span></span> | | | |  | <span data-ttu-id="cceef-169">はい</span><span class="sxs-lookup"><span data-stu-id="cceef-169">Yes</span></span> |

><span data-ttu-id="cceef-170">TODO: 上の表の * を説明</span><span class="sxs-lookup"><span data-stu-id="cceef-170">TODO: Explain * in the above table</span></span>
