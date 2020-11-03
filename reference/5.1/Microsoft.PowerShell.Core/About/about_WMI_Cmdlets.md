---
description: Windows Management Instrumentation (WMI) と Windows PowerShell の背景情報を提供します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_WMI_Cmdlets
ms.openlocfilehash: c2099c005cedf64e9621d66d6757419320c9b43e
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223192"
---
# <a name="about-wmi-cmdlets"></a><span data-ttu-id="b93a4-104">WMI コマンドレットの概要</span><span class="sxs-lookup"><span data-stu-id="b93a4-104">About WMI Cmdlets</span></span>

## <a name="short-description"></a><span data-ttu-id="b93a4-105">概要</span><span class="sxs-lookup"><span data-stu-id="b93a4-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="b93a4-106">Windows Management Instrumentation (WMI) と Windows PowerShell の背景情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-106">Provides background information about Windows Management Instrumentation (WMI) and Windows PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b93a4-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="b93a4-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="b93a4-108">このトピックでは、WMI テクノロジ、Windows PowerShell 用の WMI コマンドレット、WMI ベースのリモート処理、WMI アクセラレータ、および WMI のトラブルシューティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-108">This topic provides information about WMI technology, the WMI cmdlets for Windows PowerShell, WMI-based remoting, WMI accelerators, and WMI troubleshooting.</span></span> <span data-ttu-id="b93a4-109">このトピックでは、WMI に関する詳細情報へのリンクも示します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-109">This topic also provides links to more information about WMI.</span></span>

### <a name="about-wmi"></a><span data-ttu-id="b93a4-110">WMI について</span><span class="sxs-lookup"><span data-stu-id="b93a4-110">ABOUT WMI</span></span>

<span data-ttu-id="b93a4-111">Windows Management Instrumentation (WMI) は、Web-Based Enterprise Management (WBEM) を Microsoft が実装したものです。WBEM とは、企業環境で管理情報にアクセスするための標準技術を確立する業界の取り組みの 1 つです。</span><span class="sxs-lookup"><span data-stu-id="b93a4-111">Windows Management Instrumentation (WMI) is the Microsoft implementation of Web-Based Enterprise Management (WBEM), which is an industry initiative to develop a standard technology for accessing management information in an enterprise environment.</span></span> <span data-ttu-id="b93a4-112">WMI では、Common Information Model (CIM) 業界規格を使用して、システム、アプリケーション、ネットワーク、デバイスなどのマネージド コンポーネントを表現します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-112">WMI uses the Common Information Model (CIM) industry standard to represent systems, applications, networks, devices, and other managed components.</span></span> <span data-ttu-id="b93a4-113">CIM は、分散管理タスク フォース (DMTF) によって開発され、管理されています。</span><span class="sxs-lookup"><span data-stu-id="b93a4-113">CIM is developed and maintained by the Distributed Management Task Force (DMTF).</span></span> <span data-ttu-id="b93a4-114">WMI を使用して、ローカルコンピューターとリモートコンピューターの両方を管理できます。</span><span class="sxs-lookup"><span data-stu-id="b93a4-114">You can use WMI to manage both local and remote computers.</span></span> <span data-ttu-id="b93a4-115">たとえば、WMI を使用して次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b93a4-115">For example, you can use WMI to do the following:</span></span>

- <span data-ttu-id="b93a4-116">リモートコンピューター上のプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-116">Start a process on a remote computer.</span></span>
- <span data-ttu-id="b93a4-117">リモートでコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-117">Restart a computer remotely.</span></span>
- <span data-ttu-id="b93a4-118">ローカルコンピューターまたはリモートコンピューターにインストールされているアプリケーションの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-118">Get a list of the applications that are installed on a local or remote computer.</span></span>
- <span data-ttu-id="b93a4-119">ローカルコンピューターまたはリモートコンピューター上の Windows イベントログに対してクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-119">Query the Windows event logs on a local or remote computer.</span></span>

### <a name="the-wmi-cmdlets-for-windows-powershell"></a><span data-ttu-id="b93a4-120">WINDOWS POWERSHELL 用の WMI コマンドレット</span><span class="sxs-lookup"><span data-stu-id="b93a4-120">THE WMI CMDLETS FOR WINDOWS POWERSHELL</span></span>

<span data-ttu-id="b93a4-121">Windows PowerShell は、既定で Windows PowerShell で使用できる一連のコマンドレットを使用して WMI 機能を実装します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-121">Windows PowerShell implements WMI functionality through a set of cmdlets that are available in Windows PowerShell by default.</span></span> <span data-ttu-id="b93a4-122">これらのコマンドレットを使用して、ローカルコンピューターとリモートコンピューターを管理するために必要なエンドツーエンドのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b93a4-122">You can use these cmdlets to complete the end-to-end tasks necessary to manage local and remote computers.</span></span>

<span data-ttu-id="b93a4-123">次の WMI コマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b93a4-123">The following WMI cmdlets are included.</span></span>

|<span data-ttu-id="b93a4-124">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="b93a4-124">Cmdlet</span></span>           |<span data-ttu-id="b93a4-125">説明</span><span class="sxs-lookup"><span data-stu-id="b93a4-125">Description</span></span>                                   |
|-----------------|----------------------------------------------|
|<span data-ttu-id="b93a4-126">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="b93a4-126">Get-WmiObject</span></span>    |<span data-ttu-id="b93a4-127">WMI クラスまたは情報のインスタンスを取得します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-127">Gets instances of WMI classes or information</span></span>  |
|                 |<span data-ttu-id="b93a4-128">使用可能なクラスについて。</span><span class="sxs-lookup"><span data-stu-id="b93a4-128">about the available classes.</span></span>                  |
|<span data-ttu-id="b93a4-129">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="b93a4-129">Invoke-WmiMethod</span></span> |<span data-ttu-id="b93a4-130">WMI メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-130">Calls WMI methods.</span></span>                            |
|<span data-ttu-id="b93a4-131">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="b93a4-131">Register-WmiEvent</span></span>|<span data-ttu-id="b93a4-132">WMI イベントをサブスクライブします。</span><span class="sxs-lookup"><span data-stu-id="b93a4-132">Subscribes to a WMI event.</span></span>                    |
|<span data-ttu-id="b93a4-133">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="b93a4-133">Remove-WmiObject</span></span> |<span data-ttu-id="b93a4-134">WMI クラスおよびインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-134">Deletes WMI classes and instances.</span></span>            |
|<span data-ttu-id="b93a4-135">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="b93a4-135">Set-WmiInstance</span></span>  |<span data-ttu-id="b93a4-136">WMI クラスのインスタンスを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-136">Creates or modifies instances of WMI classes.</span></span> |

### <a name="sample-commands"></a><span data-ttu-id="b93a4-137">サンプルコマンド</span><span class="sxs-lookup"><span data-stu-id="b93a4-137">SAMPLE COMMANDS</span></span>
<span data-ttu-id="b93a4-138">次のコマンドは、ローカルコンピューターの BIOS 情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-138">The following command displays the BIOS information for the local computer.</span></span>

```powershell
C:\PS> get-wmiobject win32_bios | format-list *
```

<span data-ttu-id="b93a4-139">次のコマンドは、3台のリモートコンピューターの WinRM サービスに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-139">The following command displays information about the WinRM service for three remote computers.</span></span>

```powershell
$wql = "select * from win32_service where name='WinRM'"
get-wmiobject -query $wql -computername server01, server01, server03
```

<span data-ttu-id="b93a4-140">次のより複雑なコマンドは、プログラムのすべてのインスタンスを終了します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-140">The following more complex command exits all instances of a program.</span></span>

```powershell
C:\PS> notepad.exe
C:\PS> $wql = "select * from win32_process where name='notepad.exe'"
C:\PS> $np = get-wmiobject -query $wql
C:\PS> $np | remove-wmiobject
```

### <a name="wmi-based-remoting"></a><span data-ttu-id="b93a4-141">WMI ベースのリモート処理</span><span class="sxs-lookup"><span data-stu-id="b93a4-141">WMI-BASED REMOTING</span></span>

<span data-ttu-id="b93a4-142">WMI を使用してローカルシステムを管理する機能は便利ですが、WMI を強力な管理ツールにするリモート処理機能です。</span><span class="sxs-lookup"><span data-stu-id="b93a4-142">While the ability to manage a local system through WMI is useful, it is the remoting capabilities that make WMI a powerful administrative tool.</span></span> <span data-ttu-id="b93a4-143">WMI は、Microsoft の分散コンポーネントオブジェクトモデル (DCOM) を使用して、システムへの接続と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="b93a4-143">WMI uses Microsoft's Distributed Component Object Model (DCOM) to connect to and manage systems.</span></span> <span data-ttu-id="b93a4-144">場合によっては、DCOM 接続を許可するようにシステムを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b93a4-144">You might have to configure some systems to allow DCOM connections.</span></span>
<span data-ttu-id="b93a4-145">ファイアウォールの設定とロックダウンされた DCOM のアクセス許可によって、システムをリモートで管理する WMI の機能がブロックされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b93a4-145">Firewall settings and locked-down DCOM permissions can block WMI's ability to remotely manage systems.</span></span>

### <a name="wmi-type-accelerators"></a><span data-ttu-id="b93a4-146">WMI の種類のアクセラレータ</span><span class="sxs-lookup"><span data-stu-id="b93a4-146">WMI TYPE ACCELERATORS</span></span>

<span data-ttu-id="b93a4-147">Windows PowerShell には、WMI の種類のアクセラレータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b93a4-147">Windows PowerShell includes WMI type accelerators.</span></span> <span data-ttu-id="b93a4-148">これらの WMI 型アクセラレータ (ショートカット) を使用すると、非型のアクセラレータを使用する場合よりも、WMI オブジェクトに対するより直接的なアクセスが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b93a4-148">These WMI type accelerators (shortcuts) allow more direct access to a WMI objects than a non-type accelerator approach would allow.</span></span>

<span data-ttu-id="b93a4-149">WMI では、次の種類のアクセラレータがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b93a4-149">The following type accelerators are supported with WMI:</span></span>

<span data-ttu-id="b93a4-150">[WMISEARCHER]-WMI オブジェクトを検索するためのショートカットです。</span><span class="sxs-lookup"><span data-stu-id="b93a4-150">[WMISEARCHER] - A shortcut for searching for WMI objects.</span></span>

<span data-ttu-id="b93a4-151">[WMICLASS]-クラスの静的プロパティおよびメソッドにアクセスするためのショートカットです。</span><span class="sxs-lookup"><span data-stu-id="b93a4-151">[WMICLASS] - A shortcut for accessing the static properties and methods of a class.</span></span>

<span data-ttu-id="b93a4-152">[WMI]-クラスの単一のインスタンスを取得するためのショートカット。</span><span class="sxs-lookup"><span data-stu-id="b93a4-152">[WMI] - A shortcut for getting a single instance of a class.</span></span>

<span data-ttu-id="b93a4-153">[WMISEARCHER] は、ManagementObjectSearcher の型アクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="b93a4-153">[WMISEARCHER] is a type accelerator for a ManagementObjectSearcher.</span></span> <span data-ttu-id="b93a4-154">文字列コンストラクターを使用してサーチャーを作成することができます。これは、で GET () を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b93a4-154">It can take a string constructor to create a searcher that you can then do a GET() on.</span></span>

<span data-ttu-id="b93a4-155">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-155">For example:</span></span>

```powershell
PS> $s = [WmiSearcher]'Select * from Win32_Process where Handlecount > 1000'
PS> $s.Get() |sort handlecount |ft handlecount,__path,name -auto

count  __PATH                                              name
-----  ------                                              ----
1105   \\SERVER01\root\cimv2:Win32_Process.Handle="3724"   PowerShell...
1132   \\SERVER01\root\cimv2:Win32_Process.Handle="1388"   winlogon.exe
1495   \\SERVER01\root\cimv2:Win32_Process.Handle="2852"   iexplore.exe
1699   \\SERVER01\root\cimv2:Win32_Process.Handle="1204"   OUTLOOK.EXE
1719   \\SERVER01\root\cimv2:Win32_Process.Handle="1912"   iexplore.exe
2579   \\SERVER01\root\cimv2:Win32_Process.Handle="1768"   svchost.exe
```

<span data-ttu-id="b93a4-156">[WMICLASS] は ManagementClass の型アクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="b93a4-156">[WMICLASS] is a type accelerator for ManagementClass.</span></span> <span data-ttu-id="b93a4-157">これには、WMI クラスへのローカルまたは絶対 WMI パスを受け取り、そのクラスにバインドされたオブジェクトを返す文字列コンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="b93a4-157">This has a string constructor that takes a local or absolute WMI path to a WMI class and returns an object that is bound to that class.</span></span>

<span data-ttu-id="b93a4-158">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-158">For example:</span></span>

```powershell
PS> $c = [WMICLASS]"root\cimv2:WIn32_Process"
PS> $c |fl *
Name             : Win32_Process
__GENUS          : 1
__CLASS          : Win32_Process
__SUPERCLASS     : CIM_Process
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Process
__PROPERTY_COUNT : 45
__DERIVATION     : {CIM_Process, CIM_LogicalElement,
                   CIM_ManagedSystemElement}
__SERVER         : SERVER01
__NAMESPACE      : ROOT\cimv2
__PATH           : \\SERVER01\ROOT\cimv2:Win32_Process
```

<span data-ttu-id="b93a4-159">[WMI] は System.management.managementobject の型アクセラレータです。</span><span class="sxs-lookup"><span data-stu-id="b93a4-159">[WMI] is a type accelerator for ManagementObject.</span></span> <span data-ttu-id="b93a4-160">これには、WMI インスタンスに対してローカルまたは絶対の WMI パスを取得し、そのインスタンスにバインドされたオブジェクトを返す文字列コンストラクターがあります。</span><span class="sxs-lookup"><span data-stu-id="b93a4-160">This has a string constructor that takes a local or absolute WMI path to a WMI instance and returns an object that is bound to that instance.</span></span>

<span data-ttu-id="b93a4-161">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-161">For example:</span></span>

```powershell
PS> $p = [WMI]'\\SERVER01\root\cimv2:Win32_Process.Handle="1204"'
PS> $p.Name
OUTLOOK.EXE
```

### <a name="wmi-troubleshooting"></a><span data-ttu-id="b93a4-162">WMI のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b93a4-162">WMI TROUBLESHOOTING</span></span>

<span data-ttu-id="b93a4-163">次の問題は、リモートコンピューターに接続しようとすると発生する可能性がある最も一般的な問題です。</span><span class="sxs-lookup"><span data-stu-id="b93a4-163">The following problems are the most common problems that might occur when you try to connect to a remote computer.</span></span>

<span data-ttu-id="b93a4-164">問題 1: リモートコンピューターがオンラインではありません。</span><span class="sxs-lookup"><span data-stu-id="b93a4-164">Problem 1: The remote computer is not online.</span></span>

<span data-ttu-id="b93a4-165">コンピューターがオフラインの場合は、WMI を使用してコンピューターに接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="b93a4-165">If a computer is offline, you will not be able to connect to it by using WMI.</span></span>
<span data-ttu-id="b93a4-166">次のエラー メッセージを受け取ることがあります。</span><span class="sxs-lookup"><span data-stu-id="b93a4-166">You may receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

<span data-ttu-id="b93a4-167">このエラーメッセージが表示された場合は、コンピューターがオンラインになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-167">If you receive this error message, verify that the computer is online.</span></span> <span data-ttu-id="b93a4-168">リモートコンピューターに対して ping を実行します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-168">Try to ping the remote computer.</span></span>

<span data-ttu-id="b93a4-169">問題 2: リモートコンピューターに対するローカル管理者権限がありません。</span><span class="sxs-lookup"><span data-stu-id="b93a4-169">Problem 2: You do not have local administrator rights on the remote computer.</span></span>

<span data-ttu-id="b93a4-170">WMI をリモートで使用するには、リモートコンピューターのローカル管理者権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b93a4-170">To use WMI remotely, you must have local administrator rights on the remote computer.</span></span> <span data-ttu-id="b93a4-171">そうしないと、そのコンピューターへのアクセスが拒否されます。</span><span class="sxs-lookup"><span data-stu-id="b93a4-171">If you do not, access to that computer will be denied.</span></span>

<span data-ttu-id="b93a4-172">名前空間のセキュリティを確認するには:</span><span class="sxs-lookup"><span data-stu-id="b93a4-172">To verify namespace security:</span></span>

1. <span data-ttu-id="b93a4-173">[スタート] ボタンをクリックし、[マイコンピューター] を右クリックして、[管理] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b93a4-173">Click Start, right-click My Computer, and then click Manage.</span></span>
2. <span data-ttu-id="b93a4-174">[コンピューターの管理] で、[サービスとアプリケーション] を展開し、[WMI コントロール] を右クリックして、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b93a4-174">In Computer Management, expand Services and Applications, right-click WMI Control, and then click Properties.</span></span>
3. <span data-ttu-id="b93a4-175">[WMI コントロールのプロパティ] ダイアログボックスで、[セキュリティ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b93a4-175">In the WMI Control Properties dialog box, click  the Security tab.</span></span>

<span data-ttu-id="b93a4-176">問題 3: ファイアウォールがリモートコンピューターへのアクセスをブロックしている。</span><span class="sxs-lookup"><span data-stu-id="b93a4-176">Problem 3: A firewall is blocking access to the remote computer.</span></span>

<span data-ttu-id="b93a4-177">WMI は、DCOM (Distributed COM) および RPC (リモートプロシージャコール) プロトコルを使用してネットワークをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="b93a4-177">WMI uses the DCOM (Distributed COM) and RPC (Remote Procedure Call) protocols to traverse the network.</span></span> <span data-ttu-id="b93a4-178">既定では、多くのファイアウォールは、DCOM および RPC トラフィックをブロックします。</span><span class="sxs-lookup"><span data-stu-id="b93a4-178">By default, many firewalls block DCOM and RPC traffic.</span></span> <span data-ttu-id="b93a4-179">ファイアウォールでこれらのプロトコルがブロックされている場合、接続は失敗します。</span><span class="sxs-lookup"><span data-stu-id="b93a4-179">If your firewall is blocking these protocols, your connection will fail.</span></span> <span data-ttu-id="b93a4-180">たとえば、Microsoft Windows XP Service Pack 2 の Windows ファイアウォールは、すべての要請されていないネットワークトラフィック (DCOM および WMI を含む) を自動的にブロックするように構成されています。</span><span class="sxs-lookup"><span data-stu-id="b93a4-180">For example, Windows Firewall in Microsoft Windows XP Service Pack 2 is configured to automatically block all unsolicited network traffic, including DCOM and WMI.</span></span> <span data-ttu-id="b93a4-181">既定の構成では、Windows ファイアウォールは着信 WMI 要求を拒否し、次のエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b93a4-181">In its default configuration, Windows Firewall rejects an incoming WMI request, and you receive the following error message:</span></span>

```
Remote server machine does not exist or is unavailable
```

## <a name="see-also"></a><span data-ttu-id="b93a4-182">関連項目</span><span class="sxs-lookup"><span data-stu-id="b93a4-182">SEE ALSO</span></span>

[<span data-ttu-id="b93a4-183">WMI について</span><span class="sxs-lookup"><span data-stu-id="b93a4-183">About WMI</span></span>](/windows/win32/wmisdk/about-wmi)

[<span data-ttu-id="b93a4-184">WMI のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b93a4-184">WMI Troubleshooting</span></span>](/windows/win32/wmisdk/wmi-troubleshooting)

[<span data-ttu-id="b93a4-185">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="b93a4-185">Get-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Get-WmiObject)

[<span data-ttu-id="b93a4-186">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="b93a4-186">Invoke-WmiMethod</span></span>](xref:Microsoft.PowerShell.Management.Invoke-WmiMethod)

[<span data-ttu-id="b93a4-187">Register-WmiEvent</span><span class="sxs-lookup"><span data-stu-id="b93a4-187">Register-WmiEvent</span></span>](xref:Microsoft.PowerShell.Management.Register-WmiEvent)

[<span data-ttu-id="b93a4-188">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="b93a4-188">Remove-WmiObject</span></span>](xref:Microsoft.PowerShell.Management.Remove-WmiObject)

[<span data-ttu-id="b93a4-189">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="b93a4-189">Set-WmiInstance</span></span>](xref:Microsoft.PowerShell.Management.Set-WmiInstance)
