---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/22/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-psdrive?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSDrive
ms.openlocfilehash: df5f335780ad04b2d833180c30cc46a06f85d850
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214608"
---
# <span data-ttu-id="1417b-103">New-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1417b-103">New-PSDrive</span></span>

## <span data-ttu-id="1417b-104">概要</span><span class="sxs-lookup"><span data-stu-id="1417b-104">SYNOPSIS</span></span>
<span data-ttu-id="1417b-105">一時的および永続的にマップされたネットワーク ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="1417b-105">Creates temporary and persistent mapped network drives.</span></span>

## <span data-ttu-id="1417b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1417b-106">SYNTAX</span></span>

### <span data-ttu-id="1417b-107">All</span><span class="sxs-lookup"><span data-stu-id="1417b-107">All</span></span>

```
New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Description <String>]
 [-Scope <String>] [-Persist] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="1417b-108">Description</span><span class="sxs-lookup"><span data-stu-id="1417b-108">DESCRIPTION</span></span>

<span data-ttu-id="1417b-109">`New-PSDrive`コマンドレットでは、ネットワークドライブ、ローカルコンピューター上のディレクトリ、レジストリキー、およびリモートコンピューター上のファイルシステムの場所に関連付けられている固定の Windows マップ済みネットワークドライブなど、データストア内の場所にマップまたは関連付けられている一時ドライブと永続ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="1417b-109">The `New-PSDrive` cmdlet creates temporary and persistent drives that are mapped to or associated with a location in a data store, such as a network drive, a directory on the local computer, or a registry key, and persistent Windows mapped network drives that are associated with a file system location on a remote computer.</span></span>

<span data-ttu-id="1417b-110">一時ドライブは、現在の PowerShell セッションと、現在のセッションで作成したセッションにのみ存在します。</span><span class="sxs-lookup"><span data-stu-id="1417b-110">Temporary drives exist only in the current PowerShell session and in sessions that you create in the current session.</span></span> <span data-ttu-id="1417b-111">PowerShell で有効な任意の名前を持つことができ、任意のローカルまたはリモートリソースにマップできます。</span><span class="sxs-lookup"><span data-stu-id="1417b-111">They can have any name that is valid in PowerShell and can be mapped to any local or remote resource.</span></span> <span data-ttu-id="1417b-112">割り当てられたネットワークドライブの場合と同様に、一時 PowerShell ドライブを使用して、関連付けられているデータストア内のデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="1417b-112">You can use temporary PowerShell drives to access data in the associated data store, just as you would do with any mapped network drive.</span></span> <span data-ttu-id="1417b-113">を使用してドライブの場所を変更 `Set-Location` し、またはを使用してドライブの内容にアクセスでき `Get-Item` `Get-ChildItem` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-113">You can change locations into the drive, by using `Set-Location`, and access the contents of the drive by using `Get-Item` or `Get-ChildItem`.</span></span>

<span data-ttu-id="1417b-114">一時ドライブは PowerShell のみで認識されるため、ファイルエクスプローラー、Windows Management Instrumentation (WMI)、コンポーネントオブジェクトモデル (COM)、Microsoft .NET フレームワークを使用したり、 **NET use** などのツールでアクセスしたりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1417b-114">Because temporary drives are known only to PowerShell, you can't access them by using File Explorer, Windows Management Instrumentation (WMI), Component Object Model (COM), Microsoft .NET Framework, or with tools such as **net use** .</span></span>

<span data-ttu-id="1417b-115">PowerShell 3.0 では、次の機能がに追加されました `New-PSDrive` 。</span><span class="sxs-lookup"><span data-stu-id="1417b-115">The following features were added to `New-PSDrive` in PowerShell 3.0:</span></span>

- <span data-ttu-id="1417b-116">割り当て済みのネットワーク ドライブ</span><span class="sxs-lookup"><span data-stu-id="1417b-116">Mapped network drives.</span></span> <span data-ttu-id="1417b-117">の **Persist** パラメーターを使用して、 `New-PSDrive` Windows マップ済みネットワークドライブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1417b-117">You can use the **Persist** parameter of `New-PSDrive` to create Windows mapped network drives.</span></span> <span data-ttu-id="1417b-118">一時 PowerShell ドライブとは異なり、Windows マップ済みネットワークドライブはセッション固有ではありません。</span><span class="sxs-lookup"><span data-stu-id="1417b-118">Unlike temporary PowerShell drives, Windows mapped network drives aren't session-specific.</span></span> <span data-ttu-id="1417b-119">これらのファイルは Windows に保存され、エクスプローラーや **net use** などの標準の windows ツールを使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="1417b-119">They're saved in Windows and they can be managed by using standard Windows tools, such as File Explorer and **net use** .</span></span> <span data-ttu-id="1417b-120">マップ済みネットワーク ドライブは、ドライブ文字名を持ち、リモート ファイル システムの場所に接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1417b-120">Mapped network drives must have a drive-letter name and be connected to a remote file system location.</span></span> <span data-ttu-id="1417b-121">コマンドのスコープがローカルである場合、ドットソーシングではない場合、 **persist** パラメーターでは、コマンドが実行されているスコープを超える **PSDrive** の作成は保持されません。</span><span class="sxs-lookup"><span data-stu-id="1417b-121">When your command is scoped locally, no dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which the command is running.</span></span> <span data-ttu-id="1417b-122">スクリプト内で実行 `New-PSDrive` していて、ドライブを無期限に保持する場合は、スクリプトをドットで変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1417b-122">If you're running `New-PSDrive` inside a script, and you want the drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="1417b-123">最適な結果を得るために、新しいドライブを無期限に保持するには、 **スコープ** パラメーターをコマンドに追加し、その値を **Global** に設定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-123">For best results, to force a new drive to persist indefinitely, add the **Scope** parameter to your command, and set its value to **Global** .</span></span> <span data-ttu-id="1417b-124">ドットソーシングの詳細については、「 [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-124">For more information about dot-sourcing, see [about_Scripts](../Microsoft.PowerShell.Core/About/about_Scripts.md#script-scope-and-dot-sourcing).</span></span>
- <span data-ttu-id="1417b-125">外部ドライブ。</span><span class="sxs-lookup"><span data-stu-id="1417b-125">External drives.</span></span> <span data-ttu-id="1417b-126">外部ドライブがコンピューターに接続されている場合、PowerShell は新しいドライブを表す **PSDrive** をファイルシステムに自動的に追加します。</span><span class="sxs-lookup"><span data-stu-id="1417b-126">When an external drive is connected to the computer, PowerShell automatically adds a **PSDrive** to the file system that represents the new drive.</span></span> <span data-ttu-id="1417b-127">PowerShell を再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="1417b-127">You don't have to restart PowerShell.</span></span> <span data-ttu-id="1417b-128">同様に、外部ドライブがコンピューターから切断されると、PowerShell は、削除されたドライブを表す **PSDrive** を自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="1417b-128">Similarly, when an external drive is disconnected from the computer, PowerShell automatically deletes the **PSDrive** that represents the removed drive.</span></span>
- <span data-ttu-id="1417b-129">UNC (汎用名前付け規則) パスの資格情報。</span><span class="sxs-lookup"><span data-stu-id="1417b-129">Credentials for Universal Naming Convention (UNC) paths.</span></span>

<span data-ttu-id="1417b-130">**ルート** パラメーターの値がのような UNC パスである場合 `\\Server\Share` は、 **credential** パラメーターの値で指定された資格情報を使用して **PSDrive** が作成されます。</span><span class="sxs-lookup"><span data-stu-id="1417b-130">When the value of the **Root** parameter is a UNC path, such as `\\Server\Share`, the credential specified in the value of the **Credential** parameter is used to create the **PSDrive** .</span></span> <span data-ttu-id="1417b-131">そうしないと、新しいファイルシステムドライブを作成しているときに **資格情報** が有効になりません。</span><span class="sxs-lookup"><span data-stu-id="1417b-131">Otherwise, **Credential** isn't effective when you're creating new file system drives.</span></span>

<span data-ttu-id="1417b-132">一部のコードサンプルでは、スプラッティングを使用して、行の長さを減らし、読みやすさを向上させます。</span><span class="sxs-lookup"><span data-stu-id="1417b-132">Some code samples use splatting to reduce the line length and improve readability.</span></span> <span data-ttu-id="1417b-133">詳細については、「 [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-133">For more information, see [about_Splatting](../Microsoft.PowerShell.Core/About/about_Splatting.md).</span></span>

## <span data-ttu-id="1417b-134">例</span><span class="sxs-lookup"><span data-stu-id="1417b-134">EXAMPLES</span></span>

### <span data-ttu-id="1417b-135">例 1: ネットワーク共有にマップされた一時ドライブを作成する</span><span class="sxs-lookup"><span data-stu-id="1417b-135">Example 1: Create a temporary drive mapped to a network share</span></span>

<span data-ttu-id="1417b-136">この例では、ネットワーク共有にマップされている一時 PowerShell ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="1417b-136">This example creates a temporary PowerShell drive that's mapped to a network share.</span></span>

```powershell
New-PSDrive -Name "Public" -PSProvider "FileSystem" -Root "\\Server01\Public"
```

```Output
Name       Provider      Root
----       --------      ----
Public     FileSystem    \\Server01\Public
```

<span data-ttu-id="1417b-137">`New-PSDrive`**Name** パラメーターを使用して、という名前の powershell ドライブを指定 `Public` し、 **psprovider** パラメーターを使用して powershell プロバイダーを指定し `FileSystem` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-137">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `Public` and the **PSProvider** parameter to specify the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="1417b-138">**Root** パラメーターは、ネットワーク共有の UNC パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-138">The **Root** parameter specifies the network share's UNC path.</span></span>

<span data-ttu-id="1417b-139">PowerShell セッションの内容を表示するには、次のようにします。 `Get-ChildItem -Path Public:`</span><span class="sxs-lookup"><span data-stu-id="1417b-139">To view the contents from a PowerShell session: `Get-ChildItem -Path Public:`</span></span>

### <span data-ttu-id="1417b-140">例 2: ローカルディレクトリにマップされた一時ドライブを作成する</span><span class="sxs-lookup"><span data-stu-id="1417b-140">Example 2: Create a temporary drive mapped to a local directory</span></span>

<span data-ttu-id="1417b-141">この例では、ローカルコンピューター上のディレクトリへのアクセスを提供する一時 PowerShell ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="1417b-141">This example creates a temporary PowerShell drive that provides access to a directory on the local computer.</span></span>

```powershell
$parameters = @{
    Name = "MyDocs"
    PSProvider = "FileSystem"
    Root = "C:\Users\User01\Documents"
    Description = "Maps to my My Documents folder."
}
New-PSDrive @parameters
```

```Output
Name        Provider      Root
----        --------      ----
MyDocs      FileSystem    C:\Users\User01\Documents
```

<span data-ttu-id="1417b-142">スプラッティングは、パラメーターのキーと値を作成します。</span><span class="sxs-lookup"><span data-stu-id="1417b-142">Splatting creates the parameter keys and values.</span></span> <span data-ttu-id="1417b-143">**Name** パラメーターは、ドライブ名 **mydocs** を指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-143">The **Name** parameter specifies the drive name, **MyDocs** .</span></span> <span data-ttu-id="1417b-144">**Psprovider** パラメーターは、PowerShell プロバイダーを指定し `FileSystem` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-144">The **PSProvider** parameter specifies the PowerShell `FileSystem` provider.</span></span> <span data-ttu-id="1417b-145">**Root** ローカルコンピューターのディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-145">**Root** specifies the local computer's directory.</span></span> <span data-ttu-id="1417b-146">**Description** パラメーターはドライブの目的を説明します。</span><span class="sxs-lookup"><span data-stu-id="1417b-146">The **Description** parameter describes the drive's purpose.</span></span> <span data-ttu-id="1417b-147">`New-PSDrive` では、splatted パラメーターを使用してドライブを作成し `MyDocs` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-147">`New-PSDrive` uses the splatted parameters to create the `MyDocs` drive.</span></span>

<span data-ttu-id="1417b-148">PowerShell セッションの内容を表示するには、次のようにします。 `Get-ChildItem -Path MyDocs:`</span><span class="sxs-lookup"><span data-stu-id="1417b-148">To view the contents from a PowerShell session: `Get-ChildItem -Path MyDocs:`</span></span>

### <span data-ttu-id="1417b-149">例 3: レジストリキーの一時ドライブを作成する</span><span class="sxs-lookup"><span data-stu-id="1417b-149">Example 3: Create a temporary drive for a registry key</span></span>

<span data-ttu-id="1417b-150">この例では、レジストリキーへのアクセスを提供する一時 PowerShell ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="1417b-150">This example creates a temporary PowerShell drive that provides access to a registry key.</span></span> <span data-ttu-id="1417b-151">この例では、レジストリキーにマップされている MyCompany という名前のドライブを作成し `HKLM:\Software\MyCompany` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-151">It creates a drive named MyCompany that is mapped to the `HKLM:\Software\MyCompany` registry key.</span></span>

```powershell
New-PSDrive -Name "MyCompany" -PSProvider "Registry" -Root "HKLM:\Software\MyCompany"
```

```Output
Name           Provider      Root
----           --------      ----
MyCompany      Registry      HKLM:\Software\MyCompany
```

<span data-ttu-id="1417b-152">`New-PSDrive`**Name** パラメーターを使用して、という名前の powershell ドライブを指定 `MyCompany` し、 **psprovider** パラメーターを使用して powershell プロバイダーを指定し `Registry` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-152">`New-PSDrive` uses the **Name** parameter to specify PowerShell drive named `MyCompany` and the **PSProvider** parameter to specify the PowerShell `Registry` provider.</span></span> <span data-ttu-id="1417b-153">**Root** パラメーターは、レジストリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-153">The **Root** parameter specifies the registry location.</span></span>

<span data-ttu-id="1417b-154">PowerShell セッションの内容を表示するには、次のようにします。 `Get-ChildItem -Path MyCompany:`</span><span class="sxs-lookup"><span data-stu-id="1417b-154">To view the contents from a PowerShell session: `Get-ChildItem -Path MyCompany:`</span></span>

### <span data-ttu-id="1417b-155">例 4: 資格情報を使用して、永続的にマップされたネットワークドライブを作成する</span><span class="sxs-lookup"><span data-stu-id="1417b-155">Example 4: Create a persistent mapped network drive using credentials</span></span>

<span data-ttu-id="1417b-156">この例では、ドメインサービスアカウントの資格情報で認証されたネットワークドライブをマップします。</span><span class="sxs-lookup"><span data-stu-id="1417b-156">This example maps a network drive that's authenticated with a domain service account's credentials.</span></span>
<span data-ttu-id="1417b-157">資格情報を格納する **PSCredential** オブジェクトと、パスワードを **SecureString** として保存する方法の詳細については、 **Credential** パラメーターの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-157">For more information about the **PSCredential** object that stores credentials and how passwords are stored as a **SecureString** , see the **Credential** parameter's description.</span></span>

```powershell
$cred = Get-Credential -Credential Contoso\ServiceAccount
New-PSDrive -Name "S" -Root "\\Server01\Scripts" -Persist -PSProvider "FileSystem" -Credential $cred
Net Use
```

```Output
Status       Local     Remote                    Network
---------------------------------------------------------
OK           S:        \\Server01\Scripts        Microsoft Windows Network
```

> [!NOTE]
> <span data-ttu-id="1417b-158">スクリプトで上記のスニペットを使用する場合は、 **スコープ** パラメーターの値を "Global" に設定して、ドライブが現在のスコープの外部に保持されるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="1417b-158">Remember, if you use the above snippet in a script, set the **Scope** parameter value to "Global" to ensure the drive persists outside the current scope.</span></span>

<span data-ttu-id="1417b-159">変数には、 `$cred` サービスアカウントの資格情報を含む **PSCredential** オブジェクトが格納されます。</span><span class="sxs-lookup"><span data-stu-id="1417b-159">The `$cred` variable stores a **PSCredential** object that contains the service account's credentials.</span></span> <span data-ttu-id="1417b-160">`Get-Credential`**SecureString** に格納されているパスワードを入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417b-160">`Get-Credential` prompts you to enter the password that's stored in a **SecureString** .</span></span>

<span data-ttu-id="1417b-161">`New-PSDrive` 複数のパラメーターを使用して、マップされたネットワークドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="1417b-161">`New-PSDrive` creates the mapped network drive by using several parameters.</span></span> <span data-ttu-id="1417b-162">**名前** `S` Windows が受け入れるドライブ文字を指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-162">**Name** specifies the `S` drive letter that Windows accepts.</span></span> <span data-ttu-id="1417b-163">および **Root** `\\Server01\Scripts` は、リモートコンピューター上の場所として定義されます。</span><span class="sxs-lookup"><span data-stu-id="1417b-163">and **Root** defines `\\Server01\Scripts` as the location on a remote computer.</span></span> <span data-ttu-id="1417b-164">**Persist** は、ローカルコンピューターに保存されている Windows マップ済みネットワークドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="1417b-164">**Persist** creates a Windows mapped network drive that's saved on the local computer.</span></span> <span data-ttu-id="1417b-165">**Psprovider** はプロバイダーを指定し `FileSystem` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-165">**PSProvider** specifies the `FileSystem` provider.</span></span> <span data-ttu-id="1417b-166">**資格情報** は変数を使用して、 `$cred` 認証用のサービスアカウント資格情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="1417b-166">**Credential** uses the `$cred` variable to get the service account credentials for authentication.</span></span>

<span data-ttu-id="1417b-167">マップされたドライブは、PowerShell セッション、エクスプローラー、および **net use** などのツールを使用して、ローカルコンピューターで表示できます。</span><span class="sxs-lookup"><span data-stu-id="1417b-167">The mapped drive can be viewed on the local computer in PowerShell sessions, File Explorer, and with tools such as **net use** .</span></span> <span data-ttu-id="1417b-168">PowerShell セッションの内容を表示するには、次のようにします。 `Get-ChildItem -Path S:`</span><span class="sxs-lookup"><span data-stu-id="1417b-168">To view the contents from a PowerShell session: `Get-ChildItem -Path S:`</span></span>

### <span data-ttu-id="1417b-169">例 5: 永続的なドライブと一時ドライブを作成する</span><span class="sxs-lookup"><span data-stu-id="1417b-169">Example 5: Create persistent and temporary drives</span></span>

<span data-ttu-id="1417b-170">この例では、永続的にマップされたネットワークドライブと、同じネットワーク共有にマップされている一時 PowerShell ドライブとの違いを示します。</span><span class="sxs-lookup"><span data-stu-id="1417b-170">This example shows the difference between a persistent mapped network drive and a temporary PowerShell drive that is mapped to the same network share.</span></span>

<span data-ttu-id="1417b-171">PowerShell セッションを閉じた後で新しいセッションを開くと、一時的なドライブは使用できません `PSDrive:` が、永続的 `X:` なドライブは使用できます。</span><span class="sxs-lookup"><span data-stu-id="1417b-171">If you close the PowerShell session and then open a new session, the temporary `PSDrive:` isn't available, but the persistent `X:` drive is available.</span></span> <span data-ttu-id="1417b-172">ネットワークドライブのマップに使用する方法を決定するときは、ドライブの使用方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-172">When deciding which method to use to map network drives, consider how you'll use the drive.</span></span> <span data-ttu-id="1417b-173">たとえば、永続化する必要があるかどうか、および他の Windows 機能に対してドライブを表示する必要があるかどうかなどです。</span><span class="sxs-lookup"><span data-stu-id="1417b-173">For example, whether it has to be persistent, and whether the drive has to be visible to other Windows features.</span></span>

```powershell
# Create a temporary PowerShell drive called PSDrive:
# that's mapped to the \\Server01\Public network share.
New-PSDrive -Name "PSDrive" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Use the Persist parameter of New-PSDrive to create the X: mapped network drive,
# which is also mapped to the \\Server01\Public network share.
New-PSDrive -Persist -Name "X" -PSProvider "FileSystem" -Root "\\Server01\Public"

# Now, you can use the Get-PSDrive drive cmdlet to examine the two drives.
# The drives appear to be the same, although the network share name appears only
# in the root of the PSDrive: drive.
Get-PSDrive -Name "PSDrive", "X"
```

```Output
Name       Provider      Root
----       --------      ----

PsDrive    FileSystem    \\Server01\public
X          FileSystem    X:\
```

```powershell
# Get-Member cmdlet shows that the drives have the same object type,
# System.Management.Automation.PSDriveInfo.
Get-PSDrive "PSDrive", "x" | Get-Member
```

```Output
TypeName: System.Management.Automation.PSDriveInfo

Name                MemberType   Definition
----                ----------   ----------
CompareTo           Method       System.Int32 CompareTo(PSDriveInfo drive),
Equals              Method       System.Boolean Equals(Object obj),
GetHashCode         Method       System.Int32 GetHashCode()
...
```

```powershell
# Net Use and Get-CimInstance for the Win32_LogicalDisk class,
# and Win32_NetworkConnection class find only the persistent X: drive.
# PowerShell temporary drives are known only to PowerShell.
Net Use
Get-CimInstance Win32_LogicalDisk | Format-Table -Property DeviceID
Get-CimInstance Win32_NetworkConnection
```

```Output
Status       Local     Remote                    Network
--------------------------------------------------------
OK           X:        \\contoso-pc\data         Microsoft Windows Network

deviceid
--------
C:
D:
X:

LocalName    RemoteName              ConnectionState          Status
---------    ----------              ---------------          ------
X:           \\products\public       Disconnected             Unavailable
```

## <span data-ttu-id="1417b-174">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1417b-174">PARAMETERS</span></span>

### <span data-ttu-id="1417b-175">-Confirm</span><span class="sxs-lookup"><span data-stu-id="1417b-175">-Confirm</span></span>

<span data-ttu-id="1417b-176">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1417b-176">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-177">-Credential</span><span class="sxs-lookup"><span data-stu-id="1417b-177">-Credential</span></span>

<span data-ttu-id="1417b-178">このアクションを実行するアクセス許可を持つユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-178">Specifies a user account that has permission to do this action.</span></span> <span data-ttu-id="1417b-179">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="1417b-179">The default is the current user.</span></span>

<span data-ttu-id="1417b-180">PowerShell 3.0 以降、 **ルート** パラメーターの値が UNC パスの場合は、資格情報を使用してファイルシステムドライブを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1417b-180">Since PowerShell 3.0, when the value of the **Root** parameter is a UNC path, you can use credentials to create file system drives.</span></span>

<span data-ttu-id="1417b-181">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成される **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-181">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="1417b-182">ユーザー名を入力すると、パスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="1417b-182">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="1417b-183">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="1417b-183">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="1417b-184">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-184">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-185">-Description</span><span class="sxs-lookup"><span data-stu-id="1417b-185">-Description</span></span>

<span data-ttu-id="1417b-186">ドライブの簡単な説明テキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-186">Specifies a brief text description of the drive.</span></span> <span data-ttu-id="1417b-187">任意の文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="1417b-187">Type any string.</span></span>

<span data-ttu-id="1417b-188">セッションのすべてのドライブの説明を表示するには、「」を参照してください `Get-PSDrive | Format-Table Name, Description` 。</span><span class="sxs-lookup"><span data-stu-id="1417b-188">To see the descriptions of all the session's drives, `Get-PSDrive | Format-Table Name, Description`.</span></span>

<span data-ttu-id="1417b-189">特定のドライブの説明を表示するには、「」と入力 `(Get-PSDrive <DriveName>).Description` します。</span><span class="sxs-lookup"><span data-stu-id="1417b-189">To see the description of a particular drive, type `(Get-PSDrive <DriveName>).Description`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-190">-Name</span><span class="sxs-lookup"><span data-stu-id="1417b-190">-Name</span></span>

<span data-ttu-id="1417b-191">新しいドライブの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-191">Specifies a name for the new drive.</span></span> <span data-ttu-id="1417b-192">永続的にマップされたネットワークドライブの場合は、ドライブ文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="1417b-192">For persistent mapped network drives, use a drive letter.</span></span> <span data-ttu-id="1417b-193">一時 PowerShell ドライブの場合、ドライブ文字に制限されていないので、任意の有効な文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="1417b-193">For temporary PowerShell drives, you aren't limited to drive letters, use any valid string.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-194">-Persist</span><span class="sxs-lookup"><span data-stu-id="1417b-194">-Persist</span></span>

<span data-ttu-id="1417b-195">このコマンドレットによって、Windows マップ済みネットワークドライブが作成されることを示します。</span><span class="sxs-lookup"><span data-stu-id="1417b-195">Indicates that this cmdlet creates a Windows mapped network drive.</span></span> <span data-ttu-id="1417b-196">**Persist** パラメーターは Windows でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="1417b-196">The **Persist** parameter is only available on Windows.</span></span>

<span data-ttu-id="1417b-197">マップ済みネットワーク ドライブは、ローカル コンピューターの Windows に保存されます。</span><span class="sxs-lookup"><span data-stu-id="1417b-197">Mapped network drives are saved in Windows on the local computer.</span></span> <span data-ttu-id="1417b-198">これらは永続的で、セッション固有ではなく、エクスプローラーや他のツールで表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="1417b-198">They're persistent, not session-specific, and can be viewed and managed in File Explorer and other tools.</span></span>

<span data-ttu-id="1417b-199">ドットソーシングを使用せずにコマンドのスコープをローカルに指定した場合、 **persist** パラメーターでは、コマンドを実行するスコープを超える **PSDrive** の作成は保持されません。</span><span class="sxs-lookup"><span data-stu-id="1417b-199">When you scope the command locally, without dot-sourcing, the **Persist** parameter doesn't persist the creation of a **PSDrive** beyond the scope in which you run the command.</span></span> <span data-ttu-id="1417b-200">スクリプト内でを実行 `New-PSDrive` し、新しいドライブを無期限に保持する場合は、スクリプトをドットで変換する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1417b-200">If you run `New-PSDrive` inside a script, and you want the new drive to persist indefinitely, you must dot-source the script.</span></span> <span data-ttu-id="1417b-201">最適な結果を得るために、新しいドライブを強制的に永続化するには、 **スコープ** パラメーターの値として **Global** を指定し、コマンドに **persist** を含めます。</span><span class="sxs-lookup"><span data-stu-id="1417b-201">For best results, to force a new drive to persist, specify **Global** as the value of the **Scope** parameter and include **Persist** in your command.</span></span>

<span data-ttu-id="1417b-202">ドライブ名は、やなどの文字である必要が `D` あり `E` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-202">The name of the drive must be a letter, such as `D` or `E`.</span></span> <span data-ttu-id="1417b-203">**ルート** パラメーターの値は、別のコンピューターの UNC パスである必要があります。</span><span class="sxs-lookup"><span data-stu-id="1417b-203">The value of **Root** parameter must be a UNC path of a different computer.</span></span> <span data-ttu-id="1417b-204">**Psprovider** パラメーターの値はである必要があり `FileSystem` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-204">The **PSProvider** parameter's value must be `FileSystem`.</span></span>

<span data-ttu-id="1417b-205">Windows マップ済みネットワーク ドライブを切断するには、`Remove-PSDrive` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="1417b-205">To disconnect a Windows mapped network drive, use the `Remove-PSDrive` cmdlet.</span></span> <span data-ttu-id="1417b-206">Windows マップ済みネットワーク ドライブを切断すると、マッピングは現在のセッションから削除されるだけでなく、コンピューターから完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="1417b-206">When you disconnect a Windows mapped network drive, the mapping is permanently deleted from the computer, not just deleted from the current session.</span></span>

<span data-ttu-id="1417b-207">マップ済みネットワーク ドライブは、ユーザー アカウントに固有です。</span><span class="sxs-lookup"><span data-stu-id="1417b-207">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="1417b-208">昇格されたセッションまたは別のユーザーの資格情報を使用するセッションで作成されたマップされたドライブは、別の資格情報を使用して開始されたセッションでは</span><span class="sxs-lookup"><span data-stu-id="1417b-208">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-209">-PSProvider</span><span class="sxs-lookup"><span data-stu-id="1417b-209">-PSProvider</span></span>

<span data-ttu-id="1417b-210">この種類のドライブをサポートする PowerShell プロバイダーを指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-210">Specifies the PowerShell provider that supports drives of this kind.</span></span>

<span data-ttu-id="1417b-211">たとえば、ドライブがネットワーク共有またはファイルシステムディレクトリに関連付けられている場合、PowerShell プロバイダーはに `FileSystem` なります。</span><span class="sxs-lookup"><span data-stu-id="1417b-211">For example, if the drive is associated with a network share or file system directory, the PowerShell provider is `FileSystem`.</span></span> <span data-ttu-id="1417b-212">ドライブがレジストリキーに関連付けられている場合、プロバイダーは `Registry` です。</span><span class="sxs-lookup"><span data-stu-id="1417b-212">If the drive is associated with a registry key, the provider is `Registry`.</span></span>

<span data-ttu-id="1417b-213">一時 PowerShell ドライブは、任意の PowerShell プロバイダーに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1417b-213">Temporary PowerShell drives can be associated with any PowerShell provider.</span></span> <span data-ttu-id="1417b-214">マップされたネットワークドライブは、プロバイダーにのみ関連付けることができ `FileSystem` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-214">Mapped network drives can be associated only with the `FileSystem` provider.</span></span>

<span data-ttu-id="1417b-215">PowerShell セッションのプロバイダーの一覧を表示するには、コマンドレットを使用し `Get-PSProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-215">To see a list of the providers in your PowerShell session, use the `Get-PSProvider` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-216">-ルート</span><span class="sxs-lookup"><span data-stu-id="1417b-216">-Root</span></span>

<span data-ttu-id="1417b-217">PowerShell ドライブをマップするデータストアの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-217">Specifies the data store location to which a PowerShell drive is mapped.</span></span>

<span data-ttu-id="1417b-218">たとえば、のようなネットワーク共有、などの `\\Server01\Public` ローカルディレクトリ、レジストリキー (など) を指定し `C:\Program Files` `HKLM:\Software\Microsoft` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-218">For example, specify a network share, such as `\\Server01\Public`, a local directory, such as `C:\Program Files`, or a registry key, such as `HKLM:\Software\Microsoft`.</span></span>

<span data-ttu-id="1417b-219">一時 PowerShell ドライブは、サポートされている任意のプロバイダードライブ上のローカルまたはリモートの場所に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1417b-219">Temporary PowerShell drives can be associated with a local or remote location on any supported provider drive.</span></span> <span data-ttu-id="1417b-220">マップ済みネットワーク ドライブは、リモート コンピューター上のファイル システムの場所だけに関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="1417b-220">Mapped network drives can be associated only with a file system location on a remote computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-221">-スコープ</span><span class="sxs-lookup"><span data-stu-id="1417b-221">-Scope</span></span>

<span data-ttu-id="1417b-222">ドライブのスコープを指定します。</span><span class="sxs-lookup"><span data-stu-id="1417b-222">Specifies a scope for the drive.</span></span> <span data-ttu-id="1417b-223">このパラメーターに指定できる値は、 **Global** 、 **Local** 、および **Script** 、または現在のスコープを基準とする数値です。</span><span class="sxs-lookup"><span data-stu-id="1417b-223">The acceptable values for this parameter are: **Global** , **Local** , and **Script** , or a number relative to the current scope.</span></span> <span data-ttu-id="1417b-224">スコープは、スコープの数から0までの範囲です。</span><span class="sxs-lookup"><span data-stu-id="1417b-224">Scopes number 0 through the number of scopes.</span></span> <span data-ttu-id="1417b-225">現在のスコープ番号は0で、その親は1です。</span><span class="sxs-lookup"><span data-stu-id="1417b-225">The current scope number is 0 and its parent is 1.</span></span> <span data-ttu-id="1417b-226">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-226">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Local
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-227">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="1417b-227">-UseTransaction</span></span>

<span data-ttu-id="1417b-228">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="1417b-228">Includes the command in the active transaction.</span></span> <span data-ttu-id="1417b-229">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="1417b-229">This parameter is valid only when a transaction is in progress.</span></span> <span data-ttu-id="1417b-230">詳細については、「[about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-230">For more information, see [about_Transactions](../Microsoft.PowerShell.Core/About/about_Transactions.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-231">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="1417b-231">-WhatIf</span></span>

<span data-ttu-id="1417b-232">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="1417b-232">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="1417b-233">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="1417b-233">The cmdlet isn't run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1417b-234">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="1417b-234">CommonParameters</span></span>

<span data-ttu-id="1417b-235">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="1417b-235">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="1417b-236">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1417b-237">入力</span><span class="sxs-lookup"><span data-stu-id="1417b-237">INPUTS</span></span>

### <span data-ttu-id="1417b-238">なし</span><span class="sxs-lookup"><span data-stu-id="1417b-238">None</span></span>

<span data-ttu-id="1417b-239">このコマンドレットに入力をパイプラインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1417b-239">You can't pipeline input to this cmdlet.</span></span>

## <span data-ttu-id="1417b-240">出力</span><span class="sxs-lookup"><span data-stu-id="1417b-240">OUTPUTS</span></span>

### <span data-ttu-id="1417b-241">System.Management.Automation.PSDriveInfo</span><span class="sxs-lookup"><span data-stu-id="1417b-241">System.Management.Automation.PSDriveInfo</span></span>

## <span data-ttu-id="1417b-242">注</span><span class="sxs-lookup"><span data-stu-id="1417b-242">NOTES</span></span>

<span data-ttu-id="1417b-243">`New-PSDrive` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="1417b-243">`New-PSDrive` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="1417b-244">セッションで使用可能なプロバイダーの一覧を表示するには、を使用 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="1417b-244">To list the providers available in your session, use `Get-PSProvider`.</span></span> <span data-ttu-id="1417b-245">プロバイダーの詳細については、「 [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1417b-245">For more information about providers, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="1417b-246">マップ済みネットワーク ドライブは、ユーザー アカウントに固有です。</span><span class="sxs-lookup"><span data-stu-id="1417b-246">Mapped network drives are specific to a user account.</span></span> <span data-ttu-id="1417b-247">昇格されたセッションまたは別のユーザーの資格情報を使用するセッションで作成されたマップされたドライブは、別の資格情報を使用して開始されたセッションでは</span><span class="sxs-lookup"><span data-stu-id="1417b-247">Mapped drives created in elevated sessions or sessions using the credential of another user aren't visible in sessions started using different credentials.</span></span>

## <span data-ttu-id="1417b-248">関連リンク</span><span class="sxs-lookup"><span data-stu-id="1417b-248">RELATED LINKS</span></span>

[<span data-ttu-id="1417b-249">about_Providers</span><span class="sxs-lookup"><span data-stu-id="1417b-249">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

[<span data-ttu-id="1417b-250">Get-Credential</span><span class="sxs-lookup"><span data-stu-id="1417b-250">Get-Credential</span></span>](../Microsoft.PowerShell.Security/Get-Credential.md)

[<span data-ttu-id="1417b-251">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1417b-251">Get-PSDrive</span></span>](Get-PSDrive.md)

[<span data-ttu-id="1417b-252">Remove-PSDrive</span><span class="sxs-lookup"><span data-stu-id="1417b-252">Remove-PSDrive</span></span>](Remove-PSDrive.md)
