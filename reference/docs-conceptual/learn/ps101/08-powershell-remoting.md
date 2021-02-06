---
title: PowerShell リモート処理
description: PowerShell でリモート コンピューターにコマンドを実行する方法は多数あります。
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 0e467a41282b261c56a89578dbc841725f59a6e0
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "99600779"
---
# <a name="chapter-8---powershell-remoting"></a><span data-ttu-id="4971d-103">第 8 章 - PowerShell リモート処理</span><span class="sxs-lookup"><span data-stu-id="4971d-103">Chapter 8 - PowerShell remoting</span></span>

<span data-ttu-id="4971d-104">PowerShell では、さまざまな方法でリモート コンピューターにコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="4971d-104">PowerShell has many different ways to run commands against remote computers.</span></span> <span data-ttu-id="4971d-105">前の章では、CIM コマンドレットを使用して WMI に対してリモートでクエリを実行する方法を説明しました。</span><span class="sxs-lookup"><span data-stu-id="4971d-105">In the last chapter, you saw how to remotely query WMI using the CIM cmdlets.</span></span> <span data-ttu-id="4971d-106">PowerShell には、**ComputerName** パラメーターが組み込まれたコマンドレットも複数含まれています。</span><span class="sxs-lookup"><span data-stu-id="4971d-106">PowerShell also includes several cmdlets that have a built-in **ComputerName** parameter.</span></span>

<span data-ttu-id="4971d-107">次の例に示すように、`Get-Command` と共に **ParameterName** パラメーターを使用すると、どのコマンドに **ComputerName** パラメーターがあるかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="4971d-107">As shown in the following example, `Get-Command` can be used with the **ParameterName** parameter to determine what commands have a **ComputerName** parameter.</span></span>

```powershell
Get-Command -ParameterName ComputerName
```

```Output
CommandType Name                        Version Source
----------- ----                        ------- ------
Cmdlet      Connect-PSSession           7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Connect-WSMan               7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Disconnect-WSMan            7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Enter-PSSession             7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Get-CimAssociatedInstance   7.0.0.0 CimCmdlets
Cmdlet      Get-CimClass                7.0.0.0 CimCmdlets
Cmdlet      Get-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      Get-CimSession              7.0.0.0 CimCmdlets
Cmdlet      Get-Counter                 7.0.0.0 Microsoft.PowerShell.Diagnostics
Cmdlet      Get-HotFix                  7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Get-PSSession               7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Get-WinEvent                7.0.0.0 Microsoft.PowerShell.Diagnostics
Cmdlet      Get-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Invoke-CimMethod            7.0.0.0 CimCmdlets
Cmdlet      Invoke-Command              7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Invoke-WSManAction          7.0.0.0 Microsoft.WSMan.Management
Cmdlet      New-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      New-CimSession              7.0.0.0 CimCmdlets
Cmdlet      New-PSSession               7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      New-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Receive-Job                 7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Receive-PSSession           7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Register-CimIndicationEvent 7.0.0.0 CimCmdlets
Cmdlet      Remove-CimInstance          7.0.0.0 CimCmdlets
Cmdlet      Remove-CimSession           7.0.0.0 CimCmdlets
Cmdlet      Remove-PSSession            7.0.1.0 Microsoft.PowerShell.Core
Cmdlet      Remove-WSManInstance        7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Rename-Computer             7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Restart-Computer            7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Send-MailMessage            7.0.0.0 Microsoft.PowerShell.Utility
Cmdlet      Set-CimInstance             7.0.0.0 CimCmdlets
Cmdlet      Set-WSManInstance           7.0.0.0 Microsoft.WSMan.Management
Cmdlet      Stop-Computer               7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Test-Connection             7.0.0.0 Microsoft.PowerShell.Management
Cmdlet      Test-WSMan                  7.0.0.0 Microsoft.WSMan.Management
```

<span data-ttu-id="4971d-108">`Get-Process`、`Get-Hotfix` などのコマンドには、**ComputerName** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="4971d-108">Commands such as `Get-Process` and `Get-Hotfix` have a **ComputerName** parameter.</span></span> <span data-ttu-id="4971d-109">これは、リモート コンピューターへのコマンドの実行に関して、Microsoft が長期的に目指す方向性ではありません。</span><span class="sxs-lookup"><span data-stu-id="4971d-109">This isn't the long-term direction that Microsoft is heading for running commands against remote computers.</span></span> <span data-ttu-id="4971d-110">**ComputerName** パラメーターを持つコマンドが見つかったとしても、おそらく代替の資格情報を指定する必要が出てきます。**Credential** パラメーターが追加されることはないでしょう。</span><span class="sxs-lookup"><span data-stu-id="4971d-110">Even if you find a command that has a **ComputerName** parameter, chances are that you'll need to specify alternate credentials and it won't have a **Credential** parameter.</span></span> <span data-ttu-id="4971d-111">また、管理者特権のアカウントから PowerShell を実行しようとすると、リモート コンピューターとの間のファイアウォールによって、その要求がブロックされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4971d-111">And if you decided to run PowerShell from an elevated account, a firewall between you and the remote computer can block the request.</span></span>

<span data-ttu-id="4971d-112">この章で説明されている PowerShell リモート処理コマンドを使用するには、リモート コンピューターで PowerShell リモート処理を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4971d-112">To use the PowerShell remoting commands that are demonstrated in this chapter, PowerShell remoting must be enabled on the remote computer.</span></span> <span data-ttu-id="4971d-113">`Enable-PSRemoting` コマンドレットを使用すると、PowerShell リモート処理を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4971d-113">Use the `Enable-PSRemoting` cmdlet to enable PowerShell remoting.</span></span>

```powershell
Enable-PSRemoting
```

```Output
WinRM has been updated to receive requests.
WinRM service type changed successfully.
WinRM service started.

WinRM has been updated for remote management.
WinRM firewall exception enabled.
```

## <a name="one-to-one-remoting"></a><span data-ttu-id="4971d-114">一対一のリモート処理</span><span class="sxs-lookup"><span data-stu-id="4971d-114">One-To-One Remoting</span></span>

<span data-ttu-id="4971d-115">リモート セッションを対話型にするには、一対一のリモート処理が必要です。</span><span class="sxs-lookup"><span data-stu-id="4971d-115">If you want your remote session to be interactive, then one-to-one remoting is what you want.</span></span>
<span data-ttu-id="4971d-116">この種類のリモート処理は、`Enter-PSSession` コマンドレットによって実行できます。</span><span class="sxs-lookup"><span data-stu-id="4971d-116">This type of remoting is provided via the `Enter-PSSession` cmdlet.</span></span>

<span data-ttu-id="4971d-117">前の章で、ドメイン管理者の資格情報を `$Cred` という名前の変数に格納しました。</span><span class="sxs-lookup"><span data-stu-id="4971d-117">In the last chapter, I stored my domain admin credentials in a variable named `$Cred`.</span></span> <span data-ttu-id="4971d-118">まだドメイン管理者の資格情報を `$Cred` 変数に格納していない場合は、この作業を行ってください。</span><span class="sxs-lookup"><span data-stu-id="4971d-118">If you haven't already done so, go ahead and store your domain admin credentials in the `$Cred` variable.</span></span>

<span data-ttu-id="4971d-119">これにより資格情報を一度に入力できるため、現在の PowerShell セッションがアクティブであれば、コマンドごとにその資格情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4971d-119">This allows you to enter the credentials once and use them on a per command basis as long as your current PowerShell session is active.</span></span>

```powershell
$Cred = Get-Credential
```

<span data-ttu-id="4971d-120">dc01 という名前のドメイン コントローラーとの一対一の PowerShell リモート処理セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4971d-120">Create a one-to-one PowerShell remoting session to the domain controller named dc01.</span></span>

```powershell
Enter-PSSession -ComputerName dc01 -Credential $Cred
```

```Output
[dc01]: PS C:\Users\Administrator\Documents>
```

<span data-ttu-id="4971d-121">この例では PowerShell プロンプトの前に `[dc01]` があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4971d-121">Notice that in the previous example that the PowerShell prompt is preceded by `[dc01]`.</span></span> <span data-ttu-id="4971d-122">これは、dc01 という名前のリモート コンピューターと対話型 PowerShell セッション中であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4971d-122">This means you're in an interactive PowerShell session to the remote computer named dc01.</span></span> <span data-ttu-id="4971d-123">実行するすべてのコマンドが、ご自身のローカル コンピューターではなく、dc01 上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="4971d-123">Any commands you execute run on dc01, not on your local computer.</span></span> <span data-ttu-id="4971d-124">また、リモート コンピューター上の PowerShell コマンドにしかアクセスできないことにも注意してください。ローカル コンピューター上の PowerShell コマンドにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="4971d-124">Also, keep in mind that you only have access to the PowerShell commands that exist on the remote computer and not the ones on your local computer.</span></span> <span data-ttu-id="4971d-125">つまり、ご自身のコンピューターに追加モジュールをインストールしてある場合、そのモジュールには、リモート コンピューターではアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="4971d-125">In other words, if you've installed additional modules on your computer, they aren't accessible on the remote computer.</span></span>

<span data-ttu-id="4971d-126">一対一の対話型 PowerShell リモート処理セッションを使用してリモート コンピューターに接続している場合は、事実上、リモート コンピューターの前にいるのと同じです。</span><span class="sxs-lookup"><span data-stu-id="4971d-126">When you're connected to a remote computer via a one-to-one interactive PowerShell remoting session, you're effectively sitting at the remote computer.</span></span> <span data-ttu-id="4971d-127">オブジェクトは、本書を通して使用してきたような通常のオブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="4971d-127">The objects are normal objects just like the ones you've been working with throughout this entire book.</span></span>

```powershell
[dc01]:  Get-Process | Get-Member
```

```Output
   TypeName: System.Diagnostics.Process

Name                       MemberType     Definition
----                       ----------     ----------
Handles                    AliasProperty  Handles = Handlecount
Name                       AliasProperty  Name = ProcessName
NPM                        AliasProperty  NPM = NonpagedSystemMemorySize64
PM                         AliasProperty  PM = PagedMemorySize64
SI                         AliasProperty  SI = SessionId
VM                         AliasProperty  VM = VirtualMemorySize64
WS                         AliasProperty  WS = WorkingSet64
Disposed                   Event          System.EventHandler Disposed(System.Object, ...
ErrorDataReceived          Event          System.Diagnostics.DataReceivedEventHandler ...
Exited                     Event          System.EventHandler Exited(System.Object, Sy...
OutputDataReceived         Event          System.Diagnostics.DataReceivedEventHandler ...
BeginErrorReadLine         Method         void BeginErrorReadLine()
BeginOutputReadLine        Method         void BeginOutputReadLine()
CancelErrorRead            Method         void CancelErrorRead()
CancelOutputRead           Method         void CancelOutputRead()
Close                      Method         void Close()
CloseMainWindow            Method         bool CloseMainWindow()
CreateObjRef               Method         System.Runtime.Remoting.ObjRef CreateObjRef(...
Dispose                    Method         void Dispose(), void IDisposable.Dispose()
Equals                     Method         bool Equals(System.Object obj)
GetHashCode                Method         int GetHashCode()
GetLifetimeService         Method         System.Object GetLifetimeService()
GetType                    Method         type GetType()
InitializeLifetimeService  Method         System.Object InitializeLifetimeService()
Kill                       Method         void Kill()
Refresh                    Method         void Refresh()
Start                      Method         bool Start()
ToString                   Method         string ToString()
WaitForExit                Method         bool WaitForExit(int milliseconds), void Wai...
WaitForInputIdle           Method         bool WaitForInputIdle(int milliseconds), boo...
__NounName                 NoteProperty   string __NounName=Process
BasePriority               Property       int BasePriority {get;}
Container                  Property       System.ComponentModel.IContainer Container {...
EnableRaisingEvents        Property       bool EnableRaisingEvents {get;set;}
ExitCode                   Property       int ExitCode {get;}
ExitTime                   Property       datetime ExitTime {get;}
Handle                     Property       System.IntPtr Handle {get;}
HandleCount                Property       int HandleCount {get;}
HasExited                  Property       bool HasExited {get;}
Id                         Property       int Id {get;}
MachineName                Property       string MachineName {get;}
MainModule                 Property       System.Diagnostics.ProcessModule MainModule ...
MainWindowHandle           Property       System.IntPtr MainWindowHandle {get;}
MainWindowTitle            Property       string MainWindowTitle {get;}
MaxWorkingSet              Property       System.IntPtr MaxWorkingSet {get;set;}
MinWorkingSet              Property       System.IntPtr MinWorkingSet {get;set;}
Modules                    Property       System.Diagnostics.ProcessModuleCollection M...
NonpagedSystemMemorySize   Property       int NonpagedSystemMemorySize {get;}
NonpagedSystemMemorySize64 Property       long NonpagedSystemMemorySize64 {get;}
PagedMemorySize            Property       int PagedMemorySize {get;}
PagedMemorySize64          Property       long PagedMemorySize64 {get;}
PagedSystemMemorySize      Property       int PagedSystemMemorySize {get;}
PagedSystemMemorySize64    Property       long PagedSystemMemorySize64 {get;}
PeakPagedMemorySize        Property       int PeakPagedMemorySize {get;}
PeakPagedMemorySize64      Property       long PeakPagedMemorySize64 {get;}
PeakVirtualMemorySize      Property       int PeakVirtualMemorySize {get;}
PeakVirtualMemorySize64    Property       long PeakVirtualMemorySize64 {get;}
PeakWorkingSet             Property       int PeakWorkingSet {get;}
PeakWorkingSet64           Property       long PeakWorkingSet64 {get;}
PriorityBoostEnabled       Property       bool PriorityBoostEnabled {get;set;}
PriorityClass              Property       System.Diagnostics.ProcessPriorityClass Prio...
PrivateMemorySize          Property       int PrivateMemorySize {get;}
PrivateMemorySize64        Property       long PrivateMemorySize64 {get;}
PrivilegedProcessorTime    Property       timespan PrivilegedProcessorTime {get;}
ProcessName                Property       string ProcessName {get;}
ProcessorAffinity          Property       System.IntPtr ProcessorAffinity {get;set;}
Responding                 Property       bool Responding {get;}
SafeHandle                 Property       Microsoft.Win32.SafeHandles.SafeProcessHandl...
SessionId                  Property       int SessionId {get;}
Site                       Property       System.ComponentModel.ISite Site {get;set;}
StandardError              Property       System.IO.StreamReader StandardError {get;}
StandardInput              Property       System.IO.StreamWriter StandardInput {get;}
StandardOutput             Property       System.IO.StreamReader StandardOutput {get;}
StartInfo                  Property       System.Diagnostics.ProcessStartInfo StartInf...
StartTime                  Property       datetime StartTime {get;}
SynchronizingObject        Property       System.ComponentModel.ISynchronizeInvoke Syn...
Threads                    Property       System.Diagnostics.ProcessThreadCollection T...
TotalProcessorTime         Property       timespan TotalProcessorTime {get;}
UserProcessorTime          Property       timespan UserProcessorTime {get;}
VirtualMemorySize          Property       int VirtualMemorySize {get;}
VirtualMemorySize64        Property       long VirtualMemorySize64 {get;}
WorkingSet                 Property       int WorkingSet {get;}
WorkingSet64               Property       long WorkingSet64 {get;}
PSConfiguration            PropertySet    PSConfiguration {Name, Id, PriorityClass, Fi...
PSResources                PropertySet    PSResources {Name, Id, Handlecount, WorkingS...
Company                    ScriptProperty System.Object Company {get=$this.Mainmodule....
CPU                        ScriptProperty System.Object CPU {get=$this.TotalProcessorT...
Description                ScriptProperty System.Object Description {get=$this.Mainmod...
FileVersion                ScriptProperty System.Object FileVersion {get=$this.Mainmod...
Path                       ScriptProperty System.Object Path {get=$this.Mainmodule.Fil...
Product                    ScriptProperty System.Object Product {get=$this.Mainmodule....
ProductVersion             ScriptProperty System.Object ProductVersion {get=$this.Main...
[dc01]:
```

<span data-ttu-id="4971d-128">リモート コンピューターの操作が完了したら、`Exit-PSSession` コマンドレットを使用して、一対一のリモート処理セッションを終了します。</span><span class="sxs-lookup"><span data-stu-id="4971d-128">When you're done working with the remote computer, exit the one-to-one remoting session by using the `Exit-PSSession` cmdlet.</span></span>

```powershell
[dc01]:  Exit-PSSession
```

## <a name="one-to-many-remoting"></a><span data-ttu-id="4971d-129">一対多のリモート処理</span><span class="sxs-lookup"><span data-stu-id="4971d-129">One-To-Many Remoting</span></span>

<span data-ttu-id="4971d-130">リモート コンピューターでタスクを対話的に実行しなければならないこともあるでしょう。</span><span class="sxs-lookup"><span data-stu-id="4971d-130">Sometimes you may need to perform a task interactively on a remote computer.</span></span> <span data-ttu-id="4971d-131">しかし、リモート処理は、複数のリモート コンピューターで同時にタスクを実行するときに、さらに大きな力を発揮します。</span><span class="sxs-lookup"><span data-stu-id="4971d-131">But remoting is much more powerful when performing a task on multiple remote computers at the same time.</span></span> <span data-ttu-id="4971d-132">`Invoke-Command` コマンドレットを使用して、1 台以上のリモート コンピューターに対してコマンドを同時に実行します。</span><span class="sxs-lookup"><span data-stu-id="4971d-132">Use the `Invoke-Command` cmdlet to run a command against one or more remote computers at the same time.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="4971d-133">この例では、Windows タイム サービスの状態について、3 台のサーバーが照会されています。</span><span class="sxs-lookup"><span data-stu-id="4971d-133">In the previous example, three servers were queried for the status of the Windows Time service.</span></span> <span data-ttu-id="4971d-134">`Get-Service` コマンドレットは、`Invoke-Command` のスクリプト ブロック内に置かれました。</span><span class="sxs-lookup"><span data-stu-id="4971d-134">The `Get-Service` cmdlet was placed inside the script block of `Invoke-Command`.</span></span> <span data-ttu-id="4971d-135">`Get-Service` は実際にはリモート コンピューターで実行され、結果は、逆シリアル化されたオブジェクトとしてご自身のローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="4971d-135">`Get-Service` actually runs on the remote computer and the results are returned to your local computer as deserialized objects.</span></span>

<span data-ttu-id="4971d-136">このコマンドを `Get-Member` にパイプ処理すると、結果が本当に逆シリアル化されたオブジェクトであることが示されます。</span><span class="sxs-lookup"><span data-stu-id="4971d-136">Piping the previous command to `Get-Member` shows that the results are indeed deserialized objects.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred | Get-Member
```

```Output
   TypeName: Deserialized.System.ServiceProcess.ServiceController

Name                MemberType   Definition
----                ----------   ----------
GetType             Method       type GetType()
ToString            Method       string ToString(), string ToString(string format, Sys...
Name                NoteProperty string Name=W32time
PSComputerName      NoteProperty string PSComputerName=sql02
PSShowComputerName  NoteProperty bool PSShowComputerName=True
RequiredServices    NoteProperty Deserialized.System.ServiceProcess.ServiceController[...
RunspaceId          NoteProperty guid RunspaceId=570313c4-ac84-4109-bf67-c6b33236af0a
CanPauseAndContinue Property     System.Boolean {get;set;}
CanShutdown         Property     System.Boolean {get;set;}
CanStop             Property     System.Boolean {get;set;}
Container           Property      {get;set;}
DependentServices   Property     Deserialized.System.ServiceProcess.ServiceController[...
DisplayName         Property     System.String {get;set;}
MachineName         Property     System.String {get;set;}
ServiceHandle       Property     System.String {get;set;}
ServiceName         Property     System.String {get;set;}
ServicesDependedOn  Property     Deserialized.System.ServiceProcess.ServiceController[...
ServiceType         Property     System.String {get;set;}
Site                Property      {get;set;}
StartType           Property     System.String {get;set;}
Status              Property     System.String {get;set;}
```

<span data-ttu-id="4971d-137">逆シリアル化されたオブジェクトでは、メソッドのほとんどが欠落してることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4971d-137">Notice that the majority of the methods are missing on deserialized objects.</span></span> <span data-ttu-id="4971d-138">つまり、これらのオブジェクトはライブ オブジェクトではなく、機能していません。</span><span class="sxs-lookup"><span data-stu-id="4971d-138">This means they're not live objects; they're inert.</span></span> <span data-ttu-id="4971d-139">逆シリアル化されたオブジェクトは、リモート コンピューターでコマンドが実行された時点でのそのオブジェクトの状態のスナップショットなので、それを使ってサービスを開始または停止することはできません。</span><span class="sxs-lookup"><span data-stu-id="4971d-139">You can't start or stop a service using a deserialized object because it's a snapshot of the state of that object the point when the command ran on the remote computer.</span></span>

<span data-ttu-id="4971d-140">ただし、これは、`Invoke-Command` ではメソッドを使ってサービスを開始または停止できない、という意味ではなく、</span><span class="sxs-lookup"><span data-stu-id="4971d-140">That doesn't mean you can't start or stop a service using a method with `Invoke-Command` though.</span></span> <span data-ttu-id="4971d-141">メソッドは、リモート セッションで呼び出す必要がある、ということです。</span><span class="sxs-lookup"><span data-stu-id="4971d-141">It just means that the method has to be called in the remote session.</span></span>

<span data-ttu-id="4971d-142">これを証明するために、**Stop()** メソッドを使用して、この 3 台のリモート サーバーすべてで Windows タイム サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="4971d-142">I'll stop the Windows Time service on all three of those remote servers using the **Stop()** method to prove this point.</span></span>

```powershell
Invoke-Command -ComputerName dc01, sql02, web01 {(Get-Service -Name W32time).Stop()} -Credential $Cred
Invoke-Command -ComputerName dc01, sql02, web01 {Get-Service -Name W32time} -Credential $Cred
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="4971d-143">前の章で説明したように、タスクを完了するためのコマンドレットが存在する場合は、メソッドではなく、そのコマンドレットを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4971d-143">As mentioned in a previous chapter, if a cmdlet exists for accomplishing a task, I recommend using it instead of using a method.</span></span> <span data-ttu-id="4971d-144">前のシナリオでは、stop メソッドではなく、`Stop-Service` コマンドレットを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4971d-144">In the previous scenario, I recommend using the `Stop-Service` cmdlet instead of the stop method.</span></span> <span data-ttu-id="4971d-145">ここで **Stop()** メソッドを使用したのは、PowerShell リモート処理を使用しているときにメソッドを呼び出すことができないと誤解している人が多数いるので、そうではないことを証明するためです。</span><span class="sxs-lookup"><span data-stu-id="4971d-145">I chose to use the **Stop()** method to prove a point since many people are under the misconception that methods can't be called when using PowerShell remoting.</span></span> <span data-ttu-id="4971d-146">返されたオブジェクトは逆シリアル化されているため、そのオブジェクトではメソッドを呼び出すことはできませんが、リモート セッション自体では呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="4971d-146">They can't be called on the object that's returned because it's deserialized, but they can be called in the remote session itself.</span></span>

## <a name="powershell-sessions"></a><span data-ttu-id="4971d-147">PowerShell セッション</span><span class="sxs-lookup"><span data-stu-id="4971d-147">PowerShell Sessions</span></span>

<span data-ttu-id="4971d-148">前のセクションの最後の例では、`Invoke-Command` コマンドレットを使用して 2 つのコマンドを実行しました。</span><span class="sxs-lookup"><span data-stu-id="4971d-148">In the last example in the previous section, I ran two commands using the `Invoke-Command` cmdlet.</span></span>
<span data-ttu-id="4971d-149">つまり、これらの 2 つのコマンドを実行するには、2 つの個別のセッションを設定して、破棄する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="4971d-149">That means two separate sessions had to be set up and torn down to run those two commands.</span></span>

<span data-ttu-id="4971d-150">第 7 章で説明した CIM セッションと同様、リモート コンピューターとの PowerShell セッションを使用すると、リモート コンピューターに対して複数のコマンドを実行できます。コマンドごとに新しいセッションを使用するオーバーヘッドは発生しません。</span><span class="sxs-lookup"><span data-stu-id="4971d-150">Similar to the CIM sessions discussed in Chapter 7, a PowerShell session to a remote computer can be used to run multiple commands against the remote computer without the overhead of a new session for each individual command.</span></span>

<span data-ttu-id="4971d-151">この章で使用している 3 台のコンピューター DC01、SQL02、WEB01 それぞれについて、PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4971d-151">Create a PowerShell session to each of the three computers we've been working with in this chapter, DC01, SQL02, and WEB01.</span></span>

```powershell
$Session = New-PSSession -ComputerName dc01, sql02, web01 -Credential $Cred
```

<span data-ttu-id="4971d-152">ここで、`$Session` という名前の変数を使用して、メソッドを使って Windows タイムサービスを開始し、サービスの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="4971d-152">Now use the variable named `$Session` to start the Windows Time service using a method and check the status of the service.</span></span>

```powershell
Invoke-Command -Session $Session {(Get-Service -Name W32time).Start()}
Invoke-Command -Session $Session {Get-Service -Name W32time}
```

```Output
Status   Name        DisplayName       PSComputerName
------   ----        -----------       --------------
Running  W32time     Windows Time      web01
Start... W32time     Windows Time      dc01
Running  W32time     Windows Time      sql02
```

<span data-ttu-id="4971d-153">代替の資格情報を使用してセッションが作成されると、コマンドが実行されるたびに資格情報を指定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="4971d-153">Once the session is created using alternate credentials, it's no longer necessary to specify the credentials each time a command is run.</span></span>

<span data-ttu-id="4971d-154">使い終わったセッションは必ず削除してください。</span><span class="sxs-lookup"><span data-stu-id="4971d-154">When you're finished using the sessions, be sure to remove them.</span></span>

```powershell
Get-PSSession | Remove-PSSession
```

## <a name="summary"></a><span data-ttu-id="4971d-155">まとめ</span><span class="sxs-lookup"><span data-stu-id="4971d-155">Summary</span></span>

<span data-ttu-id="4971d-156">この章では、PowerShell リモート処理、1 台のリモート コンピューターを使用して対話型セッションでコマンドを実行する方法、および一対多のリモート処理を使用して複数のコンピューターに対してコマンドを実行する方法について学習しました。</span><span class="sxs-lookup"><span data-stu-id="4971d-156">In this chapter you've learned about PowerShell remoting, how to run commands in an interactive session with one remote computer, and how to run commands against multiple computers using one-to-many remoting.</span></span> <span data-ttu-id="4971d-157">また、同じリモート コンピューターに対して複数のコマンドを実行するときに PowerShell セッションを使用するメリットについても学習しました。</span><span class="sxs-lookup"><span data-stu-id="4971d-157">You've also learned the benefits of using a PowerShell session when running multiple commands against the same remote computer.</span></span>

## <a name="review"></a><span data-ttu-id="4971d-158">確認</span><span class="sxs-lookup"><span data-stu-id="4971d-158">Review</span></span>

1. <span data-ttu-id="4971d-159">PowerShell リモート処理を有効にするには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="4971d-159">How do you enable PowerShell remoting?</span></span>
1. <span data-ttu-id="4971d-160">リモート コンピューターとの対話型セッションを開始する PowerShell コマンドは何ですか。</span><span class="sxs-lookup"><span data-stu-id="4971d-160">What is the PowerShell command for starting an interactive session with a remote computer?</span></span>
1. <span data-ttu-id="4971d-161">各コマンドでただコンピューター名を指定するのではなく、PowerShell リモート処理セッションを使用するメリットは何ですか。</span><span class="sxs-lookup"><span data-stu-id="4971d-161">What is a benefit of using a PowerShell remoting session versus just specifying the computer name with each command?</span></span>
1. <span data-ttu-id="4971d-162">一対一のリモート処理セッションで PowerShell リモート処理セッションを使用できますか。</span><span class="sxs-lookup"><span data-stu-id="4971d-162">Can a PowerShell remoting session be used with a one-to-one remoting session?</span></span>
1. <span data-ttu-id="4971d-163">コマンドレットによって返されるオブジェクトの種類と、その同じコマンドレットを、`Invoke-Command` を使ってリモート コンピューターに対して実行することで返されるオブジェクトの種類は、どのように違いますか。</span><span class="sxs-lookup"><span data-stu-id="4971d-163">What is the difference in the type of objects that are returned by cmdlets versus those returned when running those same cmdlets against remote computers with `Invoke-Command`?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="4971d-164">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="4971d-164">Recommended Reading</span></span>

- <span data-ttu-id="4971d-165">[about_Remote][]</span><span class="sxs-lookup"><span data-stu-id="4971d-165">[about_Remote][]</span></span>
- <span data-ttu-id="4971d-166">[about_Remote_FAQ][]</span><span class="sxs-lookup"><span data-stu-id="4971d-166">[about_Remote_FAQ][]</span></span>
- <span data-ttu-id="4971d-167">[about_Remote_Output][]</span><span class="sxs-lookup"><span data-stu-id="4971d-167">[about_Remote_Output][]</span></span>
- <span data-ttu-id="4971d-168">[about_Remote_Requirements][]</span><span class="sxs-lookup"><span data-stu-id="4971d-168">[about_Remote_Requirements][]</span></span>
- <span data-ttu-id="4971d-169">[about_Remote_Troubleshooting][]</span><span class="sxs-lookup"><span data-stu-id="4971d-169">[about_Remote_Troubleshooting][]</span></span>
- <span data-ttu-id="4971d-170">[about_Remote_Variables][]</span><span class="sxs-lookup"><span data-stu-id="4971d-170">[about_Remote_Variables][]</span></span>

<!-- link references -->
[about_Remote]: /powershell/module/microsoft.powershell.core/about/about_remote
[about_Remote_FAQ]: /powershell/module/microsoft.powershell.core/about/about_remote_faq
[about_Remote_Output]: /powershell/module/microsoft.powershell.core/about/about_remote_output
[about_Remote_Requirements]: /powershell/module/microsoft.powershell.core/about/about_remote_requirements
[about_Remote_Troubleshooting]: /powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting
[about_Remote_Variables]: /powershell/module/microsoft.powershell.core/about/about_remote_variables
[Breaking changes in PowerShell 6.0]: /powershell/scripting/whats-new/breaking-changes-ps6#remove--protocol-from--computer-cmdlets-5277
