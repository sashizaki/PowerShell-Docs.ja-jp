---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: dee5e8206c61d79faadf8573a82c74d4ac0fb8e0
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="improvements-in-powershell-script-debugging"></a><span data-ttu-id="b1721-102">PowerShell スクリプト デバッグの強化</span><span class="sxs-lookup"><span data-stu-id="b1721-102">Improvements in PowerShell Script Debugging</span></span>

<span data-ttu-id="b1721-103">デバッガーの動作を向上させるため、PowerShell 5.0 では多くの点が強化されています。</span><span class="sxs-lookup"><span data-stu-id="b1721-103">A number of improvements were made in PowerShell 5.0 to enhance the debugging experience:</span></span>

## <a name="break-all"></a><span data-ttu-id="b1721-104">すべて中断</span><span class="sxs-lookup"><span data-stu-id="b1721-104">Break All</span></span>

<span data-ttu-id="b1721-105">PowerShell コンソールと Windows PowerShell ISE では、実行中のスクリプトに対してデバッガー中断が可能になりました。</span><span class="sxs-lookup"><span data-stu-id="b1721-105">The PowerShell console and Windows PowerShell ISE now allow you to break into the debugger for running scripts.</span></span> <span data-ttu-id="b1721-106">これは、ローカルとリモートの両方のセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b1721-106">This works in both local and remote sessions.</span></span>

<span data-ttu-id="b1721-107">コンソールでは、**Ctrl+Break** を押します。</span><span class="sxs-lookup"><span data-stu-id="b1721-107">In the console, press **Ctrl+Break**.</span></span>

<span data-ttu-id="b1721-108">ISE では、**Ctrl+B** を押すか、**[デバッグ] -> [すべて中断]** メニュー コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="b1721-108">In ISE, press **Ctrl+B**, or use the **Debug -> Break All** menu command.</span></span>

## <a name="remote-debugging-and-remote-file-editing-in-windows-powershell-ise"></a><span data-ttu-id="b1721-109">Windows PowerShell ISE でのリモートによるデバッグとファイル編集</span><span class="sxs-lookup"><span data-stu-id="b1721-109">Remote debugging and remote file editing in Windows PowerShell ISE</span></span>

<span data-ttu-id="b1721-110">Windows PowerShell ISE では、PSEdit コマンドを実行することにより、リモート セッションでファイルを開いて編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b1721-110">Windows PowerShell ISE now lets you open and edit files in a remote session by running the PSEdit command.</span></span>
<span data-ttu-id="b1721-111">たとえば、次のように、リモート セッションでコマンド ラインからファイルを開いて編集できます。</span><span class="sxs-lookup"><span data-stu-id="b1721-111">For example, you can open a file for editing from the command line in a remote session as follows:</span></span>

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

<span data-ttu-id="b1721-112">また、ブレークポイントにヒットしたときに、Windows PowerShell ISE で自動的に開くリモート ファイルを編集して変更を保存できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b1721-112">In addition, you can now edit and save changes in a remote file that is automatically opened in Windows PowerShell ISE when you hit a breakpoint.</span></span>
<span data-ttu-id="b1721-113">今後は、リモート コンピューターで実行しているスクリプト ファイルをデバッグし、エラー修正のためにファイルを編集し、変更したスクリプトを再実行することができます。</span><span class="sxs-lookup"><span data-stu-id="b1721-113">Now, you can debug a script file that is running on a remote computer, edit the file to fix an error, and then rerun the modified script.</span></span>

## <a name="advanced-script-debugging"></a><span data-ttu-id="b1721-114">高度なスクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="b1721-114">Advanced Script Debugging</span></span>

<span data-ttu-id="b1721-115">新しい高度なデバッグ機能では、Windows PowerShell を読み込んだローカル コンピューターのプロセスにアタッチし、そのプロセス内の任意の実行空間をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="b1721-115">There are new, advanced debugging features that let you attach to any local computer process that has loaded Windows PowerShell, and debug arbitrary runspaces in that process.</span></span>

### <a name="runspace-debugging"></a><span data-ttu-id="b1721-116">実行空間のデバッグ</span><span class="sxs-lookup"><span data-stu-id="b1721-116">Runspace Debugging</span></span>

<span data-ttu-id="b1721-117">プロセス内の現在の実行空間を一覧表示し、その実行空間に Windows PowerShell コンソールや ISE デバッガーをアタッチしてスクリプト デバッグを実行するための、新しいコマンドレットが追加されました。</span><span class="sxs-lookup"><span data-stu-id="b1721-117">New cmdlets have been added that let you list current runspaces in a process, and attach the Windows PowerShell console or ISE debugger to that runspace for script debugging:</span></span>

-   <span data-ttu-id="b1721-118">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="b1721-118">Get-Runspace</span></span>
-   <span data-ttu-id="b1721-119">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="b1721-119">Debug-Runspace</span></span>
-   <span data-ttu-id="b1721-120">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="b1721-120">Enable-RunspaceDebug</span></span>
-   <span data-ttu-id="b1721-121">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="b1721-121">Disable-RunspaceDebug</span></span>
-   <span data-ttu-id="b1721-122">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="b1721-122">Get-RunspaceDebug</span></span>

### <a name="attach-to-process-hosting-powershell"></a><span data-ttu-id="b1721-123">PowerShell をホストしているプロセスにアタッチする</span><span class="sxs-lookup"><span data-stu-id="b1721-123">Attach to Process hosting PowerShell</span></span>

<span data-ttu-id="b1721-124">Windows PowerShell が読み込まれているすべてのコンピューター プロセスにアタッチできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b1721-124">You can now attach to any computer process that has Windows PowerShell loaded.</span></span> <span data-ttu-id="b1721-125">これを行うには、プロセスを使って対話型セッションに入ります。これは、Enter-PSSession コマンドレットを実行して、対話型リモート セッションに入る方法と似ています。</span><span class="sxs-lookup"><span data-stu-id="b1721-125">You do this by entering into an interactive session with the process, similarly to how you enter into an interactive remote session by running the Enter-PSSession cmdlet:</span></span>

-   <span data-ttu-id="b1721-126">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="b1721-126">Enter-PSHostProcess</span></span>
-   <span data-ttu-id="b1721-127">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="b1721-127">Exit-PSHostProcess</span></span>