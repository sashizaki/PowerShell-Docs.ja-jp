---
title: Windows PowerShell リファレンス - 新機能
ms.date: 09/13/2016
ms.topic: article
ms.openlocfilehash: 364d081ddf2f87ceeaa47732266a35f4a126246f
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858548"
---
# <a name="whats-new"></a><span data-ttu-id="ddbbe-102">新機能</span><span class="sxs-lookup"><span data-stu-id="ddbbe-102">What's New</span></span>

<span data-ttu-id="ddbbe-103">Windows PowerShell 2.0 では、コマンドレット、プロバイダー、およびホスト アプリケーションを作成するときに使用するため、次の新機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-103">Windows PowerShell 2.0 provides the following new features for use when writing cmdlets, providers, and host applications.</span></span>

## <a name="modules"></a><span data-ttu-id="ddbbe-104">モジュール</span><span class="sxs-lookup"><span data-stu-id="ddbbe-104">Modules</span></span>

<span data-ttu-id="ddbbe-105">パッケージ化し、モジュールを使用して、Windows PowerShell のソリューションを配布できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-105">You can now package and distribute Windows PowerShell solutions by using modules.</span></span> <span data-ttu-id="ddbbe-106">モジュールにより、パーティションをするには、整理、および再利用可能な自己完結型の単位に、Windows PowerShell コードを抽象化します。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-106">Modules allow you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="ddbbe-107">モジュールの詳細については、Windows PowerShell モジュールの記述を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-107">For more information about modules, see Writing a Windows PowerShell Module.</span></span>

## <a name="the-powershell-class"></a><span data-ttu-id="ddbbe-108">PowerShell クラス</span><span class="sxs-lookup"><span data-stu-id="ddbbe-108">The PowerShell class</span></span>

<span data-ttu-id="ddbbe-109">PowerShell クラスは、プログラムでのコマンドを実行するホスト アプリケーションと呼ばれるアプリケーションを作成するための簡単なソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-109">The PowerShell class provides a simpler solution for creating applications, referred to as host applications, that programmatically run commands.</span></span> <span data-ttu-id="ddbbe-110">このクラスを使用すると、コマンドのパイプラインを作成のコマンドを実行するために使用する実行空間を指定し、同期または非同期コマンドを呼び出すことを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-110">This class allows you to create a pipeline of commands, specify the runspace that is used to run the commands, and specify invoking the commands synchronously or asynchronously.</span></span>

## <a name="the-runspacepool-class"></a><span data-ttu-id="ddbbe-111">RunspacePool クラス</span><span class="sxs-lookup"><span data-stu-id="ddbbe-111">The RunspacePool class</span></span>

<span data-ttu-id="ddbbe-112">実行空間プールを使用すると、1 回の呼び出しを使用して複数の実行空間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-112">Runspace pools allow you to create multiple runspaces by using a single call.</span></span> <span data-ttu-id="ddbbe-113">CreateRunspacePool メソッドは、同じホスト、最初のセッション状態、および接続情報など、同じ機能の実行空間を作成するために使用するいくつかのオーバー ロードを提供します。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-113">The CreateRunspacePool method provides several overloads that can be used to create runspaces that have the same features, such as the same host, initial session state, and connection information.</span></span>

## <a name="the-initialsessionstate-class"></a><span data-ttu-id="ddbbe-114">InitialSessionState クラス</span><span class="sxs-lookup"><span data-stu-id="ddbbe-114">The InitialSessionState class</span></span>

<span data-ttu-id="ddbbe-115">InitialSessionState クラスを使用する実行空間が開いたときに使用されるセッション状態の構成を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-115">The InitialSessionState class allows you to create a session state configuration that is used when a runspace is opened.</span></span> <span data-ttu-id="ddbbe-116">カスタム構成、mshshort、によって提供されるコマンドを含む既定の構成、およびそのコマンドは、セッションの機能に基づく制限の構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-116">You can create a custom configuration, a default configuration that includes the commands provided by mshshort, and a configuration whose commands are restricted based on the capabilities of the session.</span></span>

## <a name="remote-runspaces"></a><span data-ttu-id="ddbbe-117">リモート実行空間</span><span class="sxs-lookup"><span data-stu-id="ddbbe-117">Remote runspaces</span></span>

<span data-ttu-id="ddbbe-118">今すぐ作成できます空間を開くことができますのリモート コンピューター上、リモート コンピューター上のコマンドを実行し、ローカルで結果を収集することができます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-118">You can now create runspaces that can be opened on remote computers, allowing you to run commands on the remote machine and collect the results locally.</span></span> <span data-ttu-id="ddbbe-119">リモートの実行空間を作成するには、実行空間を作成するときにリモート接続に関する情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-119">To create a remote runspace, you must specify information about the remote connection when creating the runspace.</span></span> <span data-ttu-id="ddbbe-120">例については、CreateRunspace および CreateRunspacePool のメソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-120">See the CreateRunspace and CreateRunspacePool methods for examples.</span></span> <span data-ttu-id="ddbbe-121">接続情報は、RunspaceConnectionInfo クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-121">The connection information is defined by the RunspaceConnectionInfo class.</span></span>

## <a name="private-runspace-elements"></a><span data-ttu-id="ddbbe-122">実行空間のプライベート要素</span><span class="sxs-lookup"><span data-stu-id="ddbbe-122">Private runspace elements</span></span>

<span data-ttu-id="ddbbe-123">要素がパブリックまたはプライベートの実行空間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-123">You can now create runspaces whose elements are public or private.</span></span> <span data-ttu-id="ddbbe-124">これにより、要素が、実行空間を利用できますが、ユーザーが使用可能でない実行空間を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-124">This allows you to create runspaces whose elements are available to the runspace, but are not available to the user.</span></span> <span data-ttu-id="ddbbe-125">実行空間の要素をプライベートにできることを確認する ConstrainedSessionStateEntry クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-125">See the ConstrainedSessionStateEntry class to find out which elements of the runspace can be made private.</span></span>

## <a name="runspace-threading-modes-and-apartment-state"></a><span data-ttu-id="ddbbe-126">スレッド処理モードとアパートメント状態実行空間</span><span class="sxs-lookup"><span data-stu-id="ddbbe-126">Runspace threading modes and apartment state</span></span>

<span data-ttu-id="ddbbe-127">スレッドが作成され、実行空間でコマンドを実行するときに使用する方法を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-127">You can now specify how threads are created and used when running commands in a runspace.</span></span> <span data-ttu-id="ddbbe-128">System.Management.Automation.Runspaces.Runspace.ThreadOptions と System.Management.Automation.Runspaces.RunspacePool.ThreadOptions プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-128">See the System.Management.Automation.Runspaces.Runspace.ThreadOptions and System.Management.Automation.Runspaces.RunspacePool.ThreadOptions properties.</span></span>

<span data-ttu-id="ddbbe-129">使用して、実行空間でコマンドを実行するスレッドのアパートメント状態を取得できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-129">You can now get the apartment state of the threads that are used to run commands in a runspace.</span></span> <span data-ttu-id="ddbbe-130">System.Management.Automation.Runspaces.Runspace.ApartmentState と System.Management.Automation.Runspaces.RunspacePool.ApartmentState プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-130">See the System.Management.Automation.Runspaces.Runspace.ApartmentState and System.Management.Automation.Runspaces.RunspacePool.ApartmentState properties.</span></span>

## <a name="transaction-cmdlets"></a><span data-ttu-id="ddbbe-131">トランザクションのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="ddbbe-131">Transaction cmdlets</span></span>

<span data-ttu-id="ddbbe-132">トランザクション内で使用できるコマンドレットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-132">You can now create cmdlets that can be used within a transaction.</span></span> <span data-ttu-id="ddbbe-133">トランザクションでコマンドレットを使用するときにそのアクションは一時的なものと承諾または Windows PowerShell によって提供されるトランザクション コマンドレットによって拒否されたことができます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-133">When a cmdlet is used in a transaction, its actions are temporary, and they can be accepted or rejected by the transaction cmdlets provided by Windows PowerShell.</span></span>

<span data-ttu-id="ddbbe-134">トランザクションの詳細については、次を参照してください。 トランザクションをサポートする方法。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-134">For more information about transactions, see How to Support Transactions.</span></span>

## <a name="transaction-provider"></a><span data-ttu-id="ddbbe-135">トランザクションのプロバイダー</span><span class="sxs-lookup"><span data-stu-id="ddbbe-135">Transaction provider</span></span>

<span data-ttu-id="ddbbe-136">トランザクション内で使用できるプロバイダーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-136">You can now create providers that can be used within a transaction.</span></span> <span data-ttu-id="ddbbe-137">そのアクションは一時的なものは、コマンドレット、プロバイダーがトランザクションで使用される場合と同様に、および承諾または Windows PowerShell によって提供されるトランザクション コマンドレットによって拒否されたことができます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-137">Similar to cmdlets, when a provider is used in a transaction, its actions are temporary, and they can be accepted or rejected by the transaction cmdlets provided by Windows PowerShell.</span></span>

<span data-ttu-id="ddbbe-138">プロバイダー クラス内のトランザクションのサポートを指定する方法については、System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities プロパティを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-138">For more information about specifying support for transaction within a provider class, see the System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities property.</span></span>

## <a name="job-cmdlets"></a><span data-ttu-id="ddbbe-139">ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="ddbbe-139">Job cmdlets</span></span>

<span data-ttu-id="ddbbe-140">ジョブとしてその操作を実行できるコマンドレットを記述できますようになりました。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-140">You can now write cmdlets that can perform their action as a job.</span></span> <span data-ttu-id="ddbbe-141">これらのジョブは、現在のセッションと対話することがなく、バック グラウンドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-141">These jobs are run in the background without interacting with the current session.</span></span> <span data-ttu-id="ddbbe-142">Windows PowerShell でジョブをサポートする方法の詳細については、バック グラウンド ジョブを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-142">For more information about how Windows PowerShell supports jobs, see Background Jobs.</span></span>

## <a name="cmdlet-output-types"></a><span data-ttu-id="ddbbe-143">コマンドレットの出力の種類</span><span class="sxs-lookup"><span data-stu-id="ddbbe-143">Cmdlet output types</span></span>

<span data-ttu-id="ddbbe-144">これで、コマンドレットを記述するときに、OutputType 属性を宣言することで、コマンドレットによって返される .NET Framework の型を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-144">You can now specify the .NET Framework types that are returned by your cmdlets by declaring the OutputType attribute when writing your cmdlets.</span></span> <span data-ttu-id="ddbbe-145">これは、調べるコマンドレットの OutputType プロパティ コマンドレットによって返されるオブジェクトの種類を決定する他のユーザーに許可されます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-145">This will allow others to determine what type of objects are returned by a cmdlet by looking at the OutputType property of the cmdlet.</span></span>

## <a name="event-support"></a><span data-ttu-id="ddbbe-146">イベントのサポート</span><span class="sxs-lookup"><span data-stu-id="ddbbe-146">Event support</span></span>

<span data-ttu-id="ddbbe-147">追加およびイベントを使用するコマンドレットを記述できますようになりました。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-147">You can now write cmdlets that add and consume events.</span></span> <span data-ttu-id="ddbbe-148">PSEvent クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-148">See the PSEvent class.</span></span>

## <a name="proxy-commands"></a><span data-ttu-id="ddbbe-149">プロキシ コマンド</span><span class="sxs-lookup"><span data-stu-id="ddbbe-149">Proxy commands</span></span>

<span data-ttu-id="ddbbe-150">別のコマンドを実行するために使用するプロキシ コマンドを記述できますようになりました。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-150">You can now write proxy commands that can be used to run another command.</span></span> <span data-ttu-id="ddbbe-151">プロキシ コマンドを使用すると、ユーザーに可能なソース コマンドレットの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-151">A proxy command allows you to control what functionality of the source cmdlet is available to the user.</span></span> <span data-ttu-id="ddbbe-152">たとえば、ソースのコマンドで指定されているパラメーターを削除するプロキシ コマンドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-152">For example, you can create a proxy command that removes a parameter that is supplied by the source command.</span></span> <span data-ttu-id="ddbbe-153">ProxyCommand クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-153">See the ProxyCommand class.</span></span>

## <a name="multiple-choice-prompts"></a><span data-ttu-id="ddbbe-154">複数選択画面の指示</span><span class="sxs-lookup"><span data-stu-id="ddbbe-154">Multiple choice prompts</span></span>

<span data-ttu-id="ddbbe-155">ユーザーが複数の選択肢を選択する画面の指示を提供するアプリケーションを記述できますようになりました。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-155">You can now write applications that can provide prompts that allow the user to select multiple choices.</span></span> <span data-ttu-id="ddbbe-156">IHostUISupportsMultipleChoiceSelection インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-156">See the IHostUISupportsMultipleChoiceSelection interface</span></span>

## <a name="interactive-sessions"></a><span data-ttu-id="ddbbe-157">対話型セッション</span><span class="sxs-lookup"><span data-stu-id="ddbbe-157">Interactive sessions</span></span>

<span data-ttu-id="ddbbe-158">開始して、リモート コンピューター上の対話型セッションを停止できるアプリケーションを記述できますようになりました。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-158">You can now write applications that can start and stop an interactive session on a remote computer.</span></span>
<span data-ttu-id="ddbbe-159">IHostSupportsInteractiveSession インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-159">See the IHostSupportsInteractiveSession interface.</span></span>

## <a name="custom-cmdlet-help-for-providers"></a><span data-ttu-id="ddbbe-160">プロバイダーのカスタム コマンドレット ヘルプ</span><span class="sxs-lookup"><span data-stu-id="ddbbe-160">Custom Cmdlet Help for Providers</span></span>

<span data-ttu-id="ddbbe-161">プロバイダー コマンドレットのカスタマイズされたヘルプ トピックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-161">You can now create customized Help topics for the provider cmdlets.</span></span> <span data-ttu-id="ddbbe-162">カスタム コマンドレット ヘルプ トピックのコマンドレット、プロバイダー パスとドキュメントの特殊な機能に、コマンドレット、プロバイダーを追加する動的パラメーターを含むの動作方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="ddbbe-162">Custom cmdlet help topics can explain how the cmdlet works in the provider path and document special features, including the dynamic parameters that the provider adds to the cmdlet.</span></span>
