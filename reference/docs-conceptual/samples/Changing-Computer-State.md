---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: コンピューターの状態を変更する
ms.openlocfilehash: de3e31e358548943a015b7bba275c4461202b20f
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "70386279"
---
# <a name="changing-computer-state"></a><span data-ttu-id="55397-103">コンピューターの状態を変更する</span><span class="sxs-lookup"><span data-stu-id="55397-103">Changing Computer State</span></span>

<span data-ttu-id="55397-104">Windows PowerShell でコンピューターをリセットするには、標準のコマンド ライン ツール、WMI、または CIM クラスのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="55397-104">To reset a computer in Windows PowerShell, use either a standard command-line tool, WMI or CIM class.</span></span> <span data-ttu-id="55397-105">Windows PowerShell は単にツールを実行するために使用するだけですが、Windows PowerShell でコンピューターの電力状態を変更する手順には、Windows PowerShell での外部ツールの使用方法に関する重要な詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="55397-105">Although you are using Windows PowerShell only to run the tool, learning how to change a computer's power state in Windows PowerShell illustrates some of the important details about working with external tools in Windows PowerShell.</span></span>

## <a name="locking-a-computer"></a><span data-ttu-id="55397-106">コンピューターをロックする</span><span class="sxs-lookup"><span data-stu-id="55397-106">Locking a Computer</span></span>

<span data-ttu-id="55397-107">一般的に入手可能なツールを使ってコンピューターを直接ロックする唯一の方法は、**user32.dll** の **LockWorkstation()** 関数を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="55397-107">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll**:</span></span>

```
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="55397-108">このコマンドを実行すると、ワークステーションが直ちにロックされます。</span><span class="sxs-lookup"><span data-stu-id="55397-108">This command immediately locks the workstation.</span></span> <span data-ttu-id="55397-109">このコマンドでは、*rundll32.exe* を使用して Windows DLL を実行 (および、繰り返し使用できるようにそれらのライブラリを保存) することにより、Windows の管理関数のライブラリである user32.dll を実行します。</span><span class="sxs-lookup"><span data-stu-id="55397-109">It uses *rundll32.exe*, which runs Windows DLLs (and saves their libraries for repeated use) to run user32.dll, a library of Windows management functions.</span></span>

<span data-ttu-id="55397-110">Windows XP などで、ユーザーの簡易切り替えが有効なときにワークステーションをロックすると、コンピューターでは、現在のユーザーのスクリーン セーバーが起動するのではなく、ユーザーのログオン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55397-110">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="55397-111">ターミナル サーバーで特定のセッションをシャットダウンするには、**tsshutdn.exe** コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="55397-111">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

## <a name="logging-off-the-current-session"></a><span data-ttu-id="55397-112">現在のセッションからログオフする</span><span class="sxs-lookup"><span data-stu-id="55397-112">Logging Off the Current Session</span></span>

<span data-ttu-id="55397-113">ローカル システム上でセッションからログオフする場合、いくつかの方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="55397-113">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="55397-114">最も簡単な方法は、リモート デスクトップ/ターミナル サービスのコマンドライン ツールである **logoff.exe** を使用することです (詳細については、Windows PowerShell プロンプトで **logoff /?** と入力してください)。</span><span class="sxs-lookup"><span data-stu-id="55397-114">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the Windows PowerShell prompt, type **logoff /?**).</span></span> <span data-ttu-id="55397-115">現在アクティブなセッションからログオフするには、引数を付けずに **logoff** と入力します。</span><span class="sxs-lookup"><span data-stu-id="55397-115">To log off the current active session, type **logoff** with no arguments.</span></span>

<span data-ttu-id="55397-116">また、**shutdown.exe** ツールにログオフのオプションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="55397-116">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```
shutdown.exe -l
```

<span data-ttu-id="55397-117">他に、WMI を使用するというオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="55397-117">Another option is to use WMI.</span></span> <span data-ttu-id="55397-118">Win32_OperatingSystem クラスには、Win32Shutdown メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="55397-118">The Win32_OperatingSystem class has a Win32Shutdown method.</span></span> <span data-ttu-id="55397-119">このメソッドに 0 フラグを指定して呼び出すと、ログオフが開始されます。</span><span class="sxs-lookup"><span data-stu-id="55397-119">Invoking the method with the 0 flag initiates logoff:</span></span>

```powershell
(Get-WmiObject -Class Win32_OperatingSystem -ComputerName .).Win32Shutdown(0)
```

<span data-ttu-id="55397-120">詳細について、および Win32Shutdown メソッドの他の機能については、MSDN の「Win32_OperatingSystem クラスの Win32Shutdown メソッド」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55397-120">For more information, and to find other features of the Win32Shutdown method, see "Win32Shutdown Method of the Win32_OperatingSystem Class" in MSDN.</span></span>

<span data-ttu-id="55397-121">最後に、WMI メソッドで説明したのと同じ Win32_OperatingSystem クラスで CIM を使用できます。</span><span class="sxs-lookup"><span data-stu-id="55397-121">Finally you can use CIM with the same Win32_OperatingSystem class as described above in the WMI method.</span></span>

```powershell
Get-CIMInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="55397-122">コンピューターをシャットダウンまたは再起動する</span><span class="sxs-lookup"><span data-stu-id="55397-122">Shutting Down or Restarting a Computer</span></span>

<span data-ttu-id="55397-123">通常、コンピューターのシャットダウンと再起動は同じ種類に属するタスクです。</span><span class="sxs-lookup"><span data-stu-id="55397-123">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="55397-124">コンピューターをシャットダウンできるツールであれば、コンピューターを再起動することもできます。逆にコンピューターを再起動できるツールであれば、コンピューターをシャットダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="55397-124">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="55397-125">Windows PowerShell からコンピューターを簡単に再起動する方法としては、2 とおりの方法があります。</span><span class="sxs-lookup"><span data-stu-id="55397-125">There are two straightforward options for restarting a computer from Windows PowerShell.</span></span> <span data-ttu-id="55397-126">Tsshutdn.exe または Shutdown.exe に適切な引数を指定して実行することです。</span><span class="sxs-lookup"><span data-stu-id="55397-126">Use either Tsshutdn.exe or Shutdown.exe with appropriate arguments.</span></span> <span data-ttu-id="55397-127">詳しい使用方法は、**tsshutdn.exe ?**</span><span class="sxs-lookup"><span data-stu-id="55397-127">You can get detailed usage information from **tsshutdn.exe /?**</span></span> <span data-ttu-id="55397-128">または **shutdown.exe ?** を実行すると参照できます。</span><span class="sxs-lookup"><span data-stu-id="55397-128">or **shutdown.exe /?**.</span></span>

<span data-ttu-id="55397-129">シャットダウン操作と再起動操作は、Windows PowerShell から直接実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="55397-129">You can also perform shutdown and restart operations directly from Windows PowerShell as well.</span></span>

<span data-ttu-id="55397-130">コンピューターをシャットダウンするには、Stop-Computer コマンドを使用します</span><span class="sxs-lookup"><span data-stu-id="55397-130">To shut down the computer, use the Stop-Computer command</span></span>

```powershell
Stop-Computer
```

<span data-ttu-id="55397-131">オペレーティング システムを再起動するには、Restart-Computer コマンドを使用します</span><span class="sxs-lookup"><span data-stu-id="55397-131">To restart the operating system, use the Restart-Computer command</span></span>

```powershell
Restart-Computer
```

<span data-ttu-id="55397-132">コンピューターを強制的に直ちに再起動するには、-Force パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="55397-132">To force an immediate restart of the computer, use the -Force parameter.</span></span>

```powershell
Restart-Computer -Force
```
