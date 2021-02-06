---
title: ワンライナーとパイプライン
description: PowerShell ワンライナーは複数のコマンドが含まれた連続する 1 つのパイプラインで、1 つのタスクを実行します。
ms.date: 06/02/2020
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: 1483ec6b76d17c3dd081356ecff85a929fc43e2c
ms.sourcegitcommit: df5e6f032ee2d4b556d50406832732d2f7dc2502
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "99605428"
---
# <a name="chapter-4---one-liners-and-the-pipeline"></a><span data-ttu-id="e23c1-103">第 4 章 - ワンライナーとパイプライン</span><span class="sxs-lookup"><span data-stu-id="e23c1-103">Chapter 4 - One-liners and the pipeline</span></span>

<span data-ttu-id="e23c1-104">私は PowerShell の学習を初めた当初、PowerShell ワンライナーを使用してタスクを実行できなかった場合、GUI に戻っていました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-104">When I first started learning PowerShell, if I couldn't accomplish a task with a PowerShell one-liner, I went back to the GUI.</span></span> <span data-ttu-id="e23c1-105">そして、スクリプト、関数、モジュールを記述するスキルを徐々に身に付けていきました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-105">Over time, I built my skills up to writing scripts, functions, and modules.</span></span> <span data-ttu-id="e23c1-106">インターネット上で見られる一部の高度な例にひるまないようにしましょう。</span><span class="sxs-lookup"><span data-stu-id="e23c1-106">Don't allow yourself to become overwhelmed by some of the more advanced examples you may see on the internet.</span></span> <span data-ttu-id="e23c1-107">最初から PowerShell を使いこなせる人はいません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-107">No one is a natural expert with PowerShell.</span></span> <span data-ttu-id="e23c1-108">だれでもかつては初心者だったのです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-108">We were all beginners at one time.</span></span>

<span data-ttu-id="e23c1-109">今でも管理に GUI を使用している方に向けて、ちょっとしたアドバイスがあります。管理ワークステーションに管理ツールをインストールし、サーバーをリモートで管理しましょう。</span><span class="sxs-lookup"><span data-stu-id="e23c1-109">I have a bit of advice to offer those of you who are still using the GUI for administration: install the management tools on your admin workstation and manage your servers remotely.</span></span> <span data-ttu-id="e23c1-110">そうすることで、サーバーで実行しているオペレーティング システムのインストールが GUI と Server Core のどちらでも問題になりません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-110">This way it won't matter if the server is running a GUI or Server Core installation of the operating system.</span></span>
<span data-ttu-id="e23c1-111">これは、PowerShell を使用してサーバーをリモートで管理するための準備に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-111">It's going to help prepare you for managing servers remotely with PowerShell.</span></span>

<span data-ttu-id="e23c1-112">前の章と同様に、Windows 10 ラボ環境コンピューターで作業するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e23c1-112">As with previous chapters, be sure to follow along on your Windows 10 lab environment computer.</span></span>

## <a name="one-liners"></a><span data-ttu-id="e23c1-113">ワンライナー</span><span class="sxs-lookup"><span data-stu-id="e23c1-113">One-Liners</span></span>

<span data-ttu-id="e23c1-114">PowerShell の1つのコードは1つの連続したパイプラインであり、必ずしも1つの物理ライン上のコマンドではありません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-114">A PowerShell one-liner is one continuous pipeline and not necessarily a command that's on one physical line.</span></span> <span data-ttu-id="e23c1-115">1 つの物理的な行になっているすべてのコマンドがワンライナーであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-115">Not all commands that are on one physical line are one-liners.</span></span>

<span data-ttu-id="e23c1-116">次のコマンドは、複数の物理的な行になっていても、1 つの連続するパイプラインであるため、PowerShell ワンライナーです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-116">Even though the following command is on multiple physical lines, it's a PowerShell one-liner because it's one continuous pipeline.</span></span> <span data-ttu-id="e23c1-117">1 つの物理的な行に記述することもできますが、パイプ記号で改行することを選択しました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-117">It could be written on one physical line, but I've chosen to line break at the pipe symbol.</span></span> <span data-ttu-id="e23c1-118">パイプ記号は、PowerShell で自然な改行が許される文字の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-118">The pipe symbol is one of the characters where a natural line break is allowed in PowerShell.</span></span>

```powershell
Get-Service |
  Where-Object CanPauseAndContinue -eq $true |
    Select-Object -Property *
```

```Output
Name                : LanmanWorkstation
RequiredServices    : {NSI, MRxSmb20, Bowser}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Workstation
DependentServices   : {SessionEnv, Netlogon, Browser}
MachineName         : .
ServiceName         : LanmanWorkstation
ServicesDependedOn  : {NSI, MRxSmb20, Bowser}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :

Name                : Netlogon
RequiredServices    : {LanmanWorkstation}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Netlogon
DependentServices   : {}
MachineName         : .
ServiceName         : Netlogon
ServicesDependedOn  : {LanmanWorkstation}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :

Name                : vmicheartbeat
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Heartbeat Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicheartbeat
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmickvpexchange
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Data Exchange Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmickvpexchange
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicrdv
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Remote Desktop Virtualization Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicrdv
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicshutdown
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Guest Shutdown Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmicshutdown
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmictimesync
RequiredServices    : {VmGid}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Time Synchronization Service
DependentServices   : {}
MachineName         : .
ServiceName         : vmictimesync
ServicesDependedOn  : {VmGid}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : vmicvss
RequiredServices    : {}
CanPauseAndContinue : True
CanShutdown         : False
CanStop             : True
DisplayName         : Hyper-V Volume Shadow Copy Requestor
DependentServices   : {}
MachineName         : .
ServiceName         : vmicvss
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :

Name                : Winmgmt
RequiredServices    : {RPCSS}
CanPauseAndContinue : True
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Management Instrumentation
DependentServices   : {wscsvc, NcaSvc, iphlpsvc}
MachineName         : .
ServiceName         : Winmgmt
ServicesDependedOn  : {RPCSS}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Automatic
Site                :
Container           :
```

<span data-ttu-id="e23c1-119">自然な改行は、コンマ (`,`)、開始角かっこ (`[`)、中かっこ (`{`)、丸かっこ (`(`) など、よく使用される文字で行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-119">Natural line breaks can occur at commonly used characters including comma (`,`) and opening brackets (`[`), braces (`{`), and parenthesis (`(`).</span></span> <span data-ttu-id="e23c1-120">それほど一般的でないその他のものとしては、セミコロン (`;`)、等号 (`=`)、一重と二重の両方の開始引用符 (`'`、`"`) などがあります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-120">Others that aren't so common include the semicolon (`;`), equals sign (`=`), and both opening single and double quotes (`'`,`"`).</span></span>

<span data-ttu-id="e23c1-121">バックティック (`` ` ``) またはグレーブ アクセント文字を行の連結文字として使用することについては、議論があります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-121">Using the backtick (`` ` ``) or grave accent character as a line continuation character is a controversial topic.</span></span> <span data-ttu-id="e23c1-122">これは可能な限り回避することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e23c1-122">My recommendation is to try to avoid it if at all possible.</span></span> <span data-ttu-id="e23c1-123">自然な改行文字の直後にバックティックを使用して PowerShell コマンドが記述されているのをよく見ます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-123">I often see PowerShell commands written using a backtick immediately after a natural line break character.</span></span>
<span data-ttu-id="e23c1-124">そのようにしなければならない理由はありません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-124">There's no reason for it to be there.</span></span>

```powershell
Get-Service -Name w32time |
>> Select-Object -Property *
```

```Output
Name                : w32time
RequiredServices    : {}
CanPauseAndContinue : False
CanShutdown         : True
CanStop             : True
DisplayName         : Windows Time
DependentServices   : {}
MachineName         : .
ServiceName         : w32time
ServicesDependedOn  : {}
ServiceHandle       : SafeServiceHandle
Status              : Running
ServiceType         : Win32ShareProcess
StartType           : Manual
Site                :
Container           :
```

<span data-ttu-id="e23c1-125">前の 2 つの例で示したコマンドは、PowerShell コンソールで問題なく動作します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-125">The commands shown in the previous two examples work fine in the PowerShell console.</span></span> <span data-ttu-id="e23c1-126">ただし、PowerShell ISE のコンソール ペインでこれらを実行しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-126">But if you try to run them in the console pane of the PowerShell ISE, they'll generate an error.</span></span> <span data-ttu-id="e23c1-127">PowerShell ISE のコンソール ペインでは、PowerShell コンソールのように次の行で残りのコマンドの入力を待機しません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-127">The console pane of the PowerShell ISE doesn't wait for the rest of the command to be entered on the next line like the PowerShell console does.</span></span> <span data-ttu-id="e23c1-128">PowerShell ISE のコンソール ウインドウでこの問題を回避するには、コマンドを次の行で継続する際に、<kbd>Enter</kbd> キーを押すのではなく、<kbd>Shift</kbd>+<kbd>Enter</kbd> キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-128">To avoid this problem in the console pane of the PowerShell ISE, use <kbd>Shift</kbd>+<kbd>Enter</kbd> instead of just pressing <kbd>Enter</kbd> when continuing a command on another line.</span></span>

<span data-ttu-id="e23c1-129">この次の例は、1 つの連続するパイプラインではないため、PowerShell ワンライナーではありません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-129">This next example isn't a PowerShell one-liner because it's not one continuous pipeline.</span></span> <span data-ttu-id="e23c1-130">1 つの行でセミコロンによって区切られた、2 つの異なるコマンドです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-130">It's two separate commands on one line, separated by a semicolon.</span></span>

```powershell
$Service = 'w32time'; Get-Service -Name $Service
```

```powershell
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="e23c1-131">多くのプログラミング言語とスクリプト言語では、行末にセミコロンが必要です。</span><span class="sxs-lookup"><span data-stu-id="e23c1-131">Many programming and scripting languages require a semicolon at the end of each line.</span></span> <span data-ttu-id="e23c1-132">PowerShell でもそのような使用法は可能ですが、必要ではないため、推奨されません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-132">While they can be used that way in PowerShell, it's not recommended because they're not needed.</span></span>

## <a name="filtering-left"></a><span data-ttu-id="e23c1-133">左でのフィルター</span><span class="sxs-lookup"><span data-stu-id="e23c1-133">Filtering Left</span></span>

<span data-ttu-id="e23c1-134">この章で示されるコマンドの結果は、サブセットへとフィルターされています。</span><span class="sxs-lookup"><span data-stu-id="e23c1-134">The results of the commands shown in this chapter have been filtered down to a subset.</span></span> <span data-ttu-id="e23c1-135">たとえば、返されたサービスのリストを Windows タイム サービスのみにフィルターするために、`Get-Service` は **Name** パラメーターと共に使用されました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-135">For example, `Get-Service` was used with the **Name** parameter to filter the list of services that were returned to only the Windows Time service.</span></span>

<span data-ttu-id="e23c1-136">パイプラインでは常に、可能な限り早い段階で結果を目的の内容へとフィルターすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="e23c1-136">In the pipeline, you always want to filter the results down to what you're looking for as early as possible.</span></span> <span data-ttu-id="e23c1-137">これは、最初 (または左端) のコマンドでパラメーターを使用することで実現されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-137">This is accomplished using parameters on the first command or, the one to the far left.</span></span>
<span data-ttu-id="e23c1-138">これは "_左でのフィルター_" と呼ばれることがあります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-138">This is sometimes called _filtering left_.</span></span>

<span data-ttu-id="e23c1-139">次の例では、`Get-Service` の **Name** パラメーターを使用して、すぐに結果を Windows タイム サービスのみにフィルターしています。</span><span class="sxs-lookup"><span data-stu-id="e23c1-139">The following example uses the **Name** parameter of `Get-Service` to immediately filter the results to the Windows Time service only.</span></span>

```powershell
Get-Service -Name w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  w32time            Windows Time
```

<span data-ttu-id="e23c1-140">フィルターを実行するためにコマンドが `Where-Object` にパイプ処理されている例を見ることが少なくありません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-140">It's not uncommon to see examples where the command is piped to `Where-Object` to perform the filtering.</span></span>

```powershell
Get-Service | Where-Object Name -eq w32time
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  W32Time            Windows Time
```

<span data-ttu-id="e23c1-141">最初の例では、ソースでフィルターが実行され、Windows タイム サービスの結果のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-141">The first example filters at the source and only returns the results for the Windows Time service.</span></span>
<span data-ttu-id="e23c1-142">2 つ目の例では、すべてのサービスが返されてから、フィルターを実行するための別のコマンドにパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-142">The second example returns all the services then pipes them to another command to perform the filtering.</span></span> <span data-ttu-id="e23c1-143">この例では大したことではないように見えますが、Active Directory ユーザーのリストを照会していると想像してみてください。</span><span class="sxs-lookup"><span data-stu-id="e23c1-143">While this may not seem like a big deal in this example, imagine if you were querying a list of Active Directory users.</span></span> <span data-ttu-id="e23c1-144">小さなサブセットへとフィルターする別のコマンドにパイプ処理するためだけに、Active Directory から数千のユーザー アカウントに関する情報を返したいと本当に思うでしょうか。</span><span class="sxs-lookup"><span data-stu-id="e23c1-144">Do you really want to return the information for many thousands of user accounts from Active Directory only to pipe them to another command that filters them down to a tiny subset?</span></span> <span data-ttu-id="e23c1-145">一見問題がない場合でも、常に左でフィルターすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e23c1-145">My recommendation is to always filter left even when it doesn't seem to matter.</span></span> <span data-ttu-id="e23c1-146">そうすることで、本当に問題がある場合に自然と左でフィルターするようになります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-146">You'll be so use to it that you'll automatically filter left when it really does matter.</span></span>

<span data-ttu-id="e23c1-147">以前、コマンドを指定する順番は問題にならないと言われたことがあります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-147">I once had someone tell me that the order you specify the commands in doesn't matter.</span></span> <span data-ttu-id="e23c1-148">それは事実とはまったく異なります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-148">That couldn't be further from the truth.</span></span> <span data-ttu-id="e23c1-149">実際、コマンドが指定される順番はフィルターを実行する際に問題になります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-149">The order that the commands are specified in does indeed matter when performing filtering.</span></span> <span data-ttu-id="e23c1-150">たとえば、いくつかのプロパティのみを選択するために `Select-Object`、選択にないプロパティでフィルターするために `Where-Object` を使用しているシナリオを考えてみてください。</span><span class="sxs-lookup"><span data-stu-id="e23c1-150">For example, consider the scenario where you are using `Select-Object` to select only a few properties and `Where-Object` to filter on properties that won't be in the selection.</span></span> <span data-ttu-id="e23c1-151">このシナリオでは、フィルターは最初に実行される必要があります。そうしないと、フィルターの実行が試みられるときに、プロパティがパイプライン内に存在しません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-151">In that scenario, the filtering must occur first, otherwise the property won't exist in the pipeline when try to perform the filtering.</span></span>

```powershell
Get-Service |
Select-Object -Property DisplayName, Running, Status |
Where-Object CanPauseAndContinue
```

<span data-ttu-id="e23c1-152">前の例のコマンドでは、`Select-Object` の結果が `Where-Object` にパイプ処理されるときに **CanStopAndContinue** プロパティが存在しないため、結果が返されません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-152">The command in the previous example doesn't return any results because the **CanStopAndContinue** property doesn't exist when the results of `Select-Object` are piped to `Where-Object`.</span></span> <span data-ttu-id="e23c1-153">この特定のプロパティは "選択されていませんでした"。</span><span class="sxs-lookup"><span data-stu-id="e23c1-153">That particular property wasn't "selected".</span></span> <span data-ttu-id="e23c1-154">つまり、フィルターで除外されていました。`Select-Object` と `Where-Object` の順番を反対にすることで、目的の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-154">In essence, it was filtered out. Reversing the order of `Select-Object` and `Where-Object` produces the desired results.</span></span>

```powershell
Get-Service |
Where-Object CanPauseAndContinue |
Select-Object -Property DisplayName, Status
```

```Output
DisplayName                                    Status
-----------                                    ------
Workstation                                    Running
Netlogon                                       Running
Hyper-V Heartbeat Service                      Running
Hyper-V Data Exchange Service                  Running
Hyper-V Remote Desktop Virtualization Service  Running
Hyper-V Guest Shutdown Service                 Running
Hyper-V Time Synchronization Service           Running
Hyper-V Volume Shadow Copy Requestor           Running
Windows Management Instrumentation             Running
```

## <a name="the-pipeline"></a><span data-ttu-id="e23c1-155">パイプライン</span><span class="sxs-lookup"><span data-stu-id="e23c1-155">The Pipeline</span></span>

<span data-ttu-id="e23c1-156">これまで見てきたこのドキュメントの多くの例からわかるように、あるコマンドの出力を別のコマンドの入力として使用できる場合は多々あります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-156">As you've seen in many of the examples shown so far throughout this book, many times the output of one command can be used as input for another command.</span></span> <span data-ttu-id="e23c1-157">第 3 章では、コマンドで生成されるオブジェクトの種類を特定するために、`Get-Member` が使用されました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-157">In Chapter 3, `Get-Member` was used to determine what type of object a command produces.</span></span> <span data-ttu-id="e23c1-158">また第 3 章では、この種類の入力を受け取ったコマンド (ただし、パイプライン入力によっては必ずしも受け取らない) を特定するために、`Get-Command` の **ParameterType** パラメーターも使用して見せました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-158">Chapter 3 also showed using the **ParameterType** parameter of `Get-Command` to determine what commands accepted that type of input, although not necessarily by pipeline input.</span></span>

<span data-ttu-id="e23c1-159">コマンドのヘルプの詳細度に応じて、**INPUTS** および **OUTPUTS** セクションが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-159">Depending on how thorough a commands help is, it may include an **INPUTS** and **OUTPUTS** section.</span></span>

```powershell
help Stop-Service -Full
```

```Output
...
INPUTS
    System.ServiceProcess.ServiceController, System.String
        You can pipe a service object or a string that contains the name of a service
        to this cmdlet.

OUTPUTS
    None, System.ServiceProcess.ServiceController
        This cmdlet generates a System.ServiceProcess.ServiceController object that
        represents the service, if you use the PassThru parameter. Otherwise, this
        cmdlet does not generate any output.
...
```

<span data-ttu-id="e23c1-160">前の結果では、ヘルプの関連するセクションのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-160">Only the relevant section of the help is shown in the previous results.</span></span> <span data-ttu-id="e23c1-161">ご覧のとおり、**INPUTS** セクションでは、**ServiceController** または **String** のオブジェクトを `Stop-Service` コマンドレットにパイプ処理できることが述べられています。</span><span class="sxs-lookup"><span data-stu-id="e23c1-161">As you can see, the **INPUTS** section states that a **ServiceController** or a **String** object can be piped to the `Stop-Service` cmdlet.</span></span> <span data-ttu-id="e23c1-162">ここからは、この種類の入力を受け取るパラメーターがわかりません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-162">It doesn't tell you which parameters accept that type of input.</span></span> <span data-ttu-id="e23c1-163">この情報を特定する最も簡単な方法の 1 つは、`Stop-Service` コマンドレットのヘルプの完全なバージョンで各種パラメーターに目を通すことです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-163">One of the easiest ways to determine that information is to look through the different parameters in the full version of the help for the `Stop-Service` cmdlet.</span></span>

```powershell
help Stop-Service -Full
```

```powershell
...
-DisplayName <String[]>
    Specifies the display names of the services to stop. Wildcard characters are
    permitted.

    Required?                    true
    Position?                    named
    Default value                None
    Accept pipeline input?       False
    Accept wildcard characters?  false

-InputObject <ServiceController[]>
    Specifies ServiceController objects that represent the services to stop. Enter a
    variable that contains the objects, or type a command or expression that gets the
    objects.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByValue)
    Accept wildcard characters?  false

-Name <String[]>
    Specifies the service names of the services to stop. Wildcard characters are
    permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  false
...
```

<span data-ttu-id="e23c1-164">繰り返しますが、前の結果のセットではヘルプの関連部分だけをお見せしました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-164">Once again, I've only shown the relevant portion of the help in the previous set of results.</span></span> <span data-ttu-id="e23c1-165">**DisplayName** パラメーターではパイプライン入力を受け取らないこと、**InputObject** パラメーターでは **ServiceController** オブジェクトについて **値による** パイプライン入力を受け取ること、**Name** パラメーターでは **String** オブジェクトについて **値による** パイプライン入力を受け取ることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="e23c1-165">Notice that the **DisplayName** parameter doesn't accept pipeline input, the **InputObject** parameter accepts pipeline input **by value** for **ServiceController** objects, and the **Name** parameter accepts pipeline input **by value** for **string** objects.</span></span> <span data-ttu-id="e23c1-166">さらに、これは **プロパティ名による** パイプライン入力も受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-166">It also accepts pipeline input **by property name**.</span></span>

<span data-ttu-id="e23c1-167">プロパティ名と値の両方によるパイプライン入力をパラメーターが受け取る場合は、常に **値によって** 先に試行されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-167">When a parameter accepts pipeline input by both property name and by value, it always tries **by value** first.</span></span> <span data-ttu-id="e23c1-168">**値によって** 失敗した場合、次に **プロパティ名によって** 試行されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-168">If **by value** fails, then it tries **by property name**.</span></span> <span data-ttu-id="e23c1-169">"**値による**" という表現には、わずかに語弊があります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-169">**By value** is a little misleading.</span></span> <span data-ttu-id="e23c1-170">"**種類による**" という表現の方が良いでしょう。</span><span class="sxs-lookup"><span data-stu-id="e23c1-170">I prefer to call it **by type**.</span></span> <span data-ttu-id="e23c1-171">つまり、**ServiceController** というオブジェクトの種類を生成するコマンドの結果を `Stop-Service` にパイプ処理すると、その入力は **InputObject** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-171">This means if you pipe the results of a command that produces a **ServiceController** object type to `Stop-Service`, it binds that input to the **InputObject** parameter.</span></span> <span data-ttu-id="e23c1-172">しかし、**String** の出力を生成するコマンドの結果を `Stop-Service` にパイプ処理すると、それが **Name** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-172">But if you pipe the results of a command that produces **String** output to `Stop-Service`, it binds it to the **Name** parameter.</span></span> <span data-ttu-id="e23c1-173">**ServiceController** または **String** のオブジェクトを生成しないコマンドの結果を `Stop-Service` にパイプ処理しても、**Name** という名前のプロパティが含まれた出力が生成される場合、出力の **Name** プロパティは `Stop-Service` の **Name** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-173">If you pipe the results of a command that doesn't produce a **ServiceController** or **String** object to `Stop-Service`, but it does produce output containing a property called **Name**, then it binds the **Name** property from the output to the **Name** parameter of `Stop-Service`.</span></span>

<span data-ttu-id="e23c1-174">`Get-Service` コマンドで生成される出力の種類を特定します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-174">Determine what type of output the `Get-Service` command produces.</span></span>

```powershell
Get-Service -Name w32time | Get-Member
```

```Output
   TypeName: System.ServiceProcess.ServiceController
```

<span data-ttu-id="e23c1-175">`Get-Service` では、ServiceController というオブジェクトの種類が生成されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-175">`Get-Service` produces a ServiceController object type.</span></span>

<span data-ttu-id="e23c1-176">先ほどヘルプで見たとおり、`Stop-Service` の **InputObject** パラメーターでは、**値による** (種類による) パイプライン経由で **ServiceController** オブジェクトを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-176">As you previously saw in the help, the **InputObject** parameter of `Stop-Service` accepts **ServiceController** objects via the pipeline **by value** (by type).</span></span> <span data-ttu-id="e23c1-177">つまり、`Get-Service` コマンドレットの結果が `Stop-Service` にパイプ処理されると、それらは `Stop-Service` の **InputObject** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-177">This means that when the results of the `Get-Service` cmdlet are piped to `Stop-Service`, they bind to the **InputObject** parameter of `Stop-Service`.</span></span>

```powershell
Get-Service -Name w32time | Stop-Service
```

<span data-ttu-id="e23c1-178">次に文字列入力を試します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-178">Now to try string input.</span></span> <span data-ttu-id="e23c1-179">`w32time` を `Get-Member` にパイプ処理して、これが文字列であることだけ確認します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-179">Pipe `w32time` to `Get-Member` just to confirm that it's a string.</span></span>

```powershell
'w32time' | Get-Member
```

```Output
   TypeName: System.String
```

<span data-ttu-id="e23c1-180">ヘルプで前に示されていたとおり、文字列を `Stop-Service` にパイプ処理すると、それが **値によって** `Stop-Service` の **Name** パラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-180">As previously shown in the help, piping a string to `Stop-Service` binds it **by value** to the **Name** parameter of `Stop-Service`.</span></span> <span data-ttu-id="e23c1-181">それをテストするために、`w32time` を `Stop-Service` にパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-181">Test this by piping `w32time` to `Stop-Service`.</span></span>

```powershell
'w32time' | Stop-Service
```

<span data-ttu-id="e23c1-182">前の例では、文字列 `w32time` を囲むのに単一引用符を使用したことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e23c1-182">Notice that in the previous example, I used single quotes around the string `w32time`.</span></span> <span data-ttu-id="e23c1-183">PowerShell では、引用符で囲まれた文字列の内容に、実際の値に拡張する必要がある変数が含まれていない限り、常に二重引用符ではなく一重引用符を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-183">In PowerShell, you should always use single quotes instead of double quotes unless the contents of the quoted string contains a variable that needs to be expanded to its actual value.</span></span> <span data-ttu-id="e23c1-184">一重引用符を使用することで、引用符で囲まれている内容を PowerShell が解析する必要がなくなり、コードの実行速度がわずかに向上します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-184">By using single quotes, PowerShell doesn't have to parse the contents contained within the quotes so your code runs a little faster.</span></span>

<span data-ttu-id="e23c1-185">カスタム オブジェクトを作成し、`Stop-Service` の **Name** パラメーターについてプロパティ名によるパイプライン入力をテストします。</span><span class="sxs-lookup"><span data-stu-id="e23c1-185">Create a custom object to test pipeline input by property name for the **Name** parameter of `Stop-Service`.</span></span>

```powershell
$CustomObject = [pscustomobject]@{
 Name = 'w32time'
 }
```

<span data-ttu-id="e23c1-186">**CustomObject** 変数の内容は **PSCustomObject** というオブジェクトの種類で、そこには **Name** という名前のプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e23c1-186">The contents of the **CustomObject** variable is a **PSCustomObject** object type and it contains a property named **Name**.</span></span>

```powershell
$CustomObject | Get-Member
```

```Output
   TypeName: System.Management.Automation.PSCustomObject

Name        MemberType   Definition
----        ----------   ----------
Equals      Method       bool Equals(System.Object obj)
GetHashCode Method       int GetHashCode()
GetType     Method       type GetType()
ToString    Method       string ToString()
Name        NoteProperty string Name=w32time
```

<span data-ttu-id="e23c1-187">`$CustomObject` 変数を引用符で囲む場合は、二重引用符を使用します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-187">If you were to surround the `$CustomObject` variable with quotes, you want to use double quotes.</span></span>
<span data-ttu-id="e23c1-188">そうしないと、リテラル文字列 `$CustomObject` は、変数で囲まれた値ではなく、`Get-Member` にパイプ処理されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-188">Otherwise, using single quotes, the literal string `$CustomObject` is piped to `Get-Member` instead of the value contained by the variable.</span></span>

<span data-ttu-id="e23c1-189">`$CustomObject` の内容を `Stop-Service` コマンドレットにパイプ処理すると **Name** パラメーターにバインドされますが、ここでは **値によって** ではなく **プロパティ名によって** バインドされます。`$CustomObject` の内容が、**Name** という名前のプロパティを備えたオブジェクトであるためです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-189">Although piping the contents of `$CustomObject` to `Stop-Service` cmdlet binds to the **Name** parameter, this time it binds **by property name** instead of **by value** because the contents of `$CustomObject` is an object that has a property named **Name**.</span></span>

<span data-ttu-id="e23c1-190">この例では、**Service** などの異なるプロパティ名を使用して、別のカスタム オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-190">In this example, I create another custom object using a different property name, such as **Service**.</span></span>

```powershell
$CustomObject = [pscustomobject]@{
  Service = 'w32time'
}
```

<span data-ttu-id="e23c1-191">`$CustomObject` を `Stop-Service` にパイプ処理しようとするとエラーが発生します。**ServiceController** または **String** のオブジェクトが生成されず、**Name** という名前のプロパティがないためです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-191">An error is generated when trying to pipe `$CustomObject` to `Stop-Service` because it doesn't produce a **ServiceController** or **String** object, and it doesn't have a property named **Name**.</span></span>

```powershell
$CustomObject | Stop-Service
```

```Output
Stop-Service : Cannot find any service with service name '@{Service=w32time}'.
At line:1 char:17
+ $CustomObject | Stop-Service
+
    + CategoryInfo          : ObjectNotFound: (@{Service=w32time}:String) [Stop-Service]
   , ServiceCommandException
    + FullyQualifiedErrorId : NoServiceFoundForGivenName,Microsoft.PowerShell.Commands.S
   topServiceCommand
```

<span data-ttu-id="e23c1-192">あるコマンドの出力が別のコマンドのパイプライン入力オプションと揃っていない場合は、プロパティの名前を変更するために `Select-Object` を使用できず、プロパティが正常に揃いません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-192">If the output of one command doesn't line up with the pipeline input options for another command, `Select-Object` can be used to rename the property so that the properties lineup correctly.</span></span>

```powershell
$CustomObject |
  Select-Object -Property @{name='Name';expression={$_.Service}} |
    Stop-Service
```

<span data-ttu-id="e23c1-193">この例では、**Service** プロパティを **Name** という名前のプロパティに変更するために `Select-Object` が使用されました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-193">In this example, `Select-Object` was used to rename the **Service** property to a property named **Name**.</span></span>

<span data-ttu-id="e23c1-194">この例の構文は、最初は少し複雑に思えるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-194">The syntax this example may seem a little complicated at first.</span></span> <span data-ttu-id="e23c1-195">私の経験によると、コードをコピーして貼り付けても構文を学ぶことはできません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-195">What I have learned is that you'll never learn the syntax by copy and pasting code.</span></span> <span data-ttu-id="e23c1-196">時間を取ってコードを入力してみてください。</span><span class="sxs-lookup"><span data-stu-id="e23c1-196">Take the time to type the code in.</span></span> <span data-ttu-id="e23c1-197">何度か入力した後に、自然と身に付きます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-197">After a few times, it becomes second nature.</span></span> <span data-ttu-id="e23c1-198">モニターが複数あると、一方の画面にサンプル コードを表示し、もう一方の画面でそれを入力することができるので、非常に便利です。</span><span class="sxs-lookup"><span data-stu-id="e23c1-198">Having multiple monitors is a huge benefit because you can display the example code on one screen and type it in on another one.</span></span>

<span data-ttu-id="e23c1-199">場合によっては、パイプライン入力を受け取らないパラメーターを使用したいことがあるかもしれません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-199">Occasionally, you may want to use a parameter that doesn't accept pipeline input.</span></span> <span data-ttu-id="e23c1-200">次の例では、あるコマンドの出力を別のコマンドの入力として使用する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-200">The following example demonstrates using the output of one command as input for another.</span></span> <span data-ttu-id="e23c1-201">最初に、いくつかの Windows サービスの表示名をテキスト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-201">First save the display name for a couple of Windows services into a text file.</span></span>

```powershell
'Background Intelligent Transfer Service', 'Windows Time' |
Out-File -FilePath $env:TEMP\services.txt
```

<span data-ttu-id="e23c1-202">丸かっこ内の必要な出力を、入力を必要とするコマンドのパラメーターの値として指定するコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-202">You can run the command that provides the needed output within parentheses as the value for the parameter of the command requiring the input.</span></span>

```powershell
Stop-Service -DisplayName (Get-Content -Path $env:TEMP\services.txt)
```

<span data-ttu-id="e23c1-203">これは、代数の演算を覚えている人にとっては、その順序と同じです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-203">This is just like order of operations in Algebra for those of you who remember how it works.</span></span> <span data-ttu-id="e23c1-204">丸かっこ内のコマンドは常に、コマンドの外側の部分よりも先に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-204">The command within parentheses always runs prior to the outer portion of the command.</span></span>

## <a name="powershellget"></a><span data-ttu-id="e23c1-205">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="e23c1-205">PowerShellGet</span></span>

<span data-ttu-id="e23c1-206">PowerShellGet は、NuGet リポジトリとの間で PowerShell モジュール (およびその他のアーティファクト) の検出、インストール、発行、更新を行うためのコマンドが含まれている PowerShell モジュールです。</span><span class="sxs-lookup"><span data-stu-id="e23c1-206">PowerShellGet is a PowerShell module that contains commands for discovering, installing, publishing, and updating PowerShell modules (and other artifacts) to or from a NuGet repository.</span></span> <span data-ttu-id="e23c1-207">PowerShellGet は、PowerShell バージョン5.0 以上に付属しています。</span><span class="sxs-lookup"><span data-stu-id="e23c1-207">PowerShellGet ships with PowerShell version 5.0 and higher.</span></span> <span data-ttu-id="e23c1-208">PowerShell バージョン3.0 以上については、個別のダウンロードとして入手できます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-208">It is available as a separate download for PowerShell version 3.0 and higher.</span></span>

<span data-ttu-id="e23c1-209">Microsoft は、[PowerShell ギャラリー][]と呼ばれるオンライン NuGet リポジトリをホストしています。</span><span class="sxs-lookup"><span data-stu-id="e23c1-209">Microsoft hosts an online NuGet repository called the [PowerShell Gallery][].</span></span> <span data-ttu-id="e23c1-210">このリポジトリは Microsoft によってホストされていますが、リポジトリ内に含まれているモジュールの大半は、Microsoft によって記述されたものではありません。</span><span class="sxs-lookup"><span data-stu-id="e23c1-210">Although this repository is hosted by Microsoft, the majority of the modules contained within the repository aren't written by Microsoft.</span></span> <span data-ttu-id="e23c1-211">PowerShell ギャラリーから入手したコードは、運用環境での使用に適していると見なす前に、分離されたテスト環境で十分に確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e23c1-211">Any code obtain from the PowerShell Gallery should be thoroughly reviewed in an isolated test environment before being considered suitable for use in a production environment.</span></span>

<span data-ttu-id="e23c1-212">ほとんどの企業では、独自の内部プライベート NuGet リポジトリをホストしようと考えます。そこには、社内専用のモジュールをポストしたり、他のソースからダウンロードしたモジュールを、悪意のないことを確認した後にポストしたりできます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-212">Most companies will want to host their own internal private NuGet repository where they can post their internal use only modules as well as modules that they've downloaded from other sources once they've validated them as being non-malicious.</span></span>

<span data-ttu-id="e23c1-213">PowerShellGet モジュールに含まれている `Find-Module` コマンドレットを使用して、PowerShell ギャラリーにある MrToolkit という名前のモジュールを検索します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-213">Use the `Find-Module` cmdlet that's part of the PowerShellGet module to find a module in the PowerShell Gallery that I wrote named MrToolkit.</span></span>

```powershell
Find-Module -Name MrToolkit
```

```Output
NuGet provider is required to continue
PowerShellGet requires NuGet provider version '2.8.5.201' or newer to interact with
NuGet-based repositories. The NuGet provider must be available in 'C:\Program
Files\PackageManagement\ProviderAssemblies' or
'C:\Users\MrAdmin\AppData\Local\PackageManagement\ProviderAssemblies'. You can also
install the NuGet provider by running 'Install-PackageProvider -Name NuGet
-MinimumVersion 2.8.5.201 -Force'. Do you want PowerShellGet to install and import the
NuGet provider now?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"):

Version    Name                                Repository           Description
-------    ----                                ----------           -----------
1.1        MrToolkit                           PSGallery            Misc PowerShell Tools
```

<span data-ttu-id="e23c1-214">PowerShellGet モジュールのいずれかのコマンドを初めて使用する際には、NuGet プロバイダーをインストールすることが求められます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-214">The first time you use one of the commands from the PowerShellGet module, you'll be prompted to install the NuGet provider.</span></span>

<span data-ttu-id="e23c1-215">MrToolkit モジュールをインストールするには、前のコマンドを `Install-Module` にパイプ処理します。</span><span class="sxs-lookup"><span data-stu-id="e23c1-215">To install the MrToolkit module, pipe the previous command to `Install-Module`.</span></span>

```powershell
Find-Module -Name MrToolkit | Install-Module
```

```Output
Untrusted repository
You are installing the modules from an untrusted repository. If you trust this
repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet.
Are you sure you want to install the modules from
'https://www.powershellgallery.com/api/v2/'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"): y
```

<span data-ttu-id="e23c1-216">PowerShell ギャラリーは信頼されていないリポジトリのため、モジュールのインストールを承認するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-216">Since the PowerShell Gallery is an untrusted repository, it prompts you to approve the installation of the module.</span></span>

## <a name="finding-pipeline-input-the-easy-way"></a><span data-ttu-id="e23c1-217">パイプラインの入力を確認する簡単な方法</span><span class="sxs-lookup"><span data-stu-id="e23c1-217">Finding pipeline input the easy way</span></span>

<span data-ttu-id="e23c1-218">MrToolkit モジュールには、`Get-MrPipelineInput` という名前の関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e23c1-218">The MrToolkit module contains a function named `Get-MrPipelineInput`.</span></span> <span data-ttu-id="e23c1-219">このコマンドレットを使用すると、コマンドのどのパラメーターがパイプライン入力を受け取るのか、それらが受け取るオブジェクトの種類は何か、**値** と **プロパティ名** のどちらによるパイプライン入力が受け取られるのかが、簡単に特定できます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-219">This cmdlet can be used to easily determine which parameters of a command accept pipeline input, what type of object they accept, and if they accept pipeline input **by value** or **by property name**.</span></span>

```powershell
Get-MrPipelineInput -Name Stop-Service
```

```Output
ParameterName ParameterType                             ValueFromPipeline ValueFromPipelineByPropertyName
------------- -------------                             ----------------- ---------------
InputObject   System.ServiceProcess.ServiceController[]              True           False
Name          System.String[]                                        True            True
```

<span data-ttu-id="e23c1-220">ご覧のとおり、この関数を使用すれば、先ほどヘルプを精査することで特定した情報を簡単に特定できます。</span><span class="sxs-lookup"><span data-stu-id="e23c1-220">As you can see, the same information we previously determined by sifting through the help can easily be determined with this function.</span></span>

## <a name="summary"></a><span data-ttu-id="e23c1-221">まとめ</span><span class="sxs-lookup"><span data-stu-id="e23c1-221">Summary</span></span>

<span data-ttu-id="e23c1-222">この章では、PowerShell ワンライナーについて学習しました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-222">In this chapter, you've learned about PowerShell one-liners.</span></span> <span data-ttu-id="e23c1-223">コマンドの物理的な行の数は、それが PowerShell ワンライナーであるかどうかに関係ないことを学習しました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-223">You've learned that the number of physical lines that a command is on has nothing to do with whether or not it's a PowerShell one-liner.</span></span> <span data-ttu-id="e23c1-224">また、左でのフィルター、パイプライン、PowerShellGet についても学習しました。</span><span class="sxs-lookup"><span data-stu-id="e23c1-224">You've also learned about filtering left, the pipeline, and PowerShellGet.</span></span>

## <a name="review"></a><span data-ttu-id="e23c1-225">確認</span><span class="sxs-lookup"><span data-stu-id="e23c1-225">Review</span></span>

1. <span data-ttu-id="e23c1-226">PowerShell ワンライナーとは何か。</span><span class="sxs-lookup"><span data-stu-id="e23c1-226">What is a PowerShell one-liner?</span></span>
1. <span data-ttu-id="e23c1-227">PowerShell で自然な改行が行われる可能性がある文字は何か。</span><span class="sxs-lookup"><span data-stu-id="e23c1-227">What are some of the characters where natural line breaks can occur in PowerShell?</span></span>
1. <span data-ttu-id="e23c1-228">左でフィルターする必要があるのはなぜか。</span><span class="sxs-lookup"><span data-stu-id="e23c1-228">Why should you filter left?</span></span>
1. <span data-ttu-id="e23c1-229">PowerShell コマンドでパイプライン入力を受け取る 2 つの方法は何か。</span><span class="sxs-lookup"><span data-stu-id="e23c1-229">What are the two ways that a PowerShell command can accept pipeline input?</span></span>
1. <span data-ttu-id="e23c1-230">PowerShell ギャラリーにあるコマンドを信頼すべきでないのはなぜか。</span><span class="sxs-lookup"><span data-stu-id="e23c1-230">Why shouldn't you trust commands found in the PowerShell Gallery?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="e23c1-231">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="e23c1-231">Recommended Reading</span></span>

- <span data-ttu-id="e23c1-232">[about_Pipelines][]</span><span class="sxs-lookup"><span data-stu-id="e23c1-232">[about_Pipelines][]</span></span>
- <span data-ttu-id="e23c1-233">[about_Command_Syntax][]</span><span class="sxs-lookup"><span data-stu-id="e23c1-233">[about_Command_Syntax][]</span></span>
- <span data-ttu-id="e23c1-234">[about_Parameters][]</span><span class="sxs-lookup"><span data-stu-id="e23c1-234">[about_Parameters][]</span></span>
- <span data-ttu-id="e23c1-235">[PowerShellGet: PowerShell モジュールを検出、インストール、更新する非常に簡単な方法][psget]</span><span class="sxs-lookup"><span data-stu-id="e23c1-235">[PowerShellGet: The BIG EASY way to discover, install, and update PowerShell modules][psget]</span></span>

<!-- link references-->
[about_Pipelines]: /powershell/module/microsoft.powershell.core/about/about_pipelines
[about_Command_Syntax]: /powershell/module/microsoft.powershell.core/about/about_command_syntax
[about_Parameters]: /powershell/module/microsoft.powershell.core/about/about_parameters
[psget]: https://mikefrobbins.com/2015/04/23/powershellget-the-big-easy-way-to-discover-install-and-update-powershell-modules/
[PowerShell ギャラリー]: https://www.powershellgallery.com/
[PowerShell Gallery]: https://www.powershellgallery.com/
