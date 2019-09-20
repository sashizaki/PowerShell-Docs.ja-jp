---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: PowerShell スクリプト デバッグの強化
ms.openlocfilehash: f1771a451ba671da2371fcfc95374e6131573ddc
ms.sourcegitcommit: 0a6b562a497860caadba754c75a83215315d37a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2019
ms.locfileid: "71147812"
---
# <a name="improvements-in-powershell-script-debugging"></a><span data-ttu-id="f250b-103">PowerShell スクリプト デバッグの強化</span><span class="sxs-lookup"><span data-stu-id="f250b-103">Improvements in PowerShell Script Debugging</span></span>

<span data-ttu-id="f250b-104">PowerShell 5.0 には、デバッグ エクスペリエンスを強化するいくつかの機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f250b-104">PowerShell 5.0 includes several improvements that enhance the debugging experience.</span></span>

## <a name="break-all"></a><span data-ttu-id="f250b-105">すべて中断</span><span class="sxs-lookup"><span data-stu-id="f250b-105">Break All</span></span>

<span data-ttu-id="f250b-106">PowerShell コンソールと PowerShell ISE では、実行中のスクリプトにデバッガーで割り込むことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f250b-106">The PowerShell console and PowerShell ISE now allow you to break into the debugger for running scripts.</span></span> <span data-ttu-id="f250b-107">これは、ローカルとリモートの両方のセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f250b-107">This works in both local and remote sessions.</span></span>

<span data-ttu-id="f250b-108">コンソールでは、<kbd>Ctrl</kbd> + <kbd>Break</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f250b-108">In the console, press <kbd>Ctrl</kbd>+<kbd>Break</kbd>.</span></span>

<span data-ttu-id="f250b-109">ISE では、<kbd>Ctrl</kbd> + <kbd>B</kbd> キーを押すか、 **[デバッグ] -> [すべて中断]** メニュー コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="f250b-109">In ISE, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, or use the **Debug -> Break All** menu command.</span></span>

## <a name="remote-debugging-and-remote-file-editing-in-powershell-ise"></a><span data-ttu-id="f250b-110">PowerShell ISE でのリモートによるデバッグとファイル編集</span><span class="sxs-lookup"><span data-stu-id="f250b-110">Remote debugging and remote file editing in PowerShell ISE</span></span>

<span data-ttu-id="f250b-111">PowerShell ISE では、PSEdit コマンドを実行することにより、リモート セッションでファイルを開いて編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f250b-111">PowerShell ISE now lets you open and edit files in a remote session by running the PSEdit command.</span></span>
<span data-ttu-id="f250b-112">たとえば、次のように、リモート セッションでコマンド ラインからファイルを開いて編集できます。</span><span class="sxs-lookup"><span data-stu-id="f250b-112">For example, you can open a file for editing from the command line in a remote session as follows:</span></span>

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

<span data-ttu-id="f250b-113">また、ブレークポイントにヒットしたときに、PowerShell ISE で自動的に開くリモート ファイルを編集して変更を保存できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f250b-113">In addition, you can now edit and save changes in a remote file that is automatically opened in PowerShell ISE when you hit a breakpoint.</span></span> <span data-ttu-id="f250b-114">今後は、リモート コンピューターで実行しているスクリプト ファイルをデバッグし、エラー修正のためにファイルを編集し、変更したスクリプトを再実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f250b-114">Now, you can debug a script file that is running on a remote computer, edit the file to fix an error, and then rerun the modified script.</span></span>

## <a name="advanced-script-debugging"></a><span data-ttu-id="f250b-115">高度なスクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="f250b-115">Advanced Script Debugging</span></span>

<span data-ttu-id="f250b-116">新しい高度なデバッグ機能では、PowerShell が読み込まれたローカル コンピューターのプロセスにアタッチし、そのプロセス内の任意の実行空間をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="f250b-116">There are new, advanced debugging features that let you attach to any local computer process that has loaded PowerShell, and debug arbitrary runspaces in that process.</span></span>

### <a name="runspace-debugging"></a><span data-ttu-id="f250b-117">実行空間のデバッグ</span><span class="sxs-lookup"><span data-stu-id="f250b-117">Runspace Debugging</span></span>

<span data-ttu-id="f250b-118">プロセス内の現在の実行空間を一覧表示し、その実行空間に PowerShell コンソールや PowerShell ISE デバッガーをアタッチしてスクリプト デバッグを実行するための、新しいコマンドレットが追加されました。</span><span class="sxs-lookup"><span data-stu-id="f250b-118">New cmdlets have been added that let you list current runspaces in a process, and attach the PowerShell console or PowerShell ISE debugger to that runspace for script debugging:</span></span>

- <span data-ttu-id="f250b-119">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="f250b-119">Get-Runspace</span></span>
- <span data-ttu-id="f250b-120">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="f250b-120">Debug-Runspace</span></span>
- <span data-ttu-id="f250b-121">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f250b-121">Enable-RunspaceDebug</span></span>
- <span data-ttu-id="f250b-122">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f250b-122">Disable-RunspaceDebug</span></span>
- <span data-ttu-id="f250b-123">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="f250b-123">Get-RunspaceDebug</span></span>

### <a name="attach-to-process-hosting-powershell"></a><span data-ttu-id="f250b-124">PowerShell をホストしているプロセスにアタッチする</span><span class="sxs-lookup"><span data-stu-id="f250b-124">Attach to Process hosting PowerShell</span></span>

<span data-ttu-id="f250b-125">PowerShell が読み込まれているすべてのコンピューター プロセスにアタッチできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f250b-125">You can now attach to any computer process that has PowerShell loaded.</span></span> <span data-ttu-id="f250b-126">それを行うには、ホスト プロセスで対話型セッションに入ります。</span><span class="sxs-lookup"><span data-stu-id="f250b-126">You do this by entering into an interactive session with the host process.</span></span> <span data-ttu-id="f250b-127">詳細については、次のドキュメントをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f250b-127">For more information, see:</span></span>

- [<span data-ttu-id="f250b-128">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="f250b-128">Enter-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Enter-PSHostProcess)
- [<span data-ttu-id="f250b-129">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="f250b-129">Exit-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Exit-PSHostProcess)
