---
title: PowerShell Core の WS-Management (WSMan) リモート処理
description: WSMan を使用した PowerShell Core のリモート処理
ms.date: 08/06/2018
ms.openlocfilehash: e5f00128bc8ebc1b432cc77a5896a9e09d684109
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "62058881"
---
# <a name="ws-management-wsman-remoting-in-powershell-core"></a><span data-ttu-id="62f6c-103">PowerShell Core の WS-Management (WSMan) リモート処理</span><span class="sxs-lookup"><span data-stu-id="62f6c-103">WS-Management (WSMan) Remoting in PowerShell Core</span></span>

## <a name="instructions-to-create-a-remoting-endpoint"></a><span data-ttu-id="62f6c-104">リモート エンドポイントの作成手順</span><span class="sxs-lookup"><span data-stu-id="62f6c-104">Instructions to Create a Remoting Endpoint</span></span>

<span data-ttu-id="62f6c-105">Windows PowerShell Core パッケージには、WinRM プラグイン (`pwrshplugin.dll`) とインストール スクリプト (`Install-PowerShellRemoting.ps1`) が `$PSHome` に含まれています。</span><span class="sxs-lookup"><span data-stu-id="62f6c-105">The PowerShell Core package for Windows includes a WinRM plug-in (`pwrshplugin.dll`) and an installation script (`Install-PowerShellRemoting.ps1`) in `$PSHome`.</span></span>
<span data-ttu-id="62f6c-106">これらのファイルにより、そのエンドポイントが指定されている場合、PowerShell が受信の PowerShell リモート接続を受け入れるようになります。</span><span class="sxs-lookup"><span data-stu-id="62f6c-106">These files enable PowerShell to accept incoming PowerShell remote connections when its endpoint is specified.</span></span>

### <a name="motivation"></a><span data-ttu-id="62f6c-107">動機</span><span class="sxs-lookup"><span data-stu-id="62f6c-107">Motivation</span></span>

<span data-ttu-id="62f6c-108">PowerShell をインストールすると、`New-PSSession` と `Enter-PSSession` を使用したリモート コンピューターへの PowerShell セッションを確立できます。</span><span class="sxs-lookup"><span data-stu-id="62f6c-108">An installation of PowerShell can establish PowerShell sessions to remote computers using `New-PSSession` and `Enter-PSSession`.</span></span>
<span data-ttu-id="62f6c-109">PowerShell でリモートからの受信接続を受け入れるようにするには、ユーザーが WinRM リモート エンドポイントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62f6c-109">To enable it to accept incoming PowerShell remote connections, the user must create a WinRM remoting endpoint.</span></span>
<span data-ttu-id="62f6c-110">これは、ユーザーが Install-PowerShellRemoting.ps1 を実行し、WinRM エンドポイントを作成することを明示的に選択するシナリオです。</span><span class="sxs-lookup"><span data-stu-id="62f6c-110">This is an explicit opt-in scenario where the user runs Install-PowerShellRemoting.ps1 to create the WinRM endpoint.</span></span>
<span data-ttu-id="62f6c-111">このインストール スクリプトは、`Enable-PSRemoting` に同じアクションを実行する機能が追加されるまでの短期的なソリューションです。</span><span class="sxs-lookup"><span data-stu-id="62f6c-111">The installation script is a short-term solution until we add additional functionality to `Enable-PSRemoting` to perform the same action.</span></span>
<span data-ttu-id="62f6c-112">詳細については、問題 [#1193](https://github.com/PowerShell/PowerShell/issues/1193) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62f6c-112">For more details, please see issue [#1193](https://github.com/PowerShell/PowerShell/issues/1193).</span></span>

### <a name="script-actions"></a><span data-ttu-id="62f6c-113">スクリプト アクション</span><span class="sxs-lookup"><span data-stu-id="62f6c-113">Script Actions</span></span>

<span data-ttu-id="62f6c-114">スクリプトは、以下のことを行います</span><span class="sxs-lookup"><span data-stu-id="62f6c-114">The script</span></span>

1. <span data-ttu-id="62f6c-115">`$env:windir\System32\PowerShell` 内にプラグイン用のディレクトリを作成します</span><span class="sxs-lookup"><span data-stu-id="62f6c-115">Creates a directory for the plug-in within `$env:windir\System32\PowerShell`</span></span>
1. <span data-ttu-id="62f6c-116">この場所に pwrshplugin.dll をコピーします</span><span class="sxs-lookup"><span data-stu-id="62f6c-116">Copies pwrshplugin.dll to that location</span></span>
1. <span data-ttu-id="62f6c-117">構成ファイルを生成します</span><span class="sxs-lookup"><span data-stu-id="62f6c-117">Generates a configuration file</span></span>
1. <span data-ttu-id="62f6c-118">WinRM にそのプラグインを登録します</span><span class="sxs-lookup"><span data-stu-id="62f6c-118">Registers that plug-in with WinRM</span></span>

### <a name="registration"></a><span data-ttu-id="62f6c-119">登録</span><span class="sxs-lookup"><span data-stu-id="62f6c-119">Registration</span></span>

<span data-ttu-id="62f6c-120">このスクリプトは、管理者レベルで PowerShell セッション内で実行される必要があり、次の 2 つのモードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="62f6c-120">The script must be executed within an Administrator-level PowerShell session and runs in two modes.</span></span>

#### <a name="executed-by-the-instance-of-powershell-that-it-will-register"></a><span data-ttu-id="62f6c-121">登録する PowerShell インスタンスによって実行されます</span><span class="sxs-lookup"><span data-stu-id="62f6c-121">Executed by the instance of PowerShell that it will register</span></span>

```powershell
Install-PowerShellRemoting.ps1
```

#### <a name="executed-by-another-instance-of-powershell-on-behalf-of-the-instance-that-it-will-register"></a><span data-ttu-id="62f6c-122">登録するインスタンスの代わりの別の PowerShell インスタンスによって実行されます</span><span class="sxs-lookup"><span data-stu-id="62f6c-122">Executed by another instance of PowerShell on behalf of the instance that it will register</span></span>

```powershell
<path to powershell>\Install-PowerShellRemoting.ps1 -PowerShellHome "<absolute path to the instance's $PSHOME>"
```

<span data-ttu-id="62f6c-123">たとえば次のようになります。</span><span class="sxs-lookup"><span data-stu-id="62f6c-123">For Example:</span></span>

```powershell
Set-Location -Path 'C:\Program Files\PowerShell\6.0.0\'
.\Install-PowerShellRemoting.ps1 -PowerShellHome "C:\Program Files\PowerShell\6.0.0\"
```

<span data-ttu-id="62f6c-124">**注**:リモート処理の登録スクリプトによって WinRM は再起動されるので、既存のすべての PSRP セッションはこのスクリプトの実行後、直ちに終了します。</span><span class="sxs-lookup"><span data-stu-id="62f6c-124">**NOTE:** The remoting registration script will restart WinRM, so all existing PSRP sessions will terminate immediately after the script is run.</span></span> <span data-ttu-id="62f6c-125">リモート セッション中に実行される場合、これによって接続は終了します。</span><span class="sxs-lookup"><span data-stu-id="62f6c-125">If run during a remote session, this will terminate the connection.</span></span>

## <a name="how-to-connect-to-the-new-endpoint"></a><span data-ttu-id="62f6c-126">新しいエンドポイントに接続する方法</span><span class="sxs-lookup"><span data-stu-id="62f6c-126">How to Connect to the New Endpoint</span></span>

<span data-ttu-id="62f6c-127">`-ConfigurationName "some endpoint name"` を指定して、新しい PowerShell エンドポイントに対して PowerShell セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="62f6c-127">Create a PowerShell session to the new PowerShell endpoint by specifying `-ConfigurationName "some endpoint name"`.</span></span> <span data-ttu-id="62f6c-128">上記の例から、PowerShell インスタンスに接続するには、次のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="62f6c-128">To connect to the PowerShell instance from the example above, use either:</span></span>

```powershell
New-PSSession ... -ConfigurationName "powershell.6.0.0"
Enter-PSSession ... -ConfigurationName "powershell.6.0.0"
```

<span data-ttu-id="62f6c-129">なお、`-ConfigurationName` が指定されていない `New-PSSession` と `Enter-PSSession` の呼び出しは、既定の PowerShell のエンドポイントである `microsoft.powershell` をターゲットとします。</span><span class="sxs-lookup"><span data-stu-id="62f6c-129">Note that `New-PSSession` and `Enter-PSSession` invocations that do not specify `-ConfigurationName` will target the default PowerShell endpoint, `microsoft.powershell`.</span></span>