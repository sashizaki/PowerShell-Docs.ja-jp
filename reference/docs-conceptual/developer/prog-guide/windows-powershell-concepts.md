---
ms.date: 06/12/2019
ms.topic: reference
title: Windows PowerShell の概念
description: Windows PowerShell の概念
ms.openlocfilehash: a9b88a2e575b7ff7c036ce0fcbc035f0b55d0f5f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355360"
---
# <a name="windows-powershell-concepts"></a><span data-ttu-id="c7622-103">Windows PowerShell の概念</span><span class="sxs-lookup"><span data-stu-id="c7622-103">Windows PowerShell Concepts</span></span>

<span data-ttu-id="c7622-104">このセクションには、開発者の視点から PowerShell を理解するのに役立つ概念情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7622-104">This section contains conceptual information that will help you understand PowerShell from a developer's viewpoint.</span></span>

|<span data-ttu-id="c7622-105">トピック名</span><span class="sxs-lookup"><span data-stu-id="c7622-105">Topic Name</span></span>|<span data-ttu-id="c7622-106">説明</span><span class="sxs-lookup"><span data-stu-id="c7622-106">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="c7622-107">about_Objects</span><span class="sxs-lookup"><span data-stu-id="c7622-107">about_Objects</span></span>](/powershell/module/microsoft.powershell.core/about/about_objects)|<span data-ttu-id="c7622-108">PowerShell オブジェクトの説明。</span><span class="sxs-lookup"><span data-stu-id="c7622-108">Description of PowerShell objects.</span></span> <span data-ttu-id="c7622-109">詳細については、「[オブジェクトの作成につい](/powershell/module/microsoft.powershell.core/about/about_object_creation)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7622-109">For more information, see [About Object Creation](/powershell/module/microsoft.powershell.core/about/about_object_creation)</span></span>|
|[<span data-ttu-id="c7622-110">実行空間を作成する</span><span class="sxs-lookup"><span data-stu-id="c7622-110">Creating Runspaces</span></span>](../hosting/creating-runspaces.md)|<span data-ttu-id="c7622-111">コマンドが処理されるオペレーティング環境。</span><span class="sxs-lookup"><span data-stu-id="c7622-111">The operating environments where commands are processed.</span></span> <span data-ttu-id="c7622-112">詳細については、「実行 [空間クラス](/dotnet/api/system.management.automation.runspaces.runspace)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7622-112">For more information, see [Runspace Class](/dotnet/api/system.management.automation.runspaces.runspace).</span></span>|
|[<span data-ttu-id="c7622-113">出力オブジェクトを拡張する</span><span class="sxs-lookup"><span data-stu-id="c7622-113">Extending Output Objects</span></span>](../cmdlet/extending-output-objects.md)|<span data-ttu-id="c7622-114">PowerShell オブジェクトを拡張する方法。</span><span class="sxs-lookup"><span data-stu-id="c7622-114">How to extend PowerShell objects.</span></span> <span data-ttu-id="c7622-115">詳細については、「 [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7622-115">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)</span></span>|
|[<span data-ttu-id="c7622-116">コマンドレットを登録する</span><span class="sxs-lookup"><span data-stu-id="c7622-116">Registering Cmdlets</span></span>](../cmdlet/registering-cmdlets.md)|<span data-ttu-id="c7622-117">モジュールとスナップインを PowerShell で使用できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7622-117">How to make modules and snap-ins available in PowerShell.</span></span> <span data-ttu-id="c7622-118">詳細については、「 [モジュールとスナップイン](../cmdlet/modules-and-snap-ins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7622-118">For more information, see [Modules and Snap-ins](../cmdlet/modules-and-snap-ins.md).</span></span>|
|[<span data-ttu-id="c7622-119">コマンドレットからの確認を要求する</span><span class="sxs-lookup"><span data-stu-id="c7622-119">Requesting Confirmation from Cmdlets</span></span>](../cmdlet/requesting-confirmation-from-cmdlets.md)|<span data-ttu-id="c7622-120">アクションを実行する前に、コマンドレットとプロバイダーがユーザーからフィードバックを要求する方法。</span><span class="sxs-lookup"><span data-stu-id="c7622-120">How cmdlets and providers request feedback from the user before an action is taken.</span></span>|
|[<span data-ttu-id="c7622-121">Runtime、Parameter クラス</span><span class="sxs-lookup"><span data-stu-id="c7622-121">RuntimeDefinedParameter Class</span></span>](/dotnet/api/system.management.automation.runtimedefinedparameter)|<span data-ttu-id="c7622-122">ランタイムパラメーターの宣言。</span><span class="sxs-lookup"><span data-stu-id="c7622-122">Runtime parameter declarations.</span></span>|
|[<span data-ttu-id="c7622-123">System.servicemodel 名前空間</span><span class="sxs-lookup"><span data-stu-id="c7622-123">System.Management.Automation Namespace</span></span>](/dotnet/api/System.Management.Automation)|<span data-ttu-id="c7622-124">PowerShell API 名前空間の概要。</span><span class="sxs-lookup"><span data-stu-id="c7622-124">Overview of PowerShell API namespaces.</span></span>|
|[<span data-ttu-id="c7622-125">Windows PowerShell プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="c7622-125">Windows PowerShell Provider Overview</span></span>](../provider/windows-powershell-provider-overview.md)|<span data-ttu-id="c7622-126">データストアへのアクセスに使用される PowerShell プロバイダーについての概要です。</span><span class="sxs-lookup"><span data-stu-id="c7622-126">Overview about PowerShell providers that are used to access data stores.</span></span>|
|[<span data-ttu-id="c7622-127">PowerShell コマンドレットのヘルプの記述</span><span class="sxs-lookup"><span data-stu-id="c7622-127">Writing Help for PowerShell Cmdlets</span></span>](../help/writing-help-for-windows-powershell-cmdlets.md)|<span data-ttu-id="c7622-128">PowerShell コマンドレットのヘルプを記述する方法。</span><span class="sxs-lookup"><span data-stu-id="c7622-128">How to write PowerShell cmdlet Help.</span></span>|

## <a name="see-also"></a><span data-ttu-id="c7622-129">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7622-129">See also</span></span>

[<span data-ttu-id="c7622-130">PowerShell クラス</span><span class="sxs-lookup"><span data-stu-id="c7622-130">PowerShell Class</span></span>](/dotnet/api/system.management.automation.powershell)

[<span data-ttu-id="c7622-131">PowerShell Core API リファレンス</span><span class="sxs-lookup"><span data-stu-id="c7622-131">PowerShell Core API Reference</span></span>](/dotnet/api/?view=pscore-6.2.0&preserve-view=true)

[<span data-ttu-id="c7622-132">Windows PowerShell プログラマー ガイド</span><span class="sxs-lookup"><span data-stu-id="c7622-132">Windows PowerShell Programmer's Guide</span></span>](windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="c7622-133">Windows PowerShell モジュールのヘルプを記述する</span><span class="sxs-lookup"><span data-stu-id="c7622-133">Writing Help for Windows PowerShell Modules</span></span>](../module/writing-help-for-windows-powershell-modules.md)

[<span data-ttu-id="c7622-134">Windows Powershell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="c7622-134">Writing a Windows Powershell Provider</span></span>](../provider/writing-a-windows-powershell-provider.md)

[<span data-ttu-id="c7622-135">Windows PowerShell API リファレンス</span><span class="sxs-lookup"><span data-stu-id="c7622-135">Windows PowerShell API Reference</span></span>](/dotnet/api/?view=powershellsdk-1.1.0&preserve-view=true)

[<span data-ttu-id="c7622-136">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="c7622-136">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)
