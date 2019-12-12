---
title: Windows PowerShell の概念 |Microsoft Docs
ms.custom: ''
ms.date: 6/12/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3dd5608e-50b6-4c6a-aee3-dde0e86032bc
caps.latest.revision: 7
ms.openlocfilehash: 4410b1f9c80afefd5479fa68154f9947b805edcf
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72366681"
---
# <a name="windows-powershell-concepts"></a><span data-ttu-id="df436-102">Windows PowerShell の概念</span><span class="sxs-lookup"><span data-stu-id="df436-102">Windows PowerShell Concepts</span></span>

<span data-ttu-id="df436-103">このセクションには、開発者の視点から PowerShell を理解するのに役立つ概念情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="df436-103">This section contains conceptual information that will help you understand PowerShell from a developer's viewpoint.</span></span>

|<span data-ttu-id="df436-104">トピック名</span><span class="sxs-lookup"><span data-stu-id="df436-104">Topic Name</span></span>|<span data-ttu-id="df436-105">[説明]</span><span class="sxs-lookup"><span data-stu-id="df436-105">Description</span></span>|
|----------------|-----------------|
|[<span data-ttu-id="df436-106">about_Objects</span><span class="sxs-lookup"><span data-stu-id="df436-106">about_Objects</span></span>](/powershell/module/microsoft.powershell.core/about/about_objects)|<span data-ttu-id="df436-107">PowerShell オブジェクトの説明。</span><span class="sxs-lookup"><span data-stu-id="df436-107">Description of PowerShell objects.</span></span> <span data-ttu-id="df436-108">詳細については、「[オブジェクトの作成につい](/powershell/module/microsoft.powershell.core/about/about_object_creation)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df436-108">For more information, see [About Object Creation](/powershell/module/microsoft.powershell.core/about/about_object_creation)</span></span>|
|[<span data-ttu-id="df436-109">実行空間の作成</span><span class="sxs-lookup"><span data-stu-id="df436-109">Creating Runspaces</span></span>](../hosting/creating-runspaces.md)|<span data-ttu-id="df436-110">コマンドが処理されるオペレーティング環境。</span><span class="sxs-lookup"><span data-stu-id="df436-110">The operating environments where commands are processed.</span></span> <span data-ttu-id="df436-111">詳細については、「実行[空間クラス](/dotnet/api/system.management.automation.runspaces.runspace)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df436-111">For more information, see [Runspace Class](/dotnet/api/system.management.automation.runspaces.runspace).</span></span>|
|[<span data-ttu-id="df436-112">出力オブジェクトの拡張</span><span class="sxs-lookup"><span data-stu-id="df436-112">Extending Output Objects</span></span>](../cmdlet/extending-output-objects.md)|<span data-ttu-id="df436-113">PowerShell オブジェクトを拡張する方法。</span><span class="sxs-lookup"><span data-stu-id="df436-113">How to extend PowerShell objects.</span></span> <span data-ttu-id="df436-114">詳細については、「[型について](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)」を参照してください。 types.ps1xml</span><span class="sxs-lookup"><span data-stu-id="df436-114">For more information, see [About Types.ps1xml](/powershell/module/microsoft.powershell.core/about/about_types.ps1xml)</span></span>|
|[<span data-ttu-id="df436-115">コマンドレットの登録</span><span class="sxs-lookup"><span data-stu-id="df436-115">Registering Cmdlets</span></span>](../cmdlet/registering-cmdlets.md)|<span data-ttu-id="df436-116">モジュールとスナップインを PowerShell で使用できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="df436-116">How to make modules and snap-ins available in PowerShell.</span></span> <span data-ttu-id="df436-117">詳細については、「[モジュールとスナップイン](../cmdlet/modules-and-snap-ins.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df436-117">For more information, see [Modules and Snap-ins](../cmdlet/modules-and-snap-ins.md).</span></span>|
|[<span data-ttu-id="df436-118">コマンドレットからの確認要求</span><span class="sxs-lookup"><span data-stu-id="df436-118">Requesting Confirmation from Cmdlets</span></span>](../cmdlet/requesting-confirmation-from-cmdlets.md)|<span data-ttu-id="df436-119">アクションを実行する前に、コマンドレットとプロバイダーがユーザーからフィードバックを要求する方法。</span><span class="sxs-lookup"><span data-stu-id="df436-119">How cmdlets and providers request feedback from the user before an action is taken.</span></span>|
|[<span data-ttu-id="df436-120">Runtime、Parameter クラス</span><span class="sxs-lookup"><span data-stu-id="df436-120">RuntimeDefinedParameter Class</span></span>](/dotnet/api/system.management.automation.runtimedefinedparameter)|<span data-ttu-id="df436-121">ランタイムパラメーターの宣言。</span><span class="sxs-lookup"><span data-stu-id="df436-121">Runtime parameter declarations.</span></span>|
|[<span data-ttu-id="df436-122">System.servicemodel 名前空間</span><span class="sxs-lookup"><span data-stu-id="df436-122">System.Management.Automation Namespace</span></span>](/dotnet/api/System.Management.Automation)|<span data-ttu-id="df436-123">PowerShell API 名前空間の概要。</span><span class="sxs-lookup"><span data-stu-id="df436-123">Overview of PowerShell API namespaces.</span></span>|
|[<span data-ttu-id="df436-124">Windows PowerShell プロバイダーの概要</span><span class="sxs-lookup"><span data-stu-id="df436-124">Windows PowerShell Provider Overview</span></span>](../provider/windows-powershell-provider-overview.md)|<span data-ttu-id="df436-125">データストアへのアクセスに使用される PowerShell プロバイダーについての概要です。</span><span class="sxs-lookup"><span data-stu-id="df436-125">Overview about PowerShell providers that are used to access data stores.</span></span>|
|[<span data-ttu-id="df436-126">PowerShell コマンドレットのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="df436-126">Writing Help for PowerShell Cmdlets</span></span>](../help/writing-help-for-windows-powershell-cmdlets.md)|<span data-ttu-id="df436-127">PowerShell コマンドレットのヘルプを記述する方法。</span><span class="sxs-lookup"><span data-stu-id="df436-127">How to write PowerShell cmdlet Help.</span></span>|

## <a name="see-also"></a><span data-ttu-id="df436-128">「</span><span class="sxs-lookup"><span data-stu-id="df436-128">See also</span></span>

[<span data-ttu-id="df436-129">PowerShell クラス</span><span class="sxs-lookup"><span data-stu-id="df436-129">PowerShell Class</span></span>](/dotnet/api/system.management.automation.powershell)

[<span data-ttu-id="df436-130">PowerShell Core API リファレンス</span><span class="sxs-lookup"><span data-stu-id="df436-130">PowerShell Core API Reference</span></span>](/dotnet/api/?view=pscore-6.2.0)

[<span data-ttu-id="df436-131">Windows PowerShell プログラマーズガイド</span><span class="sxs-lookup"><span data-stu-id="df436-131">Windows PowerShell Programmer's Guide</span></span>](windows-powershell-programmer-s-guide.md)

[<span data-ttu-id="df436-132">Windows PowerShell モジュールのヘルプの作成</span><span class="sxs-lookup"><span data-stu-id="df436-132">Writing Help for Windows PowerShell Modules</span></span>](../module/writing-help-for-windows-powershell-modules.md)

[<span data-ttu-id="df436-133">Windows Powershell プロバイダーの作成</span><span class="sxs-lookup"><span data-stu-id="df436-133">Writing a Windows Powershell Provider</span></span>](../provider/writing-a-windows-powershell-provider.md)

[<span data-ttu-id="df436-134">Windows PowerShell API リファレンス</span><span class="sxs-lookup"><span data-stu-id="df436-134">Windows PowerShell API Reference</span></span>](/dotnet/api/?view=powershellsdk-1.1.0)

[<span data-ttu-id="df436-135">Windows PowerShell リファレンス</span><span class="sxs-lookup"><span data-stu-id="df436-135">Windows PowerShell Reference</span></span>](../windows-powershell-reference.md)