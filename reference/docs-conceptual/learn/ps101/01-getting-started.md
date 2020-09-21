---
title: PowerShell の概要
description: 新規ユーザー向けの PowerShell の場所と起動方法。
ms.date: 06/02/2020
ms.topic: guide
ms.custom: Contributor-mikefrobbins
ms.reviewer: mirobb
ms.openlocfilehash: e8938a5d36cd1c9c5a74eed1c22cd5d0e1a91966
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786749"
---
# <a name="chapter-1---getting-started-with-powershell"></a><span data-ttu-id="22db9-103">第 1 章 - PowerShell の概要</span><span class="sxs-lookup"><span data-stu-id="22db9-103">Chapter 1 - Getting Started with PowerShell</span></span>

<span data-ttu-id="22db9-104">カンファレンスやユーザー グループ ミーティングのプレゼンターがエントリレベルのプレゼンテーションを開始したときに既に PowerShell を実行していることに気付かされることはよくあります。</span><span class="sxs-lookup"><span data-stu-id="22db9-104">I often find that presenters at conferences and user group meetings already have PowerShell running when they start entry-level presentations.</span></span> <span data-ttu-id="22db9-105">このドキュメントでは、そういったセッションでこれまで PowerShell を使用したことのない参加者から寄せられた質問に回答することから始めます。</span><span class="sxs-lookup"><span data-stu-id="22db9-105">This book begins by answering the questions I've heard attendees who haven't previously used PowerShell ask in those sessions.</span></span>

<span data-ttu-id="22db9-106">具体的には、この章では、PowerShell を見つけて起動すること、および PowerShell の新しいユーザーが経験する最初の問題のいくつかを解決することに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="22db9-106">Specifically, this chapter focuses on finding and launching PowerShell, and solving some of the initial pain points that new users experience with PowerShell.</span></span> <span data-ttu-id="22db9-107">お使いの Windows 10 ラボ環境コンピューターで、この章に示されている例の手順を必ず実行してください。</span><span class="sxs-lookup"><span data-stu-id="22db9-107">Be sure to follow along and walk through the examples shown in this chapter on your Windows 10 lab environment computer.</span></span>

## <a name="what-do-i-need-to-get-started-with-powershell"></a><span data-ttu-id="22db9-108">PowerShell を使い始めるには何が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="22db9-108">What do I need to get started with PowerShell?</span></span>

<span data-ttu-id="22db9-109">Windows オペレーティング システムのすべての最新バージョンには、PowerShell がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="22db9-109">All modern versions of Windows operating systems ship with PowerShell installed.</span></span> <span data-ttu-id="22db9-110">5\.1 より前のバージョンを実行している場合は、最新バージョンをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="22db9-110">If you're running a version older than 5.1, you should install the latest version.</span></span>

- <span data-ttu-id="22db9-111">Windows PowerShell 5.1 にアップグレードするには、「[既存の Windows PowerShell をアップグレードする][]」を参照してください</span><span class="sxs-lookup"><span data-stu-id="22db9-111">To upgrade to Windows PowerShell 5.1, see [Upgrading existing Windows PowerShell][]</span></span>
- <span data-ttu-id="22db9-112">PowerShell の最新バージョンをインストールするには、[PowerShell のインストール][]に関するページを参照してください</span><span class="sxs-lookup"><span data-stu-id="22db9-112">To install the latest version of PowerShell, see [Installing PowerShell][]</span></span>

## <a name="where-do-i-find-powershell"></a><span data-ttu-id="22db9-113">PowerShell はどこにありますか?</span><span class="sxs-lookup"><span data-stu-id="22db9-113">Where do I find PowerShell?</span></span>

<span data-ttu-id="22db9-114">Windows 10 で PowerShell を見つける最も簡単な方法は、図 1-1 に示すように、検索バーに「**PowerShell**」と入力することです。</span><span class="sxs-lookup"><span data-stu-id="22db9-114">The easiest way to find PowerShell on Windows 10 is to type **PowerShell** into the search bar as shown in Figure 1-1.</span></span>

![図 1-1 - [スタート] メニューでの PowerShell の検索](media/figure1-1.png)

<span data-ttu-id="22db9-116">図 1-1 には PowerShell の 4 つの異なるショートカットが示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22db9-116">Notice that four different shortcuts for PowerShell are shown in Figure 1-1.</span></span> <span data-ttu-id="22db9-117">このドキュメントでデモに使用しているコンピューターでは、64 ビット バージョンの Windows 10 が実行されています。そのため、64 ビット バージョンの PowerShell コンソールと PowerShell ISE (統合スクリプト環境) に加え、その 32 ビット バージョンがそれぞれあります (ショートカットの (x86) サフィックスで示されます)。</span><span class="sxs-lookup"><span data-stu-id="22db9-117">The computer used for demonstration purposes in this book is running the 64-bit version of Windows 10 so there's a 64-bit version of the PowerShell console and the PowerShell ISE (Integrated Scripting Environment), and a 32-bit version of each one as denoted by the (x86) suffix on the shortcuts.</span></span> <span data-ttu-id="22db9-118">32 ビット バージョンの Windows 10 を実行している場合は、2 つのショートカットだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22db9-118">If you happen to be running a 32-bit version of Windows 10, you'll only have two shortcuts.</span></span> <span data-ttu-id="22db9-119">これらの項目には (x86) サフィックスはありませんが、32 ビット バージョンです。</span><span class="sxs-lookup"><span data-stu-id="22db9-119">Those items don't have the (x86) suffix, but are 32-bit versions.</span></span> <span data-ttu-id="22db9-120">64 ビットのオペレーティング システムを使用している場合は、32 ビット バージョンを実行する特別な理由がない限り、64 ビット バージョンの PowerShell を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22db9-120">If you have a 64-bit operating system, my recommendation is to run the 64-bit version of PowerShell unless you have a specific reason for running the 32-bit version.</span></span>

<span data-ttu-id="22db9-121">他のバージョンの Windows で PowerShell を起動する方法については、「[Windows PowerShell の開始][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22db9-121">For information about starting PowerShell on other versions of Windows, see [Starting Windows PowerShell][].</span></span>

## <a name="how-do-i-launch-powershell"></a><span data-ttu-id="22db9-122">PowerShell を起動するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="22db9-122">How do I launch PowerShell?</span></span>

<span data-ttu-id="22db9-123">私がサポートする運用エンタープライズ環境では、3 つの異なる Active Directory ユーザー アカウントを使用しています。</span><span class="sxs-lookup"><span data-stu-id="22db9-123">In the production enterprise environments that I support, I use three different Active Directory user accounts.</span></span> <span data-ttu-id="22db9-124">このドキュメントで使用しているラボ環境には、これらのアカウントが複製されています。</span><span class="sxs-lookup"><span data-stu-id="22db9-124">I've mirrored those accounts in the lab environment used in this book.</span></span> <span data-ttu-id="22db9-125">ドメイン管理者でもローカル管理者でもない、ドメイン ユーザーとして Windows 10 コンピューターにログインします。</span><span class="sxs-lookup"><span data-stu-id="22db9-125">I log into the Windows 10 computer as a domain user who is not a domain or local administrator.</span></span>

<span data-ttu-id="22db9-126">私は、図 1-1 に示すように、[Windows PowerShell] ショートカットをクリックして PowerShell コンソールを起動しました。</span><span class="sxs-lookup"><span data-stu-id="22db9-126">I've launched the PowerShell console by clicking on the "Windows PowerShell" shortcut as shown in Figure 1-1.</span></span>

![図 1-4 - PowerShell ウィンドウのタイトル バー](media/figure1-4.png)

<span data-ttu-id="22db9-128">図 1-4 に示すように、PowerShell コンソールのタイトル バーに "Windows PowerShell" と表示されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22db9-128">Notice that the title bar of the PowerShell console says "Windows PowerShell" as shown in Figure 1-4.</span></span> <span data-ttu-id="22db9-129">一部のコマンドは正常に実行されますが、PowerShell をユーザー アクセス制御 (UAC) に参加させることはできません。</span><span class="sxs-lookup"><span data-stu-id="22db9-129">Some commands run fine, but PowerShell can't participate in User Access Control (UAC).</span></span> <span data-ttu-id="22db9-130">つまり、管理者の承認を必要とするタスクの昇格を要求することはできません。</span><span class="sxs-lookup"><span data-stu-id="22db9-130">That means it's unable to prompt for elevation for tasks that require the approval of an administrator.</span></span>
<span data-ttu-id="22db9-131">次のエラー メッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="22db9-131">The following error message is generated:</span></span>

```powershell
Get-Service -Name W32Time | Stop-Service
```

```Output
Stop-Service : Service 'Windows Time (W32Time)' cannot be stopped due to the following
error: Cannot open W32Time service on computer '.'.
At line:1 char:29
+ Get-Service -Name W32Time | Stop-Service
+
    + CategoryInfo          : CloseError: (System.ServiceProcess.ServiceController:ServiceController)
     [Stop-Service], ServiceCommandException
    + FullyQualifiedErrorId : CouldNotStopService,Microsoft.PowerShell.Commands.StopServiceCommand
```

<span data-ttu-id="22db9-132">この問題の解決策は、ローカル管理者であるドメイン ユーザーとして PowerShell を実行することです。</span><span class="sxs-lookup"><span data-stu-id="22db9-132">The solution to this problem is to run PowerShell as a domain user who is a local administrator.</span></span>
<span data-ttu-id="22db9-133">これが、私の 2 番目のドメイン ユーザー アカウントの構成方法です。</span><span class="sxs-lookup"><span data-stu-id="22db9-133">This is how my second domain user account is configured.</span></span> <span data-ttu-id="22db9-134">最小限の特権の原則に従って、このアカウントはドメイン管理者にしたり、ドメイン内で昇格された特権を与えたりしないようにします。</span><span class="sxs-lookup"><span data-stu-id="22db9-134">Using the principal of least privilege, this account should NOT be a domain administrator, or have any elevated privileges in the domain.</span></span>

<span data-ttu-id="22db9-135">PowerShell を閉じます。</span><span class="sxs-lookup"><span data-stu-id="22db9-135">Close PowerShell.</span></span> <span data-ttu-id="22db9-136">PowerShell コンソールを再起動します。ただし、今回は、図 1-5 に示すように **[Windows PowerShell]** ショートカットを右クリックし、 **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22db9-136">Relaunch the PowerShell console, except this time right-click on the **Windows PowerShell** shortcut and select **Run as administrator** as shown in Figure 1-5.</span></span>

![図 1-5 - コンテキスト メニュー - [管理者として実行]](media/figure1-5.png)

<span data-ttu-id="22db9-138">通常のユーザーとして Windows にログインしている場合は、資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="22db9-138">If you're logged into Windows as a normal user, you'll be prompted for credentials.</span></span> <span data-ttu-id="22db9-139">図 1-6 に示すように、ドメイン ユーザーとローカル管理者であるユーザー アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="22db9-139">I'll enter the credentials for my user account who is a domain user and local admin as shown in Figure 1-6.</span></span>

![図 1-6](media/figure1-6.png)

<span data-ttu-id="22db9-141">PowerShell が管理者として再起動されると、タイトル バーに "管理者: Windows PowerShell" と表示されます (図 1-7)。</span><span class="sxs-lookup"><span data-stu-id="22db9-141">Once PowerShell is relaunched as an administrator, the title bar should say "Administrator: Windows PowerShell" as shown in Figure 1-7.</span></span>

![図 1-7](media/figure1-7.png)

<span data-ttu-id="22db9-143">これで PowerShell がローカル管理者として管理者特権で実行されるようになったので、通常はローカル コンピューター上で昇格のプロンプトを必要とするコマンドを実行したときに UAC が問題にならなくなります。</span><span class="sxs-lookup"><span data-stu-id="22db9-143">Now that PowerShell is being run elevated as a local administrator, UAC will no longer be a problem when a command is run on the local computer that would normally require a prompt for elevation.</span></span> <span data-ttu-id="22db9-144">このとき、PowerShell コンソールの管理者特権のインスタンスから実行されるすべてのコマンドが管理者特権で実行されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22db9-144">Keep in mind though that any command run from this elevated instance of the PowerShell console, also runs elevated.</span></span>

<span data-ttu-id="22db9-145">PowerShell を見つけて管理者として起動する作業を簡単にするために、タスク バーにピン留めし、実行するたびに管理者として自動的に起動されるように設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22db9-145">To simplify finding PowerShell and launching it as an administrator, I recommend pinning it to the taskbar and setting it to automatically launch as an admin each time it's run.</span></span>

<span data-ttu-id="22db9-146">PowerShell をもう一度検索します。ただし今回は、図 1-8 に示すように、右クリックし、[タスク バーにピン留めする] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22db9-146">Search for PowerShell again, except this time right-click on it and select "Pin to taskbar" as shown in Figure 1-8.</span></span>

![図 1-8](media/figure1-8.png)

<span data-ttu-id="22db9-148">タスク バーにピン留めされた PowerShell ショートカットを右クリックし、図 1-9 に示すように [プロパティ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22db9-148">Right-click on the PowerShell shortcut that's now pinned to the taskbar and select properties as shown in Figure 1-9.</span></span>

![図 1-9 - [ユーザー アカウント制御] - [資格情報を入力]](media/figure1-9.png)

<span data-ttu-id="22db9-150">図 1-10 の番号 1 で示されている [詳細設定] をクリックし、図 1-10 の番号 2 で示されている [管理者として実行] チェック ボックスをオンにします。[OK] を 2 回クリックして変更を受け入れ、両方のダイアログ ボックスを終了します。</span><span class="sxs-lookup"><span data-stu-id="22db9-150">Click on "Advanced" as denoted by #1 in Figure 1-10, then check the "Run as administrator" checkbox as denoted by #2 in Figure 1-10, and then click OK twice to accept the changes and exit out of both dialog boxes.</span></span>

![図 1-10 - "管理者" と表示されているタイトル バー](media/figure1-10.png)

<span data-ttu-id="22db9-152">これで、PowerShell を見つけることや PowerShell が管理者として実行されているかどうかについて再び心配する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="22db9-152">You'll never have to worry about finding PowerShell or whether or not it's running as an administrator again.</span></span>

<span data-ttu-id="22db9-153">管理者特権で PowerShell を実行して UAC に関する問題を回避した場合、ローカル コンピューターに対して実行されるコマンドのみが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="22db9-153">Running PowerShell elevated as an administrator to prevent having problems with UAC only impacts commands that are run against the local computer.</span></span> <span data-ttu-id="22db9-154">リモート コンピューターをターゲットとするコマンドは影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="22db9-154">It has no effect on commands that target remote computers.</span></span>

## <a name="what-version-of-powershell-am-i-running"></a><span data-ttu-id="22db9-155">実行されている PowerShell のバージョンは何ですか?</span><span class="sxs-lookup"><span data-stu-id="22db9-155">What version of PowerShell am I running?</span></span>

<span data-ttu-id="22db9-156">PowerShell には、状態情報を格納するための自動変数が多数あります。</span><span class="sxs-lookup"><span data-stu-id="22db9-156">There are a number of automatic variables in PowerShell that store state information.</span></span> <span data-ttu-id="22db9-157">これらの変数の 1 つに `$PSVersionTable` があります。これには、関連する PowerShell のバージョン情報を表示するために使用できるハッシュテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="22db9-157">One of these variables is `$PSVersionTable`, which contains a hashtable that can be used to display the relevant PowerShell version information:</span></span>

```powershell
$PSVersionTable
```

```Output
Name                           Value
----                           -----
PSVersion                      5.1.19041.1
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
BuildVersion                   10.0.19041.1
CLRVersion                     4.0.30319.42000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

<span data-ttu-id="22db9-158">Windows PowerShell の新しいバージョンは、Windows Management Framework (WMF) の一部として配布されます。</span><span class="sxs-lookup"><span data-stu-id="22db9-158">Newer versions of Windows PowerShell are distributed as part of the Windows Management Framework (WMF).</span></span> <span data-ttu-id="22db9-159">WMF のバージョンによっては、.NET Framework の特定のバージョンが必要になります。</span><span class="sxs-lookup"><span data-stu-id="22db9-159">A specific version of the .NET Framework is required depending on the WMF version.</span></span> <span data-ttu-id="22db9-160">Windows PowerShell 5.1 にアップグレードするには、「[既存の Windows PowerShell をアップグレードする][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22db9-160">To upgrade to Windows PowerShell 5.1, see [Upgrading existing Windows PowerShell][].</span></span>

## <a name="execution-policy"></a><span data-ttu-id="22db9-161">実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="22db9-161">Execution Policy</span></span>

<span data-ttu-id="22db9-162">一般的な考えとは異なり、PowerShell の実行ポリシーはセキュリティ境界ではありません。</span><span class="sxs-lookup"><span data-stu-id="22db9-162">Contrary to popular belief, the execution policy in PowerShell is not a security boundary.</span></span> <span data-ttu-id="22db9-163">これは、ユーザーが無意識のうちにスクリプトを実行するのを防ぐように設計されています。</span><span class="sxs-lookup"><span data-stu-id="22db9-163">It's designed to prevent a user from unknowingly running a script.</span></span> <span data-ttu-id="22db9-164">ユーザーは、その気になれば PowerShell の実行ポリシーを簡単にバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="22db9-164">A determined user can easily bypass the execution policy in PowerShell.</span></span> <span data-ttu-id="22db9-165">表 1-2 に、現在の Windows オペレーティング システムの既定の実行ポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="22db9-165">Table 1-2 shows the default execution policy for current Windows operating systems.</span></span>

| <span data-ttu-id="22db9-166">Windows オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="22db9-166">Windows Operating System Version</span></span> | <span data-ttu-id="22db9-167">既定の実行ポリシー</span><span class="sxs-lookup"><span data-stu-id="22db9-167">Default Execution Policy</span></span> |
| -------------------------------- | ------------------------ |
| <span data-ttu-id="22db9-168">Server 2019</span><span class="sxs-lookup"><span data-stu-id="22db9-168">Server 2019</span></span>                      | <span data-ttu-id="22db9-169">リモート署名</span><span class="sxs-lookup"><span data-stu-id="22db9-169">Remote Signed</span></span>            |
| <span data-ttu-id="22db9-170">Server 2016</span><span class="sxs-lookup"><span data-stu-id="22db9-170">Server 2016</span></span>                      | <span data-ttu-id="22db9-171">リモート署名</span><span class="sxs-lookup"><span data-stu-id="22db9-171">Remote Signed</span></span>            |
| <span data-ttu-id="22db9-172">Windows 10</span><span class="sxs-lookup"><span data-stu-id="22db9-172">Windows 10</span></span>                       | <span data-ttu-id="22db9-173">制限付き</span><span class="sxs-lookup"><span data-stu-id="22db9-173">Restricted</span></span>               |

<span data-ttu-id="22db9-174">実行ポリシーの設定に関係なく、すべての PowerShell コマンドは対話的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="22db9-174">Regardless of the execution policy setting, any PowerShell command can be run interactively.</span></span> <span data-ttu-id="22db9-175">実行ポリシーは、スクリプト内で実行されているコマンドにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="22db9-175">The execution policy only affects commands running in a script.</span></span> <span data-ttu-id="22db9-176">`Get-ExecutionPolicy` コマンドレットは、現在の実行ポリシー設定を確認するために使用します。`Set-ExecutionPolicy` コマンドレットは、実行ポリシーを変更するために使用します。</span><span class="sxs-lookup"><span data-stu-id="22db9-176">The `Get-ExecutionPolicy` cmdlet is used to determine what the current execution policy setting is and the `Set-ExecutionPolicy` cmdlet is used to change the execution policy.</span></span> <span data-ttu-id="22db9-177">お勧めは、**RemoteSigned** ポリシーを使用することです。これを使用すると、ダウンロードしたスクリプトを実行する際に、スクリプトが信頼できる公開元によって署名されていることが求められます。</span><span class="sxs-lookup"><span data-stu-id="22db9-177">My recommendation is to use the **RemoteSigned** policy, which requires downloaded scripts to be signed by a trusted publisher in order to be run.</span></span>

<span data-ttu-id="22db9-178">現在の実行ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="22db9-178">Check the current execution policy:</span></span>

```powershell
Get-ExecutionPolicy
```

```Output
Restricted
```

<span data-ttu-id="22db9-179">実行ポリシーが **Restricted** に設定されている場合は、PowerShell スクリプトをまったく実行できません。</span><span class="sxs-lookup"><span data-stu-id="22db9-179">PowerShell scripts can't be run at all when the execution policy is set to **Restricted**.</span></span> <span data-ttu-id="22db9-180">これは、すべての Windows クライアント オペレーティング システムの既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="22db9-180">This is the default setting on all Windows client operating systems.</span></span> <span data-ttu-id="22db9-181">この問題を実証するために、次のコードを `Stop-TimeService.ps1` という名前の `.ps1` ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="22db9-181">To demonstrate the problem, save the following code as a `.ps1` file named `Stop-TimeService.ps1`.</span></span>

```powershell
Get-Service -Name W32Time | Stop-Service -PassThru
```

<span data-ttu-id="22db9-182">このコマンドは、PowerShell が管理者特権で実行されている限り、エラーなしで対話的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="22db9-182">That command runs interactively without error as long as PowerShell is run elevated as an administrator.</span></span> <span data-ttu-id="22db9-183">しかし、これをスクリプト ファイルとして保存し、スクリプトを実行しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="22db9-183">But as soon as it's saved as a script file and you try to execute the script, it generates an error:</span></span>

```powershell
.\Stop-TimeService.ps1
```

```Output
.\Stop-TimeService.ps1 : File C:\demo\Stop-TimeService.ps1 cannot be loaded because
running scripts is disabled on this system. For more information, see
about_Execution_Policies at http://go.microsoft.com/fwlink/?LinkID=135170.
At line:1 char:1
+ .\Stop-TimeService.ps1
+
    + CategoryInfo          : SecurityError: (:) [], PSSecurityException
    + FullyQualifiedErrorId : UnauthorizedAccess
```

<span data-ttu-id="22db9-184">前の結果のセットに示されているエラー "running scripts is disabled on this system" (このシステムではスクリプトの実行が無効になっています) から問題の内容が正確にわかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22db9-184">Notice that the error shown in the previous set of results tells you exactly what the problem is (running scripts is disabled on this system).</span></span> <span data-ttu-id="22db9-185">PowerShell でエラー メッセージを生成するコマンドを実行する場合は、コマンドを再実行して正常に実行されることを期待するのではなく、必ずエラー メッセージを読んでください。</span><span class="sxs-lookup"><span data-stu-id="22db9-185">When you run a command in PowerShell that generates an error message, be sure to read the error message instead of just rerunning the command and hoping that it runs successfully.</span></span>

<span data-ttu-id="22db9-186">PowerShell 実行ポリシーを "リモート署名" に変更します。</span><span class="sxs-lookup"><span data-stu-id="22db9-186">Change the PowerShell execution policy to remote signed.</span></span>

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

```Output
Execution Policy Change
The execution policy helps protect you from scripts that you do not trust. Changing the execution
policy might expose you to the security risks described in the about_Execution_Policies help topic
at http://go.microsoft.com/fwlink/?LinkID=135170. Do you want to change the execution policy?
[Y] Yes [A] Yes to All [N] No [L] No to All [S] Suspend [?] Help (default is "N"):y
```

<span data-ttu-id="22db9-187">実行ポリシーを変更するときは、表示される警告を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="22db9-187">Be sure to read the warning that's displayed when changing the execution policy.</span></span> <span data-ttu-id="22db9-188">また、[about_Execution_Policies][] のヘルプ トピックを参照して、実行ポリシーを変更した場合のセキュリティへの影響を理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22db9-188">I also recommend taking a look at the [about_Execution_Policies][] help topic to make sure you understand the security implications of changing the execution policy.</span></span>

<span data-ttu-id="22db9-189">実行ポリシーが **RemoteSigned** に設定されたので、`Stop-TimeService.ps1` スクリプトはエラーなしで実行されます。</span><span class="sxs-lookup"><span data-stu-id="22db9-189">Now that the execution policy has been set to **RemoteSigned**, the `Stop-TimeService.ps1` script runs error free.</span></span>

```powershell
.\Stop-TimeService.ps1
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  W32Time            Windows Time
```

<span data-ttu-id="22db9-190">続行する前に Windows タイム サービスを開始してください。そうしないと、予期しない問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22db9-190">Be sure to start your Windows Time service before continuing otherwise you may run into unforeseen problems.</span></span>

```powershell
Start-Service -Name w32time
```

## <a name="summary"></a><span data-ttu-id="22db9-191">まとめ</span><span class="sxs-lookup"><span data-stu-id="22db9-191">Summary</span></span>

<span data-ttu-id="22db9-192">この章では、PowerShell を見つけて起動する方法と、PowerShell を管理者として起動するショートカットを作成する方法を学習しました。</span><span class="sxs-lookup"><span data-stu-id="22db9-192">In this chapter, you've learned how to find and launch PowerShell, and how to create a shortcut that launches PowerShell as an administrator.</span></span> <span data-ttu-id="22db9-193">また、既定の実行ポリシーとその変更方法についても学習しました。</span><span class="sxs-lookup"><span data-stu-id="22db9-193">You've also learned about the default execution policy and how to change it.</span></span>

## <a name="review"></a><span data-ttu-id="22db9-194">確認</span><span class="sxs-lookup"><span data-stu-id="22db9-194">Review</span></span>

1. <span data-ttu-id="22db9-195">コンピューターで実行されている PowerShell のバージョンを確認するにはどうすればよいか。</span><span class="sxs-lookup"><span data-stu-id="22db9-195">How do you determine what PowerShell version a computer is running?</span></span>
1. <span data-ttu-id="22db9-196">管理者特権で PowerShell を起動することが重要なのはなぜか。</span><span class="sxs-lookup"><span data-stu-id="22db9-196">Why is it important to launch PowerShell elevated as an administrator?</span></span>
1. <span data-ttu-id="22db9-197">現在の PowerShell 実行ポリシーを確認するにはどうすればよいか。</span><span class="sxs-lookup"><span data-stu-id="22db9-197">How do you determine the current PowerShell execution policy?</span></span>
1. <span data-ttu-id="22db9-198">Windows クライアント コンピューターの既定の PowerShell 実行ポリシーでは、どのような操作が回避されるか。</span><span class="sxs-lookup"><span data-stu-id="22db9-198">What does the default PowerShell execution policy on Windows client computers prevent from occurring?</span></span>
1. <span data-ttu-id="22db9-199">PowerShell 実行ポリシーを変更するにはどうすればよいか。</span><span class="sxs-lookup"><span data-stu-id="22db9-199">How do you change the PowerShell execution policy?</span></span>

## <a name="recommended-reading"></a><span data-ttu-id="22db9-200">推奨トピック</span><span class="sxs-lookup"><span data-stu-id="22db9-200">Recommended Reading</span></span>

<span data-ttu-id="22db9-201">この章で説明しているトピックについてもっと詳しく知りたい方は、次の PowerShell のヘルプ トピックを読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="22db9-201">For those who want to know more information about the topics covered in this chapter, I recommend reading the following PowerShell help topics.</span></span>

- <span data-ttu-id="22db9-202">[about_Automatic_Variables][]</span><span class="sxs-lookup"><span data-stu-id="22db9-202">[about_Automatic_Variables][]</span></span>
- <span data-ttu-id="22db9-203">[about_Hash_Tables][]</span><span class="sxs-lookup"><span data-stu-id="22db9-203">[about_Hash_Tables][]</span></span>
- <span data-ttu-id="22db9-204">[about_Execution_Policies][]</span><span class="sxs-lookup"><span data-stu-id="22db9-204">[about_Execution_Policies][]</span></span>

<span data-ttu-id="22db9-205">次の章では、PowerShell のコマンドの見つけやすさについて学習します。</span><span class="sxs-lookup"><span data-stu-id="22db9-205">In the next chapter, you'll learn about the discoverability of commands in PowerShell.</span></span> <span data-ttu-id="22db9-206">扱われている項目の 1 つでは、PowerShell を更新して、これらのヘルプ トピックをインターネットで表示する代わりに PowerShell 内から直接表示できるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="22db9-206">One of the things that will be covered is how to update PowerShell so those help topics can be viewed right from within PowerShell instead of having to view them on the internet.</span></span>

<!-- link references -->
[about_Automatic_Variables]: /powershell/module/microsoft.powershell.core/about/about_automatic_variables
[about_Hash_Tables]: /powershell/module/microsoft.powershell.core/about/about_hash_tables
[about_Execution_Policies]: /powershell/module/microsoft.powershell.core/about/about_execution_policies
[既存の Windows PowerShell をアップグレードする]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[Upgrading existing Windows PowerShell]: /powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell
[PowerShell のインストール]: /powershell/scripting/install/installing-powershell
[Installing PowerShell]: /powershell/scripting/install/installing-powershell
[Windows PowerShell の開始]: /powershell/scripting/windows-powershell/starting-windows-powershell
[Starting Windows PowerShell]: /powershell/scripting/windows-powershell/starting-windows-powershell
