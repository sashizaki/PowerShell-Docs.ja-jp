---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell SDK のインストール"
ms.assetid: c3636b45-61aa-4720-85f0-58312c4fc8f9
ms.openlocfilehash: c6acba828e469e716c80603ec2432176652a7280
ms.sourcegitcommit: 598b7835046577841aea2211d613bb8513271a8b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2017
---
# <a name="installing-the-windows-powershell-sdk"></a><span data-ttu-id="a6ee1-103">Windows PowerShell SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="a6ee1-103">Installing the Windows PowerShell SDK</span></span>

<span data-ttu-id="a6ee1-104">以下のトピックでは、異なるバージョンの Windows に PowerShell SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-104">The following topic describes how to install the PowerShell SDK on different versions of Windows.</span></span>

## <a name="installing-windows-powershell-30-sdk-for-windows-8-and-windows-server-2012"></a><span data-ttu-id="a6ee1-105">Windows 8 と Windows Server 2012 での Windows PowerShell 3.0 SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="a6ee1-105">Installing Windows PowerShell 3.0 SDK for Windows 8 and Windows Server 2012</span></span>

<span data-ttu-id="a6ee1-106">Windows PowerShell 3.0 は Windows 8 と Windows Server 2012 で自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-106">Windows PowerShell 3.0 is automatically installed with Windows 8 and Windows Server 2012.</span></span>
<span data-ttu-id="a6ee1-107">さらに、Windows 8 SDK の一部としての Windows PowerShell 3.0 の参照アセンブリもダウンロードおよびインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-107">In addition, you can download and install the reference assemblies for Windows PowerShell 3.0 as part of the Windows 8 SDK.</span></span>
<span data-ttu-id="a6ee1-108">これらのアセンブリでは、Windows PowerShell 3.0 のコマンドレット、プロバイダー、およびホスト プログラムを記述できます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-108">These assemblies allow you to write cmdlets, providers, and host programs for Windows PowerShell 3.0.</span></span>
<span data-ttu-id="a6ee1-109">Windows 8 用 Windows SDK をインストールすると、Windows PowerShell アセンブリが自動的に \Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0 にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-109">When you install the Windows SDK for Windows 8, the Windows PowerShell assemblies are automatically installed in the reference assembly folder, in \Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0.</span></span>
<span data-ttu-id="a6ee1-110">詳細については、[Windows 8 SDK ダウンロード サイト](http://msdn.microsoft.com/windows/hardware/hh852363.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-110">For more information, see the [Windows 8 SDK download site](http://msdn.microsoft.com/windows/hardware/hh852363.aspx).</span></span>
<span data-ttu-id="a6ee1-111">Windows PowerShell のサンプル コードもデベロッパー センターで入手できます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-111">Windows PowerShell code samples are also available on the Development Center.</span></span>
<span data-ttu-id="a6ee1-112">詳細については、[デベロッパー センター サイト](http://code.msdn.microsoft.com/windowsdesktop/)のデスクトップ サンプル コード ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-112">For more information, see the Desktop code sample page on the [Dev center site](http://code.msdn.microsoft.com/windowsdesktop/).</span></span>

<span data-ttu-id="a6ee1-113">さらに、Windows PowerShell 3.0 には Windows PowerShell 2.0 SDK との下位互換性があり、これには多くのサンプルコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-113">In addition, Windows PowerShell 3.0 is backwards-compatible with the Windows PowerShell 2.0 SDK, which includes a number of code samples.</span></span>
<span data-ttu-id="a6ee1-114">Windows PowerShell 2.0 SDK をダウンロードする方法の詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-114">For more information on how to download the Windows PowerShell 2.0 SDK, see below.</span></span>
<span data-ttu-id="a6ee1-115">(2.0 のサンプル コードは Windows 8 および Windows PowerShell 3.0 と互換性がありますが、Windows PowerShell 2.0 を Windows 8 プラットフォームにインストールすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-115">(Note that while the 2.0 code samples are compatible with Windows 8 and Windows PowerShell 3.0, you cannot install Windows PowerShell 2.0 on a Windows 8 platform.)</span></span>

##<a name="installing-windows-powershell-30-sdk-for-windows-7-and-windows-server-2008-r2"></a><span data-ttu-id="a6ee1-116">Windows 7 と Windows Server 2008 R2 での Windows PowerShell 3.0 SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="a6ee1-116">Installing Windows PowerShell 3.0 SDK for Windows 7 and Windows Server 2008 R2</span></span>

<span data-ttu-id="a6ee1-117">Windows 7 と Windows Server 2008 R2 では、PowerShell 2.0 が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-117">Windows 7 and Windows Server 2008 R2 automatically have PowerShell 2.0 installed.</span></span>
<span data-ttu-id="a6ee1-118">さらに、これらのシステムに PowerShell 3.0 をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-118">In addition, you can install PowerShell 3.0 on these systems.</span></span>
<span data-ttu-id="a6ee1-119">(詳細については、「[Windows PowerShell のインストール](Installing-Windows-PowerShell.md)」をご覧ください。)</span><span class="sxs-lookup"><span data-stu-id="a6ee1-119">(For more information, see [Installing Windows PowerShell](Installing-Windows-PowerShell.md).).</span></span>
<span data-ttu-id="a6ee1-120">前述のように、Windows 7 および Windows Server 2008 R2 で Windows 8 SDK をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-120">As described above, you can also install the Windows 8 SDK on Windows 7 and Windows Server 2008 R2.</span></span>

## <a name="installing-windows-powershell-20-sdk-for-windows-7-vista-xp-server-2003-and-server-2008"></a><span data-ttu-id="a6ee1-121">Windows 7、Vista、XP、Server 2003、Server 2008 での Windows PowerShell 2.0 SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="a6ee1-121">Installing Windows PowerShell 2.0 SDK for Windows 7, Vista, XP, Server 2003, and Server 2008</span></span>

<span data-ttu-id="a6ee1-122">Windows PowerShell 2.0 SDK は、コマンドレット、プロバイダー、アプリケーションのホストを記述するために必要な参照アセンブリを提供し、コードの記述を開始するときに開始点として使用できる C# サンプル コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-122">The Windows PowerShell 2.0 SDK provides the reference assemblies needed to write cmdlets, providers, and hosting applications, and it provides C# sample code that can be used as the starting point when you begin writing code.</span></span>

<span data-ttu-id="a6ee1-123">この SDK をインストールするには、「[Windows PowerShell 2.0 SDK](http://go.microsoft.com/fwlink/?LinkId=184611)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-123">To install this SDK, see [Windows PowerShell 2.0 SDK](http://go.microsoft.com/fwlink/?LinkId=184611).</span></span>

## <a name="reference-assemblies"></a><span data-ttu-id="a6ee1-124">参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="a6ee1-124">Reference assemblies</span></span>

<span data-ttu-id="a6ee1-125">既定では、参照アセンブリは `c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-125">Reference assemblies are installed in the following location by default: `c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0`.</span></span>

> <span data-ttu-id="a6ee1-126">**注記**: Windows PowerShell 2.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 1.0 のインストールに読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-126">**Note**: Code that is compiled against the Windows PowerShell 2.0 assemblies cannot be loaded into Windows PowerShell 1.0 installations.</span></span>
><span data-ttu-id="a6ee1-127">ただし、Windows PowerShell 1.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 2.0 のインストールに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-127">However, code that is compiled against the Windows PowerShell 1.0 assemblies can be loaded into Windows PowerShell 2.0 installations.</span></span>

## <a name="samples"></a><span data-ttu-id="a6ee1-128">サンプル</span><span class="sxs-lookup"><span data-stu-id="a6ee1-128">Samples</span></span>

<span data-ttu-id="a6ee1-129">既定では、コード サンプルは `C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-129">Code samples are installed in the following location by default: `C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.</span></span>

<span data-ttu-id="a6ee1-130">次のセクションでは、各サンプル コードについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-130">The following sections provide a brief description of what each sample does.</span></span>

## <a name="cmdlet-samples"></a><span data-ttu-id="a6ee1-131">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="a6ee1-131">Cmdlet samples</span></span>
<span data-ttu-id="a6ee1-132">**GetProcessSample01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-132">**GetProcessSample01**</span></span>

<span data-ttu-id="a6ee1-133">ローカル コンピューターのすべてのプロセスを取得する簡単なコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-133">Shows how to write a simple cmdlet that gets all the processes on the local computer.</span></span>

<span data-ttu-id="a6ee1-134">**GetProcessSample02**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-134">**GetProcessSample02**</span></span>

<span data-ttu-id="a6ee1-135">コマンドレットにパラメーターを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-135">Shows how to add parameters to the cmdlet.</span></span>
<span data-ttu-id="a6ee1-136">このコマンドレットは 1 つまたは複数のプロセス名を取得し、それに一致するプロセスを返します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-136">The cmdlet takes one or more process names and returns the matching processes.</span></span>

<span data-ttu-id="a6ee1-137">**GetProcessSample03**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-137">**GetProcessSample03**</span></span>

<span data-ttu-id="a6ee1-138">パイプラインからの入力を受け入れるパラメーターを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-138">Shows how to add parameters that accept input from the pipeline.</span></span>

<span data-ttu-id="a6ee1-139">**GetProcessSample04**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-139">**GetProcessSample04**</span></span>

<span data-ttu-id="a6ee1-140">終了しないエラーの処理方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-140">Shows how to handle nonterminating errors.</span></span>

<span data-ttu-id="a6ee1-141">**GetProcessSample05**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-141">**GetProcessSample05**</span></span>

<span data-ttu-id="a6ee1-142">指定されたプロセスの一覧を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-142">Shows how to display a list of specified processes.</span></span>

<span data-ttu-id="a6ee1-143">**SelectObject**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-143">**SelectObject**</span></span>

<span data-ttu-id="a6ee1-144">特定のオブジェクトのみを選択するフィルターの記述方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-144">Shows how to write a filter to select only certain objects.</span></span>

<span data-ttu-id="a6ee1-145">**SelectString**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-145">**SelectString**</span></span>

<span data-ttu-id="a6ee1-146">指定されたパターンのファイルを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-146">Shows how to search files for specified patterns.</span></span>

<span data-ttu-id="a6ee1-147">**StopProcessSample01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-147">**StopProcessSample01**</span></span>

<span data-ttu-id="a6ee1-148">*PassThru* パラメーターの実装方法と、[ShouldProcess](https://technet.microsoft.com/library/system.management.automation.cmdlet.shouldprocess.aspx) メソッドと [ShouldContinue](https://technet.microsoft.com/library/system.management.automation.cmdlet.shouldcontinue.aspx) メソッドを呼び出すことでユーザーにフィードバックを要求する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-148">Shows how to implement a *PassThru* parameter, and how to request user feedback by calls to the [ShouldProcess](https://technet.microsoft.com/library/system.management.automation.cmdlet.shouldprocess.aspx) and [ShouldContinue](https://technet.microsoft.com/library/system.management.automation.cmdlet.shouldcontinue.aspx) methods.</span></span>
<span data-ttu-id="a6ee1-149">ユーザーはオブジェクトを返すようにコマンドレットに強制するとき、*PassThru* を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-149">Users specify the *PassThru* parameter when they want to force the cmdlet to return an object,</span></span>

<span data-ttu-id="a6ee1-150">**StopProcessSample02**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-150">**StopProcessSample02**</span></span>

<span data-ttu-id="a6ee1-151">特定のプロセスの停止方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-151">Shows how to stop a specific process.</span></span>

<span data-ttu-id="a6ee1-152">**StopProcessSample03**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-152">**StopProcessSample03**</span></span>

<span data-ttu-id="a6ee1-153">パラメーターのエイリアスの宣言方法とワイルドカードのサポート方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-153">Shows how to declare aliases for parameters and how to support wildcards.</span></span>

<span data-ttu-id="a6ee1-154">**StopProcessSample04**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-154">**StopProcessSample04**</span></span>

<span data-ttu-id="a6ee1-155">パラメーター セットの宣言方法、コマンドレットが入力として取得するオブジェクト、既定として使用するパラメーター セットの指定方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-155">Shows how to declare parameter sets, the object that the cmdlet takes as input, and how to specify the default parameter set to use.</span></span>

## <a name="remoting-samples"></a><span data-ttu-id="a6ee1-156">リモート処理のサンプル</span><span class="sxs-lookup"><span data-stu-id="a6ee1-156">Remoting samples</span></span>

<span data-ttu-id="a6ee1-157">**RemoteRunspace01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-157">**RemoteRunspace01**</span></span>

<span data-ttu-id="a6ee1-158">リモート接続の確立に使用されるリモート実行空間の作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-158">Shows how to create a remote runspace that is used to establish a remote connection.</span></span>

<span data-ttu-id="a6ee1-159">**RemoteRunspacePool01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-159">**RemoteRunspacePool01**</span></span>

<span data-ttu-id="a6ee1-160">リモート実行空間プールの構築方法とそのプールを使用して複数のコマンドを同時に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-160">Shows how to construct a remote runspace pool and how to run multiple commands concurrently by using this pool.</span></span>

<span data-ttu-id="a6ee1-161">**Serialization01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-161">**Serialization01**</span></span>

<span data-ttu-id="a6ee1-162">既存の .NET クラスを見て、そのクラスで選択されているパブリック プロパティからの情報がシリアル化/逆シリアル化全体で維持されていることを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-162">Shows how to look at an existing .NET class and make sure that information from selected public properties of this class is preserved across serialization/deserialization.</span></span>

<span data-ttu-id="a6ee1-163">**Serialization02**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-163">**Serialization02**</span></span>

<span data-ttu-id="a6ee1-164">既存の .NET クラスを見て、そのクラスのインスタンスからの情報がクラスのパブリック プロパティで利用できないとき、その情報がシリアル化/シリアル化解除全体で維持されていることを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-164">Shows how to look at an existing .NET class and make sure that information from instance of this class is preserved across serialization/deserialization when the information is not available in public properties of the class.</span></span>

<span data-ttu-id="a6ee1-165">**Serialization03**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-165">**Serialization03**</span></span>

<span data-ttu-id="a6ee1-166">既存の .NET クラスを見て、そのクラスのインスタンスと派生クラスのインスタンスがライブ .NET オブジェクトに逆シリアル化 (リハイドレート) されていることを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-166">Shows how to look at an existing .NET class and make sure that instances of this class and of derived classes are deserialized (rehydrated) into live .NET objects.</span></span>

## <a name="event-samples"></a><span data-ttu-id="a6ee1-167">イベントのサンプル</span><span class="sxs-lookup"><span data-stu-id="a6ee1-167">Event samples</span></span>

<span data-ttu-id="a6ee1-168">**Event01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-168">**Event01**</span></span>

<span data-ttu-id="a6ee1-169">ObjectEventRegistrationBase から派生させることでイベント登録のコマンドレットを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-169">Shows how to create a cmdlet for event registration by deriving from ObjectEventRegistrationBase.</span></span>

<span data-ttu-id="a6ee1-170">**Event02**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-170">**Event02**</span></span>

<span data-ttu-id="a6ee1-171">リモート コンピューターで生成された Windows PowerShell イベントの通知を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-171">Shows how to shows how to receive notifications of Windows PowerShell events that are generated on remote computers.</span></span>
<span data-ttu-id="a6ee1-172">[Runspace](https://technet.microsoft.com/library/system.management.automation.runspaces.runspace.aspx) クラスで公開された PSEventReceived イベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-172">It uses the PSEventReceived event exposed through the [Runspace](https://technet.microsoft.com/library/system.management.automation.runspaces.runspace.aspx) class.</span></span>

## <a name="hosting-application-samples"></a><span data-ttu-id="a6ee1-173">アプリケーションのホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="a6ee1-173">Hosting application samples</span></span>

<span data-ttu-id="a6ee1-174">**Runspace01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-174">**Runspace01**</span></span>

<span data-ttu-id="a6ee1-175">[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) クラスを使用し、[Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) コマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-175">Shows how to use the [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) class to run the [Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) cmdlet synchronously.</span></span>
<span data-ttu-id="a6ee1-176">[Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) コマンドレットは、ローカル コンピューターで実行されているプロセスごとに [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-176">The [Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) cmdlet returns [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) objects for each process running on the local computer.</span></span>

<span data-ttu-id="a6ee1-177">**Runspace02**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-177">**Runspace02**</span></span>

<span data-ttu-id="a6ee1-178">[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) クラスを使用し、[Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) コマンドレットと [Sort-Object](http://go.microsoft.com/fwlink/?LinkID=113403) コマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-178">Shows how to use the [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) class to run the [Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) and [Sort-Object](http://go.microsoft.com/fwlink/?LinkID=113403) cmdlets synchronously.</span></span>
<span data-ttu-id="a6ee1-179">[Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) コマンドレットは、ローカル コンピューターで実行されているプロセスごとに [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) オブジェクトを返します。Sort-Object は、[Id](https://technet.microsoft.com/library/system.diagnostics.process.id.aspx) プロパティに基づいてオブジェクトを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-179">The [Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) cmdlet returns [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) objects for each process running on the local computer, and the Sort-Object sorts the objects based on their [Id](https://technet.microsoft.com/library/system.diagnostics.process.id.aspx) property.</span></span>
<span data-ttu-id="a6ee1-180">これらのコマンドの結果は、[DataGridView](https://technet.microsoft.com/library/system.windows.forms.datagridview.aspx) コントロールを利用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-180">The results of these commands is displayed by using a [DataGridView](https://technet.microsoft.com/library/system.windows.forms.datagridview.aspx) control.</span></span>

<span data-ttu-id="a6ee1-181">**Runspace03**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-181">**Runspace03**</span></span>

<span data-ttu-id="a6ee1-182">[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) クラスを使用してスクリプトを同期的に実行する方法と終了しないエラーを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-182">Shows how to use the [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) class to run a script synchronously, and how to handle non-terminating errors.</span></span>
<span data-ttu-id="a6ee1-183">このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-183">The script receives a list of process names and then retrieves those processes.</span></span>
<span data-ttu-id="a6ee1-184">スクリプトの実行時に生成された終了しないエラーを含む、スクリプトの結果がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-184">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

<span data-ttu-id="a6ee1-185">**Runspace04**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-185">**Runspace04**</span></span>

<span data-ttu-id="a6ee1-186">[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) クラスを使用してコマンドを実行する方法とコマンドの実行時にスローされた終了するエラーをキャッチする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-186">Shows how to use the [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span>
<span data-ttu-id="a6ee1-187">2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-187">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span>
<span data-ttu-id="a6ee1-188">結果として、オブジェクトは返されず、終了するエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-188">As a result, no objects are returned and a terminating error is thrown.</span></span>

<span data-ttu-id="a6ee1-189">**Runspace05**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-189">**Runspace05**</span></span>

<span data-ttu-id="a6ee1-190">実行空間が開いたとき、スナップショットのコマンドレットが利用できるように [InitialSessionState](https://technet.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.aspx) オブジェクトにスナップインを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-190">Shows how to add a snap-in to an [InitialSessionState](https://technet.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.aspx) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span>
<span data-ttu-id="a6ee1-191">このスナップインにより、[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) オブジェクトを使用して同期的に実行される Get-Proc コマンドレット ([GetProcessSample01 サンプル](https://technet.microsoft.com/library/ff602028.aspx)により定義) が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-191">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](https://technet.microsoft.com/library/ff602028.aspx)) that is run synchronously by using a [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) object.</span></span>

<span data-ttu-id="a6ee1-192">**Runspace06**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-192">**Runspace06**</span></span>

<span data-ttu-id="a6ee1-193">実行空間が開いたとき、モジュールが読み込まれるように [InitialSessionState](https://technet.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.aspx) オブジェクトにモジュールを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-193">Shows how to add a module to an [InitialSessionState](https://technet.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.aspx) object so that the module is loaded when the runspace is opened.</span></span>
<span data-ttu-id="a6ee1-194">このモジュールにより、[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) オブジェクトを使用して同期的に実行される Get-Proc コマンドレット ([GetProcessSample02 サンプル](https://technet.microsoft.com/library/ff602027.aspx)により定義) が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-194">The module provides a Get-Proc cmdlet (defined by the [GetProcessSample02 Sample](https://technet.microsoft.com/library/ff602027.aspx)) that is run synchronously by using a [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) object.</span></span>

<span data-ttu-id="a6ee1-195">**Runspace07**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-195">**Runspace07**</span></span>

<span data-ttu-id="a6ee1-196">実行空間を作成し、その実行空間を使用し、[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) オブジェクトを使用して 2 つのコマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-196">Shows how to create a runspace, and then use that runspace to run two cmdlets synchronously by using a [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) object.</span></span>

<span data-ttu-id="a6ee1-197">**Runspace08**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-197">**Runspace08**</span></span>

<span data-ttu-id="a6ee1-198">[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) オブジェクトのパイプラインにコマンドと引数を追加する方法とコマンドを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-198">Shows how to add commands and arguments to the pipeline of a [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) object and how to run the commands synchronously.</span></span>

<span data-ttu-id="a6ee1-199">**Runspace09**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-199">**Runspace09**</span></span>

<span data-ttu-id="a6ee1-200">[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) オブジェクトのパイプラインにスクリプトを追加する方法とそのスクリプトを非同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-200">Shows how to add a script to the pipeline of a [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) object and how to run the script asynchronously.</span></span>
<span data-ttu-id="a6ee1-201">イベントはスクリプトの出力を処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-201">Events are used to handle the output of the script.</span></span>

<span data-ttu-id="a6ee1-202">**Runspace10**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-202">**Runspace10**</span></span>

<span data-ttu-id="a6ee1-203">既定の最初のセッション状態を作成する方法、コマンドレットを [InitialSessionState](https://technet.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.aspx) に追加する方法、最初のセッション状態を使用する実行空間を作成する方法、[PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) オブジェクトを使用してコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-203">Shows how to create a default initial session state, how to add a cmdlet to the [InitialSessionState](https://technet.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.aspx), how to create a runspace that uses the initial session state, and how to run the command by using a [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) object.</span></span>

<span data-ttu-id="a6ee1-204">**Runspace11**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-204">**Runspace11**</span></span>

<span data-ttu-id="a6ee1-205">[ProxyCommand](https://technet.microsoft.com/library/system.management.automation.proxycommand.aspx) クラスを使用し、既存のコマンドレットを呼び出すが、利用できるパラメーターのセットを制約するプロキシ コマンドを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-205">Shows how to use the [ProxyCommand](https://technet.microsoft.com/library/system.management.automation.proxycommand.aspx) class to create a proxy command that calls an existing cmdlet, but restricts the set of available parameters.</span></span>
<span data-ttu-id="a6ee1-206">このプロキシ コマンドは、制約付き実行空間の作成に使用される最初のセッション状態に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-206">The proxy command is then added to an initial session state that is used to create a constrained runspace.</span></span>
<span data-ttu-id="a6ee1-207">つまり、ユーザーはプロキシ コマンドを使用しないとコマンドレットの機能にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-207">This means that the user can access the functionality of the cmdlet only through the proxy command.</span></span>

<span data-ttu-id="a6ee1-208">**PowerShell01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-208">**PowerShell01**</span></span>

<span data-ttu-id="a6ee1-209">[InitialSessionState](https://technet.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.aspx) オブジェクトを使用し、制約のある実行空間を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-209">Shows how to create a constrained runspace using an [InitialSessionState](https://technet.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.aspx) object.</span></span>

<span data-ttu-id="a6ee1-210">**PowerShell02**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-210">**PowerShell02**</span></span>

<span data-ttu-id="a6ee1-211">実行空間プールを使用し、複数のコマンドを同時に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-211">Shows how to use a runspace pool to run multiple commands concurrently.</span></span>

## <a name="host-samples"></a><span data-ttu-id="a6ee1-212">ホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="a6ee1-212">Host samples</span></span>

<span data-ttu-id="a6ee1-213">**Host01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-213">**Host01**</span></span>

<span data-ttu-id="a6ee1-214">カスタム ホストを使用するホスト アプリケーションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-214">Shows how to implement a host application that uses a custom host.</span></span>
<span data-ttu-id="a6ee1-215">このサンプルでは、カスタム ホストを使用する実行空間が作成され、その後 [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) API を使用して "exit" を呼び出すスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-215">In this sample a runspace is created that uses the custom host, and then the [PowerShell](https://technet.microsoft.com/library/system.management.automation.powershell.aspx) API is used to run a script that calls "exit".</span></span>
<span data-ttu-id="a6ee1-216">ホスト アプリケーションはスクリプトの出力を確認し、結果を印刷します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-216">The host application then looks at the output of the script and prints out the results.</span></span>

<span data-ttu-id="a6ee1-217">**Host02**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-217">**Host02**</span></span>

<span data-ttu-id="a6ee1-218">カスタム ホストの実装と共に Windows PowerShell ランタイムを使用するホスト アプリケーションを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-218">Shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span>
<span data-ttu-id="a6ee1-219">ホスト アプリケーションはホストのカルチャをドイツ語に設定し、[Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) コマンドレットを実行して、pwrsh.exe を使用して確認できるものと同じ結果を表示し、最新のデータと時刻をドイツ語で印刷します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-219">The host application sets the host culture to German, runs the [Get-Process](http://go.microsoft.com/fwlink/?LinkId=113324) cmdlet and displays the results as you would see them by using pwrsh.exe, and then prints out the current data and time in German.</span></span>

<span data-ttu-id="a6ee1-220">**Host03**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-220">**Host03**</span></span>

<span data-ttu-id="a6ee1-221">コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-221">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

<span data-ttu-id="a6ee1-222">**Host04**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-222">**Host04**</span></span>

<span data-ttu-id="a6ee1-223">コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-223">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="a6ee1-224">このホスト アプリケーションでは、複数選択を指定するための確認メッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-224">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

<span data-ttu-id="a6ee1-225">**Host05**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-225">**Host05**</span></span>

<span data-ttu-id="a6ee1-226">コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-226">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="a6ee1-227">このホスト アプリケーションでは、[Enter-PsSession](http://go.microsoft.com/fwlink/?LinkId=135210) コマンドレットと [Exit-PsSession](http://go.microsoft.com/fwlink/?LinkId=135212) コマンドレットを使用してリモート コンピューターを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-227">This host application also supports calls to remote computers by using the [Enter-PsSession](http://go.microsoft.com/fwlink/?LinkId=135210) and [Exit-PsSession](http://go.microsoft.com/fwlink/?LinkId=135212) cmdlets.</span></span>

<span data-ttu-id="a6ee1-228">**Host06**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-228">**Host06**</span></span>

<span data-ttu-id="a6ee1-229">コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-229">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="a6ee1-230">さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-230">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="provider-samples"></a><span data-ttu-id="a6ee1-231">プロバイダーのサンプル</span><span class="sxs-lookup"><span data-stu-id="a6ee1-231">Provider samples</span></span>

<span data-ttu-id="a6ee1-232">**AccessDBProviderSample01**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-232">**AccessDBProviderSample01**</span></span>

<span data-ttu-id="a6ee1-233">[CmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.cmdletprovider.aspx) クラスから直接派生するプロバイダー クラスの宣言方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-233">Shows how to declare a provider class that derives directly from the [CmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.cmdletprovider.aspx) class.</span></span>
<span data-ttu-id="a6ee1-234">すべてを網羅しておく目的でここに含めておきます。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-234">It is included here only for completeness.</span></span>

<span data-ttu-id="a6ee1-235">**AccessDBProviderSample02**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-235">**AccessDBProviderSample02**</span></span>

<span data-ttu-id="a6ee1-236">New-PSDrive コマンドレットと Remove-PSDrive コマンドレットを呼び出すために [NewDrive](https://technet.microsoft.com/library/system.management.automation.provider.drivecmdletprovider.newdrive.aspx) メソッドと [RemoveDrive](https://technet.microsoft.com/library/system.management.automation.provider.drivecmdletprovider.removedrive.aspx) メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-236">Shows how to overwrite the [NewDrive](https://technet.microsoft.com/library/system.management.automation.provider.drivecmdletprovider.newdrive.aspx) and [RemoveDrive](https://technet.microsoft.com/library/system.management.automation.provider.drivecmdletprovider.removedrive.aspx) methods to support calls to the New-PSDrive and Remove-PSDrive cmdlets.</span></span>
<span data-ttu-id="a6ee1-237">このサンプルのプロバイダー クラスは [DriveCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.drivecmdletprovider.aspx) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-237">The provider class in this sample derives from the [DriveCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.drivecmdletprovider.aspx) class.</span></span>

<span data-ttu-id="a6ee1-238">**AccessDBProviderSample03**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-238">**AccessDBProviderSample03**</span></span>

<span data-ttu-id="a6ee1-239">Get-Item コマンドレットと Set-Item コマンドレットを呼び出すために [GetItem](https://technet.microsoft.com/library/system.management.automation.provider.itemcmdletprovider.getitem.aspx) メソッドと [SetItem](https://technet.microsoft.com/library/system.management.automation.provider.itemcmdletprovider.setitem.aspx) メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-239">Shows how to overwrite the [GetItem](https://technet.microsoft.com/library/system.management.automation.provider.itemcmdletprovider.getitem.aspx) and [SetItem](https://technet.microsoft.com/library/system.management.automation.provider.itemcmdletprovider.setitem.aspx) methods to support calls to the Get-Item and Set-Item cmdlets.</span></span>
<span data-ttu-id="a6ee1-240">このサンプルのプロバイダー クラスは [ItemCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.itemcmdletprovider.aspx) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-240">The provider class in this sample derives from the [ItemCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.itemcmdletprovider.aspx) class.</span></span>

<span data-ttu-id="a6ee1-241">**AccessDBProviderSample04**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-241">**AccessDBProviderSample04**</span></span>

<span data-ttu-id="a6ee1-242">Copy-Item コマンドレット、Get-ChildItem コマンドレット、New-Item コマンドレット、Remove-Item コマンドレットを呼び出すためにコンテナー メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-242">Shows how to overwrite container methods to support calls to the Copy-Item, Get-ChildItem, New-Item, and Remove-Item cmdlets.</span></span>
<span data-ttu-id="a6ee1-243">これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-243">These methods should be implemented when the data store contains items that are containers.</span></span>
<span data-ttu-id="a6ee1-244">コンテナーは、共通の親項目の子項目のグループです。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-244">A container is a group of child items under a common parent item.</span></span>
<span data-ttu-id="a6ee1-245">このサンプルのプロバイダー クラスは [ItemCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.itemcmdletprovider.aspx) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-245">The provider class in this sample derives from the [ItemCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.itemcmdletprovider.aspx) class.</span></span>

<span data-ttu-id="a6ee1-246">**AccessDBProviderSample05**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-246">**AccessDBProviderSample05**</span></span>

<span data-ttu-id="a6ee1-247">Move-Item コマンドレットと Join-Path コマンドレットを呼び出すためにコンテナー メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-247">Shows how to overwrite container methods to support calls to the Move-Item and Join-Path cmdlets.</span></span>
<span data-ttu-id="a6ee1-248">これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-248">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span>
<span data-ttu-id="a6ee1-249">このサンプルのプロバイダー クラスは [NavigationCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.navigationcmdletprovider.aspx) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-249">The provider class in this sample derives from the [NavigationCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.navigationcmdletprovider.aspx) class.</span></span>

<span data-ttu-id="a6ee1-250">**AccessDBProviderSample06**</span><span class="sxs-lookup"><span data-stu-id="a6ee1-250">**AccessDBProviderSample06**</span></span>

<span data-ttu-id="a6ee1-251">Clear-Content コマンドレット、Get-Content コマンドレット、Set-Content コマンドレットを呼び出すためにコンテナー メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-251">Shows how to overwrite content methods to support calls to the Clear-Content, Get-Content, and Set-Content cmdlets.</span></span>
<span data-ttu-id="a6ee1-252">これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-252">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span>
<span data-ttu-id="a6ee1-253">このサンプルのプロバイダー クラスは [NavigationCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.navigationcmdletprovider.aspx) クラスから派生し、[IContentCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.icontentcmdletprovider.aspx) インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="a6ee1-253">The provider class in this sample derives from the [NavigationCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.navigationcmdletprovider.aspx) class, and it implements the [IContentCmdletProvider](https://technet.microsoft.com/library/system.management.automation.provider.icontentcmdletprovider.aspx) interface.</span></span>

