---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: コンピューターの状態を変更する
ms.assetid: 8093268b-27f8-4a49-8871-142c5cc33f01
ms.openlocfilehash: 4b5b4adb349dd8036117c364ed2ebb1ffaf8c88f
ms.sourcegitcommit: c3f1a83b59484651119630f3089aa51b6e7d4c3c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2018
ms.locfileid: "39267887"
---
# <a name="changing-computer-state"></a><span data-ttu-id="2918c-103">コンピューターの状態を変更する</span><span class="sxs-lookup"><span data-stu-id="2918c-103">Changing Computer State</span></span>

<span data-ttu-id="2918c-104">Windows PowerShell でコンピューターをリセットするには、標準のコマンド ライン ツールまたは WMI クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="2918c-104">To reset a computer in Windows PowerShell, use either a standard command-line tool or a WMI class.</span></span> <span data-ttu-id="2918c-105">Windows PowerShell は単にツールを実行するために使用するだけですが、Windows PowerShell でコンピューターの電力状態を変更する手順には、Windows PowerShell での外部ツールの使用方法に関する重要な詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="2918c-105">Although you are using Windows PowerShell only to run the tool, learning how to change a computer's power state in Windows PowerShell illustrates some of the important details about working with external tools in Windows PowerShell.</span></span>

### <a name="locking-a-computer"></a><span data-ttu-id="2918c-106">コンピューターをロックする</span><span class="sxs-lookup"><span data-stu-id="2918c-106">Locking a Computer</span></span>

<span data-ttu-id="2918c-107">一般的に入手可能なツールを使ってコンピューターを直接ロックする唯一の方法は、**user32.dll** の **LockWorkstation()** 関数を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="2918c-107">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll**:</span></span>

```
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="2918c-108">このコマンドを実行すると、ワークステーションが直ちにロックされます。</span><span class="sxs-lookup"><span data-stu-id="2918c-108">This command immediately locks the workstation.</span></span> <span data-ttu-id="2918c-109">このコマンドでは、*rundll32.exe* を使用して Windows DLL を実行 (および、繰り返し使用できるようにそれらのライブラリを保存) することにより、Windows の管理関数のライブラリである user32.dll を実行します。</span><span class="sxs-lookup"><span data-stu-id="2918c-109">It uses *rundll32.exe*, which runs Windows DLLs (and saves their libraries for repeated use) to run user32.dll, a library of Windows management functions.</span></span>

<span data-ttu-id="2918c-110">Windows XP の場合など、ユーザーの簡易切り替えが有効なときにワークステーションをロックすると、コンピューターでは、現在のユーザーのスクリーン セーバーが起動するのではなく、ユーザーのログオン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2918c-110">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="2918c-111">ターミナル サーバーで特定のセッションをシャットダウンするには、**tsshutdn.exe** コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="2918c-111">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

### <a name="logging-off-the-current-session"></a><span data-ttu-id="2918c-112">現在のセッションからログオフする</span><span class="sxs-lookup"><span data-stu-id="2918c-112">Logging Off the Current Session</span></span>

<span data-ttu-id="2918c-113">ローカル システム上でセッションからログオフする場合、いくつかの方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="2918c-113">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="2918c-114">最も簡単な方法は、リモート デスクトップ/ターミナル サービスのコマンドライン ツールである **logoff.exe** を使用することです (詳細については、Windows PowerShell プロンプトで **logoff /?** と入力してください)。</span><span class="sxs-lookup"><span data-stu-id="2918c-114">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the Windows PowerShell prompt, type **logoff /?**).</span></span> <span data-ttu-id="2918c-115">現在アクティブなセッションからログオフするには、引数を付けずに **logoff** と入力します。</span><span class="sxs-lookup"><span data-stu-id="2918c-115">To log off the current active session, type **logoff** with no arguments.</span></span>

<span data-ttu-id="2918c-116">また、**shutdown.exe** ツールにログオフのオプションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2918c-116">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```
shutdown.exe -l
```

<span data-ttu-id="2918c-117">3 つ目は、WMI を使用する方法です。</span><span class="sxs-lookup"><span data-stu-id="2918c-117">A third option is to use WMI.</span></span> <span data-ttu-id="2918c-118">Win32_OperatingSystem クラスには、Win32Shutdown メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="2918c-118">The Win32_OperatingSystem class has a Win32Shutdown method.</span></span> <span data-ttu-id="2918c-119">このメソッドに 0 フラグを指定して呼び出すと、ログオフが開始されます。</span><span class="sxs-lookup"><span data-stu-id="2918c-119">Invoking the method with the 0 flag initiates logoff:</span></span>

```powershell
(Get-WmiObject -Class Win32_OperatingSystem -ComputerName .).Win32Shutdown(0)
```

<span data-ttu-id="2918c-120">詳細について、および Win32Shutdown メソッドの他の機能については、MSDN の「Win32_OperatingSystem クラスの Win32Shutdown メソッド」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2918c-120">For more information, and to find other features of the Win32Shutdown method, see "Win32Shutdown Method of the Win32_OperatingSystem Class" in MSDN.</span></span>

### <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="2918c-121">コンピューターをシャットダウンまたは再起動する</span><span class="sxs-lookup"><span data-stu-id="2918c-121">Shutting Down or Restarting a Computer</span></span>

<span data-ttu-id="2918c-122">通常、コンピューターのシャットダウンと再起動は同じ種類に属するタスクです。</span><span class="sxs-lookup"><span data-stu-id="2918c-122">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="2918c-123">コンピューターをシャットダウンできるツールであれば、コンピューターを再起動することもできます。逆にコンピューターを再起動できるツールであれば、コンピューターをシャットダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2918c-123">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="2918c-124">Windows PowerShell からコンピューターを簡単に再起動する方法としては、2 とおりの方法があります。</span><span class="sxs-lookup"><span data-stu-id="2918c-124">There are two straightforward options for restarting a computer from Windows PowerShell.</span></span> <span data-ttu-id="2918c-125">Tsshutdn.exe または Shutdown.exe に適切な引数を指定して実行することです。</span><span class="sxs-lookup"><span data-stu-id="2918c-125">Use either Tsshutdn.exe or Shutdown.exe with appropriate arguments.</span></span> <span data-ttu-id="2918c-126">詳しい使用方法は、**tsshutdn.exe ?**</span><span class="sxs-lookup"><span data-stu-id="2918c-126">You can get detailed usage information from **tsshutdn.exe /?**</span></span> <span data-ttu-id="2918c-127">または **shutdown.exe ?** を実行すると参照できます。</span><span class="sxs-lookup"><span data-stu-id="2918c-127">or **shutdown.exe /?**.</span></span>

<span data-ttu-id="2918c-128">シャットダウン操作と再起動操作は、Windows PowerShell から直接実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="2918c-128">You can also perform shutdown and restart operations directly from Windows PowerShell as well.</span></span>

<span data-ttu-id="2918c-129">コンピューターをシャットダウンするには、stop-computer コマンドを使用します</span><span class="sxs-lookup"><span data-stu-id="2918c-129">To shut down the computer, use the stop-computer command</span></span>

```powershell
stop-computer
```

<span data-ttu-id="2918c-130">オペレーティング システムを再起動するには、restart-computer コマンドを使用します</span><span class="sxs-lookup"><span data-stu-id="2918c-130">To restart the operating system, use the restart-computer command</span></span>

```powershell
restart-computer
```
