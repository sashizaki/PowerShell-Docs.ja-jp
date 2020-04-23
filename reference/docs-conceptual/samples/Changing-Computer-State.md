---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: コンピューターの状態を変更する
ms.openlocfilehash: 9278df55ba027134a61c8ed4e89b5b839d460b29
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "75736915"
---
# <a name="changing-computer-state"></a><span data-ttu-id="78ffc-103">コンピューターの状態を変更する</span><span class="sxs-lookup"><span data-stu-id="78ffc-103">Changing Computer State</span></span>

<span data-ttu-id="78ffc-104">PowerShell でコンピューターをリセットするには、標準のコマンド ライン ツール、WMI、または CIM クラスのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="78ffc-104">To reset a computer in PowerShell, use either a standard command-line tool, WMI or CIM class.</span></span>
<span data-ttu-id="78ffc-105">PowerShell は単にツールを実行するために使用するだけですが、PowerShell でコンピューターの電力状態を変更する手順には、PowerShell での外部ツールの使用方法に関する重要な詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="78ffc-105">Although you are using PowerShell only to run the tool, learning how to change a computer's power state in PowerShell illustrates some of the important details about working with external tools in PowerShell.</span></span>

## <a name="locking-a-computer"></a><span data-ttu-id="78ffc-106">コンピューターをロックする</span><span class="sxs-lookup"><span data-stu-id="78ffc-106">Locking a Computer</span></span>

<span data-ttu-id="78ffc-107">一般的に入手可能なツールを使ってコンピューターを直接ロックする唯一の方法は、**user32.dll** の **LockWorkstation()** 関数を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="78ffc-107">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll**:</span></span>

```powershell
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="78ffc-108">このコマンドを実行すると、ワークステーションが直ちにロックされます。</span><span class="sxs-lookup"><span data-stu-id="78ffc-108">This command immediately locks the workstation.</span></span> <span data-ttu-id="78ffc-109">このコマンドでは、**rundll32.exe** を使用して Windows DLL を実行 (および、繰り返し使用できるようにそれらのライブラリを保存) することにより、Windows の管理関数のライブラリである `user32.dll` を実行します。</span><span class="sxs-lookup"><span data-stu-id="78ffc-109">It uses **rundll32.exe**, which runs Windows DLLs (and saves their libraries for repeated use) to run `user32.dll`, a library of Windows management functions.</span></span>

<span data-ttu-id="78ffc-110">Windows XP の場合など、ユーザーの簡易切り替えが有効なときにワークステーションをロックすると、コンピューターでは、現在のユーザーのスクリーン セーバーが起動するのではなく、ユーザーのログオン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="78ffc-110">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="78ffc-111">ターミナル サーバーで特定のセッションをシャットダウンするには、**tsshutdn.exe** コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="78ffc-111">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

## <a name="logging-off-the-current-session"></a><span data-ttu-id="78ffc-112">現在のセッションからログオフする</span><span class="sxs-lookup"><span data-stu-id="78ffc-112">Logging Off the Current Session</span></span>

<span data-ttu-id="78ffc-113">ローカル システム上でセッションからログオフする場合、いくつかの方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="78ffc-113">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="78ffc-114">最も簡単な方法は、リモート デスクトップ/ターミナル サービスのコマンドライン ツールである **logoff.exe** を使用することです (詳細については、PowerShell プロンプトで「`logoff /?`」と入力してください)。</span><span class="sxs-lookup"><span data-stu-id="78ffc-114">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the PowerShell prompt, type `logoff /?`).</span></span> <span data-ttu-id="78ffc-115">現在アクティブなセッションからログオフするには、引数を付けずに「`logoff`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="78ffc-115">To log off the current active session, type `logoff` with no arguments.</span></span>

<span data-ttu-id="78ffc-116">また、**shutdown.exe** ツールにログオフのオプションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="78ffc-116">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```powershell
shutdown.exe -l
```

<span data-ttu-id="78ffc-117">他に、WMI を使用するというオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="78ffc-117">Another option is to use WMI.</span></span> <span data-ttu-id="78ffc-118">**Win32_OperatingSystem** クラスには、**Shutdown** メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="78ffc-118">The **Win32_OperatingSystem** class has a **Shutdown** method.</span></span>
<span data-ttu-id="78ffc-119">このメソッドに 0 フラグを指定して呼び出すと、ログオフが開始されます。</span><span class="sxs-lookup"><span data-stu-id="78ffc-119">Invoking the method with the 0 flag initiates logoff:</span></span>

<span data-ttu-id="78ffc-120">**Shutdown** メソッドの詳細については、「[Win32_OperatingSystem クラスの Shutdown メソッド](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="78ffc-120">For more information about the **Shutdown** method, see [Shutdown method of the Win32_OperatingSystem class](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)</span></span>

```powershell
Get-CimInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="78ffc-121">コンピューターをシャットダウンまたは再起動する</span><span class="sxs-lookup"><span data-stu-id="78ffc-121">Shutting Down or Restarting a Computer</span></span>

<span data-ttu-id="78ffc-122">通常、コンピューターのシャットダウンと再起動は同じ種類に属するタスクです。</span><span class="sxs-lookup"><span data-stu-id="78ffc-122">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="78ffc-123">コンピューターをシャットダウンできるツールであれば、コンピューターを再起動することもできます。逆にコンピューターを再起動できるツールであれば、コンピューターをシャットダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="78ffc-123">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="78ffc-124">PowerShell からコンピューターを簡単に再起動する方法としては、2 とおりの方法があります。</span><span class="sxs-lookup"><span data-stu-id="78ffc-124">There are two straightforward options for restarting a computer from PowerShell.</span></span> <span data-ttu-id="78ffc-125">**tsshutdn.exe** または **shutdown.exe** に適切な引数を指定して実行することです。</span><span class="sxs-lookup"><span data-stu-id="78ffc-125">Use either **tsshutdn.exe** or **shutdown.exe** with appropriate arguments.</span></span> <span data-ttu-id="78ffc-126">詳しい使用方法は、`tsshutdn.exe /?` または `shutdown.exe /?` で参照できます。</span><span class="sxs-lookup"><span data-stu-id="78ffc-126">You can get detailed usage information from `tsshutdn.exe /?` or `shutdown.exe /?`.</span></span>

<span data-ttu-id="78ffc-127">シャットダウン操作と再起動操作は、PowerShell から直接実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="78ffc-127">You can also perform shutdown and restart operations directly from PowerShell as well.</span></span>

<span data-ttu-id="78ffc-128">コンピューターをシャットダウンするには、Stop-Computer コマンドを使用します</span><span class="sxs-lookup"><span data-stu-id="78ffc-128">To shut down the computer, use the Stop-Computer command</span></span>

```powershell
Stop-Computer
```

<span data-ttu-id="78ffc-129">オペレーティング システムを再起動するには、Restart-Computer コマンドを使用します</span><span class="sxs-lookup"><span data-stu-id="78ffc-129">To restart the operating system, use the Restart-Computer command</span></span>

```powershell
Restart-Computer
```

<span data-ttu-id="78ffc-130">コンピューターを強制的に直ちに再起動するには、-Force パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="78ffc-130">To force an immediate restart of the computer, use the -Force parameter.</span></span>

```powershell
Restart-Computer -Force
```
