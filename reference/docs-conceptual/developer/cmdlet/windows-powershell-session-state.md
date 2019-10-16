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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72369101"
---
# <a name="windows-powershell-session-state"></a><span data-ttu-id="755de-102">Windows PowerShell セッション状態</span><span class="sxs-lookup"><span data-stu-id="755de-102">Windows PowerShell Session State</span></span>

<span data-ttu-id="755de-103">セッション状態とは、Windows PowerShell セッションまたはモジュールの現在の構成を指します。</span><span class="sxs-lookup"><span data-stu-id="755de-103">Session state refers to the current configuration of a Windows PowerShell session or module.</span></span> <span data-ttu-id="755de-104">Windows PowerShell セッションは、コマンドラインユーザーが対話形式で、またはホストアプリケーションによってプログラムによって使用される運用環境です。</span><span class="sxs-lookup"><span data-stu-id="755de-104">A Windows PowerShell session is the operational environment that is used interactively by the command-line user or programmatically by a host application.</span></span> <span data-ttu-id="755de-105">セッションのセッション状態は、グローバルセッション状態と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="755de-105">The session state for a session is referred to as the global session state.</span></span>

<span data-ttu-id="755de-106">開発者の観点から見ると、Windows PowerShell セッションとは、ホストアプリケーションが Windows PowerShell の実行空間を開いて実行空間を閉じるまでの時間を指します。</span><span class="sxs-lookup"><span data-stu-id="755de-106">From a developer perspective, a Windows PowerShell session refers to the time between when a host application opens a Windows PowerShell runspace and when it closes the runspace.</span></span> <span data-ttu-id="755de-107">もう1つの方法として、セッションは、実行空間が存在する間に呼び出される Windows PowerShell エンジンのインスタンスの有効期間です。</span><span class="sxs-lookup"><span data-stu-id="755de-107">Looked at another way, the session is the lifetime of an instance of the Windows PowerShell engine that is invoked while the runspace exists.</span></span>

## <a name="module-session-state"></a><span data-ttu-id="755de-108">モジュールセッション状態</span><span class="sxs-lookup"><span data-stu-id="755de-108">Module Session State</span></span>

<span data-ttu-id="755de-109">モジュールセッション状態は、モジュールまたは入れ子になったモジュールのいずれかがセッションにインポートされるたびに作成されます。</span><span class="sxs-lookup"><span data-stu-id="755de-109">Module session states are created whenever the module or one of its nested modules is imported into the session.</span></span> <span data-ttu-id="755de-110">モジュールがコマンドレット、関数、またはスクリプトなどの要素をエクスポートすると、その要素への参照がセッションのグローバルセッション状態に追加されます。</span><span class="sxs-lookup"><span data-stu-id="755de-110">When a module exports an element such as a cmdlet, function, or script, a reference to that element is added to the global session state of the session.</span></span> <span data-ttu-id="755de-111">ただし、要素が実行されると、モジュールのセッション状態内で実行されます。</span><span class="sxs-lookup"><span data-stu-id="755de-111">However, when the element is run, it is executed within the session state of the module.</span></span>

## <a name="session-state-data"></a><span data-ttu-id="755de-112">セッション状態データ</span><span class="sxs-lookup"><span data-stu-id="755de-112">Session-State Data</span></span>

<span data-ttu-id="755de-113">セッション状態データは、パブリックまたはプライベートにすることができます。</span><span class="sxs-lookup"><span data-stu-id="755de-113">Session state data can be public or private.</span></span> <span data-ttu-id="755de-114">パブリックデータは、セッション状態の外部からの呼び出しに使用できます。プライベートデータは、セッション状態内からの呼び出しに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="755de-114">Public data is available to calls from outside the session state while private data is available only to calls from within the session state.</span></span> <span data-ttu-id="755de-115">たとえば、モジュールは、モジュールによってのみ呼び出すことができるプライベート関数を持つことができます。または、エクスポートされたパブリック要素によって内部的にのみ呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="755de-115">For example, a module can have a private function that can be called only by the module or only internally by a public element that has been exported.</span></span> <span data-ttu-id="755de-116">これは、.NET Framework 型のプライベートメンバーとパブリックメンバーに似ています。</span><span class="sxs-lookup"><span data-stu-id="755de-116">This is similar to the private and public members of a .NET Framework type.</span></span>

<span data-ttu-id="755de-117">セッション状態データは、現在の Windows PowerShell セッションのコンテキスト内で、実行エンジンの現在のインスタンスによって格納されます。</span><span class="sxs-lookup"><span data-stu-id="755de-117">Session-state data is stored by the current instance of the execution engine within the context of the current Windows PowerShell session.</span></span> <span data-ttu-id="755de-118">セッション状態データは、次の項目で構成されます。</span><span class="sxs-lookup"><span data-stu-id="755de-118">Session-state data consists of the following items:</span></span>

- <span data-ttu-id="755de-119">パス情報</span><span class="sxs-lookup"><span data-stu-id="755de-119">Path information</span></span>

- <span data-ttu-id="755de-120">ドライブ情報</span><span class="sxs-lookup"><span data-stu-id="755de-120">Drive information</span></span>

- <span data-ttu-id="755de-121">Windows PowerShell プロバイダーの情報</span><span class="sxs-lookup"><span data-stu-id="755de-121">Windows PowerShell provider information</span></span>

- <span data-ttu-id="755de-122">モジュールによってエクスポートされるモジュール要素 (コマンドレット、関数、スクリプトなど) へのインポートされたモジュールおよび参照に関する情報。</span><span class="sxs-lookup"><span data-stu-id="755de-122">Information about the imported modules and references to the module elements (such as cmdlets, functions, and scripts) that are exported by the module.</span></span> <span data-ttu-id="755de-123">この情報とこれらの参照は、グローバルセッション状態のみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="755de-123">This information and these references are for the global session state only.</span></span>

- <span data-ttu-id="755de-124">セッション状態変数の情報</span><span class="sxs-lookup"><span data-stu-id="755de-124">Session-state variable information</span></span>

## <a name="accessing-session-state-data-within-cmdlets"></a><span data-ttu-id="755de-125">コマンドレット内のセッション状態データへのアクセス</span><span class="sxs-lookup"><span data-stu-id="755de-125">Accessing Session-State Data Within Cmdlets</span></span>

<span data-ttu-id="755de-126">コマンドレットは、コマンドレットクラスの[Sessionstate \*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)プロパティを介して、または[Sessionstate](/dotnet/api/System.Management.Automation.SessionState)クラスを直接介して、セッション状態データに間接的にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="755de-126">Cmdlets can access session-state data either indirectly through the [System.Management.Automation.PSCmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) property of the cmdlet class or directly through the [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class.</span></span> <span data-ttu-id="755de-127">[Sessionstate](/dotnet/api/System.Management.Automation.SessionState)クラスには、さまざまな種類のセッション状態データを調査するために使用できるプロパティが用意されています。</span><span class="sxs-lookup"><span data-stu-id="755de-127">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class provides properties that can be used to investigate different types of session-state data.</span></span>

## <a name="see-also"></a><span data-ttu-id="755de-128">参照</span><span class="sxs-lookup"><span data-stu-id="755de-128">See Also</span></span>

[<span data-ttu-id="755de-129">PSCmdlet. Sessionstate (システムの管理)</span><span class="sxs-lookup"><span data-stu-id="755de-129">System.Management.Automation.PSCmdlet.Sessionstate</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[<span data-ttu-id="755de-130">Sessionstate ですか?Displayproperty = Fullname</span><span class="sxs-lookup"><span data-stu-id="755de-130">System.Management.Automation.Sessionstate?Displayproperty=Fullname</span></span>](/dotnet/api/System.Management.Automation.SessionState)

[<span data-ttu-id="755de-131">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="755de-131">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="755de-132">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="755de-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="755de-133">Windows PowerShell Shell SDK</span><span class="sxs-lookup"><span data-stu-id="755de-133">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
