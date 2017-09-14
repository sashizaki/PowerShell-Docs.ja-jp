---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "ISE オブジェクト モデルの階層"
ms.openlocfilehash: 2df6d40f39dbe14bd3f46a6400cde4a6e91052ef
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="the-ise-object-model-hierarchy"></a><span data-ttu-id="f6ef0-103">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="f6ef0-103">The ISE Object Model Hierarchy</span></span>
<span data-ttu-id="f6ef0-104">このトピックでは、Windows PowerShell Integrated Scripting Environment (ISE) の一部であるオブジェクトの階層について説明します。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-104">This topic shows the hierarchy of objects that are part of Windows PowerShell Integrated Scripting Environment (ISE).</span></span> <span data-ttu-id="f6ef0-105">Windows PowerShell ISE は、Windows PowerShell 3.0 と Windows PowerShell 4.0 に付属しています。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-105">Windows PowerShell ISE is included in Windows PowerShell 3.0 and in Windows PowerShell 4.0.</span></span> <span data-ttu-id="f6ef0-106">オブジェクトをクリックすると、そのオブジェクトを定義するクラスのリファレンス ドキュメントに移動します。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-106">Click an object to take you to the reference documentation for the class that defines the object.</span></span>

## <a name="psise-object"></a><span data-ttu-id="f6ef0-107">$psISE オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f6ef0-107">$psISE Object</span></span>

<span data-ttu-id="f6ef0-108">**$psISE** オブジェクトは、Windows PowerShell ISE オブジェクト階層の[ルート オブジェクト](The-ObjectModelRoot-Object.md)です。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-108">The **$psISE** object is the [root object](The-ObjectModelRoot-Object.md) of the Windows PowerShell ISE object hierarchy.</span></span>
<span data-ttu-id="f6ef0-109">最上位のこのオブジェクトでは、スクリプト作成に次のオブジェクトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-109">Located at the top level, it makes the following objects available for scripting:</span></span>

## <a name="psisecurrentfilethe-isefile-objectmd"></a>[<span data-ttu-id="f6ef0-110">$psISE.CurrentFile</span><span class="sxs-lookup"><span data-stu-id="f6ef0-110">$psISE.CurrentFile</span></span>](The-ISEFile-Object.md)

<span data-ttu-id="f6ef0-111">**$PsISE.CurrentFile** オブジェクトは、[ISEFile](The-ISEFile-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-111">The **$psISE.CurrentFile** object is an instance of the [ISEFile](The-ISEFile-Object.md) class.</span></span>

## <a name="psisecurrentpowershelltabthe-powershelltab-objectmd"></a>[<span data-ttu-id="f6ef0-112">$psISE.CurrentPowerShellTab</span><span class="sxs-lookup"><span data-stu-id="f6ef0-112">$psISE.CurrentPowerShellTab</span></span>](The-PowerShellTab-Object.md)

<span data-ttu-id="f6ef0-113">**$psISE.CurrentPowerShellTab** オブジェクトは、[PowerShellTab](The-PowerShellTab-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-113">The **$psISE.CurrentPowerShellTab** object is an instance of the [PowerShellTab](The-PowerShellTab-Object.md) class.</span></span>

## <a name="psisecurrentvisiblehorizontaltool"></a><span data-ttu-id="f6ef0-114">$psISE.CurrentVisibleHorizontalTool</span><span class="sxs-lookup"><span data-stu-id="f6ef0-114">$psISE.CurrentVisibleHorizontalTool</span></span>

<span data-ttu-id="f6ef0-115">**$psISE.CurrentVisibleHorizontalTool** オブジェクトは [ISEAddOnTool](The-ISEAddOnTool-Object.md) クラスのインスタンスで、</span><span class="sxs-lookup"><span data-stu-id="f6ef0-115">The **$psISE.CurrentVisibleHorizontalTool** object is an instance of the [ISEAddOnTool](The-ISEAddOnTool-Object.md) class.</span></span>
<span data-ttu-id="f6ef0-116">現在 [Windows PowerShell ISE] ウィンドウの上端にドッキングされているインストール済みのアドオンを表しています。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-116">It represents the installed add-on tool that is currently docked to the top edge of the Windows PowerShell ISE window.</span></span>

## <a name="psisecurrentvisibleverticaltool"></a><span data-ttu-id="f6ef0-117">$psISE.CurrentVisibleVerticalTool</span><span class="sxs-lookup"><span data-stu-id="f6ef0-117">$psISE.CurrentVisibleVerticalTool</span></span>

<span data-ttu-id="f6ef0-118">**$psISE.CurrentVisibleHorizontalTool** オブジェクトは [ISEAddOnTool](The-ISEAddOnTool-Object.md) クラスのインスタンスで、</span><span class="sxs-lookup"><span data-stu-id="f6ef0-118">The **$psISE.CurrentVisibleHorizontalTool** object is an instance of the [ISEAddOnTool](The-ISEAddOnTool-Object.md) class.</span></span>
<span data-ttu-id="f6ef0-119">現在 [Windows PowerShell ISE] ウィンドウの右端にドッキングされているインストール済みのアドオンを表しています。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-119">It represents the installed add-on tool that is currently docked to the right-hand edge of the Windows PowerShell ISE window.</span></span>

## <a name="psiseoptionsthe-iseoptions-objectmd"></a>[<span data-ttu-id="f6ef0-120">$psISE.Options</span><span class="sxs-lookup"><span data-stu-id="f6ef0-120">$psISE.Options</span></span>](The-ISEOptions-Object.md)

<span data-ttu-id="f6ef0-121">**$psISE.Options** オブジェクトは、[ISEOptions](The-ISEOptions-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-121">The **$psISE.Options** object is an instance of the [ISEOptions](The-ISEOptions-Object.md) class.</span></span>
<span data-ttu-id="f6ef0-122">ISEOptions オブジェクトは、Windows PowerShell ISE のさまざまな設定を表します。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-122">The ISEOptions object represents various settings for Windows PowerShell ISE.</span></span>
<span data-ttu-id="f6ef0-123">これは Microsoft.PowerShell.Host.ISE.ISEOptions クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-123">It is an instance of the Microsoft.PowerShell.Host.ISE.ISEOptions class.</span></span>

## <a name="psisepowershelltabsthe-powershelltabcollection-objectmd"></a>[<span data-ttu-id="f6ef0-124">$psISE.PowerShellTabs</span><span class="sxs-lookup"><span data-stu-id="f6ef0-124">$psISE.PowerShellTabs</span></span>](The-PowerShellTabCollection-Object.md)

<span data-ttu-id="f6ef0-125">**$psISE.PowerShellTabs** オブジェクトは [PowerShellTabCollection](The-PowerShellTabCollection-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-125">The **$psISE.PowerShellTabs** object is an instance of the [PowerShellTabCollection](The-PowerShellTabCollection-Object.md) class.</span></span>
<span data-ttu-id="f6ef0-126">これは現在開いているすべての PowerShell タブのコレクションで、ローカル コンピューターまたは接続されているリモート コンピューターで利用可能な Windows PowerShell の実行環境を表しています。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-126">It is a collection of all the currently open PowerShell tabs that represent the available Windows PowerShell run environments on the local computer or on connected remote computers.</span></span> <span data-ttu-id="f6ef0-127">コレクション内の個々のメンバーは [PowerShellTab](The-PowerShellTab-Object.md) クラスのインスタンスです。</span><span class="sxs-lookup"><span data-stu-id="f6ef0-127">Each member in the collection is an instance of the [PowerShellTab](The-PowerShellTab-Object.md) class.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6ef0-128">参照</span><span class="sxs-lookup"><span data-stu-id="f6ef0-128">See Also</span></span>
- [<span data-ttu-id="f6ef0-129">Windows PowerShell ISE スクリプト オブジェクト モデル</span><span class="sxs-lookup"><span data-stu-id="f6ef0-129">The Windows PowerShell ISE Scripting Object Model</span></span>](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="f6ef0-130">Windows PowerShell ISE オブジェクト モデル リファレンス</span><span class="sxs-lookup"><span data-stu-id="f6ef0-130">Windows PowerShell ISE Object Model Reference</span></span>](Windows-PowerShell-ISE-Object-Model-Reference.md)
