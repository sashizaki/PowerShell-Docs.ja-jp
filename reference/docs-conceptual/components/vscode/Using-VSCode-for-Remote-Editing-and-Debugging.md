---
title: Visual Studio Code を使用したリモート編集およびデバッグ
description: Visual Studio Code を使用したリモート編集およびデバッグ
ms.date: 08/06/2018
ms.openlocfilehash: fbc1ee3556e822b4afb2b37111d0688dc89fdab3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086675"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a><span data-ttu-id="f989c-103">Visual Studio Code を使用したリモート編集およびデバッグ</span><span class="sxs-lookup"><span data-stu-id="f989c-103">Using Visual Studio Code for remote editing and debugging</span></span>

<span data-ttu-id="f989c-104">ISE に精通している場合、統合コンソールから `psedit file.ps1` を実行してファイル (ローカルまたはリモート) を ISE で開くことができたことを憶えているかもしれません。</span><span class="sxs-lookup"><span data-stu-id="f989c-104">For those of you that were familiar with the ISE, you may recall that you could run `psedit file.ps1` from the integrated console to open files - local or remote - right in the ISE.</span></span>

<span data-ttu-id="f989c-105">この機能は、VSCode 用の PowerShell 拡張機能でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="f989c-105">As it turns out, this feature is also available in the PowerShell extension for VSCode.</span></span> <span data-ttu-id="f989c-106">このガイドではそれを行う方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="f989c-106">This guide will show you how to do it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f989c-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="f989c-107">Prerequisites</span></span>

<span data-ttu-id="f989c-108">このガイドでは、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="f989c-108">This guide assumes that you have:</span></span>

- <span data-ttu-id="f989c-109">アクセスできるリモート リソース (例: VM、コンテナー)</span><span class="sxs-lookup"><span data-stu-id="f989c-109">a remote resource (ex: a VM, a container) that you have access to</span></span>
- <span data-ttu-id="f989c-110">その上で実行する PowerShell およびホスト マシン</span><span class="sxs-lookup"><span data-stu-id="f989c-110">PowerShell running on it and the host machine</span></span>
- <span data-ttu-id="f989c-111">VSCode および VSCode 用 PowerShell 拡張機能</span><span class="sxs-lookup"><span data-stu-id="f989c-111">VSCode and the PowerShell extension for VSCode</span></span>

<span data-ttu-id="f989c-112">この機能は、Windows PowerShell と PowerShell Core で動作します。</span><span class="sxs-lookup"><span data-stu-id="f989c-112">This feature works on Windows PowerShell and PowerShell Core.</span></span>

<span data-ttu-id="f989c-113">また、この機能は、WinRM、PowerShell Direct、または SSH でリモート マシンに接続しているときにも動作します。</span><span class="sxs-lookup"><span data-stu-id="f989c-113">This feature also works when connecting to a remote machine via WinRM, PowerShell Direct, or SSH.</span></span> <span data-ttu-id="f989c-114">SSH を使用したいが、Windows を使用している場合は、[SSH の Win32 バージョン](https://github.com/PowerShell/Win32-OpenSSH)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="f989c-114">If you want to use SSH, but are using Windows, check out the [Win32 version of SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span></span>

## <a name="lets-go"></a><span data-ttu-id="f989c-115">始めましょう</span><span class="sxs-lookup"><span data-stu-id="f989c-115">Let's go</span></span>

<span data-ttu-id="f989c-116">このセクションでは、MacBook Pro から Azure で実行されている Ubuntu VM に対するリモート編集およびデバッグの手順を紹介します。</span><span class="sxs-lookup"><span data-stu-id="f989c-116">In this section, I'll walk through remote editing and debugging from my MacBook Pro, to an Ubuntu VM running in Azure.</span></span> <span data-ttu-id="f989c-117">Windows を使用する場合も**プロセスと同じです**。</span><span class="sxs-lookup"><span data-stu-id="f989c-117">I might not be using Windows, but **the process is identical**.</span></span>

### <a name="local-file-editing-with-open-editorfile"></a><span data-ttu-id="f989c-118">Open-EditorFile でのローカル ファイル編集</span><span class="sxs-lookup"><span data-stu-id="f989c-118">Local file editing with Open-EditorFile</span></span>

<span data-ttu-id="f989c-119">VSCode 用 PowerShell 拡張機能を開始し、PowerShell 統合コンソールを開くと、「`Open-EditorFile foo.ps1`」または「`psedit foo.ps1`」と入力してエディターでローカル環境の foo.ps1 ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="f989c-119">With the PowerShell extension for VSCode started and the PowerShell Integrated Console opened, we can type `Open-EditorFile foo.ps1` or `psedit foo.ps1` to open the local foo.ps1 file right in the editor.</span></span>

![ローカルに動作する Open-EditorFile foo.ps1](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> <span data-ttu-id="f989c-121">foo.ps1 が既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f989c-121">foo.ps1 must already exist.</span></span>

<span data-ttu-id="f989c-122">そこから次のことができます。</span><span class="sxs-lookup"><span data-stu-id="f989c-122">From there, we can:</span></span>

<span data-ttu-id="f989c-123">余白にブレークポイントを追加します![余白にブレークポイントを追加](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span><span class="sxs-lookup"><span data-stu-id="f989c-123">add breakpoints to the gutter ![adding breakpoint to gutter](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span></span>

<span data-ttu-id="f989c-124">F5 キーを押して PowerShell スクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="f989c-124">and hit F5 to debug the PowerShell script.</span></span>
<span data-ttu-id="f989c-125">![ローカルの PowerShell スクリプトのデバッグ](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span><span class="sxs-lookup"><span data-stu-id="f989c-125">![debugging the PowerShell local script](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span></span>

<span data-ttu-id="f989c-126">デバッグ中に、デバッグ コンソールと対話し、左側でスコープ内の変数を確認し、他のすべての標準デバッグ ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f989c-126">While debugging, you can interact with the debug console, check out the variables in the scope on the left, and all the other standard debugging tools.</span></span>

### <a name="remote-file-editing-with-open-editorfile"></a><span data-ttu-id="f989c-127">Open-EditorFile でのリモート ファイル編集</span><span class="sxs-lookup"><span data-stu-id="f989c-127">Remote file editing with Open-EditorFile</span></span>

<span data-ttu-id="f989c-128">次に、リモート ファイルを編集してデバッグします。</span><span class="sxs-lookup"><span data-stu-id="f989c-128">Now let's get into remote file editing and debugging.</span></span> <span data-ttu-id="f989c-129">手順はほぼ同じですが、最初に行う必要があることが 1 つだけあります。リモート サーバーへの PowerShell セッションに入ります。</span><span class="sxs-lookup"><span data-stu-id="f989c-129">The steps are nearly the same, there's just one thing we need to do first - enter our PowerShell session to the remote server.</span></span>

<span data-ttu-id="f989c-130">それを行うためのコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="f989c-130">There's a cmdlet for to do so.</span></span> <span data-ttu-id="f989c-131">`Enter-PSSession` です。</span><span class="sxs-lookup"><span data-stu-id="f989c-131">It's called `Enter-PSSession`.</span></span>

<span data-ttu-id="f989c-132">コマンドレットの簡単な説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f989c-132">The watered down explanation of the cmdlet is:</span></span>

- <span data-ttu-id="f989c-133">`Enter-PSSession -ComputerName foo` は WinRM でセッションを開始します</span><span class="sxs-lookup"><span data-stu-id="f989c-133">`Enter-PSSession -ComputerName foo` starts a session via WinRM</span></span>
- <span data-ttu-id="f989c-134">`Enter-PSSession -ContainerId foo` と `Enter-PSSession -VmId foo` は PowerShell Direct でセッションを開始します</span><span class="sxs-lookup"><span data-stu-id="f989c-134">`Enter-PSSession -ContainerId foo` and `Enter-PSSession -VmId foo` start a session via PowerShell Direct</span></span>
- <span data-ttu-id="f989c-135">`Enter-PSSession -HostName foo` は SSH でセッションを開始します</span><span class="sxs-lookup"><span data-stu-id="f989c-135">`Enter-PSSession -HostName foo` starts a session via SSH</span></span>

<span data-ttu-id="f989c-136">`Enter-PSSession` について詳しくは、[こちら](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6)のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f989c-136">For more info on `Enter-PSSession`, check out the docs [here](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).</span></span>

<span data-ttu-id="f989c-137">ここでは、Azure の Ubuntu VM に macOS から接続するので、リモート処理に SSH を使用します。</span><span class="sxs-lookup"><span data-stu-id="f989c-137">I'll be using SSH for remoting since I'm going from macOS to an Ubuntu VM in Azure.</span></span>

<span data-ttu-id="f989c-138">最初に、統合コンソールで Enter-PSSession を実行します。</span><span class="sxs-lookup"><span data-stu-id="f989c-138">First, in the Integrated Console, let's run our Enter-PSSession.</span></span> <span data-ttu-id="f989c-139">プロンプトの左側に `[something]` と表示されるので、セッション内にいることがわかります。</span><span class="sxs-lookup"><span data-stu-id="f989c-139">You'll know that you're in the session because `[something]` will show up to the left of your prompt.</span></span>

![Enter-PSSession の呼び出し](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

<span data-ttu-id="f989c-141">そこからは、ローカル スクリプトを編集する場合とまったく同じ手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f989c-141">From there, we can do the exact steps as if we were editing a local script.</span></span>

1. <span data-ttu-id="f989c-142">`Open-EditorFile test.ps1` または `psedit test.ps1` を実行して、リモートの `test.ps1` ファイルを開きます ![test.ps1 ファイルの Open-EditorFile](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span><span class="sxs-lookup"><span data-stu-id="f989c-142">Run `Open-EditorFile test.ps1` or `psedit test.ps1` to open the remote `test.ps1` file ![Open-EditorFile the test.ps1 file](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span></span>
2. <span data-ttu-id="f989c-143">ファイルを編集し、ブレークポイントを設定します</span><span class="sxs-lookup"><span data-stu-id="f989c-143">Edit the file/set breakpoints</span></span> ![編集とブレークポイントの設定](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. <span data-ttu-id="f989c-145">リモート ファイルのデバッグを開始します (F5)</span><span class="sxs-lookup"><span data-stu-id="f989c-145">Start debugging (F5) the remote file</span></span>

![リモート ファイルのデバッグ](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

<span data-ttu-id="f989c-147">以上ですべてです。</span><span class="sxs-lookup"><span data-stu-id="f989c-147">That's all there's to it!</span></span> <span data-ttu-id="f989c-148">VSCode での PowerShell のリモート編集とデバッグに関する質問に、このガイドが役立ったでしょうか。</span><span class="sxs-lookup"><span data-stu-id="f989c-148">We hope that this guide helped clear up any questions about remote debugging and editing PowerShell in VSCode.</span></span>

<span data-ttu-id="f989c-149">何か問題があれば、[GitHub リポジトリ](http://github.com/powershell/vscode-powershell)で自由に問題を開いてください。</span><span class="sxs-lookup"><span data-stu-id="f989c-149">If you have any problems, feel free to open issues [on the GitHub repo](http://github.com/powershell/vscode-powershell).</span></span>
