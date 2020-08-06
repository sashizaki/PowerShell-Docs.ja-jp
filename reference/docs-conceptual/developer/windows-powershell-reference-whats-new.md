---
title: Windows PowerShell リファレンス-新機能
ms.date: 09/13/2016
ms.openlocfilehash: 4e87fce34f74e0fcbfe25939e1555df308a7f7d0
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786698"
---
# <a name="whats-new"></a><span data-ttu-id="380ef-102">新着記事</span><span class="sxs-lookup"><span data-stu-id="380ef-102">What's New</span></span>

<span data-ttu-id="380ef-103">Windows PowerShell 2.0 には、コマンドレット、プロバイダー、およびホストアプリケーションを記述するときに使用できる次の新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="380ef-103">Windows PowerShell 2.0 provides the following new features for use when writing cmdlets, providers, and host applications.</span></span>

## <a name="modules"></a><span data-ttu-id="380ef-104">モジュール</span><span class="sxs-lookup"><span data-stu-id="380ef-104">Modules</span></span>

<span data-ttu-id="380ef-105">モジュールを使用して、Windows PowerShell ソリューションをパッケージ化して配布できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-105">You can now package and distribute Windows PowerShell solutions by using modules.</span></span> <span data-ttu-id="380ef-106">モジュールを使用すると、Windows PowerShell コードをパーティション分割し、自己完結型の再利用可能な単位にまとめることができます。</span><span class="sxs-lookup"><span data-stu-id="380ef-106">Modules allow you to partition, organize, and abstract your Windows PowerShell code into self-contained, reusable units.</span></span> <span data-ttu-id="380ef-107">モジュールの詳細については、「Windows PowerShell モジュールの記述」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-107">For more information about modules, see Writing a Windows PowerShell Module.</span></span>

## <a name="the-powershell-class"></a><span data-ttu-id="380ef-108">PowerShell クラス</span><span class="sxs-lookup"><span data-stu-id="380ef-108">The PowerShell class</span></span>

<span data-ttu-id="380ef-109">PowerShell クラスは、ホストアプリケーションと呼ばれるアプリケーションを作成し、プログラムを使用してコマンドを実行するためのより簡単なソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="380ef-109">The PowerShell class provides a simpler solution for creating applications, referred to as host applications, that programmatically run commands.</span></span> <span data-ttu-id="380ef-110">このクラスを使用すると、コマンドのパイプラインを作成したり、コマンドの実行に使用する実行空間を指定したり、コマンドを同期的または非同期的に呼び出すように指定したりできます。</span><span class="sxs-lookup"><span data-stu-id="380ef-110">This class allows you to create a pipeline of commands, specify the runspace that is used to run the commands, and specify invoking the commands synchronously or asynchronously.</span></span>

## <a name="the-runspacepool-class"></a><span data-ttu-id="380ef-111">RunspacePool クラス</span><span class="sxs-lookup"><span data-stu-id="380ef-111">The RunspacePool class</span></span>

<span data-ttu-id="380ef-112">実行空間プールを使用すると、1回の呼び出しで複数の実行空間を作成できます。</span><span class="sxs-lookup"><span data-stu-id="380ef-112">Runspace pools allow you to create multiple runspaces by using a single call.</span></span> <span data-ttu-id="380ef-113">Createrunspace プールメソッドには、同じホスト、初期セッション状態、接続情報など、同じ機能を持つ実行空間を作成するために使用できるいくつかのオーバーロードが用意されています。</span><span class="sxs-lookup"><span data-stu-id="380ef-113">The CreateRunspacePool method provides several overloads that can be used to create runspaces that have the same features, such as the same host, initial session state, and connection information.</span></span>

## <a name="the-initialsessionstate-class"></a><span data-ttu-id="380ef-114">InitialSessionState クラス</span><span class="sxs-lookup"><span data-stu-id="380ef-114">The InitialSessionState class</span></span>

<span data-ttu-id="380ef-115">InitialSessionState クラスを使用すると、実行空間を開いたときに使用されるセッション状態の構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="380ef-115">The InitialSessionState class allows you to create a session state configuration that is used when a runspace is opened.</span></span> <span data-ttu-id="380ef-116">カスタム構成、mshshort によって提供されるコマンドを含む既定の構成、およびセッションの機能に基づいてコマンドが制限されている構成を作成できます。</span><span class="sxs-lookup"><span data-stu-id="380ef-116">You can create a custom configuration, a default configuration that includes the commands provided by mshshort, and a configuration whose commands are restricted based on the capabilities of the session.</span></span>

## <a name="remote-runspaces"></a><span data-ttu-id="380ef-117">リモート実行空間</span><span class="sxs-lookup"><span data-stu-id="380ef-117">Remote runspaces</span></span>

<span data-ttu-id="380ef-118">リモートコンピューターで開くことができる実行空間を作成できるようになりました。これにより、リモートコンピューターでコマンドを実行し、結果をローカルに収集できます。</span><span class="sxs-lookup"><span data-stu-id="380ef-118">You can now create runspaces that can be opened on remote computers, allowing you to run commands on the remote machine and collect the results locally.</span></span> <span data-ttu-id="380ef-119">リモート実行空間を作成するには、実行空間を作成するときに、リモート接続に関する情報を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="380ef-119">To create a remote runspace, you must specify information about the remote connection when creating the runspace.</span></span> <span data-ttu-id="380ef-120">例については、CreateRunspace および Createrunspace プールのメソッドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-120">See the CreateRunspace and CreateRunspacePool methods for examples.</span></span> <span data-ttu-id="380ef-121">接続情報は、RunspaceConnectionInfo クラスによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="380ef-121">The connection information is defined by the RunspaceConnectionInfo class.</span></span>

## <a name="private-runspace-elements"></a><span data-ttu-id="380ef-122">プライベート実行空間要素</span><span class="sxs-lookup"><span data-stu-id="380ef-122">Private runspace elements</span></span>

<span data-ttu-id="380ef-123">要素がパブリックまたはプライベートである実行空間を作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-123">You can now create runspaces whose elements are public or private.</span></span> <span data-ttu-id="380ef-124">これにより、実行空間で使用できる要素を持つ実行空間を作成できますが、ユーザーが使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="380ef-124">This allows you to create runspaces whose elements are available to the runspace, but are not available to the user.</span></span> <span data-ttu-id="380ef-125">実行空間のどの要素をプライベートにできるかを確認するには、ConstrainedSessionStateEntry クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-125">See the ConstrainedSessionStateEntry class to find out which elements of the runspace can be made private.</span></span>

## <a name="runspace-threading-modes-and-apartment-state"></a><span data-ttu-id="380ef-126">実行空間スレッドモードとアパートメント状態</span><span class="sxs-lookup"><span data-stu-id="380ef-126">Runspace threading modes and apartment state</span></span>

<span data-ttu-id="380ef-127">実行空間でコマンドを実行するときに、スレッドを作成して使用する方法を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-127">You can now specify how threads are created and used when running commands in a runspace.</span></span> <span data-ttu-id="380ef-128">RunspacePool プロパティとプロパティを参照してください。このプロパティについては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-128">See the System.Management.Automation.Runspaces.Runspace.ThreadOptions and System.Management.Automation.Runspaces.RunspacePool.ThreadOptions properties.</span></span>

<span data-ttu-id="380ef-129">実行空間でコマンドを実行するために使用されるスレッドのアパートメント状態を取得できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-129">You can now get the apartment state of the threads that are used to run commands in a runspace.</span></span> <span data-ttu-id="380ef-130">System.threading.thread.apartmentstate プロパティと RunspacePool プロパティを参照してください。このプロパティについては、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-130">See the System.Management.Automation.Runspaces.Runspace.ApartmentState and System.Management.Automation.Runspaces.RunspacePool.ApartmentState properties.</span></span>

## <a name="transaction-cmdlets"></a><span data-ttu-id="380ef-131">トランザクションのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="380ef-131">Transaction cmdlets</span></span>

<span data-ttu-id="380ef-132">トランザクション内で使用できるコマンドレットを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-132">You can now create cmdlets that can be used within a transaction.</span></span> <span data-ttu-id="380ef-133">コマンドレットがトランザクションで使用されている場合、そのアクションは一時的なものであり、Windows PowerShell によって提供されるトランザクションコマンドレットによって受け入れまたは拒否されることがあります。</span><span class="sxs-lookup"><span data-stu-id="380ef-133">When a cmdlet is used in a transaction, its actions are temporary, and they can be accepted or rejected by the transaction cmdlets provided by Windows PowerShell.</span></span>

<span data-ttu-id="380ef-134">トランザクションの詳細については、「トランザクションをサポートする方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-134">For more information about transactions, see How to Support Transactions.</span></span>

## <a name="transaction-provider"></a><span data-ttu-id="380ef-135">トランザクションプロバイダー</span><span class="sxs-lookup"><span data-stu-id="380ef-135">Transaction provider</span></span>

<span data-ttu-id="380ef-136">トランザクション内で使用できるプロバイダーを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-136">You can now create providers that can be used within a transaction.</span></span> <span data-ttu-id="380ef-137">コマンドレットと同様に、プロバイダーがトランザクションで使用されている場合、そのアクションは一時的であり、Windows PowerShell によって提供されるトランザクションコマンドレットによって受け入れまたは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="380ef-137">Similar to cmdlets, when a provider is used in a transaction, its actions are temporary, and they can be accepted or rejected by the transaction cmdlets provided by Windows PowerShell.</span></span>

<span data-ttu-id="380ef-138">プロバイダークラス内でのトランザクションのサポートを指定する方法の詳細については、「」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-138">For more information about specifying support for transaction within a provider class, see the System.Management.Automation.Provider.CmdletProviderAttribute.ProviderCapabilities property.</span></span>

## <a name="job-cmdlets"></a><span data-ttu-id="380ef-139">ジョブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="380ef-139">Job cmdlets</span></span>

<span data-ttu-id="380ef-140">アクションをジョブとして実行できるコマンドレットを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-140">You can now write cmdlets that can perform their action as a job.</span></span> <span data-ttu-id="380ef-141">これらのジョブは、現在のセッションと対話することなくバックグラウンドで実行されます。</span><span class="sxs-lookup"><span data-stu-id="380ef-141">These jobs are run in the background without interacting with the current session.</span></span> <span data-ttu-id="380ef-142">Windows PowerShell がジョブをサポートする方法の詳細については、「バックグラウンドジョブ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-142">For more information about how Windows PowerShell supports jobs, see Background Jobs.</span></span>

## <a name="cmdlet-output-types"></a><span data-ttu-id="380ef-143">コマンドレットの出力の種類</span><span class="sxs-lookup"><span data-stu-id="380ef-143">Cmdlet output types</span></span>

<span data-ttu-id="380ef-144">コマンドレットを記述するときに OutputType 属性を宣言することで、コマンドレットによって返される .NET Framework の種類を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-144">You can now specify the .NET Framework types that are returned by your cmdlets by declaring the OutputType attribute when writing your cmdlets.</span></span> <span data-ttu-id="380ef-145">これにより、コマンドレットの OutputType プロパティを確認することで、コマンドレットによって返されるオブジェクトの種類を他のユーザーが判断できるようになります。</span><span class="sxs-lookup"><span data-stu-id="380ef-145">This will allow others to determine what type of objects are returned by a cmdlet by looking at the OutputType property of the cmdlet.</span></span>

## <a name="event-support"></a><span data-ttu-id="380ef-146">イベントのサポート</span><span class="sxs-lookup"><span data-stu-id="380ef-146">Event support</span></span>

<span data-ttu-id="380ef-147">イベントを追加して使用するコマンドレットを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-147">You can now write cmdlets that add and consume events.</span></span> <span data-ttu-id="380ef-148">PSEvent クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-148">See the PSEvent class.</span></span>

## <a name="proxy-commands"></a><span data-ttu-id="380ef-149">プロキシコマンド</span><span class="sxs-lookup"><span data-stu-id="380ef-149">Proxy commands</span></span>

<span data-ttu-id="380ef-150">別のコマンドを実行するために使用できるプロキシコマンドを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-150">You can now write proxy commands that can be used to run another command.</span></span> <span data-ttu-id="380ef-151">プロキシコマンドを使用すると、ユーザーが使用できる source コマンドレットの機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="380ef-151">A proxy command allows you to control what functionality of the source cmdlet is available to the user.</span></span> <span data-ttu-id="380ef-152">たとえば、source コマンドによって指定されたパラメーターを削除するプロキシコマンドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="380ef-152">For example, you can create a proxy command that removes a parameter that is supplied by the source command.</span></span> <span data-ttu-id="380ef-153">ProxyCommand クラスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-153">See the ProxyCommand class.</span></span>

## <a name="multiple-choice-prompts"></a><span data-ttu-id="380ef-154">複数選択のプロンプト</span><span class="sxs-lookup"><span data-stu-id="380ef-154">Multiple choice prompts</span></span>

<span data-ttu-id="380ef-155">ユーザーが複数の選択肢を選択できるようにするためのプロンプトを提供できるアプリケーションを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-155">You can now write applications that can provide prompts that allow the user to select multiple choices.</span></span> <span data-ttu-id="380ef-156">IHostUISupportsMultipleChoiceSelection インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-156">See the IHostUISupportsMultipleChoiceSelection interface</span></span>

## <a name="interactive-sessions"></a><span data-ttu-id="380ef-157">対話型セッション</span><span class="sxs-lookup"><span data-stu-id="380ef-157">Interactive sessions</span></span>

<span data-ttu-id="380ef-158">リモートコンピューターで対話型セッションを開始および停止できるアプリケーションを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-158">You can now write applications that can start and stop an interactive session on a remote computer.</span></span>
<span data-ttu-id="380ef-159">IHostSupportsInteractiveSession インターフェイスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="380ef-159">See the IHostSupportsInteractiveSession interface.</span></span>

## <a name="custom-cmdlet-help-for-providers"></a><span data-ttu-id="380ef-160">プロバイダーのカスタムコマンドレットヘルプ</span><span class="sxs-lookup"><span data-stu-id="380ef-160">Custom Cmdlet Help for Providers</span></span>

<span data-ttu-id="380ef-161">プロバイダーコマンドレットのカスタマイズされたヘルプトピックを作成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="380ef-161">You can now create customized Help topics for the provider cmdlets.</span></span> <span data-ttu-id="380ef-162">カスタムコマンドレットのヘルプトピックでは、プロバイダーパスでのコマンドレットの動作と、プロバイダーがコマンドレットに追加する動的パラメーターなどの特別な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="380ef-162">Custom cmdlet help topics can explain how the cmdlet works in the provider path and document special features, including the dynamic parameters that the provider adds to the cmdlet.</span></span>
