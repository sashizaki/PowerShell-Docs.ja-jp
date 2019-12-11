---
title: Visual Studio Code を使用したリモート編集およびデバッグ
description: Visual Studio Code を使用したリモート編集およびデバッグ
ms.date: 06/13/2019
ms.openlocfilehash: ae3b7a3709498fcd547a48d0849b0dc880217225
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "67263929"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a><span data-ttu-id="bb564-103">Visual Studio Code を使用したリモート編集およびデバッグ</span><span class="sxs-lookup"><span data-stu-id="bb564-103">Using Visual Studio Code for remote editing and debugging</span></span>

<span data-ttu-id="bb564-104">ISE に精通していれば、統合コンソールから `psedit file.ps1` を実行してファイル (ローカルまたはリモート) を ISE で開けることをご存じではないでしょうか。</span><span class="sxs-lookup"><span data-stu-id="bb564-104">For those of you that are familiar with the ISE, you may recall that you could run `psedit file.ps1` from the integrated console to open files - local or remote - right in the ISE.</span></span>

<span data-ttu-id="bb564-105">この機能は、VSCode 用の PowerShell 拡張機能でも使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb564-105">This feature is also available in the PowerShell extension for VSCode.</span></span> <span data-ttu-id="bb564-106">このガイドではそれを行う方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="bb564-106">This guide shows you how to do it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb564-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="bb564-107">Prerequisites</span></span>

<span data-ttu-id="bb564-108">このガイドでは、次のことを前提としています。</span><span class="sxs-lookup"><span data-stu-id="bb564-108">This guide assumes that you have:</span></span>

- <span data-ttu-id="bb564-109">アクセスできるリモート リソース (例: VM、コンテナー)</span><span class="sxs-lookup"><span data-stu-id="bb564-109">A remote resource (ex: a VM, a container) that you have access to</span></span>
- <span data-ttu-id="bb564-110">その上で実行する PowerShell およびホスト マシン</span><span class="sxs-lookup"><span data-stu-id="bb564-110">PowerShell running on it and the host machine</span></span>
- <span data-ttu-id="bb564-111">VSCode および VSCode 用 PowerShell 拡張機能</span><span class="sxs-lookup"><span data-stu-id="bb564-111">VSCode and the PowerShell extension for VSCode</span></span>

<span data-ttu-id="bb564-112">この機能は、Windows PowerShell と PowerShell Core で動作します。</span><span class="sxs-lookup"><span data-stu-id="bb564-112">This feature works on Windows PowerShell and PowerShell Core.</span></span>

<span data-ttu-id="bb564-113">また、この機能は、WinRM、PowerShell Direct、または SSH でリモート マシンに接続しているときにも動作します。</span><span class="sxs-lookup"><span data-stu-id="bb564-113">This feature also works when connecting to a remote machine via WinRM, PowerShell Direct, or SSH.</span></span> <span data-ttu-id="bb564-114">SSH を使用したいが、Windows を使用している場合は、[SSH の Win32 バージョン](https://github.com/PowerShell/Win32-OpenSSH)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="bb564-114">If you want to use SSH, but are using Windows, check out the [Win32 version of SSH](https://github.com/PowerShell/Win32-OpenSSH)!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb564-115">`Open-EditorFile` および `psedit` コマンドは、VSCode 用の PowerShell 拡張機能によって作成された **PowerShell 統合コンソール**でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="bb564-115">The `Open-EditorFile` and `psedit` commands only work in the **PowerShell Integrated Console** created by the PowerShell extension for VSCode.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="bb564-116">使用例</span><span class="sxs-lookup"><span data-stu-id="bb564-116">Usage examples</span></span>

<span data-ttu-id="bb564-117">これらの例は、MacBook Pro から Azure で実行されている Ubuntu VM に対するリモート編集およびデバッグを示しています。</span><span class="sxs-lookup"><span data-stu-id="bb564-117">These examples show remote editing and debugging from a MacBook Pro to an Ubuntu VM running in Azure.</span></span> <span data-ttu-id="bb564-118">プロセスは Windows 上と同じです。</span><span class="sxs-lookup"><span data-stu-id="bb564-118">The process is identical on Windows.</span></span>

### <a name="local-file-editing-with-open-editorfile"></a><span data-ttu-id="bb564-119">Open-EditorFile でのローカル ファイル編集</span><span class="sxs-lookup"><span data-stu-id="bb564-119">Local file editing with Open-EditorFile</span></span>

<span data-ttu-id="bb564-120">VSCode 用 PowerShell 拡張機能を開始し、PowerShell 統合コンソールを開くと、「`Open-EditorFile foo.ps1`」または「`psedit foo.ps1`」と入力してエディターでローカル環境の foo.ps1 ファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="bb564-120">With the PowerShell extension for VSCode started and the PowerShell Integrated Console opened, we can type `Open-EditorFile foo.ps1` or `psedit foo.ps1` to open the local foo.ps1 file right in the editor.</span></span>

![ローカルに動作する Open-EditorFile foo.ps1](images/Using-VSCode-for-Remote-Editing-and-Debugging/1-open-local-file.png)

>[!NOTE]
> <span data-ttu-id="bb564-122">ファイル `foo.ps1` は既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb564-122">The file `foo.ps1` must already exist.</span></span>

<span data-ttu-id="bb564-123">そこから次のことができます。</span><span class="sxs-lookup"><span data-stu-id="bb564-123">From there, we can:</span></span>

- <span data-ttu-id="bb564-124">余白にブレークポイントを追加します</span><span class="sxs-lookup"><span data-stu-id="bb564-124">Add breakpoints to the gutter</span></span>

  ![余白にブレークポイントを追加する](images/Using-VSCode-for-Remote-Editing-and-Debugging/2-adding-breakpoint-gutter.png)

- <span data-ttu-id="bb564-126">F5 キーを押して PowerShell スクリプトをデバッグします。</span><span class="sxs-lookup"><span data-stu-id="bb564-126">Hit F5 to debug the PowerShell script.</span></span>

  ![PowerShell のローカル スクリプトをデバッグする](images/Using-VSCode-for-Remote-Editing-and-Debugging/3-local-debug.png)

<span data-ttu-id="bb564-128">デバッグ中に、デバッグ コンソールと対話し、左側でスコープ内の変数を確認し、他のすべての標準デバッグ ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb564-128">While debugging, you can interact with the debug console, check out the variables in the scope on the left, and all the other standard debugging tools.</span></span>

### <a name="remote-file-editing-with-open-editorfile"></a><span data-ttu-id="bb564-129">Open-EditorFile でのリモート ファイル編集</span><span class="sxs-lookup"><span data-stu-id="bb564-129">Remote file editing with Open-EditorFile</span></span>

<span data-ttu-id="bb564-130">次に、リモート ファイルを編集してデバッグします。</span><span class="sxs-lookup"><span data-stu-id="bb564-130">Now let's get into remote file editing and debugging.</span></span> <span data-ttu-id="bb564-131">手順はほぼ同じですが、最初に行う必要があることが 1 つだけあります。リモート サーバーへの PowerShell セッションに入ります。</span><span class="sxs-lookup"><span data-stu-id="bb564-131">The steps are nearly the same, there's just one thing we need to do first - enter our PowerShell session to the remote server.</span></span>

<span data-ttu-id="bb564-132">それを行うためのコマンドレットがあります。</span><span class="sxs-lookup"><span data-stu-id="bb564-132">There's a cmdlet for to do so.</span></span> <span data-ttu-id="bb564-133">`Enter-PSSession` です。</span><span class="sxs-lookup"><span data-stu-id="bb564-133">It's called `Enter-PSSession`.</span></span>

<span data-ttu-id="bb564-134">コマンドレットの簡単な説明は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bb564-134">The watered down explanation of the cmdlet is:</span></span>

- <span data-ttu-id="bb564-135">`Enter-PSSession -ComputerName foo` は WinRM でセッションを開始します</span><span class="sxs-lookup"><span data-stu-id="bb564-135">`Enter-PSSession -ComputerName foo` starts a session via WinRM</span></span>
- <span data-ttu-id="bb564-136">`Enter-PSSession -ContainerId foo` と `Enter-PSSession -VmId foo` は PowerShell Direct でセッションを開始します</span><span class="sxs-lookup"><span data-stu-id="bb564-136">`Enter-PSSession -ContainerId foo` and `Enter-PSSession -VmId foo` start a session via PowerShell Direct</span></span>
- <span data-ttu-id="bb564-137">`Enter-PSSession -HostName foo` は SSH でセッションを開始します</span><span class="sxs-lookup"><span data-stu-id="bb564-137">`Enter-PSSession -HostName foo` starts a session via SSH</span></span>

<span data-ttu-id="bb564-138">詳細については、[Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb564-138">For more information, see the documentation for [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span></span>

<span data-ttu-id="bb564-139">ここでは macOS から Azure の Ubuntu VM に移行するので、リモート処理に SSH を使用しています。</span><span class="sxs-lookup"><span data-stu-id="bb564-139">Since we are going from macOS to an Ubuntu VM in Azure, we are using SSH for remoting.</span></span>

<span data-ttu-id="bb564-140">まず、統合コンソールで `Enter-PSSession` を実行します。</span><span class="sxs-lookup"><span data-stu-id="bb564-140">First, in the Integrated Console, run `Enter-PSSession`.</span></span> <span data-ttu-id="bb564-141">プロンプトの左側に `[<hostname>]` が表示されたら、リモート セッションに接続しています。</span><span class="sxs-lookup"><span data-stu-id="bb564-141">You're connected to the remote session when `[<hostname>]` shows up to the left of your prompt.</span></span>

![Enter-PSSession の呼び出し](images/Using-VSCode-for-Remote-Editing-and-Debugging/4-enter-pssession.png)

<span data-ttu-id="bb564-143">これで、ローカル スクリプトを編集する場合と同じ手順を実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bb564-143">Now, we can do the same steps as if we are editing a local script.</span></span>

1. <span data-ttu-id="bb564-144">`Open-EditorFile test.ps1` または `psedit test.ps1` を実行してリモートの `test.ps1` ファイルを開きます</span><span class="sxs-lookup"><span data-stu-id="bb564-144">Run `Open-EditorFile test.ps1` or `psedit test.ps1` to open the remote `test.ps1` file</span></span>

  ![Open-EditorFile the test.ps1 ファイル](images/Using-VSCode-for-Remote-Editing-and-Debugging/5-open-remote-file.png)

1. <span data-ttu-id="bb564-146">ファイルを編集し、ブレークポイントを設定します</span><span class="sxs-lookup"><span data-stu-id="bb564-146">Edit the file/set breakpoints</span></span>

   ![編集とブレークポイントの設定](images/Using-VSCode-for-Remote-Editing-and-Debugging/6-set-breakpoints.png)

1. <span data-ttu-id="bb564-148">リモート ファイルのデバッグを開始します (F5)</span><span class="sxs-lookup"><span data-stu-id="bb564-148">Start debugging (F5) the remote file</span></span>

   ![リモート ファイルのデバッグ](images/Using-VSCode-for-Remote-Editing-and-Debugging/7-start-debugging.png)

<span data-ttu-id="bb564-150">何か問題があれば、[GitHub リポジトリ](https://github.com/powershell/vscode-powershell)で問題を開いてください。</span><span class="sxs-lookup"><span data-stu-id="bb564-150">If you have any problems, you can open issues in the [GitHub repo](https://github.com/powershell/vscode-powershell).</span></span>
