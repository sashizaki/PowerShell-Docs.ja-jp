---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: コンピューターの状態を変更する
description: この例では、PowerShell から外部コマンドを使用して、コンピューターの構成を管理する方法を示します。
ms.openlocfilehash: 341f29f24d7e4bd341ccc0954b16d4b75880678b
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500676"
---
# <a name="changing-computer-state"></a><span data-ttu-id="d15c0-104">コンピューターの状態を変更する</span><span class="sxs-lookup"><span data-stu-id="d15c0-104">Changing Computer State</span></span>

<span data-ttu-id="d15c0-105">PowerShell でコンピューターをリセットするには、標準のコマンド ライン ツール、WMI、または CIM クラスのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="d15c0-105">To reset a computer in PowerShell, use either a standard command-line tool, WMI, or a CIM class.</span></span>
<span data-ttu-id="d15c0-106">PowerShell は単にツールを実行するために使用するだけですが、PowerShell でコンピューターの電力状態を変更する手順には、PowerShell での外部ツールの使用方法に関する重要な詳細も含まれています。</span><span class="sxs-lookup"><span data-stu-id="d15c0-106">Although you are using PowerShell only to run the tool, learning how to change a computer's power state in PowerShell illustrates some of the important details about working with external tools in PowerShell.</span></span>

## <a name="locking-a-computer"></a><span data-ttu-id="d15c0-107">コンピューターをロックする</span><span class="sxs-lookup"><span data-stu-id="d15c0-107">Locking a Computer</span></span>

<span data-ttu-id="d15c0-108">一般的に入手可能なツールを使ってコンピューターを直接ロックする唯一の方法は、 **user32.dll** の **LockWorkstation()** 関数を呼び出すことです。</span><span class="sxs-lookup"><span data-stu-id="d15c0-108">The only way to lock a computer directly with the standard available tools is to call the **LockWorkstation()** function in **user32.dll** :</span></span>

```powershell
rundll32.exe user32.dll,LockWorkStation
```

<span data-ttu-id="d15c0-109">このコマンドを実行すると、ワークステーションが直ちにロックされます。</span><span class="sxs-lookup"><span data-stu-id="d15c0-109">This command immediately locks the workstation.</span></span> <span data-ttu-id="d15c0-110">このコマンドでは、 **rundll32.exe** を使用して Windows DLL を実行 (および、繰り返し使用できるようにそれらのライブラリを保存) することにより、Windows の管理関数のライブラリである `user32.dll` を実行します。</span><span class="sxs-lookup"><span data-stu-id="d15c0-110">It uses **rundll32.exe** , which runs Windows DLLs (and saves their libraries for repeated use) to run `user32.dll`, a library of Windows management functions.</span></span>

<span data-ttu-id="d15c0-111">Windows XP の場合など、ユーザーの簡易切り替えが有効なときにワークステーションをロックすると、コンピューターでは、現在のユーザーのスクリーン セーバーが起動するのではなく、ユーザーのログオン画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d15c0-111">When you lock a workstation while Fast User Switching is enabled, such as on Windows XP, the computer displays the user logon screen rather than starting the current user's screensaver.</span></span>

<span data-ttu-id="d15c0-112">ターミナル サーバーで特定のセッションをシャットダウンするには、 **tsshutdn.exe** コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d15c0-112">To shut down particular sessions on a Terminal Server, use the **tsshutdn.exe** command-line tool.</span></span>

## <a name="logging-off-the-current-session"></a><span data-ttu-id="d15c0-113">現在のセッションからログオフする</span><span class="sxs-lookup"><span data-stu-id="d15c0-113">Logging Off the Current Session</span></span>

<span data-ttu-id="d15c0-114">ローカル システム上でセッションからログオフする場合、いくつかの方法が考えられます。</span><span class="sxs-lookup"><span data-stu-id="d15c0-114">You can use several different techniques to log off of a session on the local system.</span></span> <span data-ttu-id="d15c0-115">最も簡単な方法は、リモート デスクトップ/ターミナル サービスのコマンドライン ツールである **logoff.exe** を使用することです (詳細については、PowerShell プロンプトで「`logoff /?`」と入力してください)。</span><span class="sxs-lookup"><span data-stu-id="d15c0-115">The simplest way is to use the Remote Desktop/Terminal Services command-line tool, **logoff.exe** (For details, at the PowerShell prompt, type `logoff /?`).</span></span> <span data-ttu-id="d15c0-116">現在アクティブなセッションからログオフするには、引数を付けずに「`logoff`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="d15c0-116">To log off the current active session, type `logoff` with no arguments.</span></span>

<span data-ttu-id="d15c0-117">また、 **shutdown.exe** ツールにログオフのオプションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d15c0-117">You can also use the **shutdown.exe** tool with its logoff option:</span></span>

```powershell
shutdown.exe -l
```

<span data-ttu-id="d15c0-118">他に、WMI を使用するというオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="d15c0-118">Another option is to use WMI.</span></span> <span data-ttu-id="d15c0-119">**Win32_OperatingSystem** クラスには、 **Shutdown** メソッドがあります。</span><span class="sxs-lookup"><span data-stu-id="d15c0-119">The **Win32_OperatingSystem** class has a **Shutdown** method.</span></span>
<span data-ttu-id="d15c0-120">このメソッドに 0 フラグを指定して呼び出すと、ログオフが開始されます。</span><span class="sxs-lookup"><span data-stu-id="d15c0-120">Invoking the method with the 0 flag initiates logoff:</span></span>

<span data-ttu-id="d15c0-121">**Shutdown** メソッドの詳細については、「 [Win32_OperatingSystem クラスの Shutdown メソッド](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d15c0-121">For more information about the **Shutdown** method, see [Shutdown method of the Win32_OperatingSystem class](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)</span></span>

```powershell
Get-CimInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a><span data-ttu-id="d15c0-122">コンピューターをシャットダウンまたは再起動する</span><span class="sxs-lookup"><span data-stu-id="d15c0-122">Shutting Down or Restarting a Computer</span></span>

<span data-ttu-id="d15c0-123">通常、コンピューターのシャットダウンと再起動は同じ種類に属するタスクです。</span><span class="sxs-lookup"><span data-stu-id="d15c0-123">Shutting down and restarting computers are generally the same types of task.</span></span> <span data-ttu-id="d15c0-124">コンピューターをシャットダウンできるツールであれば、コンピューターを再起動することもできます。逆にコンピューターを再起動できるツールであれば、コンピューターをシャットダウンすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d15c0-124">Tools that shut down a computer will generally restart it as well—and vice versa.</span></span> <span data-ttu-id="d15c0-125">PowerShell からコンピューターを簡単に再起動する方法としては、2 とおりの方法があります。</span><span class="sxs-lookup"><span data-stu-id="d15c0-125">There are two straightforward options for restarting a computer from PowerShell.</span></span> <span data-ttu-id="d15c0-126">**tsshutdn.exe** または **shutdown.exe** に適切な引数を指定して実行することです。</span><span class="sxs-lookup"><span data-stu-id="d15c0-126">Use either **tsshutdn.exe** or **shutdown.exe** with appropriate arguments.</span></span> <span data-ttu-id="d15c0-127">詳しい使用方法は、`tsshutdn.exe /?` または `shutdown.exe /?` で参照できます。</span><span class="sxs-lookup"><span data-stu-id="d15c0-127">You can get detailed usage information from `tsshutdn.exe /?` or `shutdown.exe /?`.</span></span>

<span data-ttu-id="d15c0-128">シャットダウン操作と再起動操作は、PowerShell から直接実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="d15c0-128">You can also perform shutdown and restart operations directly from PowerShell as well.</span></span>

<span data-ttu-id="d15c0-129">コンピューターをシャットダウンするには、Stop-Computer コマンドを使用します</span><span class="sxs-lookup"><span data-stu-id="d15c0-129">To shut down the computer, use the Stop-Computer command</span></span>

```powershell
Stop-Computer
```

<span data-ttu-id="d15c0-130">オペレーティング システムを再起動するには、Restart-Computer コマンドを使用します</span><span class="sxs-lookup"><span data-stu-id="d15c0-130">To restart the operating system, use the Restart-Computer command</span></span>

```powershell
Restart-Computer
```

<span data-ttu-id="d15c0-131">コンピューターを強制的に直ちに再起動するには、-Force パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d15c0-131">To force an immediate restart of the computer, use the -Force parameter.</span></span>

```powershell
Restart-Computer -Force
```
