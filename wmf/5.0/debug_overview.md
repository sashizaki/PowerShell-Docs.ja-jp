---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 22a027ebc97e15075980bc77ce272d8ecdae0b5f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058665"
---
# <a name="improvements-in-powershell-script-debugging"></a><span data-ttu-id="45784-102">PowerShell スクリプト デバッグの強化</span><span class="sxs-lookup"><span data-stu-id="45784-102">Improvements in PowerShell Script Debugging</span></span>

<span data-ttu-id="45784-103">デバッガーの動作を向上させるため、PowerShell 5.0 では多くの点が強化されています。</span><span class="sxs-lookup"><span data-stu-id="45784-103">A number of improvements were made in PowerShell 5.0 to enhance the debugging experience:</span></span>

## <a name="break-all"></a><span data-ttu-id="45784-104">すべて中断</span><span class="sxs-lookup"><span data-stu-id="45784-104">Break All</span></span>

<span data-ttu-id="45784-105">PowerShell コンソールと Windows PowerShell ISE では、実行中のスクリプトに対してデバッガー中断が可能になりました。</span><span class="sxs-lookup"><span data-stu-id="45784-105">The PowerShell console and Windows PowerShell ISE now allow you to break into the debugger for running scripts.</span></span> <span data-ttu-id="45784-106">これは、ローカルとリモートの両方のセッションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="45784-106">This works in both local and remote sessions.</span></span>

<span data-ttu-id="45784-107">コンソールでは、**Ctrl+Break** を押します。</span><span class="sxs-lookup"><span data-stu-id="45784-107">In the console, press **Ctrl+Break**.</span></span>

<span data-ttu-id="45784-108">ISE では、**Ctrl+B** を押すか、**[デバッグ] -> [すべて中断]** メニュー コマンドを使います。</span><span class="sxs-lookup"><span data-stu-id="45784-108">In ISE, press **Ctrl+B**, or use the **Debug -> Break All** menu command.</span></span>

## <a name="remote-debugging-and-remote-file-editing-in-windows-powershell-ise"></a><span data-ttu-id="45784-109">Windows PowerShell ISE でのリモートによるデバッグとファイル編集</span><span class="sxs-lookup"><span data-stu-id="45784-109">Remote debugging and remote file editing in Windows PowerShell ISE</span></span>

<span data-ttu-id="45784-110">Windows PowerShell ISE では、PSEdit コマンドを実行することにより、リモート セッションでファイルを開いて編集できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="45784-110">Windows PowerShell ISE now lets you open and edit files in a remote session by running the PSEdit command.</span></span>
<span data-ttu-id="45784-111">たとえば、次のように、リモート セッションでコマンド ラインからファイルを開いて編集できます。</span><span class="sxs-lookup"><span data-stu-id="45784-111">For example, you can open a file for editing from the command line in a remote session as follows:</span></span>

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

<span data-ttu-id="45784-112">また、ブレークポイントにヒットしたときに、Windows PowerShell ISE で自動的に開くリモート ファイルを編集して変更を保存できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="45784-112">In addition, you can now edit and save changes in a remote file that is automatically opened in Windows PowerShell ISE when you hit a breakpoint.</span></span>
<span data-ttu-id="45784-113">今後は、リモート コンピューターで実行しているスクリプト ファイルをデバッグし、エラー修正のためにファイルを編集し、変更したスクリプトを再実行することができます。</span><span class="sxs-lookup"><span data-stu-id="45784-113">Now, you can debug a script file that is running on a remote computer, edit the file to fix an error, and then rerun the modified script.</span></span>

## <a name="advanced-script-debugging"></a><span data-ttu-id="45784-114">高度なスクリプトのデバッグ</span><span class="sxs-lookup"><span data-stu-id="45784-114">Advanced Script Debugging</span></span>

<span data-ttu-id="45784-115">新しい高度なデバッグ機能では、Windows PowerShell を読み込んだローカル コンピューターのプロセスにアタッチし、そのプロセス内の任意の実行空間をデバッグできます。</span><span class="sxs-lookup"><span data-stu-id="45784-115">There are new, advanced debugging features that let you attach to any local computer process that has loaded Windows PowerShell, and debug arbitrary runspaces in that process.</span></span>

### <a name="runspace-debugging"></a><span data-ttu-id="45784-116">実行空間のデバッグ</span><span class="sxs-lookup"><span data-stu-id="45784-116">Runspace Debugging</span></span>

<span data-ttu-id="45784-117">プロセス内の現在の実行空間を一覧表示し、その実行空間に Windows PowerShell コンソールや ISE デバッガーをアタッチしてスクリプト デバッグを実行するための、新しいコマンドレットが追加されました。</span><span class="sxs-lookup"><span data-stu-id="45784-117">New cmdlets have been added that let you list current runspaces in a process, and attach the Windows PowerShell console or ISE debugger to that runspace for script debugging:</span></span>

-   <span data-ttu-id="45784-118">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="45784-118">Get-Runspace</span></span>
-   <span data-ttu-id="45784-119">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="45784-119">Debug-Runspace</span></span>
-   <span data-ttu-id="45784-120">Enable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="45784-120">Enable-RunspaceDebug</span></span>
-   <span data-ttu-id="45784-121">Disable-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="45784-121">Disable-RunspaceDebug</span></span>
-   <span data-ttu-id="45784-122">Get-RunspaceDebug</span><span class="sxs-lookup"><span data-stu-id="45784-122">Get-RunspaceDebug</span></span>

### <a name="attach-to-process-hosting-powershell"></a><span data-ttu-id="45784-123">PowerShell をホストしているプロセスにアタッチする</span><span class="sxs-lookup"><span data-stu-id="45784-123">Attach to Process hosting PowerShell</span></span>

<span data-ttu-id="45784-124">Windows PowerShell が読み込まれているすべてのコンピューター プロセスにアタッチできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="45784-124">You can now attach to any computer process that has Windows PowerShell loaded.</span></span> <span data-ttu-id="45784-125">これを行うには、プロセスを使って対話型セッションに入ります。これは、Enter-PSSession コマンドレットを実行して、対話型リモート セッションに入る方法と似ています。</span><span class="sxs-lookup"><span data-stu-id="45784-125">You do this by entering into an interactive session with the process, similarly to how you enter into an interactive remote session by running the Enter-PSSession cmdlet:</span></span>

-   <span data-ttu-id="45784-126">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="45784-126">Enter-PSHostProcess</span></span>
-   <span data-ttu-id="45784-127">Exit-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="45784-127">Exit-PSHostProcess</span></span>
