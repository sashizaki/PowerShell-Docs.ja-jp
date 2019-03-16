---
title: Windows PowerShell セッションの状態 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Cmdlets [PowerShell], session state
- session state [PowerShell]
ms.assetid: 74912940-2b10-4a76-b174-6d035d71c02b
caps.latest.revision: 8
ms.openlocfilehash: fa207130bbb120750780bb0aa9b32150a32daaa2
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059543"
---
# <a name="windows-powershell-session-state"></a><span data-ttu-id="d9943-102">Windows PowerShell セッション状態</span><span class="sxs-lookup"><span data-stu-id="d9943-102">Windows PowerShell Session State</span></span>

<span data-ttu-id="d9943-103">セッション状態は、Windows PowerShell セッションまたはモジュールの現在の構成を参照します。</span><span class="sxs-lookup"><span data-stu-id="d9943-103">Session state refers to the current configuration of a Windows PowerShell session or module.</span></span> <span data-ttu-id="d9943-104">Windows PowerShell セッションは、コマンド ライン ユーザーまたはプログラムによって、ホスト アプリケーションによって対話的に使用される運用環境です。</span><span class="sxs-lookup"><span data-stu-id="d9943-104">A Windows PowerShell session is the operational environment that is used interactively by the command-line user or programmatically by a host application.</span></span> <span data-ttu-id="d9943-105">セッションのセッション状態が"グローバル セッション状態"と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="d9943-105">The session state for a session is referred to as the global session state.</span></span>

<span data-ttu-id="d9943-106">開発者の観点からは、Windows PowerShell セッションは、ホスト アプリケーションが Windows PowerShell 実行空間を開くと、実行空間が閉じられますまでの時間を指します。</span><span class="sxs-lookup"><span data-stu-id="d9943-106">From a developer perspective, a Windows PowerShell session refers to the time between when a host application opens a Windows PowerShell runspace and when it closes the runspace.</span></span> <span data-ttu-id="d9943-107">別の方法で検索すると、セッションは、実行空間が存在する場合に呼び出される、Windows PowerShell エンジンのインスタンスの有効期間です。</span><span class="sxs-lookup"><span data-stu-id="d9943-107">Looked at another way, the session is the lifetime of an instance of the Windows PowerShell engine that is invoked while the runspace exists.</span></span>

## <a name="module-session-state"></a><span data-ttu-id="d9943-108">モジュールのセッションの状態</span><span class="sxs-lookup"><span data-stu-id="d9943-108">Module Session State</span></span>

<span data-ttu-id="d9943-109">モジュール セッション状態は、モジュール、またはその入れ子になったモジュールの 1 つは、セッションにインポートされるたびに作成されます。</span><span class="sxs-lookup"><span data-stu-id="d9943-109">Module session states are created whenever the module or one of its nested modules is imported into the session.</span></span> <span data-ttu-id="d9943-110">モジュールをエクスポートするコマンドレット、関数、またはスクリプトなど、要素と、セッションのグローバル セッション状態にその要素への参照が追加されます。</span><span class="sxs-lookup"><span data-stu-id="d9943-110">When a module exports an element such as a cmdlet, function, or script, a reference to that element is added to the global session state of the session.</span></span> <span data-ttu-id="d9943-111">ただし、要素が実行されるモジュールのセッション状態で実行されます。</span><span class="sxs-lookup"><span data-stu-id="d9943-111">However, when the element is run, it is executed within the session state of the module.</span></span>

## <a name="session-state-data"></a><span data-ttu-id="d9943-112">セッション状態データ</span><span class="sxs-lookup"><span data-stu-id="d9943-112">Session-State Data</span></span>

<span data-ttu-id="d9943-113">セッション状態データは、パブリックまたはプライベートにできます。</span><span class="sxs-lookup"><span data-stu-id="d9943-113">Session state data can be public or private.</span></span> <span data-ttu-id="d9943-114">パブリック データは、セッション状態の外部からの呼び出しに使用できるプライベート データはセッション状態の内部からの呼び出しでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="d9943-114">Public data is available to calls from outside the session state while private data is available only to calls from within the session state.</span></span> <span data-ttu-id="d9943-115">たとえば、モジュールは、モジュールによってのみ、または内部でのみ呼び出すことができるプライベート関数があるエクスポートされたパブリック要素。</span><span class="sxs-lookup"><span data-stu-id="d9943-115">For example, a module can have a private function that can be called only by the module or only internally by a public element that has been exported.</span></span> <span data-ttu-id="d9943-116">.NET Framework 型のプライベートおよびパブリック メンバーに似ています。</span><span class="sxs-lookup"><span data-stu-id="d9943-116">This is similar to the private and public members of a .NET Framework type.</span></span>

<span data-ttu-id="d9943-117">セッション状態データは、現在の Windows PowerShell セッションのコンテキスト内での実行エンジンの現在のインスタンスが格納されます。</span><span class="sxs-lookup"><span data-stu-id="d9943-117">Session-state data is stored by the current instance of the execution engine within the context of the current Windows PowerShell session.</span></span> <span data-ttu-id="d9943-118">セッション状態データは、次の項目で構成されます。</span><span class="sxs-lookup"><span data-stu-id="d9943-118">Session-state data consists of the following items:</span></span>

- <span data-ttu-id="d9943-119">パス情報</span><span class="sxs-lookup"><span data-stu-id="d9943-119">Path information</span></span>

- <span data-ttu-id="d9943-120">ドライブの情報</span><span class="sxs-lookup"><span data-stu-id="d9943-120">Drive information</span></span>

- <span data-ttu-id="d9943-121">Windows PowerShell プロバイダーの情報</span><span class="sxs-lookup"><span data-stu-id="d9943-121">Windows PowerShell provider information</span></span>

- <span data-ttu-id="d9943-122">インポートしたモジュールとモジュールによってエクスポートされるモジュール要素 (コマンドレット、関数、スクリプトなど) への参照に関する情報。</span><span class="sxs-lookup"><span data-stu-id="d9943-122">Information about the imported modules and references to the module elements (such as cmdlets, functions, and scripts) that are exported by the module.</span></span> <span data-ttu-id="d9943-123">この情報は、これらの参照はグローバル セッション状態のみです。</span><span class="sxs-lookup"><span data-stu-id="d9943-123">This information and these references are for the global session state only.</span></span>

- <span data-ttu-id="d9943-124">セッション状態変数の情報</span><span class="sxs-lookup"><span data-stu-id="d9943-124">Session-state variable information</span></span>

## <a name="accessing-session-state-data-within-cmdlets"></a><span data-ttu-id="d9943-125">コマンドレット内でセッション状態データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="d9943-125">Accessing Session-State Data Within Cmdlets</span></span>

<span data-ttu-id="d9943-126">コマンドレットでは、セッション状態データをかアクセスを通じて間接的に、 [System.Management.Automation.PSCmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)または直接コマンドレット クラスのプロパティ、 [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState)クラス。</span><span class="sxs-lookup"><span data-stu-id="d9943-126">Cmdlets can access session-state data either indirectly through the [System.Management.Automation.PSCmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) property of the cmdlet class or directly through the [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class.</span></span> <span data-ttu-id="d9943-127">[System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState)クラスには、さまざまな種類のセッション状態データを調査するために使用できるプロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d9943-127">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class provides properties that can be used to investigate different types of session-state data.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9943-128">参照</span><span class="sxs-lookup"><span data-stu-id="d9943-128">See Also</span></span>

[<span data-ttu-id="d9943-129">System.Management.Automation.PSCmdlet.Sessionstate</span><span class="sxs-lookup"><span data-stu-id="d9943-129">System.Management.Automation.PSCmdlet.Sessionstate</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[<span data-ttu-id="d9943-130">System.Management.Automation.Sessionstate?Displayproperty=Fullname</span><span class="sxs-lookup"><span data-stu-id="d9943-130">System.Management.Automation.Sessionstate?Displayproperty=Fullname</span></span>](/dotnet/api/System.Management.Automation.SessionState)

[<span data-ttu-id="d9943-131">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="d9943-131">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="d9943-132">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="d9943-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="d9943-133">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="d9943-133">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
