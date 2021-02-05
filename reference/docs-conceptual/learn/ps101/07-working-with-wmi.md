---
title: WMI の操作
description: PowerShell には、WMI を操作するためのコマンドレットが最初から備わっています。
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 119bb3381ee55c70340da89d1c0690d84b3e70d2
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "99599282"
---
# <a name="chapter-7---working-with-wmi"></a><span data-ttu-id="e13de-103">第 7 章 - WMI の操作</span><span class="sxs-lookup"><span data-stu-id="e13de-103">Chapter 7 - Working with WMI</span></span>

## <a name="wmi-and-cim"></a><span data-ttu-id="e13de-104">WMI と CIM</span><span class="sxs-lookup"><span data-stu-id="e13de-104">WMI and CIM</span></span>

<span data-ttu-id="e13de-105">PowerShell には、Windows Management Instrumentation (WMI) など、その他のテクノロジを操作するためのコマンドレットが既定で付属しています。</span><span class="sxs-lookup"><span data-stu-id="e13de-105">PowerShell ships by default with cmdlets for working with other technologies such as Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="e13de-106">PowerShell にはネイティブな WMI コマンドレットがいくつもあり、追加のソフトウェアやモジュールをインストールする必要がありません。</span><span class="sxs-lookup"><span data-stu-id="e13de-106">There are several native WMI cmdlets that exist in PowerShell without having to install any additional software or modules.</span></span>

<span data-ttu-id="e13de-107">PowerShell には、WMI を操作するためのコマンドレットが最初から備わっています。</span><span class="sxs-lookup"><span data-stu-id="e13de-107">PowerShell has had cmdlets for working with WMI since the beginning.</span></span> <span data-ttu-id="e13de-108">PowerShell にどのような WMI コマンドレットがあるのかを特定するには、`Get-Command` を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13de-108">`Get-Command` can be used to determine what WMI cmdlets exist in PowerShell.</span></span> <span data-ttu-id="e13de-109">次の結果は、PowerShell バージョン 5.1 を実行している Windows 10 ラボ環境コンピューターからのものです。</span><span class="sxs-lookup"><span data-stu-id="e13de-109">The following results are from my Windows 10 lab environment computer that is running PowerShell version 5.1.</span></span> <span data-ttu-id="e13de-110">実行している PowerShell バージョンによっては、結果が異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e13de-110">Your results may differ depending on what PowerShell version you're running.</span></span>

```powershell
Get-Command -Noun WMI*
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Get-WmiObject                                      3.1.0.0    Microsof...
Cmdlet          Invoke-WmiMethod                                   3.1.0.0    Microsof...
Cmdlet          Register-WmiEvent                                  3.1.0.0    Microsof...
Cmdlet          Remove-WmiObject                                   3.1.0.0    Microsof...
Cmdlet          Set-WmiInstance                                    3.1.0.0    Microsof...
```

<span data-ttu-id="e13de-111">Common Information Model (CIM) コマンドレットは、PowerShell バージョン 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="e13de-111">Common Information Model (CIM) cmdlets were introduced in PowerShell version 3.0.</span></span> <span data-ttu-id="e13de-112">CIM コマンドレットは、Windows マシンと Windows 以外のマシンの両方で使用できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e13de-112">The CIM cmdlets are designed so they can be used on both Windows and non-Windows machines.</span></span> <span data-ttu-id="e13de-113">WMI コマンドレットは非推奨化されているため、古い WMI ではなく CIM コマンドレットを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e13de-113">The WMI cmdlets are deprecated so my recommendation is to use the CIM cmdlets instead of the older WMI ones.</span></span>

<span data-ttu-id="e13de-114">CIM コマンドレットはすべて、モジュール内に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e13de-114">The CIM cmdlets are all contained within a module.</span></span> <span data-ttu-id="e13de-115">CIM コマンドレットの一覧を取得するには、次の例に示すように、**Module** パラメーターを指定して `Get-Command` を使用します。</span><span class="sxs-lookup"><span data-stu-id="e13de-115">To obtain a list of the CIM cmdlets, use `Get-Command` with the **Module** parameter as shown in the following example.</span></span>

```powershell
Get-Command -Module CimCmdlets
```

```Output
CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Export-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Get-CimAssociatedInstance                          1.0.0.0    CimCmdlets
Cmdlet          Get-CimClass                                       1.0.0.0    CimCmdlets
Cmdlet          Get-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          Get-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          Import-BinaryMiLog                                 1.0.0.0    CimCmdlets
Cmdlet          Invoke-CimMethod                                   1.0.0.0    CimCmdlets
Cmdlet          New-CimInstance                                    1.0.0.0    CimCmdlets
Cmdlet          New-CimSession                                     1.0.0.0    CimCmdlets
Cmdlet          New-CimSessionOption                               1.0.0.0    CimCmdlets
Cmdlet          Register-CimIndicationEvent                        1.0.0.0    CimCmdlets
Cmdlet          Remove-CimInstance                                 1.0.0.0    CimCmdlets
Cmdlet          Remove-CimSession                                  1.0.0.0    CimCmdlets
Cmdlet          Set-CimInstance                                    1.0.0.0    CimCmdlets
```

<span data-ttu-id="e13de-116">CIM コマンドレットでは引き続き WMI を操作できます。そのため、他のユーザーが "PowerShell CIM コマンドレットを使用して WMI のクエリを実行するとき" と言っても、混乱しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e13de-116">The CIM cmdlets still allow you to work with WMI so don't be confused when someone makes the statement "When I query WMI with the PowerShell CIM cmdlets..."</span></span>

<span data-ttu-id="e13de-117">前述したように、WMI は PowerShell とは別個のテクノロジであり、ユーザーは WMI にアクセスするために CIM コマンドレットを使用しているだけです。</span><span class="sxs-lookup"><span data-stu-id="e13de-117">As I previously mentioned, WMI is a separate technology from PowerShell and you're just using the CIM cmdlets for accessing WMI.</span></span> <span data-ttu-id="e13de-118">次の例のように、WMI Query Language (WQL) を使用して WMI のクエリを実行する古い VB スクリプトが見つかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e13de-118">You may find an old VBScript that uses WMI Query Language (WQL) to query WMI such as in the following example.</span></span>

```vb
strComputer = "."
Set objWMIService = GetObject("winmgmts:" _
    & "{impersonationLevel=impersonate}!\\" & strComputer & "\root\cimv2")

Set colBIOS = objWMIService.ExecQuery _
    ("Select * from Win32_BIOS")

For each objBIOS in colBIOS
    Wscript.Echo "Manufacturer: " & objBIOS.Manufacturer
    Wscript.Echo "Name: " & objBIOS.Name
    Wscript.Echo "Serial Number: " & objBIOS.SerialNumber
    Wscript.Echo "SMBIOS Version: " & objBIOS.SMBIOSBIOSVersion
    Wscript.Echo "Version: " & objBIOS.Version
Next
```

<span data-ttu-id="e13de-119">その VB スクリプトから WQL クエリを取得して、変更することなく `Get-CimInstance` コマンドレットで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13de-119">You can take the WQL query from that VBScript and use it with the `Get-CimInstance` cmdlet without any modifications.</span></span>

```powershell
Get-CimInstance -Query 'Select * from Win32_BIOS'
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 3810-1995-1654-4615-2295-2755-89
Version           : VRTUAL - 4001628
```

<span data-ttu-id="e13de-120">これは、PowerShell で WMI のクエリを実行する通常の方法ではありません。</span><span class="sxs-lookup"><span data-stu-id="e13de-120">That's not how I typically query WMI with PowerShell.</span></span> <span data-ttu-id="e13de-121">しかし、これは問題なく使えて、既存の VB スクリプトを PowerShell に簡単に移行できます。</span><span class="sxs-lookup"><span data-stu-id="e13de-121">But it does work and allows you to easily migrate existing VBScripts to PowerShell.</span></span> <span data-ttu-id="e13de-122">WMI のクエリを実行するワンライナーの記述に取り掛かる際には、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="e13de-122">When I start out writing a one-liner to query WMI, I use the following syntax.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 3810-1995-1654-4615-2295-2755-89
Version           : VRTUAL - 4001628
```

<span data-ttu-id="e13de-123">シリアル番号だけが必要な場合は、出力を `Select-Object` にパイプ処理して、**SerialNumber** プロパティのみを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e13de-123">If I only want the serial number, I can pipe the output to `Select-Object` and specify only the **SerialNumber** property.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS | Select-Object -Property SerialNumber
```

```Output
SerialNumber
------------
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="e13de-124">既定では、使用されることがないのに背後で取得されるプロパティがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e13de-124">By default, there are several properties that are retrieved behind the scenes that are never used.</span></span>
<span data-ttu-id="e13de-125">これは、ローカル コンピューター上で WMI のクエリを実行するときにはそれほど問題にならないでしょう。</span><span class="sxs-lookup"><span data-stu-id="e13de-125">It may not matter much when querying WMI on the local computer.</span></span> <span data-ttu-id="e13de-126">しかし、リモート コンピュートに対するクエリを開始すると、その情報を返すのに追加の処理時間がかかるだけでなく、必要ない余計な情報をネットワーク経由でプルしなければならなくなります。</span><span class="sxs-lookup"><span data-stu-id="e13de-126">But once you start querying remote computers, it's not only additional processing time to return that information, but also additional unnecessary information to have to pull across the network.</span></span> <span data-ttu-id="e13de-127">`Get-CimInstance` には、取得される情報を制限する **Property** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="e13de-127">`Get-CimInstance` has a **Property** parameter that limits the information that's retrieved.</span></span> <span data-ttu-id="e13de-128">これにより、WMI へのクエリの効率が向上します。</span><span class="sxs-lookup"><span data-stu-id="e13de-128">This makes the query to WMI more efficient.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber |
Select-Object -Property SerialNumber
```

```Output
SerialNumber
------------
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="e13de-129">前の結果ではオブジェクトが返されました。</span><span class="sxs-lookup"><span data-stu-id="e13de-129">The previous results returned an object.</span></span> <span data-ttu-id="e13de-130">単純な文字列を返すには、**ExpandProperty** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e13de-130">To return a simple string, use the **ExpandProperty** parameter.</span></span>

```powershell
Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber |
Select-Object -ExpandProperty SerialNumber
```

```Output
3810-1995-1654-4615-2295-2755-89
```

<span data-ttu-id="e13de-131">単純な文字列を返すには、ピリオドを使うスタイルの構文を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e13de-131">You could also use the dotted style of syntax to return a simple string.</span></span> <span data-ttu-id="e13de-132">そうすれば `Select-Object` にパイプ処理する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="e13de-132">This eliminates the need to pipe to `Select-Object`.</span></span>

```powershell
(Get-CimInstance -ClassName Win32_BIOS -Property SerialNumber).SerialNumber
```

```Output
3810-1995-1654-4615-2295-2755-89
```

## <a name="query-remote-computers-with-the-cim-cmdlets"></a><span data-ttu-id="e13de-133">CIM コマンドレットによるリモート コンピューターへのクエリ実行</span><span class="sxs-lookup"><span data-stu-id="e13de-133">Query Remote Computers with the CIM cmdlets</span></span>

<span data-ttu-id="e13de-134">引き続き、ドメイン ユーザーであるローカル管理者として PowerShell を実行しています。</span><span class="sxs-lookup"><span data-stu-id="e13de-134">I'm still running PowerShell as a local admin who is a domain user.</span></span> <span data-ttu-id="e13de-135">`Get-CimInstance` コマンドレットを使用してリモート コンピューターから情報のクエリを実行しようとすると、アクセス拒否のエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e13de-135">When I try to query information from a remote computer using the `Get-CimInstance` cmdlet, I receive an access denied error message.</span></span>

```powershell
Get-CimInstance -ComputerName dc01 -ClassName Win32_BIOS
```

```Output
Get-CimInstance : Access is denied.
At line:1 char:1
+ Get-CimInstance -ComputerName dc01 -ClassName Win32_BIOS
+ ``````````````````````````````````````````````````````~~
    + CategoryInfo          : PermissionDenied: (root\cimv2:Win32_BIOS:String) [Get-CimI
   nstance], CimException
    + FullyQualifiedErrorId : HRESULT 0x80070005,Microsoft.Management.Infrastructure.Cim
   Cmdlets.GetCimInstanceCommand
    + PSComputerName        : dc01
```

<span data-ttu-id="e13de-136">多くのユーザーが PowerShell のセキュリティについて懸念を抱いていますが、実際のところ、PowerShell でユーザーが付与されるアクセス許可は GUI とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="e13de-136">Many people have security concerns when it comes to PowerShell, but the truth is you have exactly the same permissions in PowerShell as you do in the GUI.</span></span> <span data-ttu-id="e13de-137">それ以上でも以下でもありません。</span><span class="sxs-lookup"><span data-stu-id="e13de-137">No more and no less.</span></span> <span data-ttu-id="e13de-138">前の例の問題は、PowerShell を実行しているユーザーに、DC01 サーバーから WMI 情報のクエリを実行する権限がないことです。</span><span class="sxs-lookup"><span data-stu-id="e13de-138">The problem in the previous example is that the user running PowerShell doesn't have rights to query WMI information from the DC01 server.</span></span> <span data-ttu-id="e13de-139">`Get-CimInstance` には **Credential** パラメーターがないため、ドメイン管理者として PowerShell を再起動することができます。</span><span class="sxs-lookup"><span data-stu-id="e13de-139">I could relaunch PowerShell as a domain administrator since `Get-CimInstance` doesn't have a **Credential** parameter.</span></span> <span data-ttu-id="e13de-140">ただし、PowerShell から実行する内容がすべてドメイン管理者として実行されるため、この方法はお勧めできません。セキュリティの観点からすると、これは状況によっては危険な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e13de-140">But, trust me, that isn't a good idea because then anything that I run from PowerShell would be running as a domain admin. That could be dangerous from a security standpoint depending on the situation.</span></span>

<span data-ttu-id="e13de-141">最小限の特権の原則に従って、**Credential** パラメーター (コマンドにある場合) を使用し、コマンドごとにドメイン管理アカウントに昇格します。</span><span class="sxs-lookup"><span data-stu-id="e13de-141">Using the principle of least privilege, I elevate to my domain admin account on a per command basis using the **Credential** parameter, if a command has one.</span></span> <span data-ttu-id="e13de-142">`Get-CimInstance` には **Credential** パラメーターがないため、このシナリオの解決策は、**CimSession** を先に作成することです。</span><span class="sxs-lookup"><span data-stu-id="e13de-142">`Get-CimInstance` doesn't have a **Credential** parameter so the solution in this scenario is to create a **CimSession** first.</span></span> <span data-ttu-id="e13de-143">次に、コンピューター名の代わりに **CimSession** を使用して、リモート コンピューター上の WMI のクエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="e13de-143">Then I use the **CimSession** instead of a computer name to query WMI on the remote computer.</span></span>

```powershell
$CimSession = New-CimSession -ComputerName dc01 -Credential (Get-Credential)
```

```Output
cmdlet Get-Credential at command pipeline position 1
Supply values for the following parameters:
Credential
```

<span data-ttu-id="e13de-144">CIM セッションは、`$CimSession` という名前の変数に格納されました。</span><span class="sxs-lookup"><span data-stu-id="e13de-144">The CIM session was stored in a variable named `$CimSession`.</span></span> <span data-ttu-id="e13de-145">先に実行されるようにかっこ内で `Get-Credential` コマンドレットを指定したことにも注目してください。これで、新しいセッションが作成される前に、代替の資格情報が要求されます。</span><span class="sxs-lookup"><span data-stu-id="e13de-145">Notice that I also specified the `Get-Credential` cmdlet in parentheses so that it executes first, prompting me for alternate credentials, before creating the new session.</span></span> <span data-ttu-id="e13de-146">この章の後半で、代替の資格情報を指定する、より効率的な別の方法を紹介しますが、複雑化する前にこの基本的な概念を理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="e13de-146">I'll show you another more efficient way to specify alternate credentials later in this chapter, but it's important to understand this basic concept before making it more complicated.</span></span>

<span data-ttu-id="e13de-147">前の例で作成した CIM セッションを `Get-CimInstance` コマンドレットと共に使用して、リモート コンピューター上の WMI から BIOS 情報を照会できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="e13de-147">The CIM session created in the previous example can now be used with the `Get-CimInstance` cmdlet to query the BIOS information from WMI on the remote computer.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 0986-6980-3916-0512-6608-8243-13
Version           : VRTUAL - 4001628
PSComputerName    : dc01
```

<span data-ttu-id="e13de-148">単にコンピューター名を指定するのではなく、CIM セッションを使用することには、追加のメリットがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="e13de-148">There are several additional benefits to using CIM sessions instead of just specifying a computer name.</span></span> <span data-ttu-id="e13de-149">同じコンピューターに対して複数のクエリを実行する場合、クエリごとにコンピューター名を使用するよりも、CIM セッションを使用する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="e13de-149">When running multiple queries to the same computer, using a CIM session is more efficient than using the computer name for each query.</span></span> <span data-ttu-id="e13de-150">CIM セッションを作成するだけで、接続が一度に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e13de-150">Creating a CIM session only sets up the connection once.</span></span>
<span data-ttu-id="e13de-151">次に、その同じセッションが、複数のクエリで情報を取得するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e13de-151">Then, multiple queries use that same session to retrieve information.</span></span> <span data-ttu-id="e13de-152">コンピューター名を使用する場合、コマンドレットで個別のクエリごとに接続を設定して破棄しなければなりません。</span><span class="sxs-lookup"><span data-stu-id="e13de-152">Using the computer name requires the cmdlets to set up and tear down the connection with each individual query.</span></span>

<span data-ttu-id="e13de-153">`Get-CimInstance` コマンドレットでは既定で WSMan プロトコルを使用します。これは、リモート コンピューターが接続するために PowerShell バージョン 3.0 以上が必要であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="e13de-153">The `Get-CimInstance` cmdlet uses the WSMan protocol by default, which means the remote computer needs PowerShell version 3.0 or higher to connect.</span></span> <span data-ttu-id="e13de-154">実際に問題になるのは、PowerShell バージョンではなくスタック バージョンです。</span><span class="sxs-lookup"><span data-stu-id="e13de-154">It's actually not the PowerShell version that matters, it's the stack version.</span></span> <span data-ttu-id="e13de-155">スタック バージョンは、`Test-WSMan` コマンドレットを使用して特定できます。</span><span class="sxs-lookup"><span data-stu-id="e13de-155">The stack version can be determined using the `Test-WSMan` cmdlet.</span></span>
<span data-ttu-id="e13de-156">バージョン 3.0 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e13de-156">It needs to be version 3.0.</span></span> <span data-ttu-id="e13de-157">これは、PowerShell バージョン 3.0 以上で見つかるバージョンです。</span><span class="sxs-lookup"><span data-stu-id="e13de-157">That's the version you'll find with PowerShell version 3.0 and higher.</span></span>

```powershell
Test-WSMan -ComputerName dc01
```

```Output
wsmid           : http://schemas.dmtf.org/wbem/wsman/identity/1/wsmanidentity.xsd
ProtocolVersion : http://schemas.dmtf.org/wbem/wsman/1/wsman.xsd
ProductVendor   : Microsoft Corporation
ProductVersion  : OS: 0.0.0 SP: 0.0 Stack: 3.0
```

<span data-ttu-id="e13de-158">古い WMI コマンドレットでは、以前のバージョンの Windows と互換性がある DCOM プロトコルを使用しています。</span><span class="sxs-lookup"><span data-stu-id="e13de-158">The older WMI cmdlets use the DCOM protocol, which is compatible with older versions of Windows.</span></span> <span data-ttu-id="e13de-159">しかし、DCOM は新しいバージョンの Windows でファイアウォールによってブロックされるのが普通です。</span><span class="sxs-lookup"><span data-stu-id="e13de-159">But DCOM is typically blocked by the firewall on newer versions of Windows.</span></span> <span data-ttu-id="e13de-160">`New-CimSessionOption` コマンドレットでは、`New-CimSession` で使用するための DCOM プロトコル接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="e13de-160">The `New-CimSessionOption` cmdlet allows you to create a DCOM protocol connection for use with `New-CimSession`.</span></span> <span data-ttu-id="e13de-161">これにより、Windows Server 2000 と同じくらい古いバージョンの Windows と通信するために `Get-CimInstance` コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e13de-161">This allows the `Get-CimInstance` cmdlet to be used to communicate with versions of Windows as old as Windows Server 2000.</span></span> <span data-ttu-id="e13de-162">これはまた、DCOM プロトコルを使うように構成された CimSession と共に `Get-CimInstance` コマンドレットを使用する場合、リモート コンピューター上に PowerShell が必要ないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="e13de-162">This also means that PowerShell is not required on the remote computer when using the `Get-CimInstance` cmdlet with a CimSession that's configured to use the DCOM protocol.</span></span>

<span data-ttu-id="e13de-163">`New-CimSessionOption` コマンドレットを使用して DCOM プロトコル オプションを作成し、それを変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="e13de-163">Create the DCOM protocol option using the `New-CimSessionOption` cmdlet and store it in a variable.</span></span>

```powershell
$DCOM = New-CimSessionOption -Protocol Dcom
```

<span data-ttu-id="e13de-164">効率を上げるために、ドメイン管理者または管理者特権の資格情報を変数に格納できます。そうすることで、それらをコマンドごとに何度も入力する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="e13de-164">For efficiency, you can store your domain administrator or elevated credentials in a variable so you don't have to constantly enter them for each command.</span></span>

```powershell
$Cred = Get-Credential
```

```Output
cmdlet Get-Credential at command pipeline position 1
Supply values for the following parameters:
Credential
```

<span data-ttu-id="e13de-165">Windows Server 2008 (R2 以外) を実行する SQL03 という名前のサーバーがあります。</span><span class="sxs-lookup"><span data-stu-id="e13de-165">I have a server named SQL03 that runs Windows Server 2008 (non-R2).</span></span> <span data-ttu-id="e13de-166">これは、既定では PowerShell がインストールされていない最新の Windows Server オペレーティング システムです。</span><span class="sxs-lookup"><span data-stu-id="e13de-166">It's the newest Windows Server operating system that doesn't have PowerShell installed by default.</span></span>

<span data-ttu-id="e13de-167">DCOM プロトコルを使用して、SQL03 への **CimSession** を作成します。</span><span class="sxs-lookup"><span data-stu-id="e13de-167">Create a **CimSession** to SQL03 using the DCOM protocol.</span></span>

```powershell
$CimSession = New-CimSession -ComputerName sql03 -SessionOption $DCOM -Credential $Cred
```

<span data-ttu-id="e13de-168">前のコマンドでは、今度は再び手動で入力するのではなく、**Credential** パラメーターの値として `$Cred` という名前の変数を指定したことに注目してください。</span><span class="sxs-lookup"><span data-stu-id="e13de-168">Notice in the previous command, this time I specified the variable named `$Cred` as the value for the **Credential** parameter instead of having to enter them manually again.</span></span>

<span data-ttu-id="e13de-169">クエリの出力は、基になるプロトコルとして何が使用されているかに関係なく同じです。</span><span class="sxs-lookup"><span data-stu-id="e13de-169">The output of the query is the same regardless of the underlying protocol being used.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 7237-7483-8873-8926-7271-5004-86
Version           : VRTUAL - 4001628
PSComputerName    : sql03
```

<span data-ttu-id="e13de-170">`Get-CimSession` コマンドレットは、現在接続されている **CimSession** の内容と、それらで使用されているプロトコルを確認するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e13de-170">The `Get-CimSession` cmdlet is used to see what **CimSessions** are currently connected and what protocols they're using.</span></span>

```powershell
Get-CimSession
```

```Output
Id           : 1
Name         : CimSession1
InstanceId   : 80742787-e38e-41b1-a7d7-fa1369cf1402
ComputerName : dc01
Protocol     : WSMAN

Id           : 2
Name         : CimSession2
InstanceId   : 8fcabd81-43cf-4682-bd53-ccce1e24aecb
ComputerName : sql03
Protocol     : DCOM
```

<span data-ttu-id="e13de-171">前に作成した **CimSession** を両方取得して、`$CimSession` という名前の変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="e13de-171">Retrieve and store both of the previously created **CimSessions** in a variable named `$CimSession`.</span></span>

```powershell
$CimSession = Get-CimSession
```

<span data-ttu-id="e13de-172">1 つのコマンドを使用して、両方のコンピューターに対してクエリを実行します。1 つには WSMan プロトコルを、もう 1 つには DCOM を使用します。</span><span class="sxs-lookup"><span data-stu-id="e13de-172">Query both of the computers with one command, one using the WSMan protocol and the other one with DCOM.</span></span>

```powershell
Get-CimInstance -CimSession $CimSession -ClassName Win32_BIOS
```

```Output
SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 0986-6980-3916-0512-6608-8243-13
Version           : VRTUAL - 4001628
PSComputerName    : dc01

SMBIOSBIOSVersion : 090006
Manufacturer      : American Megatrends Inc.
Name              : Intel(R) Xeon(R) CPU E3-1505M v5 @ 2.80GHz
SerialNumber      : 7237-7483-8873-8926-7271-5004-86
Version           : VRTUAL - 4001628
PSComputerName    : sql03
```

<span data-ttu-id="e13de-173">私は WMI と CIM のコマンドレットについて多数のブログ記事を執筆しています。</span><span class="sxs-lookup"><span data-stu-id="e13de-173">I've written numerous blog articles about the WMI and CIM cmdlets.</span></span> <span data-ttu-id="e13de-174">最も役に立つものの 1 つでは、WSMan と DCOM のどちらを使用すべきかを自動的に特定し、どれを手動で設定するかを把握する必要なしに CIM セッションを自動的に設定するために作成した関数について説明しています。</span><span class="sxs-lookup"><span data-stu-id="e13de-174">One of the most useful ones is about a function that I created to automatically determine if WSMan or DCOM should be used and set up the CIM session automatically without having to figure out which one manually.</span></span> <span data-ttu-id="e13de-175">そのブログ記事のタイトルは、「[DCOM へのフォールバックを使用してリモート コンピューターへの CimSession を作成する PowerShell 関数][]」です。</span><span class="sxs-lookup"><span data-stu-id="e13de-175">That blog article is titled [PowerShell Function to Create CimSessions to Remote Computers with Fallback to Dcom][].</span></span>

<span data-ttu-id="e13de-176">CIM セッションが完了したら、`Remove-CimSession` コマンドレットを使用してそれらを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e13de-176">When you're finished with the CIM sessions, you should remove them with the `Remove-CimSession` cmdlet.</span></span> <span data-ttu-id="e13de-177">すべての CIM セッションを削除するには、`Get-CimSession` を `Remove-CimSession` にパイプ処理するだけでかまいません。</span><span class="sxs-lookup"><span data-stu-id="e13de-177">To remove all CIM sessions, simply pipe `Get-CimSession` to `Remove-CimSession`.</span></span>

```powershell
Get-CimSession | Remove-CimSession
```

## <a name="summary"></a><span data-ttu-id="e13de-178">まとめ</span><span class="sxs-lookup"><span data-stu-id="e13de-178">Summary</span></span>

<span data-ttu-id="e13de-179">この章では、PowerShell を使用してローカルとリモート両方のコンピューター上の WMI を操作する方法について学習しました。</span><span class="sxs-lookup"><span data-stu-id="e13de-179">In this chapter, you've learned about using PowerShell to work with WMI on both local and remote computers.</span></span> <span data-ttu-id="e13de-180">さらに、CIM コマンドレットを使用して、WSMan と DCOM の両方のプロトコルでリモート コンピューターを操作する方法を学習しました。</span><span class="sxs-lookup"><span data-stu-id="e13de-180">You've also learned how to use the CIM cmdlets to work with remote computers with both the WSMan or DCOM protocol.</span></span>

## <a name="review"></a><span data-ttu-id="e13de-181">確認</span><span class="sxs-lookup"><span data-stu-id="e13de-181">Review</span></span>

1. <span data-ttu-id="e13de-182">WMI コマンドレットと CIM コマンドレットの違いは何か。</span><span class="sxs-lookup"><span data-stu-id="e13de-182">What is the difference in the WMI and CIM cmdlets?</span></span>
1. <span data-ttu-id="e13de-183">既定では、`Get-CimInstance` コマンドレットで使用されるプロトコルは何か。</span><span class="sxs-lookup"><span data-stu-id="e13de-183">By default, what protocol does the `Get-CimInstance` cmdlet use?</span></span>
1. <span data-ttu-id="e13de-184">`Get-CimInstance` を使用してコンピューター名を指定する代わりに、CIM セッションを使用するメリットは何か。</span><span class="sxs-lookup"><span data-stu-id="e13de-184">What are some of the benefits of using a CIM session instead of specifying a computer name with `Get-CimInstance`?</span></span>
1. <span data-ttu-id="e13de-185">`Get-CimInstance` で使用する既定のプロトコルとは異なる、別のプロトコルを指定する方法は何か。</span><span class="sxs-lookup"><span data-stu-id="e13de-185">How do you specify an alternate protocol other than the default one for use with `Get-CimInstance`?</span></span>
1. <span data-ttu-id="e13de-186">CIM セッションはどのように終了または削除するか。</span><span class="sxs-lookup"><span data-stu-id="e13de-186">How do you close or remove CIM sessions?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="e13de-187">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="e13de-187">Recommended Reading</span></span>

- <span data-ttu-id="e13de-188">[about_WMI][]</span><span class="sxs-lookup"><span data-stu-id="e13de-188">[about_WMI][]</span></span>
- <span data-ttu-id="e13de-189">[about_WMI_Cmdlets][]</span><span class="sxs-lookup"><span data-stu-id="e13de-189">[about_WMI_Cmdlets][]</span></span>
- <span data-ttu-id="e13de-190">[about_WQL][]</span><span class="sxs-lookup"><span data-stu-id="e13de-190">[about_WQL][]</span></span>
- <span data-ttu-id="e13de-191">[CimCmdlets モジュール][]</span><span class="sxs-lookup"><span data-stu-id="e13de-191">[CimCmdlets Module][]</span></span>
- <span data-ttu-id="e13de-192">[ビデオ: CIM コマンドレットと CIM セッションの使用][]</span><span class="sxs-lookup"><span data-stu-id="e13de-192">[Video: Using CIM Cmdlets and CIM Sessions][]</span></span>

<!-- link references -->
[about_WMI]: /powershell/module/microsoft.powershell.core/about/about_wmi
[about_WMI_Cmdlets]: /powershell/module/microsoft.powershell.core/about/about_wmi_cmdlets
[about_WQL]: /powershell/module/microsoft.powershell.core/about/about_wql
[CimCmdlets モジュール]: /powershell/module/cimcmdlets/
[CimCmdlets Module]: /powershell/module/cimcmdlets/
[ビデオ: CIM コマンドレットと CIM セッションの使用]: https://mikefrobbins.com/2013/09/12/phillyposh-user-group-meeting-presentation-follow-up-powershell-second-hop-problem-with-cimsessions/
[Video: Using CIM Cmdlets and CIM Sessions]: https://mikefrobbins.com/2013/09/12/phillyposh-user-group-meeting-presentation-follow-up-powershell-second-hop-problem-with-cimsessions/
[DCOM へのフォールバックを使用してリモート コンピューターへの CimSession を作成する PowerShell 関数]: https://mikefrobbins.com/2014/08/28/powershell-function-to-create-cimsessions-to-remote-computers-with-fallback-to-dcom/
[PowerShell Function to Create CimSessions to Remote Computers with Fallback to Dcom]: https://mikefrobbins.com/2014/08/28/powershell-function-to-create-cimsessions-to-remote-computers-with-fallback-to-dcom/
