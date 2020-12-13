---
ms.date: 09/13/2016
ms.topic: reference
title: Windows PowerShell リファレンス-新機能
description: Windows PowerShell リファレンス-新機能
ms.openlocfilehash: b6fa97eacd476f055dd0c69eed2e547c450b85e1
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647127"
---
# <a name="whats-new"></a><span data-ttu-id="fb63c-103">新機能</span><span class="sxs-lookup"><span data-stu-id="fb63c-103">What's New</span></span>

<span data-ttu-id="fb63c-104">Windows PowerShell 2.0 には、コマンドレット、プロバイダー、およびホストアプリケーションを記述するときに使用できる次の新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fb63c-104">Windows PowerShell 2.0 provides the following new features for use when writing cmdlets, providers, and host applications.</span></span>

## <a name="modules"></a><span data-ttu-id="fb63c-105">モジュール</span><span class="sxs-lookup"><span data-stu-id="fb63c-105">Modules</span></span>

<span data-ttu-id="fb63c-106">モジュールを使用して、Windows PowerShell ソリューションをパッケージ化して配布できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-106">You can now package and distribute Windows PowerShell solutions by using modules.</span></span> <span data-ttu-id="fb63c-107">モジュールを使用すると、Windows PowerShell コードをパーティション分割し、自己完結型の再利用可能な単位にまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-107">Modules allow you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="fb63c-108">モジュールの詳細については、「Windows PowerShell モジュールの記述」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-108">For more information about modules, see Writing a Windows PowerShell Module.</span></span>

## <a name="the-powershell-class"></a><span data-ttu-id="fb63c-109">PowerShell クラス</span><span class="sxs-lookup"><span data-stu-id="fb63c-109">The PowerShell class</span></span>

<span data-ttu-id="fb63c-110">PowerShell クラスは、ホストアプリケーションと呼ばれるアプリケーションを作成し、プログラムを使用してコマンドを実行するためのより簡単なソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="fb63c-110">The PowerShell class provides a simpler solution for creating applications, referred to as host applications, that programmatically run commands.</span></span> <span data-ttu-id="fb63c-111">このクラスを使用すると、コマンドのパイプラインを作成したり、コマンドの実行に使用する実行空間を指定したり、コマンドを同期的または非同期的に呼び出すように指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-111">This class allows you to create a pipeline of commands, specify the runspace that is used to run the commands, and specify invoking the commands synchronously or asynchronously.</span></span>

## <a name="the-runspacepool-class"></a><span data-ttu-id="fb63c-112">RunspacePool クラス</span><span class="sxs-lookup"><span data-stu-id="fb63c-112">The RunspacePool class</span></span>

<span data-ttu-id="fb63c-113">実行空間プールを使用すると、1回の呼び出しで複数の実行空間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-113">Runspace pools allow you to create multiple runspaces by using a single call.</span></span> <span data-ttu-id="fb63c-114">Createrunspace プールメソッドには、同じホスト、初期セッション状態、接続情報など、同じ機能を持つ実行空間を作成するために使用できるいくつかのオーバーロードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="fb63c-114">The CreateRunspacePool method provides several overloads that can be used to create runspaces that have the same features, such as the same host, initial session state, and connection information.</span></span>

## <a name="the-initialsessionstate-class"></a><span data-ttu-id="fb63c-115">InitialSessionState クラス</span><span class="sxs-lookup"><span data-stu-id="fb63c-115">The InitialSessionState class</span></span>

<span data-ttu-id="fb63c-116">InitialSessionState クラスを使用すると、実行空間を開いたときに使用されるセッション状態の構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-116">The InitialSessionState class allows you to create a session state configuration that is used when a runspace is opened.</span></span> <span data-ttu-id="fb63c-117">カスタム構成、mshshort によって提供されるコマンドを含む既定の構成、およびセッションの機能に基づいてコマンドが制限されている構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-117">You can create a custom configuration, a default configuration that includes the commands provided by mshshort, and a configuration whose commands are restricted based on the capabilities of the session.</span></span>

## <a name="remote-runspaces"></a><span data-ttu-id="fb63c-118">リモート実行空間</span><span class="sxs-lookup"><span data-stu-id="fb63c-118">Remote runspaces</span></span>

<span data-ttu-id="fb63c-119">リモートコンピューターで開くことができる実行空間を作成できるようになりました。これにより、リモートコンピューターでコマンドを実行し、結果をローカルに収集できます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-119">You can now create runspaces that can be opened on remote computers, allowing you to run commands on the remote machine and collect the results locally.</span></span> <span data-ttu-id="fb63c-120">リモート実行空間を作成するには、実行空間を作成するときに、リモート接続に関する情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb63c-120">To create a remote runspace, you must specify information about the remote connection when creating the runspace.</span></span> <span data-ttu-id="fb63c-121">例については、CreateRunspace および Createrunspace プールのメソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-121">See the CreateRunspace and CreateRunspacePool methods for examples.</span></span> <span data-ttu-id="fb63c-122">接続情報は、RunspaceConnectionInfo クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-122">The connection information is defined by the RunspaceConnectionInfo class.</span></span>

## <a name="private-runspace-elements"></a><span data-ttu-id="fb63c-123">プライベート実行空間要素</span><span class="sxs-lookup"><span data-stu-id="fb63c-123">Private runspace elements</span></span>

<span data-ttu-id="fb63c-124">要素がパブリックまたはプライベートである実行空間を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-124">You can now create runspaces whose elements are public or private.</span></span> <span data-ttu-id="fb63c-125">これにより、実行空間で使用できる要素を持つ実行空間を作成できますが、ユーザーが使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fb63c-125">This allows you to create runspaces whose elements are available to the runspace, but are not available to the user.</span></span> <span data-ttu-id="fb63c-126">実行空間のどの要素をプライベートにできるかを確認するには、ConstrainedSessionStateEntry クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-126">See the ConstrainedSessionStateEntry class to find out which elements of the runspace can be made private.</span></span>

## <a name="runspace-threading-modes-and-apartment-state"></a><span data-ttu-id="fb63c-127">実行空間スレッドモードとアパートメント状態</span><span class="sxs-lookup"><span data-stu-id="fb63c-127">Runspace threading modes and apartment state</span></span>

<span data-ttu-id="fb63c-128">実行空間でコマンドを実行するときに、スレッドを作成して使用する方法を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-128">You can now specify how threads are created and used when running commands in a runspace.</span></span> <span data-ttu-id="fb63c-129">RunspacePool プロパティとプロパティを参照してください。このプロパティについては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-129">See the System.Management.Automation.Runspaces.Runspace.ThreadOptions and System.Management.Automation.Runspaces.RunspacePool.ThreadOptions properties.</span></span>

<span data-ttu-id="fb63c-130">実行空間でコマンドを実行するために使用されるスレッドのアパートメント状態を取得できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-130">You can now get the apartment state of the threads that are used to run commands in a runspace.</span></span> <span data-ttu-id="fb63c-131">System.threading.thread.apartmentstate プロパティと RunspacePool プロパティを参照してください。このプロパティについては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-131">See the System.Management.Automation.Runspaces.Runspace.ApartmentState and System.Management.Automation.Runspaces.RunspacePool.ApartmentState properties.</span></span>

## <a name="transaction-cmdlets"></a><span data-ttu-id="fb63c-132">トランザクションのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="fb63c-132">Transaction cmdlets</span></span>

<span data-ttu-id="fb63c-133">トランザクション内で使用できるコマンドレットを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-133">You can now create cmdlets that can be used within a transaction.</span></span> <span data-ttu-id="fb63c-134">コマンドレットがトランザクションで使用されている場合、そのアクションは一時的なものであり、Windows PowerShell によって提供されるトランザクションコマンドレットによって受け入れまたは拒否されることがあります。</span><span class="sxs-lookup"><span data-stu-id="fb63c-134">When a cmdlet is used in a transaction, its actions are temporary, and they can be accepted or rejected by the transaction cmdlets provided by Windows PowerShell.</span></span>

<span data-ttu-id="fb63c-135">トランザクションの詳細については、「トランザクションをサポートする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-135">For more information about transactions, see How to Support Transactions.</span></span>

## <a name="transaction-provider"></a><span data-ttu-id="fb63c-136">トランザクションプロバイダー</span><span class="sxs-lookup"><span data-stu-id="fb63c-136">Transaction provider</span></span>

<span data-ttu-id="fb63c-137">トランザクション内で使用できるプロバイダーを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-137">You can now create providers that can be used within a transaction.</span></span> <span data-ttu-id="fb63c-138">コマンドレットと同様に、プロバイダーがトランザクションで使用されている場合、そのアクションは一時的であり、Windows PowerShell によって提供されるトランザクションコマンドレットによって受け入れまたは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-138">Similar to cmdlets, when a provider is used in a transaction, its actions are temporary, and they can be accepted or rejected by the transaction cmdlets provided by Windows PowerShell.</span></span>

<span data-ttu-id="fb63c-139">プロバイダークラス内でのトランザクションのサポートを指定する方法の詳細については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-139">For more information about specifying support for transaction within a provider class, see the System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities property.</span></span>

## <a name="job-cmdlets"></a><span data-ttu-id="fb63c-140">ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="fb63c-140">Job cmdlets</span></span>

<span data-ttu-id="fb63c-141">アクションをジョブとして実行できるコマンドレットを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-141">You can now write cmdlets that can perform their action as a job.</span></span> <span data-ttu-id="fb63c-142">これらのジョブは、現在のセッションと対話することなくバックグラウンドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-142">These jobs are run in the background without interacting with the current session.</span></span> <span data-ttu-id="fb63c-143">Windows PowerShell がジョブをサポートする方法の詳細については、「バックグラウンドジョブ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-143">For more information about how Windows PowerShell supports jobs, see Background Jobs.</span></span>

## <a name="cmdlet-output-types"></a><span data-ttu-id="fb63c-144">コマンドレットの出力の種類</span><span class="sxs-lookup"><span data-stu-id="fb63c-144">Cmdlet output types</span></span>

<span data-ttu-id="fb63c-145">コマンドレットを記述するときに OutputType 属性を宣言することで、コマンドレットによって返される .NET Framework の種類を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-145">You can now specify the .NET Framework types that are returned by your cmdlets by declaring the OutputType attribute when writing your cmdlets.</span></span> <span data-ttu-id="fb63c-146">これにより、コマンドレットの OutputType プロパティを確認することで、コマンドレットによって返されるオブジェクトの種類を他のユーザーが判断できるようになります。</span><span class="sxs-lookup"><span data-stu-id="fb63c-146">This will allow others to determine what type of objects are returned by a cmdlet by looking at the OutputType property of the cmdlet.</span></span>

## <a name="event-support"></a><span data-ttu-id="fb63c-147">イベントのサポート</span><span class="sxs-lookup"><span data-stu-id="fb63c-147">Event support</span></span>

<span data-ttu-id="fb63c-148">イベントを追加して使用するコマンドレットを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-148">You can now write cmdlets that add and consume events.</span></span> <span data-ttu-id="fb63c-149">PSEvent クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-149">See the PSEvent class.</span></span>

## <a name="proxy-commands"></a><span data-ttu-id="fb63c-150">プロキシコマンド</span><span class="sxs-lookup"><span data-stu-id="fb63c-150">Proxy commands</span></span>

<span data-ttu-id="fb63c-151">別のコマンドを実行するために使用できるプロキシコマンドを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-151">You can now write proxy commands that can be used to run another command.</span></span> <span data-ttu-id="fb63c-152">プロキシコマンドを使用すると、ユーザーが使用できる source コマンドレットの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-152">A proxy command allows you to control what functionality of the source cmdlet is available to the user.</span></span> <span data-ttu-id="fb63c-153">たとえば、source コマンドによって指定されたパラメーターを削除するプロキシコマンドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb63c-153">For example, you can create a proxy command that removes a parameter that is supplied by the source command.</span></span> <span data-ttu-id="fb63c-154">ProxyCommand クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-154">See the ProxyCommand class.</span></span>

## <a name="multiple-choice-prompts"></a><span data-ttu-id="fb63c-155">複数選択のプロンプト</span><span class="sxs-lookup"><span data-stu-id="fb63c-155">Multiple choice prompts</span></span>

<span data-ttu-id="fb63c-156">ユーザーが複数の選択肢を選択できるようにするためのプロンプトを提供できるアプリケーションを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-156">You can now write applications that can provide prompts that allow the user to select multiple choices.</span></span> <span data-ttu-id="fb63c-157">IHostUISupportsMultipleChoiceSelection インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-157">See the IHostUISupportsMultipleChoiceSelection interface</span></span>

## <a name="interactive-sessions"></a><span data-ttu-id="fb63c-158">対話型セッション</span><span class="sxs-lookup"><span data-stu-id="fb63c-158">Interactive sessions</span></span>

<span data-ttu-id="fb63c-159">リモートコンピューターで対話型セッションを開始および停止できるアプリケーションを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-159">You can now write applications that can start and stop an interactive session on a remote computer.</span></span>
<span data-ttu-id="fb63c-160">IHostSupportsInteractiveSession インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb63c-160">See the IHostSupportsInteractiveSession interface.</span></span>

## <a name="custom-cmdlet-help-for-providers"></a><span data-ttu-id="fb63c-161">プロバイダーのカスタムコマンドレットヘルプ</span><span class="sxs-lookup"><span data-stu-id="fb63c-161">Custom Cmdlet Help for Providers</span></span>

<span data-ttu-id="fb63c-162">プロバイダーコマンドレットのカスタマイズされたヘルプトピックを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fb63c-162">You can now create customized Help topics for the provider cmdlets.</span></span> <span data-ttu-id="fb63c-163">カスタムコマンドレットのヘルプトピックでは、プロバイダーパスでのコマンドレットの動作と、プロバイダーがコマンドレットに追加する動的パラメーターなどの特別な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb63c-163">Custom cmdlet help topics can explain how the cmdlet works in the provider path and document special features, including the dynamic parameters that the provider adds to the cmdlet.</span></span>
