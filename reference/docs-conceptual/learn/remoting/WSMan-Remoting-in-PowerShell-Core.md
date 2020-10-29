---
title: PowerShell Core の WS-Management (WSMan) リモート処理
description: WSMan を使用した PowerShell Core のリモート処理
ms.date: 08/06/2018
ms.openlocfilehash: fdc4159279db28b8ee60bc0853e19512a1f9ec14
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501305"
---
# <a name="ws-management-wsman-remoting-in-powershell-core"></a><span data-ttu-id="8a890-103">PowerShell Core の WS-Management (WSMan) リモート処理</span><span class="sxs-lookup"><span data-stu-id="8a890-103">WS-Management (WSMan) Remoting in PowerShell Core</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="8a890-104">リモート エンドポイントの作成手順</span><span class="sxs-lookup"><span data-stu-id="8a890-104">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="8a890-105">Windows PowerShell Core パッケージには、WinRM プラグイン (`pwrshplugin.dll`) とインストール スクリプト (`Install-PowerShellRemoting.ps1`) が `$PSHome` に含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a890-105">The PowerShell Core package for Windows includes a WinRM plug-in (`pwrshplugin.dll`) and an installation script (`Install-PowerShellRemoting.ps1`) in `$PSHome`.</span></span> <span data-ttu-id="8a890-106">これらのファイルにより、そのエンドポイントが指定されている場合、PowerShell が受信の PowerShell リモート接続を受け入れるようになります。</span><span class="sxs-lookup"><span data-stu-id="8a890-106">These files enable PowerShell to accept incoming PowerShell remote connections when its endpoint is specified.</span></span>

### <a name="motivation"></a><span data-ttu-id="8a890-107">目的</span><span class="sxs-lookup"><span data-stu-id="8a890-107">Motivation</span></span>

<span data-ttu-id="8a890-108">PowerShell をインストールすると、`New-PSSession` と `Enter-PSSession` を使用したリモート コンピューターへの PowerShell セッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="8a890-108">An installation of PowerShell can establish PowerShell sessions to remote computers using `New-PSSession` and `Enter-PSSession`.</span></span> <span data-ttu-id="8a890-109">PowerShell でリモートからの受信接続を受け入れるようにするには、ユーザーが WinRM リモート エンドポイントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a890-109">To enable it to accept incoming PowerShell remote connections, the user must create a WinRM remoting endpoint.</span></span> <span data-ttu-id="8a890-110">これは、ユーザーが Install-PowerShellRemoting.ps1 を実行し、WinRM エンドポイントを作成することを明示的に選択するシナリオです。</span><span class="sxs-lookup"><span data-stu-id="8a890-110">This is an explicit opt-in scenario where the user runs Install-PowerShellRemoting.ps1 to create the WinRM endpoint.</span></span> <span data-ttu-id="8a890-111">このインストール スクリプトは、`Enable-PSRemoting` に同じアクションを実行する機能が追加されるまでの短期的なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="8a890-111">The installation script is a short-term solution until we add additional functionality to `Enable-PSRemoting` to perform the same action.</span></span> <span data-ttu-id="8a890-112">詳細については、問題 [#1193](https://github.com/PowerShell/PowerShell/issues/1193) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a890-112">For more details, please see issue [#1193](https://github.com/PowerShell/PowerShell/issues/1193).</span></span>

### <a name="script-actions"></a><span data-ttu-id="8a890-113">[スクリプト操作]</span><span class="sxs-lookup"><span data-stu-id="8a890-113">Script Actions</span></span>

<span data-ttu-id="8a890-114">スクリプトは、以下のことを行います</span><span class="sxs-lookup"><span data-stu-id="8a890-114">The script</span></span>

1. <span data-ttu-id="8a890-115">`$env:windir\System32\PowerShell` 内にプラグイン用のディレクトリを作成します</span><span class="sxs-lookup"><span data-stu-id="8a890-115">Creates a directory for the plug-in within `$env:windir\System32\PowerShell`</span></span>
1. <span data-ttu-id="8a890-116">この場所に pwrshplugin.dll をコピーします</span><span class="sxs-lookup"><span data-stu-id="8a890-116">Copies pwrshplugin.dll to that location</span></span>
1. <span data-ttu-id="8a890-117">構成ファイルを生成します</span><span class="sxs-lookup"><span data-stu-id="8a890-117">Generates a configuration file</span></span>
1. <span data-ttu-id="8a890-118">WinRM にそのプラグインを登録します</span><span class="sxs-lookup"><span data-stu-id="8a890-118">Registers that plug-in with WinRM</span></span>

### <a name="registration"></a><span data-ttu-id="8a890-119">登録</span><span class="sxs-lookup"><span data-stu-id="8a890-119">Registration</span></span>

<span data-ttu-id="8a890-120">このスクリプトは、管理者レベルで PowerShell セッション内で実行される必要があり、次の 2 つのモードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a890-120">The script must be executed within an Administrator-level PowerShell session and runs in two modes.</span></span>

#### <a name="executed-by-the-instance-of-powershell-that-it-will-register"></a><span data-ttu-id="8a890-121">登録する PowerShell インスタンスによって実行されます</span><span class="sxs-lookup"><span data-stu-id="8a890-121">Executed by the instance of PowerShell that it will register</span></span>

```powershell
Install-PowerShellRemoting.ps1
```

#### <a name="executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register"></a><span data-ttu-id="8a890-122">登録するインスタンスの代わりの別の PowerShell インスタンスによって実行されます</span><span class="sxs-lookup"><span data-stu-id="8a890-122">Executed by another instance of PowerShell on behalf of the instance that it will register</span></span>

```powershell
<path to powershell>\Install-PowerShellRemoting.ps1 -PowerShellHome "<absolute path to the instance's $PSHOME>"
```

<span data-ttu-id="8a890-123">たとえば次のようになります。</span><span class="sxs-lookup"><span data-stu-id="8a890-123">For Example:</span></span>

```powershell
Set-Location -Path 'C:\Program Files\PowerShell\6.0.0\'
.\Install-PowerShellRemoting.ps1 -PowerShellHome "C:\Program Files\PowerShell\6.0.0\"
```

> [!NOTE]
> <span data-ttu-id="8a890-124">リモート処理登録スクリプトによって、WinRM が再起動されます。</span><span class="sxs-lookup"><span data-stu-id="8a890-124">The remoting registration script restarts WinRM.</span></span> <span data-ttu-id="8a890-125">既存のすべての PSRP セッションは、スクリプトが実行された直後に終了します。</span><span class="sxs-lookup"><span data-stu-id="8a890-125">All existing PSRP sessions are terminate immediately after the script is run.</span></span> <span data-ttu-id="8a890-126">リモート セッションの間も実行していると、スクリプトによって接続が終了されます。</span><span class="sxs-lookup"><span data-stu-id="8a890-126">If run during a remote session, the script terminates the connection.</span></span>

## <a name="how-to-connect-to-the-new-endpoint"></a><span data-ttu-id="8a890-127">新しいエンドポイントに接続する方法</span><span class="sxs-lookup"><span data-stu-id="8a890-127">How to Connect to the New Endpoint</span></span>

<span data-ttu-id="8a890-128">`-ConfigurationName "some endpoint name"` を指定して、新しい PowerShell エンドポイントに対して PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a890-128">Create a PowerShell session to the new PowerShell endpoint by specifying `-ConfigurationName "some endpoint name"`.</span></span> <span data-ttu-id="8a890-129">上記の例から、PowerShell インスタンスに接続するには、次のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="8a890-129">To connect to the PowerShell instance from the example above, use either:</span></span>

```powershell
New-PSSession ... -ConfigurationName "powershell.6.0.0"
Enter-PSSession ... -ConfigurationName "powershell.6.0.0"
```

<span data-ttu-id="8a890-130">なお、`-ConfigurationName` が指定されていない `New-PSSession` と `Enter-PSSession` の呼び出しは、既定の PowerShell のエンドポイントである `microsoft.powershell` をターゲットとします。</span><span class="sxs-lookup"><span data-stu-id="8a890-130">Note that `New-PSSession` and `Enter-PSSession` invocations that do not specify `-ConfigurationName` will target the default PowerShell endpoint, `microsoft.powershell`.</span></span>
