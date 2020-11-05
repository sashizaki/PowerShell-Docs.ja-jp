---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: PowerShell スクリプト デバッグの強化
description: WMF 5.0 では、Windows PoowerShell に新しいデバッグ機能が追加されています。
ms.openlocfilehash: 5703343e1b85024931638e8b04a09f7208ea123c
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92646730"
---
# <a name="improvements-in-powershell-script-debugging"></a><span data-ttu-id="ebe46-104">PowerShell スクリプト デバッグの強化</span><span class="sxs-lookup"><span data-stu-id="ebe46-104">Improvements in PowerShell Script Debugging</span></span>

<span data-ttu-id="ebe46-105">PowerShell 5.0 には、デバッグ エクスペリエンスを強化するいくつかの機能強化が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ebe46-105">PowerShell 5.0 includes several improvements that enhance the debugging experience.</span></span>

## <a name="break-all"></a><span data-ttu-id="ebe46-106">すべて中断</span><span class="sxs-lookup"><span data-stu-id="ebe46-106">Break All</span></span>

<span data-ttu-id="ebe46-107">PowerShell コンソールと PowerShell ISE では、実行中のスクリプトにデバッガーで割り込むことができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ebe46-107">The PowerShell console and PowerShell ISE now allow you to break into the debugger for running scripts.</span></span> <span data-ttu-id="ebe46-108">これは、ローカルとリモートの両方のセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ebe46-108">This works in both local and remote sessions.</span></span>

<span data-ttu-id="ebe46-109">コンソールでは、<kbd>Ctrl</kbd>+<kbd>Break</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ebe46-109">In the console, press <kbd>Ctrl</kbd>+<kbd>Break</kbd>.</span></span>

<span data-ttu-id="ebe46-110">ISE では、 <kbd>Ctrl</kbd>+<kbd>B</kbd> キーを押すか、 **[デバッグ] -> [すべて中断]** メニュー コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="ebe46-110">In ISE, press <kbd>Ctrl</kbd>+<kbd>B</kbd>, or use the **Debug -> Break All** menu command.</span></span>

## <a name="remote-debugging-and-remote-file-editing-in-powershell-ise"></a><span data-ttu-id="ebe46-111">PowerShell ISE でのリモートによるデバッグとファイル編集</span><span class="sxs-lookup"><span data-stu-id="ebe46-111">Remote debugging and remote file editing in PowerShell ISE</span></span>

<span data-ttu-id="ebe46-112">PowerShell ISE では、PSEdit コマンドを実行することにより、リモート セッションでファイルを開いて編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ebe46-112">PowerShell ISE now lets you open and edit files in a remote session by running the PSEdit command.</span></span>
<span data-ttu-id="ebe46-113">たとえば、次のように、リモート セッションでコマンド ラインからファイルを開いて編集できます。</span><span class="sxs-lookup"><span data-stu-id="ebe46-113">For example, you can open a file for editing from the command line in a remote session as follows:</span></span>

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

<span data-ttu-id="ebe46-114">また、ブレークポイントにヒットしたときに、PowerShell ISE で自動的に開くリモート ファイルを編集して変更を保存できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ebe46-114">In addition, you can now edit and save changes in a remote file that is automatically opened in PowerShell ISE when you hit a breakpoint.</span></span> <span data-ttu-id="ebe46-115">今後は、リモート コンピューターで実行しているスクリプト ファイルをデバッグし、エラー修正のためにファイルを編集し、変更したスクリプトを再実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ebe46-115">Now, you can debug a script file that is running on a remote computer, edit the file to fix an error, and then rerun the modified script.</span></span>

## <a name="advanced-script-debugging"></a><span data-ttu-id="ebe46-116">高度なスクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="ebe46-116">Advanced Script Debugging</span></span>

<span data-ttu-id="ebe46-117">新しい高度なデバッグ機能では、PowerShell が読み込まれたローカル コンピューターのプロセスにアタッチし、そのプロセス内の任意の実行空間をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="ebe46-117">There are new, advanced debugging features that let you attach to any local computer process that has loaded PowerShell, and debug arbitrary runspaces in that process.</span></span>

### <a name="runspace-debugging"></a><span data-ttu-id="ebe46-118">実行空間のデバッグ</span><span class="sxs-lookup"><span data-stu-id="ebe46-118">Runspace Debugging</span></span>

<span data-ttu-id="ebe46-119">プロセス内の現在の実行空間を一覧表示し、その実行空間に PowerShell コンソールや PowerShell ISE デバッガーをアタッチしてスクリプト デバッグを実行するための、新しいコマンドレットが追加されました。</span><span class="sxs-lookup"><span data-stu-id="ebe46-119">New cmdlets have been added that let you list current runspaces in a process, and attach the PowerShell console or PowerShell ISE debugger to that runspace for script debugging:</span></span>

- <span data-ttu-id="ebe46-120">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="ebe46-120">Get-Runspace</span></span>
- <span data-ttu-id="ebe46-121">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="ebe46-121">Debug-Runspace</span></span>
- <span data-ttu-id="ebe46-122">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ebe46-122">Enable-RunspaceDebug</span></span>
- <span data-ttu-id="ebe46-123">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ebe46-123">Disable-RunspaceDebug</span></span>
- <span data-ttu-id="ebe46-124">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="ebe46-124">Get-RunspaceDebug</span></span>

### <a name="attach-to-process-hosting-powershell"></a><span data-ttu-id="ebe46-125">PowerShell をホストしているプロセスにアタッチする</span><span class="sxs-lookup"><span data-stu-id="ebe46-125">Attach to Process hosting PowerShell</span></span>

<span data-ttu-id="ebe46-126">PowerShell が読み込まれているすべてのコンピューター プロセスにアタッチできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="ebe46-126">You can now attach to any computer process that has PowerShell loaded.</span></span> <span data-ttu-id="ebe46-127">それを行うには、ホスト プロセスで対話型セッションに入ります。</span><span class="sxs-lookup"><span data-stu-id="ebe46-127">You do this by entering into an interactive session with the host process.</span></span> <span data-ttu-id="ebe46-128">詳細については、次をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ebe46-128">For more information, see:</span></span>

- [<span data-ttu-id="ebe46-129">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="ebe46-129">Enter-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Enter-PSHostProcess)
- [<span data-ttu-id="ebe46-130">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="ebe46-130">Exit-PSHostProcess</span></span>](/powershell/module/Microsoft.PowerShell.Core/Exit-PSHostProcess)
