---
ms.date: 12/31/2019
title: ISE オブジェクト モデルの階層
description: この記事では、Windows PowerShell ISE の一部であるオブジェクトの階層について説明します。
ms.openlocfilehash: 00980cda72f05bc6ccb398079b129de13a98f783
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658311"
---
# <a name="the-ise-object-model-hierarchy"></a><span data-ttu-id="82c31-103">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="82c31-103">The ISE Object Model Hierarchy</span></span>

<span data-ttu-id="82c31-104">この記事では、Windows PowerShell Integrated Scripting Environment (ISE) の一部であるオブジェクトの階層について説明します。</span><span class="sxs-lookup"><span data-stu-id="82c31-104">This article shows the hierarchy of objects that are part of Windows PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="82c31-105">Windows PowerShell ISE は、Windows PowerShell 3.0、4.0、5.1 に付属しています。</span><span class="sxs-lookup"><span data-stu-id="82c31-105">Windows PowerShell ISE is included in Windows PowerShell 3.0, 4.0, and 5.1.</span></span> <span data-ttu-id="82c31-106">オブジェクトをクリックすると、そのオブジェクトを定義するクラスのリファレンス ドキュメントに移動します。</span><span class="sxs-lookup"><span data-stu-id="82c31-106">Click an object to take you to the reference documentation for the class that defines the object.</span></span>

## <a name="psise-object"></a><span data-ttu-id="82c31-107">$psISE オブジェクト</span><span class="sxs-lookup"><span data-stu-id="82c31-107">$psISE Object</span></span>

<span data-ttu-id="82c31-108">`$psISE` オブジェクトは、Windows PowerShell ISE オブジェクト階層の[ルート オブジェクト](The-ObjectModelRoot-Object.md)です。</span><span class="sxs-lookup"><span data-stu-id="82c31-108">The `$psISE` object is the [root object](The-ObjectModelRoot-Object.md) of the Windows PowerShell ISE object hierarchy.</span></span> <span data-ttu-id="82c31-109">最上位のこのオブジェクトでは、スクリプト作成に次のオブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="82c31-109">Located at the top level, it makes the following objects available for scripting:</span></span>

## <a name="psisecurrentfile"></a>[<span data-ttu-id="82c31-110">$psISE.CurrentFile</span><span class="sxs-lookup"><span data-stu-id="82c31-110">$psISE.CurrentFile</span></span>](The-ISEFile-Object.md)

<span data-ttu-id="82c31-111">`$psISE.CurrentFile` オブジェクトは、[ISEFile](The-ISEFile-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="82c31-111">The `$psISE.CurrentFile` object is an instance of the [ISEFile](The-ISEFile-Object.md) class.</span></span>

## <a name="psisecurrentpowershelltab"></a>[<span data-ttu-id="82c31-112">$psISE.CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="82c31-112">$psISE.CurrentPowerShellTab</span></span>](The-PowerShellTab-Object.md)

<span data-ttu-id="82c31-113">`$psISE.CurrentPowerShellTab` オブジェクトは、[PowerShellTab](The-PowerShellTab-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="82c31-113">The `$psISE.CurrentPowerShellTab` object is an instance of the [PowerShellTab](The-PowerShellTab-Object.md) class.</span></span>

## <a name="psisecurrentvisiblehorizontaltool"></a><span data-ttu-id="82c31-114">$psISE.CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="82c31-114">$psISE.CurrentVisibleHorizontalTool</span></span>

<span data-ttu-id="82c31-115">`$psISE.CurrentVisibleHorizontalTool` オブジェクトは、[ISEAddOnTool](The-ISEAddOnTool-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="82c31-115">The `$psISE.CurrentVisibleHorizontalTool` object is an instance of the [ISEAddOnTool](The-ISEAddOnTool-Object.md) class.</span></span> <span data-ttu-id="82c31-116">現在 [Windows PowerShell ISE] ウィンドウの上端にドッキングされているインストール済みのアドオンを表しています。</span><span class="sxs-lookup"><span data-stu-id="82c31-116">It represents the installed add-on tool that is currently docked to the top edge of the Windows PowerShell ISE window.</span></span>

## <a name="psisecurrentvisibleverticaltool"></a><span data-ttu-id="82c31-117">$psISE.CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="82c31-117">$psISE.CurrentVisibleVerticalTool</span></span>

<span data-ttu-id="82c31-118">`$psISE.CurrentVisibleHorizontalTool` オブジェクトは、[ISEAddOnTool](The-ISEAddOnTool-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="82c31-118">The `$psISE.CurrentVisibleHorizontalTool` object is an instance of the [ISEAddOnTool](The-ISEAddOnTool-Object.md) class.</span></span> <span data-ttu-id="82c31-119">現在 [Windows PowerShell ISE] ウィンドウの右端にドッキングされているインストール済みのアドオンを表しています。</span><span class="sxs-lookup"><span data-stu-id="82c31-119">It represents the installed add-on tool that is currently docked to the right-hand edge of the Windows PowerShell ISE window.</span></span>

## <a name="psiseoptions"></a>[<span data-ttu-id="82c31-120">$psISE.Options</span><span class="sxs-lookup"><span data-stu-id="82c31-120">$psISE.Options</span></span>](The-ISEOptions-Object.md)

<span data-ttu-id="82c31-121">`$psISE.Options` オブジェクトは、[ISEOptions](The-ISEOptions-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="82c31-121">The `$psISE.Options` object is an instance of the [ISEOptions](The-ISEOptions-Object.md) class.</span></span> <span data-ttu-id="82c31-122">ISEOptions オブジェクトは、Windows PowerShell ISE のさまざまな設定を表します。</span><span class="sxs-lookup"><span data-stu-id="82c31-122">The ISEOptions object represents various settings for Windows PowerShell ISE.</span></span> <span data-ttu-id="82c31-123">これは Microsoft.PowerShell.Host.ISE.ISEOptions クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="82c31-123">It is an instance of the Microsoft.PowerShell.Host.ISE.ISEOptions class.</span></span>

## <a name="psisepowershelltabs"></a>[<span data-ttu-id="82c31-124">$psISE.PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="82c31-124">$psISE.PowerShellTabs</span></span>](The-PowerShellTabCollection-Object.md)

<span data-ttu-id="82c31-125">`$psISE.PowerShellTabs` オブジェクトは、[PowerShellTabCollection](The-PowerShellTabCollection-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="82c31-125">The `$psISE.PowerShellTabs` object is an instance of the [PowerShellTabCollection](The-PowerShellTabCollection-Object.md) class.</span></span> <span data-ttu-id="82c31-126">これは現在開いているすべての PowerShell タブのコレクションで、ローカル コンピューターまたは接続されているリモート コンピューターで利用可能な Windows PowerShell の実行環境を表しています。</span><span class="sxs-lookup"><span data-stu-id="82c31-126">It is a collection of all the currently open PowerShell tabs that represent the available Windows PowerShell run environments on the local computer or on connected remote computers.</span></span> <span data-ttu-id="82c31-127">コレクション内の個々のメンバーは [PowerShellTab](The-PowerShellTab-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="82c31-127">Each member in the collection is an instance of the [PowerShellTab](The-PowerShellTab-Object.md) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="82c31-128">参照</span><span class="sxs-lookup"><span data-stu-id="82c31-128">See Also</span></span>

- [<span data-ttu-id="82c31-129">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="82c31-129">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="82c31-130">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="82c31-130">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
