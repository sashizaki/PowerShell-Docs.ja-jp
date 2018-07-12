---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell SDK のインストール
ms.assetid: c3636b45-61aa-4720-85f0-58312c4fc8f9
ms.openlocfilehash: fa876bac0c1afac24f93d11dd2e7ecfb1165cf5f
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893540"
---
# <a name="installing-the-windows-powershell-sdk"></a><span data-ttu-id="e1cbf-103">Windows PowerShell SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="e1cbf-103">Installing the Windows PowerShell SDK</span></span>

<span data-ttu-id="e1cbf-104">以下のトピックでは、異なるバージョンの Windows に PowerShell SDK をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-104">The following topic describes how to install the PowerShell SDK on different versions of Windows.</span></span>

## <a name="installing-windows-powershell-30-sdk-for-windows-8-and-windows-server-2012"></a><span data-ttu-id="e1cbf-105">Windows 8 と Windows Server 2012 での Windows PowerShell 3.0 SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="e1cbf-105">Installing Windows PowerShell 3.0 SDK for Windows 8 and Windows Server 2012</span></span>

<span data-ttu-id="e1cbf-106">Windows PowerShell 3.0 は Windows 8 と Windows Server 2012 で自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-106">Windows PowerShell 3.0 is automatically installed with Windows 8 and Windows Server 2012.</span></span>
<span data-ttu-id="e1cbf-107">さらに、Windows 8 SDK の一部としての Windows PowerShell 3.0 の参照アセンブリもダウンロードおよびインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-107">In addition, you can download and install the reference assemblies for Windows PowerShell 3.0 as part of the Windows 8 SDK.</span></span>
<span data-ttu-id="e1cbf-108">これらのアセンブリでは、Windows PowerShell 3.0 のコマンドレット、プロバイダー、およびホスト プログラムを記述できます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-108">These assemblies allow you to write cmdlets, providers, and host programs for Windows PowerShell 3.0.</span></span>
<span data-ttu-id="e1cbf-109">Windows 8 用 Windows SDK をインストールすると、Windows PowerShell アセンブリが自動的に参照アセンブリ フォルダー (`\Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0`) にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-109">When you install the Windows SDK for Windows 8, the Windows PowerShell assemblies are automatically installed in the reference assembly folder, in `\Program Files (x86)\Reference Assemblies\Microsoft\WindowsPowerShell\3.0`.</span></span>
<span data-ttu-id="e1cbf-110">詳細については、[Windows 8 SDK ダウンロード サイト](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-110">For more information, see the [Windows 8 SDK download site](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive).</span></span>
<span data-ttu-id="e1cbf-111">Windows PowerShell のサンプル コードもデベロッパー センターで入手できます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-111">Windows PowerShell code samples are also available on the Development Center.</span></span>
<span data-ttu-id="e1cbf-112">詳細については、[デベロッパー センター サイト](https://code.msdn.microsoft.com:443/windowsdesktop/)のデスクトップ サンプル コード ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-112">For more information, see the Desktop code sample page on the [Dev center site](https://code.msdn.microsoft.com:443/windowsdesktop/).</span></span>

<span data-ttu-id="e1cbf-113">さらに、Windows PowerShell 3.0 には Windows PowerShell 2.0 SDK との下位互換性があり、これには多くのサンプルコードが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-113">In addition, Windows PowerShell 3.0 is backwards-compatible with the Windows PowerShell 2.0 SDK, which includes a number of code samples.</span></span>
<span data-ttu-id="e1cbf-114">Windows PowerShell 2.0 SDK をダウンロードする方法の詳細については、以下をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-114">For more information on how to download the Windows PowerShell 2.0 SDK, see below.</span></span>
<span data-ttu-id="e1cbf-115">(2.0 のサンプル コードは Windows 8 および Windows PowerShell 3.0 と互換性がありますが、Windows PowerShell 2.0 を Windows 8 プラットフォームにインストールすることはできません)。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-115">(Note that while the 2.0 code samples are compatible with Windows 8 and Windows PowerShell 3.0, you cannot install Windows PowerShell 2.0 on a Windows 8 platform.)</span></span>

## <a name="installing-windows-powershell-30-sdk-for-windows-7-and-windows-server-2008-r2"></a><span data-ttu-id="e1cbf-116">Windows 7 と Windows Server 2008 R2 での Windows PowerShell 3.0 SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="e1cbf-116">Installing Windows PowerShell 3.0 SDK for Windows 7 and Windows Server 2008 R2</span></span>

<span data-ttu-id="e1cbf-117">Windows 7 と Windows Server 2008 R2 では、PowerShell 2.0 が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-117">Windows 7 and Windows Server 2008 R2 automatically have PowerShell 2.0 installed.</span></span>
<span data-ttu-id="e1cbf-118">さらに、これらのシステムに PowerShell 3.0 をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-118">In addition, you can install PowerShell 3.0 on these systems.</span></span>
<span data-ttu-id="e1cbf-119">(詳細については、「[Windows PowerShell のインストール](Installing-Windows-PowerShell.md)」をご覧ください。)</span><span class="sxs-lookup"><span data-stu-id="e1cbf-119">(For more information, see [Installing Windows PowerShell](Installing-Windows-PowerShell.md).).</span></span>
<span data-ttu-id="e1cbf-120">前述のように、Windows 7 および Windows Server 2008 R2 で Windows 8 SDK をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-120">As described above, you can also install the Windows 8 SDK on Windows 7 and Windows Server 2008 R2.</span></span>

## <a name="installing-windows-powershell-20-sdk-for-windows-7-vista-xp-server-2003-and-server-2008"></a><span data-ttu-id="e1cbf-121">Windows 7、Vista、XP、Server 2003、Server 2008 での Windows PowerShell 2.0 SDK のインストール</span><span class="sxs-lookup"><span data-stu-id="e1cbf-121">Installing Windows PowerShell 2.0 SDK for Windows 7, Vista, XP, Server 2003, and Server 2008</span></span>

<span data-ttu-id="e1cbf-122">Windows PowerShell 2.0 SDK は、コマンドレット、プロバイダー、アプリケーションのホストを記述するために必要な参照アセンブリを提供し、コードの記述を開始するときに開始点として使用できる C# サンプル コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-122">The Windows PowerShell 2.0 SDK provides the reference assemblies needed to write cmdlets, providers, and hosting applications, and it provides C# sample code that can be used as the starting point when you begin writing code.</span></span>

<span data-ttu-id="e1cbf-123">この SDK をインストールするには、「[Windows PowerShell 2.0 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=2560)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-123">To install this SDK, see [Windows PowerShell 2.0 SDK](http://www.microsoft.com/en-us/download/details.aspx?id=2560).</span></span>

## <a name="reference-assemblies"></a><span data-ttu-id="e1cbf-124">参照アセンブリ</span><span class="sxs-lookup"><span data-stu-id="e1cbf-124">Reference assemblies</span></span>

<span data-ttu-id="e1cbf-125">既定では、参照アセンブリは `c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-125">Reference assemblies are installed in the following location by default: `c:\Program Files\Reference Assemblies\Microsoft\WindowsPowerShell\V1.0`.</span></span>

> [!NOTE] 
> <span data-ttu-id="e1cbf-126">Windows PowerShell 2.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 1.0 のインストールに読み込むことができません。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-126">Code that is compiled against the Windows PowerShell 2.0 assemblies cannot be loaded into Windows PowerShell 1.0 installations.</span></span>
> <span data-ttu-id="e1cbf-127">ただし、Windows PowerShell 1.0 のアセンブリに対してコンパイルされるコードは、Windows PowerShell 2.0 のインストールに読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-127">However, code that is compiled against the Windows PowerShell 1.0 assemblies can be loaded into Windows PowerShell 2.0 installations.</span></span>

## <a name="samples"></a><span data-ttu-id="e1cbf-128">サンプル</span><span class="sxs-lookup"><span data-stu-id="e1cbf-128">Samples</span></span>

<span data-ttu-id="e1cbf-129">既定では、コード サンプルは `C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\` にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-129">Code samples are installed in the following location by default: `C:\Program Files\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\`.</span></span>

<span data-ttu-id="e1cbf-130">次のセクションでは、各サンプル コードについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-130">The following sections provide a brief description of what each sample does.</span></span>

## <a name="cmdlet-samples"></a><span data-ttu-id="e1cbf-131">コマンドレット サンプル</span><span class="sxs-lookup"><span data-stu-id="e1cbf-131">Cmdlet samples</span></span>

### <a name="getprocesssample01"></a><span data-ttu-id="e1cbf-132">GetProcessSample01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-132">GetProcessSample01</span></span>

<span data-ttu-id="e1cbf-133">ローカル コンピューターのすべてのプロセスを取得する簡単なコマンドレットを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-133">Shows how to write a simple cmdlet that gets all the processes on the local computer.</span></span>

### <a name="getprocesssample02"></a><span data-ttu-id="e1cbf-134">GetProcessSample02</span><span class="sxs-lookup"><span data-stu-id="e1cbf-134">GetProcessSample02</span></span>

<span data-ttu-id="e1cbf-135">コマンドレットにパラメーターを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-135">Shows how to add parameters to the cmdlet.</span></span>
<span data-ttu-id="e1cbf-136">このコマンドレットは 1 つまたは複数のプロセス名を取得し、それに一致するプロセスを返します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-136">The cmdlet takes one or more process names and returns the matching processes.</span></span>

### <a name="getprocesssample03"></a><span data-ttu-id="e1cbf-137">GetProcessSample03</span><span class="sxs-lookup"><span data-stu-id="e1cbf-137">GetProcessSample03</span></span>

<span data-ttu-id="e1cbf-138">パイプラインからの入力を受け入れるパラメーターを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-138">Shows how to add parameters that accept input from the pipeline.</span></span>

### <a name="getprocesssample04"></a><span data-ttu-id="e1cbf-139">GetProcessSample04</span><span class="sxs-lookup"><span data-stu-id="e1cbf-139">GetProcessSample04</span></span>

<span data-ttu-id="e1cbf-140">終了しないエラーの処理方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-140">Shows how to handle nonterminating errors.</span></span>

### <a name="getprocesssample05"></a><span data-ttu-id="e1cbf-141">GetProcessSample05</span><span class="sxs-lookup"><span data-stu-id="e1cbf-141">GetProcessSample05</span></span>

<span data-ttu-id="e1cbf-142">指定されたプロセスの一覧を表示する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-142">Shows how to display a list of specified processes.</span></span>

### <a name="selectobject"></a><span data-ttu-id="e1cbf-143">SelectObject</span><span class="sxs-lookup"><span data-stu-id="e1cbf-143">SelectObject</span></span>

<span data-ttu-id="e1cbf-144">特定のオブジェクトのみを選択するフィルターの記述方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-144">Shows how to write a filter to select only certain objects.</span></span>

### <a name="selectstring"></a><span data-ttu-id="e1cbf-145">SelectString</span><span class="sxs-lookup"><span data-stu-id="e1cbf-145">SelectString</span></span>

<span data-ttu-id="e1cbf-146">指定されたパターンのファイルを検索する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-146">Shows how to search files for specified patterns.</span></span>

### <a name="stopprocesssample01"></a><span data-ttu-id="e1cbf-147">StopProcessSample01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-147">StopProcessSample01</span></span>

<span data-ttu-id="e1cbf-148">*PassThru* パラメーターの実装方法と、[ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess) メソッドと [ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue) メソッドを呼び出すことでユーザーにフィードバックを要求する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-148">Shows how to implement a *PassThru* parameter, and how to request user feedback by calls to the [ShouldProcess](/dotnet/api/system.management.automation.cmdlet.shouldprocess) and [ShouldContinue](/dotnet/api/system.management.automation.cmdlet.shouldcontinue) methods.</span></span>
<span data-ttu-id="e1cbf-149">ユーザーはオブジェクトを返すようにコマンドレットに強制するとき、*PassThru* を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-149">Users specify the *PassThru* parameter when they want to force the cmdlet to return an object,</span></span>

### <a name="stopprocesssample02"></a><span data-ttu-id="e1cbf-150">StopProcessSample02</span><span class="sxs-lookup"><span data-stu-id="e1cbf-150">StopProcessSample02</span></span>

<span data-ttu-id="e1cbf-151">特定のプロセスの停止方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-151">Shows how to stop a specific process.</span></span>

### <a name="stopprocesssample03"></a><span data-ttu-id="e1cbf-152">StopProcessSample03</span><span class="sxs-lookup"><span data-stu-id="e1cbf-152">StopProcessSample03</span></span>

<span data-ttu-id="e1cbf-153">パラメーターのエイリアスの宣言方法とワイルドカードのサポート方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-153">Shows how to declare aliases for parameters and how to support wildcards.</span></span>

### <a name="stopprocesssample04"></a><span data-ttu-id="e1cbf-154">StopProcessSample04</span><span class="sxs-lookup"><span data-stu-id="e1cbf-154">StopProcessSample04</span></span>

<span data-ttu-id="e1cbf-155">パラメーター セットの宣言方法、コマンドレットが入力として取得するオブジェクト、既定として使用するパラメーター セットの指定方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-155">Shows how to declare parameter sets, the object that the cmdlet takes as input, and how to specify the default parameter set to use.</span></span>

## <a name="remoting-samples"></a><span data-ttu-id="e1cbf-156">リモート処理のサンプル</span><span class="sxs-lookup"><span data-stu-id="e1cbf-156">Remoting samples</span></span>

### <a name="remoterunspace01"></a><span data-ttu-id="e1cbf-157">RemoteRunspace01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-157">RemoteRunspace01</span></span>

<span data-ttu-id="e1cbf-158">リモート接続の確立に使用されるリモート実行空間の作成方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-158">Shows how to create a remote runspace that is used to establish a remote connection.</span></span>

### <a name="remoterunspacepool01"></a><span data-ttu-id="e1cbf-159">RemoteRunspacePool01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-159">RemoteRunspacePool01</span></span>

<span data-ttu-id="e1cbf-160">リモート実行空間プールの構築方法とそのプールを使用して複数のコマンドを同時に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-160">Shows how to construct a remote runspace pool and how to run multiple commands concurrently by using this pool.</span></span>

### <a name="serialization01"></a><span data-ttu-id="e1cbf-161">Serialization01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-161">Serialization01</span></span>

<span data-ttu-id="e1cbf-162">既存の .NET クラスを見て、そのクラスで選択されているパブリック プロパティからの情報がシリアル化/逆シリアル化全体で維持されていることを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-162">Shows how to look at an existing .NET class and make sure that information from selected public properties of this class is preserved across serialization/deserialization.</span></span>

### <a name="serialization02"></a><span data-ttu-id="e1cbf-163">Serialization02</span><span class="sxs-lookup"><span data-stu-id="e1cbf-163">Serialization02</span></span>

<span data-ttu-id="e1cbf-164">既存の .NET クラスを見て、そのクラスのインスタンスからの情報がクラスのパブリック プロパティで利用できないとき、その情報がシリアル化/シリアル化解除全体で維持されていることを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-164">Shows how to look at an existing .NET class and make sure that information from instance of this class is preserved across serialization/deserialization when the information is not available in public properties of the class.</span></span>

### <a name="serialization03"></a><span data-ttu-id="e1cbf-165">Serialization03</span><span class="sxs-lookup"><span data-stu-id="e1cbf-165">Serialization03</span></span>

<span data-ttu-id="e1cbf-166">既存の .NET クラスを見て、そのクラスのインスタンスと派生クラスのインスタンスがライブ .NET オブジェクトに逆シリアル化 (リハイドレート) されていることを確認する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-166">Shows how to look at an existing .NET class and make sure that instances of this class and of derived classes are deserialized (rehydrated) into live .NET objects.</span></span>

## <a name="event-samples"></a><span data-ttu-id="e1cbf-167">イベントのサンプル</span><span class="sxs-lookup"><span data-stu-id="e1cbf-167">Event samples</span></span>

### <a name="event01"></a><span data-ttu-id="e1cbf-168">Event01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-168">Event01</span></span>

<span data-ttu-id="e1cbf-169">ObjectEventRegistrationBase から派生させることでイベント登録のコマンドレットを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-169">Shows how to create a cmdlet for event registration by deriving from ObjectEventRegistrationBase.</span></span>

### <a name="event02"></a><span data-ttu-id="e1cbf-170">Event02</span><span class="sxs-lookup"><span data-stu-id="e1cbf-170">Event02</span></span>

<span data-ttu-id="e1cbf-171">リモート コンピューターで生成された Windows PowerShell イベントの通知を受信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-171">Shows how to shows how to receive notifications of Windows PowerShell events that are generated on remote computers.</span></span>
<span data-ttu-id="e1cbf-172">[Runspace](/dotnet/api/system.management.automation.runspaces.runspace) クラスで公開された PSEventReceived イベントを使用します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-172">It uses the PSEventReceived event exposed through the [Runspace](/dotnet/api/system.management.automation.runspaces.runspace) class.</span></span>

## <a name="hosting-application-samples"></a><span data-ttu-id="e1cbf-173">アプリケーションのホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="e1cbf-173">Hosting application samples</span></span>

### <a name="runspace01"></a><span data-ttu-id="e1cbf-174">Runspace01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-174">Runspace01</span></span>

<span data-ttu-id="e1cbf-175">[PowerShell](/dotnet/api/system.management.automation.powershell) クラスを使用し、[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-175">Shows how to use the [PowerShell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet synchronously.</span></span>
<span data-ttu-id="e1cbf-176">[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットは、ローカル コンピューターで実行されているプロセスごとに [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-176">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) objects for each process running on the local computer.</span></span>

### <a name="runspace02"></a><span data-ttu-id="e1cbf-177">Runspace02</span><span class="sxs-lookup"><span data-stu-id="e1cbf-177">Runspace02</span></span>

<span data-ttu-id="e1cbf-178">[PowerShell](/dotnet/api/system.management.automation.powershell) クラスを使用し、[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットと [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) コマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-178">Shows how to use the [PowerShell](/dotnet/api/system.management.automation.powershell) class to run the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) and [Sort-Object](/powershell/module/Microsoft.PowerShell.Utility/Sort-Object) cmdlets synchronously.</span></span>
<span data-ttu-id="e1cbf-179">[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットは、ローカル コンピューターで実行されているプロセスごとに [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) オブジェクトを返します。`Sort-Object` は、[Id](https://technet.microsoft.com/library/system.diagnostics.process.id.aspx) プロパティに基づいてオブジェクトを並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-179">The [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet returns [Process](https://technet.microsoft.com/library/system.diagnostics.process.aspx) objects for each process running on the local computer, and the `Sort-Object` sorts the objects based on their [Id](https://technet.microsoft.com/library/system.diagnostics.process.id.aspx) property.</span></span>
<span data-ttu-id="e1cbf-180">これらのコマンドの結果は、[DataGridView](https://technet.microsoft.com/library/system.windows.forms.datagridview.aspx) コントロールを利用して表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-180">The results of these commands is displayed by using a [DataGridView](https://technet.microsoft.com/library/system.windows.forms.datagridview.aspx) control.</span></span>

### <a name="runspace03"></a><span data-ttu-id="e1cbf-181">Runspace03</span><span class="sxs-lookup"><span data-stu-id="e1cbf-181">Runspace03</span></span>

<span data-ttu-id="e1cbf-182">[PowerShell](/dotnet/api/system.management.automation.powershell) クラスを使用してスクリプトを同期的に実行する方法と終了しないエラーを処理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-182">Shows how to use the [PowerShell](/dotnet/api/system.management.automation.powershell) class to run a script synchronously, and how to handle non-terminating errors.</span></span>
<span data-ttu-id="e1cbf-183">このスクリプトはプロセス名の一覧を受信し、これらのプロセスを取得します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-183">The script receives a list of process names and then retrieves those processes.</span></span>
<span data-ttu-id="e1cbf-184">スクリプトの実行時に生成された終了しないエラーを含む、スクリプトの結果がコンソール ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-184">The results of the script, including any non-terminating errors that were generated when running the script, are displayed in a console window.</span></span>

### <a name="runspace04"></a><span data-ttu-id="e1cbf-185">Runspace04</span><span class="sxs-lookup"><span data-stu-id="e1cbf-185">Runspace04</span></span>

<span data-ttu-id="e1cbf-186">[PowerShell](/dotnet/api/system.management.automation.powershell) クラスを使用してコマンドを実行する方法とコマンドの実行時にスローされた終了するエラーをキャッチする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-186">Shows how to use the [PowerShell](/dotnet/api/system.management.automation.powershell) class to run commands, and how to catch terminating errors that are thrown when running the commands.</span></span>
<span data-ttu-id="e1cbf-187">2 つのコマンドが実行され、最後のコマンドには無効なパラメーターの引数が渡されます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-187">Two commands are run, and the last command is passed a parameter argument that is not valid.</span></span>
<span data-ttu-id="e1cbf-188">結果として、オブジェクトは返されず、終了するエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-188">As a result, no objects are returned and a terminating error is thrown.</span></span>

### <a name="runspace05"></a><span data-ttu-id="e1cbf-189">Runspace05</span><span class="sxs-lookup"><span data-stu-id="e1cbf-189">Runspace05</span></span>

<span data-ttu-id="e1cbf-190">実行空間が開いたとき、スナップショットのコマンドレットが利用できるように [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) オブジェクトにスナップインを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-190">Shows how to add a snap-in to an [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) object so that the cmdlet of the snap-in is available when the runspace is opened.</span></span>
<span data-ttu-id="e1cbf-191">このスナップインにより、[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用して同期的に実行される Get-Proc コマンドレット ([GetProcessSample01 サンプル](https://technet.microsoft.com/library/ff602028.aspx)により定義) が与えられます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-191">The snap-in provides a Get-Proc cmdlet (defined by the [GetProcessSample01 Sample](https://technet.microsoft.com/library/ff602028.aspx)) that is run synchronously by using a [PowerShell](/dotnet/api/system.management.automation.powershell) object.</span></span>

### <a name="runspace06"></a><span data-ttu-id="e1cbf-192">Runspace06</span><span class="sxs-lookup"><span data-stu-id="e1cbf-192">Runspace06</span></span>

<span data-ttu-id="e1cbf-193">実行空間が開いたとき、モジュールが読み込まれるように [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) オブジェクトにモジュールを追加する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-193">Shows how to add a module to an [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) object so that the module is loaded when the runspace is opened.</span></span>
<span data-ttu-id="e1cbf-194">このモジュールにより、[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用して同期的に実行される Get-Proc コマンドレット ([GetProcessSample02 サンプル](https://technet.microsoft.com/library/ff602027.aspx)により定義) が与えられます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-194">The module provides a Get-Proc cmdlet (defined by the [GetProcessSample02 Sample](https://technet.microsoft.com/library/ff602027.aspx)) that is run synchronously by using a [PowerShell](/dotnet/api/system.management.automation.powershell) object.</span></span>

### <a name="runspace07"></a><span data-ttu-id="e1cbf-195">Runspace07</span><span class="sxs-lookup"><span data-stu-id="e1cbf-195">Runspace07</span></span>

<span data-ttu-id="e1cbf-196">実行空間を作成し、その実行空間を使用し、[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用して 2 つのコマンドレットを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-196">Shows how to create a runspace, and then use that runspace to run two cmdlets synchronously by using a [PowerShell](/dotnet/api/system.management.automation.powershell) object.</span></span>

### <a name="runspace08"></a><span data-ttu-id="e1cbf-197">Runspace08</span><span class="sxs-lookup"><span data-stu-id="e1cbf-197">Runspace08</span></span>

<span data-ttu-id="e1cbf-198">[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトのパイプラインにコマンドと引数を追加する方法とコマンドを同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-198">Shows how to add commands and arguments to the pipeline of a [PowerShell](/dotnet/api/system.management.automation.powershell) object and how to run the commands synchronously.</span></span>

### <a name="runspace09"></a><span data-ttu-id="e1cbf-199">Runspace09</span><span class="sxs-lookup"><span data-stu-id="e1cbf-199">Runspace09</span></span>

<span data-ttu-id="e1cbf-200">[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトのパイプラインにスクリプトを追加する方法とそのスクリプトを非同期的に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-200">Shows how to add a script to the pipeline of a [PowerShell](/dotnet/api/system.management.automation.powershell) object and how to run the script asynchronously.</span></span>
<span data-ttu-id="e1cbf-201">イベントはスクリプトの出力を処理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-201">Events are used to handle the output of the script.</span></span>

### <a name="runspace10"></a><span data-ttu-id="e1cbf-202">Runspace10</span><span class="sxs-lookup"><span data-stu-id="e1cbf-202">Runspace10</span></span>

<span data-ttu-id="e1cbf-203">既定の最初のセッション状態を作成する方法、コマンドレットを [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) に追加する方法、最初のセッション状態を使用する実行空間を作成する方法、[PowerShell](/dotnet/api/system.management.automation.powershell) オブジェクトを使用してコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-203">Shows how to create a default initial session state, how to add a cmdlet to the [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate), how to create a runspace that uses the initial session state, and how to run the command by using a [PowerShell](/dotnet/api/system.management.automation.powershell) object.</span></span>

### <a name="runspace11"></a><span data-ttu-id="e1cbf-204">Runspace11</span><span class="sxs-lookup"><span data-stu-id="e1cbf-204">Runspace11</span></span>

<span data-ttu-id="e1cbf-205">[ProxyCommand](/dotnet/api/system.management.automation.proxycommand) クラスを使用し、既存のコマンドレットを呼び出すが、利用できるパラメーターのセットを制約するプロキシ コマンドを作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-205">Shows how to use the [ProxyCommand](/dotnet/api/system.management.automation.proxycommand) class to create a proxy command that calls an existing cmdlet, but restricts the set of available parameters.</span></span>
<span data-ttu-id="e1cbf-206">このプロキシ コマンドは、制約付き実行空間の作成に使用される最初のセッション状態に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-206">The proxy command is then added to an initial session state that is used to create a constrained runspace.</span></span>
<span data-ttu-id="e1cbf-207">つまり、ユーザーはプロキシ コマンドを使用しないとコマンドレットの機能にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-207">This means that the user can access the functionality of the cmdlet only through the proxy command.</span></span>

### <a name="powershell01"></a><span data-ttu-id="e1cbf-208">PowerShell01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-208">PowerShell01</span></span>

<span data-ttu-id="e1cbf-209">[InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) オブジェクトを使用し、制約のある実行空間を作成する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-209">Shows how to create a constrained runspace using an [InitialSessionState](/dotnet/api/system.management.automation.runspaces.initialsessionstate) object.</span></span>

### <a name="powershell02"></a><span data-ttu-id="e1cbf-210">PowerShell02</span><span class="sxs-lookup"><span data-stu-id="e1cbf-210">PowerShell02</span></span>

<span data-ttu-id="e1cbf-211">実行空間プールを使用し、複数のコマンドを同時に実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-211">Shows how to use a runspace pool to run multiple commands concurrently.</span></span>

## <a name="host-samples"></a><span data-ttu-id="e1cbf-212">ホストのサンプル</span><span class="sxs-lookup"><span data-stu-id="e1cbf-212">Host samples</span></span>

### <a name="host01"></a><span data-ttu-id="e1cbf-213">Host01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-213">Host01</span></span>

<span data-ttu-id="e1cbf-214">カスタム ホストを使用するホスト アプリケーションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-214">Shows how to implement a host application that uses a custom host.</span></span>
<span data-ttu-id="e1cbf-215">このサンプルでは、カスタム ホストを使用する実行空間が作成され、その後 [PowerShell](/dotnet/api/system.management.automation.powershell) API を使用して "exit" を呼び出すスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-215">In this sample a runspace is created that uses the custom host, and then the [PowerShell](/dotnet/api/system.management.automation.powershell) API is used to run a script that calls "exit".</span></span>
<span data-ttu-id="e1cbf-216">ホスト アプリケーションはスクリプトの出力を確認し、結果を印刷します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-216">The host application then looks at the output of the script and prints out the results.</span></span>

### <a name="host02"></a><span data-ttu-id="e1cbf-217">Host02</span><span class="sxs-lookup"><span data-stu-id="e1cbf-217">Host02</span></span>

<span data-ttu-id="e1cbf-218">カスタム ホストの実装と共に Windows PowerShell ランタイムを使用するホスト アプリケーションを記述する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-218">Shows how to write a host application that uses the Windows PowerShell runtime along with a custom host implementation.</span></span>
<span data-ttu-id="e1cbf-219">ホスト アプリケーションはホストのカルチャをドイツ語に設定し、[Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) コマンドレットを実行して、pwrsh.exe を使用して確認できるものと同じ結果を表示し、最新のデータと時刻をドイツ語で印刷します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-219">The host application sets the host culture to German, runs the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet and displays the results as you would see them by using pwrsh.exe, and then prints out the current data and time in German.</span></span>

### <a name="host03"></a><span data-ttu-id="e1cbf-220">Host03</span><span class="sxs-lookup"><span data-stu-id="e1cbf-220">Host03</span></span>

<span data-ttu-id="e1cbf-221">コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-221">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>

### <a name="host04"></a><span data-ttu-id="e1cbf-222">Host04</span><span class="sxs-lookup"><span data-stu-id="e1cbf-222">Host04</span></span>

<span data-ttu-id="e1cbf-223">コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-223">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="e1cbf-224">このホスト アプリケーションでは、複数選択を指定するための確認メッセージを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-224">This host application also supports displaying prompts that allow the user to specify multiple choices.</span></span>

### <a name="host05"></a><span data-ttu-id="e1cbf-225">Host05</span><span class="sxs-lookup"><span data-stu-id="e1cbf-225">Host05</span></span>

<span data-ttu-id="e1cbf-226">コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-226">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="e1cbf-227">このホスト アプリケーションでは、[Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) コマンドレットと [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) コマンドレットを使用してリモート コンピューターを呼び出すこともできます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-227">This host application also supports calls to remote computers by using the [Enter-PsSession](/powershell/module/Microsoft.PowerShell.Core/Enter-PSSession) and [Exit-PsSession](/powershell/module/Microsoft.PowerShell.Core/Exit-PSSession) cmdlets.</span></span>

### <a name="host06"></a><span data-ttu-id="e1cbf-228">Host06</span><span class="sxs-lookup"><span data-stu-id="e1cbf-228">Host06</span></span>

<span data-ttu-id="e1cbf-229">コマンドラインからコマンドを読み取ってコマンドを実行し、結果をコンソールに表示する対話型コンソール ベースのホスト アプリケーションを構築する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-229">Shows how to build an interactive console-based host application that reads commands from the command line, executes the commands, and then displays the results to the console.</span></span>
<span data-ttu-id="e1cbf-230">さらに、このサンプルでは、トークナイザー API を使用して、ユーザーが入力したテキストの色を指定します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-230">In addition, this sample uses the Tokenizer APIs to specify the color of the text that is entered by the user.</span></span>

## <a name="provider-samples"></a><span data-ttu-id="e1cbf-231">プロバイダーのサンプル</span><span class="sxs-lookup"><span data-stu-id="e1cbf-231">Provider samples</span></span>

### <a name="accessdbprovidersample01"></a><span data-ttu-id="e1cbf-232">AccessDBProviderSample01</span><span class="sxs-lookup"><span data-stu-id="e1cbf-232">AccessDBProviderSample01</span></span>

<span data-ttu-id="e1cbf-233">[CmdletProvider](/dotnet/api/system.management.automation.provider.cmdletprovider) クラスから直接派生するプロバイダー クラスの宣言方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-233">Shows how to declare a provider class that derives directly from the [CmdletProvider](/dotnet/api/system.management.automation.provider.cmdletprovider) class.</span></span>
<span data-ttu-id="e1cbf-234">すべてを網羅しておく目的でここに含めておきます。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-234">It is included here only for completeness.</span></span>

### <a name="accessdbprovidersample02"></a><span data-ttu-id="e1cbf-235">AccessDBProviderSample02</span><span class="sxs-lookup"><span data-stu-id="e1cbf-235">AccessDBProviderSample02</span></span>

<span data-ttu-id="e1cbf-236">`New-PSDrive` コマンドレットと `Remove-PSDrive` コマンドレットを呼び出すために [NewDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.newdrive) メソッドと [RemoveDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.removedrive) メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-236">Shows how to overwrite the [NewDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.newdrive) and [RemoveDrive](/dotnet/api/system.management.automation.provider.drivecmdletprovider.removedrive) methods to support calls to the `New-PSDrive` and `Remove-PSDrive` cmdlets.</span></span>
<span data-ttu-id="e1cbf-237">このサンプルのプロバイダー クラスは [DriveCmdletProvider](/dotnet/api/system.management.automation.provider.drivecmdletprovider) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-237">The provider class in this sample derives from the [DriveCmdletProvider](/dotnet/api/system.management.automation.provider.drivecmdletprovider) class.</span></span>

### <a name="accessdbprovidersample03"></a><span data-ttu-id="e1cbf-238">AccessDBProviderSample03</span><span class="sxs-lookup"><span data-stu-id="e1cbf-238">AccessDBProviderSample03</span></span>

<span data-ttu-id="e1cbf-239">`Get-Item` コマンドレットと `Set-Item` コマンドレットを呼び出すために [GetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.getitem) メソッドと [SetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.setitem) メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-239">Shows how to overwrite the [GetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.getitem) and [SetItem](/dotnet/api/system.management.automation.provider.itemcmdletprovider.setitem) methods to support calls to the `Get-Item` and `Set-Item` cmdlets.</span></span>
<span data-ttu-id="e1cbf-240">このサンプルのプロバイダー クラスは [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-240">The provider class in this sample derives from the [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider) class.</span></span>

### <a name="accessdbprovidersample04"></a><span data-ttu-id="e1cbf-241">AccessDBProviderSample04</span><span class="sxs-lookup"><span data-stu-id="e1cbf-241">AccessDBProviderSample04</span></span>

<span data-ttu-id="e1cbf-242">`Copy-Item`、`Get-ChildItem`、`New-Item`、`Remove-Item` コマンドレットを呼び出すためにコンテナー メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-242">Shows how to overwrite container methods to support calls to the `Copy-Item`, `Get-ChildItem`, `New-Item`, and `Remove-Item` cmdlets.</span></span>
<span data-ttu-id="e1cbf-243">これらのメソッドは、データ ストアにコンテナーであるアイテムが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-243">These methods should be implemented when the data store contains items that are containers.</span></span>
<span data-ttu-id="e1cbf-244">コンテナーは、共通の親項目の子項目のグループです。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-244">A container is a group of child items under a common parent item.</span></span>
<span data-ttu-id="e1cbf-245">このサンプルのプロバイダー クラスは [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-245">The provider class in this sample derives from the [ItemCmdletProvider](/dotnet/api/system.management.automation.provider.itemcmdletprovider) class.</span></span>

### <a name="accessdbprovidersample05"></a><span data-ttu-id="e1cbf-246">AccessDBProviderSample05</span><span class="sxs-lookup"><span data-stu-id="e1cbf-246">AccessDBProviderSample05</span></span>

<span data-ttu-id="e1cbf-247">`Move-Item` コマンドレットと `Join-Path` コマンドレットを呼び出すためにコンテナー メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-247">Shows how to overwrite container methods to support calls to the `Move-Item` and `Join-Path` cmdlets.</span></span>
<span data-ttu-id="e1cbf-248">これらのメソッドは、ユーザーがコンテナー内で項目を移動する必要があり、データ ストアに入れ子状態のコンテナーが含まれる場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-248">These methods should be implemented when the user needs to move items within a container and if the data store contains nested containers.</span></span>
<span data-ttu-id="e1cbf-249">このサンプルのプロバイダー クラスは [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) クラスから派生します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-249">The provider class in this sample derives from the [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) class.</span></span>

### <a name="accessdbprovidersample06"></a><span data-ttu-id="e1cbf-250">AccessDBProviderSample06</span><span class="sxs-lookup"><span data-stu-id="e1cbf-250">AccessDBProviderSample06</span></span>

<span data-ttu-id="e1cbf-251">`Clear-Content`、`Get-Content`、`Set-Content` コマンドレットを呼び出すためにコンテンツ メソッドを上書きする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-251">Shows how to overwrite content methods to support calls to the `Clear-Content`, `Get-Content`, and `Set-Content` cmdlets.</span></span>
<span data-ttu-id="e1cbf-252">これらのメソッドは、ユーザーがデータ ストア内の項目のコンテンツを管理する必要がある場合に実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-252">These methods should be implemented when the user needs to manage the content of the items in the data store.</span></span>
<span data-ttu-id="e1cbf-253">このサンプルのプロバイダー クラスは [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) クラスから派生し、[IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) インターフェイスを実装します。</span><span class="sxs-lookup"><span data-stu-id="e1cbf-253">The provider class in this sample derives from the [NavigationCmdletProvider](/dotnet/api/system.management.automation.provider.navigationcmdletprovider) class, and it implements the [IContentCmdletProvider](/dotnet/api/system.management.automation.provider.icontentcmdletprovider) interface.</span></span>