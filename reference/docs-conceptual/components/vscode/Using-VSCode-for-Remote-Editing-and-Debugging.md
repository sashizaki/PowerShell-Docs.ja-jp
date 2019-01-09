---
title: Visual Studio Code を使用したリモート編集およびデバッグ
description: Visual Studio Code を使用したリモート編集およびデバッグ
ms.date: 08/06/2018
ms.openlocfilehash: bab1a629a7e9dafd5957cf93025abb18b8a4f326
ms.sourcegitcommit: 548547b2d5fc73e726bb9fec6175d452a351d975
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655609"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a><span data-ttu-id="df805-103">Visual Studio Code を使用したリモート編集およびデバッグ</span><span class="sxs-lookup"><span data-stu-id="df805-103">Using Visual Studio Code for remote editing and debugging</span></span>

<span data-ttu-id="df805-104">それらの ISE に精通していることを実行できますを取り消すことがあります`psedit file.ps1`ファイル - ローカルまたはリモート - を開くための統合されたコンソールから、ISE で右します。</span><span class="sxs-lookup"><span data-stu-id="df805-104">For those of you that were familiar with the ISE, you may recall that you could run `psedit file.ps1` from the integrated console to open files - local or remote - right in the ISE.</span></span>

<span data-ttu-id="df805-105">結局のところ、この機能は VSCode の PowerShell の拡張機能で使用できるもします。</span><span class="sxs-lookup"><span data-stu-id="df805-105">As it turns out, this feature is also available in the PowerShell extension for VSCode.</span></span> <span data-ttu-id="df805-106">このガイドでは、これを行う方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="df805-106">This guide will show you how to do it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df805-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="df805-107">Prerequisites</span></span>

<span data-ttu-id="df805-108">このガイドでは、あることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="df805-108">This guide assumes that you have:</span></span>

- <span data-ttu-id="df805-109">リモート リソース (例: VM、コンテナー) へのアクセスがあります。</span><span class="sxs-lookup"><span data-stu-id="df805-109">a remote resource (ex: a VM, a container) that you have access to</span></span>
- <span data-ttu-id="df805-110">また、ホスト マシンで実行する PowerShell</span><span class="sxs-lookup"><span data-stu-id="df805-110">PowerShell running on it and the host machine</span></span>
- <span data-ttu-id="df805-111">VSCode と for VSCode PowerShell 拡張機能</span><span class="sxs-lookup"><span data-stu-id="df805-111">VSCode and the PowerShell extension for VSCode</span></span>

<span data-ttu-id="df805-112">この機能は、Windows PowerShell と PowerShell Core で動作します。</span><span class="sxs-lookup"><span data-stu-id="df805-112">This feature works on Windows PowerShell and PowerShell Core.</span></span>

<span data-ttu-id="df805-113">この機能は、WinRM、PowerShell ダイレクトでは、または SSH を使用してリモート コンピューターに接続するときにも動作します。</span><span class="sxs-lookup"><span data-stu-id="df805-113">This feature also works when connecting to a remote machine via WinRM, PowerShell Direct, or SSH.</span></span> <span data-ttu-id="df805-114">SSH を使用する Windows を使用している場合は、チェック アウト、 [SSH の Win32 バージョン](https://github.com/PowerShell/Win32-OpenSSH)!</span><span class="sxs-lookup"><span data-stu-id="df805-114">If you want to use SSH, but are using Windows, check out the [Win32 version of SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span></span>

## <a name="lets-go"></a><span data-ttu-id="df805-115">始めましょう</span><span class="sxs-lookup"><span data-stu-id="df805-115">Let's go</span></span>

<span data-ttu-id="df805-116">このセクションでリモート編集、および Azure で実行されている Ubuntu VM に、MacBook Pro からデバッグを紹介します。</span><span class="sxs-lookup"><span data-stu-id="df805-116">In this section, I'll walk through remote editing and debugging from my MacBook Pro, to an Ubuntu VM running in Azure.</span></span> <span data-ttu-id="df805-117">可能性がありますいない使用する、Windows が **、プロセスと同じです**します。</span><span class="sxs-lookup"><span data-stu-id="df805-117">I might not be using Windows, but **the process is identical**.</span></span>

### <a name="local-file-editing-with-open-editorfile"></a><span data-ttu-id="df805-118">ローカル ファイルを開く EditorFile での編集</span><span class="sxs-lookup"><span data-stu-id="df805-118">Local file editing with Open-EditorFile</span></span>

<span data-ttu-id="df805-119">PowerShell の拡張機能で VSCode の開始し、PowerShell の統合されたコンソールを開く、入力も可能`Open-EditorFile foo.ps1`または`psedit foo.ps1`をエディターでローカル foo.ps1 ファイル権限を開きます。</span><span class="sxs-lookup"><span data-stu-id="df805-119">With the PowerShell extension for VSCode started and the PowerShell Integrated Console opened, we can type `Open-EditorFile foo.ps1` or `psedit foo.ps1` to open the local foo.ps1 file right in the editor.</span></span>

![オープン EditorFile foo.ps1 がローカルで動作します。](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> <span data-ttu-id="df805-121">foo.ps1 は既に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df805-121">foo.ps1 must already exist.</span></span>

<span data-ttu-id="df805-122">そこからできます。</span><span class="sxs-lookup"><span data-stu-id="df805-122">From there, we can:</span></span>

<span data-ttu-id="df805-123">余白にブレークポイントを追加![余白にブレークポイントを追加します。](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span><span class="sxs-lookup"><span data-stu-id="df805-123">add breakpoints to the gutter ![adding breakpoint to gutter](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)</span></span>

<span data-ttu-id="df805-124">f5 キーを押して PowerShell スクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="df805-124">and hit F5 to debug the PowerShell script.</span></span>
<span data-ttu-id="df805-125">![ローカルの PowerShell スクリプトのデバッグ](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span><span class="sxs-lookup"><span data-stu-id="df805-125">![debugging the PowerShell local script](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)</span></span>

<span data-ttu-id="df805-126">デバッグ中に、デバッグ コンソールとの対話、左、およびデバッグ ツールの他のすべての標準のスコープ内の変数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="df805-126">While debugging, you can interact with the debug console, check out the variables in the scope on the left, and all the other standard debugging tools.</span></span>

### <a name="remote-file-editing-with-open-editorfile"></a><span data-ttu-id="df805-127">リモート ファイルを開く EditorFile での編集</span><span class="sxs-lookup"><span data-stu-id="df805-127">Remote file editing with Open-EditorFile</span></span>

<span data-ttu-id="df805-128">今すぐ編集とデバッグ、リモート ファイルを見ていきましょう。</span><span class="sxs-lookup"><span data-stu-id="df805-128">Now let's get into remote file editing and debugging.</span></span> <span data-ttu-id="df805-129">手順はほぼ同じ、最初の操作を行います: リモート サーバーに、PowerShell セッションを入力する必要があります。 1 つだけのことです。</span><span class="sxs-lookup"><span data-stu-id="df805-129">The steps are nearly the same, there's just one thing we need to do first - enter our PowerShell session to the remote server.</span></span>

<span data-ttu-id="df805-130">これを行うには、コマンドレットです。</span><span class="sxs-lookup"><span data-stu-id="df805-130">There's a cmdlet for to do so.</span></span> <span data-ttu-id="df805-131">呼び出された`Enter-PSSession`します。</span><span class="sxs-lookup"><span data-stu-id="df805-131">It's called `Enter-PSSession`.</span></span>

<span data-ttu-id="df805-132">コマンドレットの機能を削ったダウンについては次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df805-132">The watered down explanation of the cmdlet is:</span></span>

- <span data-ttu-id="df805-133">`Enter-PSSession -ComputerName foo` WinRM を使用してセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="df805-133">`Enter-PSSession -ComputerName foo` starts a session via WinRM</span></span>
- <span data-ttu-id="df805-134">`Enter-PSSession -ContainerId foo` `Enter-PSSession -VmId foo` PowerShell Direct を使用してセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="df805-134">`Enter-PSSession -ContainerId foo` and `Enter-PSSession -VmId foo` start a session via PowerShell Direct</span></span>
- <span data-ttu-id="df805-135">`Enter-PSSession -HostName foo` SSH を使用してセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="df805-135">`Enter-PSSession -HostName foo` starts a session via SSH</span></span>

<span data-ttu-id="df805-136">詳細について`Enter-PSSession`、ドキュメントのチェック アウト[ここ](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6)します。</span><span class="sxs-lookup"><span data-stu-id="df805-136">For more info on `Enter-PSSession`, check out the docs [here](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6).</span></span>

<span data-ttu-id="df805-137">使用する SSH リモート処理のため macOS から Azure で Ubuntu VM にします。</span><span class="sxs-lookup"><span data-stu-id="df805-137">I'll be using SSH for remoting since I'm going from macOS to an Ubuntu VM in Azure.</span></span>

<span data-ttu-id="df805-138">最初に、統合コンソールで、Enter-pssession を実行してみましょう。</span><span class="sxs-lookup"><span data-stu-id="df805-138">First, in the Integrated Console, let's run our Enter-PSSession.</span></span> <span data-ttu-id="df805-139">セッションにいることがわかります`[something]`プロンプトの左側に表示されます。</span><span class="sxs-lookup"><span data-stu-id="df805-139">You'll know that you're in the session because `[something]` will show up to the left of your prompt.</span></span>

![Enter-pssession への呼び出し](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

<span data-ttu-id="df805-141">そこから、ローカル スクリプトを編集していた場合、正確な手順を実行しましたできます。</span><span class="sxs-lookup"><span data-stu-id="df805-141">From there, we can do the exact steps as if we were editing a local script.</span></span>

1. <span data-ttu-id="df805-142">実行`Open-EditorFile test.ps1`または`psedit test.ps1`を開くリモート`test.ps1`ファイル![オープン EditorFile test.ps1 ファイル](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span><span class="sxs-lookup"><span data-stu-id="df805-142">Run `Open-EditorFile test.ps1` or `psedit test.ps1` to open the remote `test.ps1` file ![Open-EditorFile the test.ps1 file](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)</span></span>
2. <span data-ttu-id="df805-143">ファイル/設定ブレークポイントを編集します。</span><span class="sxs-lookup"><span data-stu-id="df805-143">Edit the file/set breakpoints</span></span> ![編集し、ブレークポイントを設定](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. <span data-ttu-id="df805-145">(F5)、リモート ファイルのデバッグを開始します。</span><span class="sxs-lookup"><span data-stu-id="df805-145">Start debugging (F5) the remote file</span></span>

![リモート ファイルのデバッグ](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

<span data-ttu-id="df805-147">すべてです。</span><span class="sxs-lookup"><span data-stu-id="df805-147">That's all there's to it!</span></span> <span data-ttu-id="df805-148">このガイドがリモート デバッグと VSCode での PowerShell の編集に関する質問を明確に役立ったことことと思います。</span><span class="sxs-lookup"><span data-stu-id="df805-148">We hope that this guide helped clear up any questions about remote debugging and editing PowerShell in VSCode.</span></span>

<span data-ttu-id="df805-149">問題があれば、自由に未解決の問題[GitHub リポジトリで](http://github.com/powershell/vscode-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="df805-149">If you have any problems, feel free to open issues [on the GitHub repo](http://github.com/powershell/vscode-powershell).</span></span>
