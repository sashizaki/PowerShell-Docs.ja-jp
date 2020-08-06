---
title: Windows PowerShell の概念 |Microsoft Docs
ms.date: 6/12/2019
ms.openlocfilehash: a31c1df784b7b5f872c4647aece8fafa535db66b
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786953"
---
# <a name="windows-powershell-concepts"></a><span data-ttu-id="3a410-102">Windows PowerShell の概念</span><span class="sxs-lookup"><span data-stu-id="3a410-102">Windows PowerShell Concepts</span></span>

<span data-ttu-id="3a410-103">このセクションには、開発者の視点から PowerShell を理解するのに役立つ概念情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a410-103">This section contains conceptual information that will help you understand PowerShell from a developer's viewpoint.</span></span>

|<span data-ttu-id="3a410-104">トピック名</span><span class="sxs-lookup"><span data-stu-id="3a410-104">Topic Name</span></span>|<span data-ttu-id="3a410-105">説明</span><span class="sxs-lookup"><span data-stu-id="3a410-105">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="3a410-106">about_Objects</span><span class="sxs-lookup"><span data-stu-id="3a410-106">about_Objects</span></span>](/powershell/module/microsoft.powershell.core/about/about_objects)|<span data-ttu-id="3a410-107">PowerShell オブジェクトの説明。</span><span class="sxs-lookup"><span data-stu-id="3a410-107">Description of PowerShell objects.</span></span> <span data-ttu-id="3a410-108">詳細については、「[オブジェクトの作成につい](/powershell/module/microsoft.powershell.core/about/about_object_creation)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a410-108">For more information, see [About Object Creation](/powershell/module/microsoft.powershell.core/about/about_object_creation)</span></span>|
|[<span data-ttu-id="3a410-109">実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="3a410-109">Creating Runspaces</span></span>](../hosting/creating-runspaces.md)|<span data-ttu-id="3a410-110">コマンドが処理されるオペレーティング環境。</span><span class="sxs-lookup"><span data-stu-id="3a410-110">The operating environments where commands are processed.</span></span> <span data-ttu-id="3a410-111">詳細については、「実行[空間クラス](/dotnet/api/system.management.automation.runspaces.runspace)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a410-111">For more information, see [Runspace Class](/dotnet/api/system.management.automation.runspaces.runspace).</span></span>|
|[<span data-ttu-id="3a410-112">出力オブジェクトを拡張する</span><span class="sxs-lookup"><span data-stu-id="3a410-112">Extending Output Objects</span></span>](../cmdlet/extending-output-objects.md)|<span data-ttu-id="3a410-113">PowerShell オブジェクトを拡張する方法。</span><span class="sxs-lookup"><span data-stu-id="3a410-113">How to extend PowerShell objects.</span></span> <span data-ttu-id="3a410-114">詳細については、「 [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a410-114">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)</span></span>|
|[<span data-ttu-id="3a410-115">コマンドレットを登録する</span><span class="sxs-lookup"><span data-stu-id="3a410-115">Registering Cmdlets</span></span>](../cmdlet/registering-cmdlets.md)|<span data-ttu-id="3a410-116">モジュールとスナップインを PowerShell で使用できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a410-116">How to make modules and snap-ins available in PowerShell.</span></span> <span data-ttu-id="3a410-117">詳細については、「[モジュールとスナップイン](../cmdlet/modules-and-snap-ins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a410-117">For more information, see [Modules and Snap-ins](../cmdlet/modules-and-snap-ins.md).</span></span>|
|[<span data-ttu-id="3a410-118">コマンドレットからの確認を要求する</span><span class="sxs-lookup"><span data-stu-id="3a410-118">Requesting Confirmation from Cmdlets</span></span>](../cmdlet/requesting-confirmation-from-cmdlets.md)|<span data-ttu-id="3a410-119">アクションを実行する前に、コマンドレットとプロバイダーがユーザーからフィードバックを要求する方法。</span><span class="sxs-lookup"><span data-stu-id="3a410-119">How cmdlets and providers request feedback from the user before an action is taken.</span></span>|
|[<span data-ttu-id="3a410-120">Runtime、Parameter クラス</span><span class="sxs-lookup"><span data-stu-id="3a410-120">RuntimeDefinedParameter Class</span></span>](/dotnet/api/system.management.automation.runtimedefinedparameter)|<span data-ttu-id="3a410-121">ランタイムパラメーターの宣言。</span><span class="sxs-lookup"><span data-stu-id="3a410-121">Runtime parameter declarations.</span></span>|
|[<span data-ttu-id="3a410-122">System.servicemodel 名前空間</span><span class="sxs-lookup"><span data-stu-id="3a410-122">System.Management.Automation Namespace</span></span>](/dotnet/api/System.Management.Automation)|<span data-ttu-id="3a410-123">PowerShell API 名前空間の概要。</span><span class="sxs-lookup"><span data-stu-id="3a410-123">Overview of PowerShell API namespaces.</span></span>|
|[<span data-ttu-id="3a410-124">Windows PowerShell プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="3a410-124">Windows PowerShell Provider Overview</span></span>](../provider/windows-powershell-provider-overview.md)|<span data-ttu-id="3a410-125">データストアへのアクセスに使用される PowerShell プロバイダーについての概要です。</span><span class="sxs-lookup"><span data-stu-id="3a410-125">Overview about PowerShell providers that are used to access data stores.</span></span>|
|[<span data-ttu-id="3a410-126">PowerShell コマンドレットのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="3a410-126">Writing Help for PowerShell Cmdlets</span></span>](../help/writing-help-for-windows-powershell-cmdlets.md)|<span data-ttu-id="3a410-127">PowerShell コマンドレットのヘルプを記述する方法。</span><span class="sxs-lookup"><span data-stu-id="3a410-127">How to write PowerShell cmdlet Help.</span></span>|

## <a name="see-also"></a><span data-ttu-id="3a410-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="3a410-128">See also</span></span>

[<span data-ttu-id="3a410-129">PowerShell クラス</span><span class="sxs-lookup"><span data-stu-id="3a410-129">PowerShell Class</span></span>](/dotnet/api/system.management.automation.powershell)

[<span data-ttu-id="3a410-130">PowerShell Core API リファレンス</span><span class="sxs-lookup"><span data-stu-id="3a410-130">PowerShell Core API Reference</span></span>](/dotnet/api/?view=pscore-6.2.0)

[<span data-ttu-id="3a410-131">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="3a410-131">Windows PowerShell Programmer's Guide</span></span>](windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="3a410-132">Windows PowerShell モジュールのヘルプを記述する</span><span class="sxs-lookup"><span data-stu-id="3a410-132">Writing Help for Windows PowerShell Modules</span></span>](../module/writing-help-for-windows-powershell-modules.md)

[<span data-ttu-id="3a410-133">Windows Powershell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="3a410-133">Writing a Windows Powershell Provider</span></span>](../provider/writing-a-windows-powershell-provider.md)

[<span data-ttu-id="3a410-134">Windows PowerShell API リファレンス</span><span class="sxs-lookup"><span data-stu-id="3a410-134">Windows PowerShell API Reference</span></span>](/dotnet/api/?view=powershellsdk-1.1.0)

[<span data-ttu-id="3a410-135">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="3a410-135">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)
