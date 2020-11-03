---
description: コンピューターにリモート接続できるユーザーとそのユーザーが実行できるコマンドを決定するセッション構成について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 12/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Session_Configurations
ms.openlocfilehash: 0956e2e96cb67d1c4b8c3ef245c6fa084b781351
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221168"
---
# <a name="about-session-configurations"></a><span data-ttu-id="07cf2-104">セッション構成について</span><span class="sxs-lookup"><span data-stu-id="07cf2-104">About Session Configurations</span></span>

## <a name="short-description"></a><span data-ttu-id="07cf2-105">概要</span><span class="sxs-lookup"><span data-stu-id="07cf2-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="07cf2-106">コンピューターにリモート接続できるユーザーとそのユーザーが実行できるコマンドを決定するセッション構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-106">Describes session configurations, which determine the users who can connect to the computer remotely and the commands they can run.</span></span>

## <a name="long-description"></a><span data-ttu-id="07cf2-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="07cf2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="07cf2-108">セッション構成は、"エンドポイント" とも呼ばれ、ローカルコンピューター上の設定のグループで、リモートユーザーまたはローカルユーザーがローカルコンピューター上の PowerShell に接続するときに作成される PowerShell セッションの環境を定義します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-108">A session configuration, also known as an "endpoint" is a group of settings on the local computer that define the environment for the PowerShell sessions that are created when remote or local users connect to PowerShell on the local computer.</span></span>

<span data-ttu-id="07cf2-109">コンピューターの管理者は、セッション構成を使用してコンピューターを保護し、コンピューターに接続するユーザーのカスタム環境を定義できます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-109">Administrators of the computer can use session configurations to protect the computer and to define custom environments for users who connect to the computer.</span></span>

<span data-ttu-id="07cf2-110">また、管理者は、セッション構成を使用して、リモートでコンピューターに接続するために必要なアクセス許可を決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-110">Administrators can also use session configurations to determine the permissions that are required to connect to the computer remotely.</span></span> <span data-ttu-id="07cf2-111">既定では、管理者グループのメンバーのみが、セッション構成を使用してリモート接続するためのアクセス許可を持っていますが、既定の設定を変更して、すべてのユーザーまたは選択したユーザーがコンピューターにリモート接続できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-111">By default, only members of the Administrators group have permission to use the session configuration to connect remotely, but you can change the default settings to allow all users, or selected users, to connect remotely to your computer.</span></span>

<span data-ttu-id="07cf2-112">PowerShell 3.0 以降では、セッション構成ファイルを使用して、セッション構成の要素を定義できます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-112">Beginning in PowerShell 3.0, you can use a session configuration file to define the elements of a session configuration.</span></span> <span data-ttu-id="07cf2-113">この機能を使用すると、コードを記述したり、セッション構成のプロパティを検出したりすることなく、簡単にセッションをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-113">This feature makes it easy to customize sessions without writing code and to discover the properties of a session configuration.</span></span> <span data-ttu-id="07cf2-114">セッション構成ファイルを作成するには、New-PSSessionConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-114">To create a session configuration file, use the New-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="07cf2-115">セッション構成ファイルの詳細については、「[about_Session_Configuration_Files](about_Session_Configuration_Files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07cf2-115">For more information about session configuration files, see [about_Session_Configuration_Files](about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="07cf2-116">セッション構成は、Web Services for Management (WS-MANAGEMENT) ベースの PowerShell リモート処理の機能です。</span><span class="sxs-lookup"><span data-stu-id="07cf2-116">Session configurations are a feature of Web Services for Management (WS-Management) based PowerShell remoting.</span></span> <span data-ttu-id="07cf2-117">これらは、リモートコンピューターに接続するために、新しい PSSession、Invoke コマンド、または Enter-PSSession コマンドレットを使用する場合にのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-117">They are used only when you use the New-PSSession, Invoke-Command, or Enter-PSSession cmdlets to connect to a remote computer.</span></span>

<span data-ttu-id="07cf2-118">注: セッション構成を管理するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-118">Note: To manage the session configurations, start PowerShell with the "Run as administrator" option.</span></span>

<span data-ttu-id="07cf2-119">セッション構成について</span><span class="sxs-lookup"><span data-stu-id="07cf2-119">About Session Configurations</span></span>

<span data-ttu-id="07cf2-120">すべての PowerShell セッションは、セッション構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-120">Every PowerShell session uses a session configuration.</span></span> <span data-ttu-id="07cf2-121">これには、New-PSSession または Enter-PSSession コマンドレットを使用して作成した永続的なセッションと、WS-MANAGEMENT ベースのリモート処理テクノロジを使用するコマンドレットの ComputerName パラメーターを使用するときに PowerShell で作成される一時的なセッション (Invoke コマンドなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-121">This includes persistent sessions that you create by using the New-PSSession or Enter-PSSession cmdlets, and the temporary sessions that PowerShell creates when you use the ComputerName parameter of a cmdlet that uses WS-Management-based remoting technology, such as Invoke-Command.</span></span>

<span data-ttu-id="07cf2-122">管理者は、セッション構成を使用してコンピューターのリソースを保護し、コンピューターに接続するユーザーのカスタム環境を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-122">Administrators can use session configurations to protect the resources of the computer and to create custom environments for users who connect to the computer.</span></span> <span data-ttu-id="07cf2-123">たとえば、セッション構成を使用して、セッションでコンピューターが受信するオブジェクトのサイズを制限したり、セッションの言語モードを定義したり、セッションで使用できるコマンドレット、プロバイダー、および関数を指定したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-123">For example, you can use a session configuration to limit the size of objects that the computer receives in the session, to define the language mode of the session, and to specify the cmdlets, providers, and functions that are available in the session.</span></span>

<span data-ttu-id="07cf2-124">セッション構成のセキュリティ記述子を構成することにより、セッション構成を使用してコンピューターに接続できるユーザーを決定します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-124">By configuring the security descriptor of a session configuration, you determine who can use the session configuration to connect to the computer.</span></span>
<span data-ttu-id="07cf2-125">セッションで使用するには、ユーザーがセッション構成に対する Execute 権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="07cf2-125">Users must have Execute permission to a session configuration to use it in a session.</span></span> <span data-ttu-id="07cf2-126">コンピューター上の任意のセッション構成を使用するために必要なアクセス許可がユーザーにない場合、ユーザーはリモートでコンピューターに接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="07cf2-126">If a user does not have the required permissions to use any of the session configurations on a computer, the user cannot connect to the computer remotely.</span></span>

<span data-ttu-id="07cf2-127">既定では、コンピューターの管理者のみが既定のセッション構成を使用するアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="07cf2-127">By default, only Administrators of the computer have permission to use the default session configurations.</span></span> <span data-ttu-id="07cf2-128">ただし、セキュリティ記述子を変更して、すべてのユーザーが使用できるようにするか、または選択したユーザーのみがコンピューター上でセッション構成を使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-128">But, you can change the security descriptors to allow everyone, no one, or only selected users to use the session configurations on your computer.</span></span>

<span data-ttu-id="07cf2-129">組み込みのセッション構成</span><span class="sxs-lookup"><span data-stu-id="07cf2-129">Built-in Session Configurations</span></span>

<span data-ttu-id="07cf2-130">PowerShell 3.0 には、Microsoft PowerShell および Microsoft. PowerShell. Workflow という名前の組み込みのセッション構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="07cf2-130">PowerShell 3.0 includes built-in session configurations named Microsoft.PowerShell and Microsoft.PowerShell.Workflow.</span></span> <span data-ttu-id="07cf2-131">Windows の64ビットバージョンを実行しているコンピューターでは、PowerShell は32ビットのセッション構成である Microsoft.powershell32 も提供します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-131">On computers running 64-bit versions of Windows, PowerShell also provides Microsoft.PowerShell32, a 32-bit session configuration.</span></span>

<span data-ttu-id="07cf2-132">既定では、セッションのために使用されるのは、セッションを作成するコマンドに、新しい PSSession、Enter PSSession、または Invoke-Command コマンドレットの ConfigurationName パラメーターが含まれていない場合です。</span><span class="sxs-lookup"><span data-stu-id="07cf2-132">The Microsoft.PowerShell session configuration is used for sessions by default, that is, when a command to create a session does not include the ConfigurationName parameter of the New-PSSession, Enter-PSSession, or Invoke-Command cmdlet.</span></span>

<span data-ttu-id="07cf2-133">既定のセッション構成のセキュリティ記述子を使用すると、ローカルコンピューター上の Administrators グループのメンバーだけがこれらを使用できます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-133">The security descriptors for the default session configurations allow only members of the Administrators group on the local computer to use them.</span></span> <span data-ttu-id="07cf2-134">そのため、既定の設定を変更しない限り、Administrators グループのメンバーだけがリモートでコンピューターに接続できます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-134">As such, only members of the Administrators group can connect to the computer remotely unless you change the default settings.</span></span>

<span data-ttu-id="07cf2-135">既定のセッション構成を変更するには、$PSSessionConfigurationName ユーザー設定変数を使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-135">You can change the default session configurations by using the $PSSessionConfigurationName preference variable.</span></span> <span data-ttu-id="07cf2-136">詳細については、「about_Preference_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07cf2-136">For more information, see about_Preference_Variables.</span></span>

<span data-ttu-id="07cf2-137">ローカルコンピューター上のセッション構成を表示する</span><span class="sxs-lookup"><span data-stu-id="07cf2-137">Viewing Session Configurations on the Local Computer</span></span>

<span data-ttu-id="07cf2-138">ローカルコンピューター上のセッション構成を取得するには、Get-PSSessionConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-138">To get the session configurations on your local computer, use the Get-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="07cf2-139">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-139">For example, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property Name, Permission

Name       : microsoft.powershell
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell.workflow
Permission : BUILTIN\Administrators AccessAllowed

Name       : microsoft.powershell32
Permission : BUILTIN\Administrators AccessAllowed
```

<span data-ttu-id="07cf2-140">セッション構成オブジェクトは、セッション構成ファイルを使用して構成されたセッション構成のプロパティを表示するために、PowerShell 3.0 で展開されます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-140">The session configuration object is expanded in PowerShell 3.0 to display the properties of the session configuration that are configured by using a session configuration file.</span></span>

<span data-ttu-id="07cf2-141">たとえば、セッション構成オブジェクトのすべてのプロパティを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-141">For example, to see all of the properties of a session configuration object, type:</span></span>

```powershell
PS C:> Get-PSSessionConfiguration | Format-List -Property *
```

<span data-ttu-id="07cf2-142">PowerShell で WSMan プロバイダーを使用して、セッション構成を表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-142">You can also use the WSMan provider in PowerShell to view session configurations.</span></span> <span data-ttu-id="07cf2-143">WSMan プロバイダーは、セッションで WSMAN: ドライブを作成します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-143">The WSMan provider creates a WSMAN: drive in your session.</span></span>

<span data-ttu-id="07cf2-144">WSMAN: ドライブでは、セッション構成はプラグインノードにあります。</span><span class="sxs-lookup"><span data-stu-id="07cf2-144">In the WSMAN: drive, session configurations are in the Plugin node.</span></span> <span data-ttu-id="07cf2-145">(すべてのセッション構成はプラグインノードに含まれていますが、セッション構成ではないプラグインノードに項目があります)。</span><span class="sxs-lookup"><span data-stu-id="07cf2-145">(All session configurations are in the Plugin node, but there are items in the Plugin node that are not session configurations.)</span></span>

<span data-ttu-id="07cf2-146">たとえば、ローカルコンピューター上のセッション構成を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-146">For example, to view the session configurations on the local computer, type:</span></span>

```powershell
PS C:> dir wsman:\localhost\plugin\microsoft*

WSManConfig: Microsoft.WSMan.Management\WSMan::localhost\Plugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="07cf2-147">リモートコンピューター上のセッション構成の表示</span><span class="sxs-lookup"><span data-stu-id="07cf2-147">Viewing Session Configurations on a Remote Computer</span></span>

<span data-ttu-id="07cf2-148">リモートコンピューター上のセッション構成を表示するには、Connect-WSMan コマンドレットを使用して、リモートコンピューターのメモをローカルコンピューターの WSMAN: ドライブに追加し、WSMAN: ドライブを使用してセッション構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-148">To view the session configurations on a remote computer, use the Connect-WSMan cmdlet to add a note for the remote computer to the WSMAN: drive on your local computer, and then use the WSMAN: drive to view the session configurations.</span></span>

<span data-ttu-id="07cf2-149">たとえば、次のコマンドは、Server01 リモートコンピューターのノードをローカルコンピューターの WSMAN: ドライブに追加します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-149">For example, the following command adds a node for the Server01 remote computer to the WSMAN: drive on the local computer.</span></span>

```powershell
PS C:> Connect-WSMan server01.corp.fabrikam.com
```

<span data-ttu-id="07cf2-150">コマンドが完了したら、Server01 コンピューターのノードに移動して、セッション構成を表示できます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-150">When the command is complete, you can navigate to the node for the Server01 computer to view the session configurations.</span></span>

<span data-ttu-id="07cf2-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-151">For example:</span></span>

```powershell
PS C:> cd wsman:

PS WSMan:> dir

ComputerName                                  Type
------------                                  ----
localhost                                     Container
server01.corp.fabrikam.com                    Container

PS WSMan:> dir server01\plugin\

WSManConfig: Microsoft.WSMan.Management\WSMan::server01.corp.fabrikam.com\Pl
ugin

Type       Keys                              Name
----       ----                              ----
Container  {Name=microsoft.powershell}       microsoft.powershell
Container  {Name=microsoft.powershell.wor... microsoft.powershell.workflow
Container  {Name=microsoft.powershell32}     microsoft.powershell32
```

<span data-ttu-id="07cf2-152">セッション構成のセキュリティ記述子の変更</span><span class="sxs-lookup"><span data-stu-id="07cf2-152">Changing the Security Descriptor of a Session Configuration</span></span>

<span data-ttu-id="07cf2-153">Windows server 2012 および windows Server の新しいリリースでは、組み込みのセッション構成がリモートユーザーに対して既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="07cf2-153">In Windows Server 2012 and newer releases of Windows Server, the built-in session configurations are enabled for remote users by default.</span></span> <span data-ttu-id="07cf2-154">サポートされているその他のバージョンの Windows では、リモートアクセスを許可するようにセッション構成のセキュリティ記述子を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="07cf2-154">In other supported versions of Windows, you must change the security descriptors of the session configurations to allow remote access.</span></span>

<span data-ttu-id="07cf2-155">コンピューター上のセッション構成へのリモートアクセスを有効にするには、Enable-PSRemoting コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-155">To enable remote access to the session configurations on the computer, use the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="07cf2-156">このコマンドレットは、次の2つのセッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-156">This cmdlet creates two session configurations:</span></span>

- <span data-ttu-id="07cf2-157">名前を "PowerShell" に定義します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-157">with the name defined as: "PowerShell."</span></span> <span data-ttu-id="07cf2-158">+ "現在の PowerShell バージョン"</span><span class="sxs-lookup"><span data-stu-id="07cf2-158">+ "current PowerShell version"</span></span>
- <span data-ttu-id="07cf2-159">名前が "PowerShell. 6" で、特定の PowerShell バージョンには関連付けられていません。</span><span class="sxs-lookup"><span data-stu-id="07cf2-159">with name "PowerShell.6", untied to any specific PowerShell version.</span></span>

<span data-ttu-id="07cf2-160">また、既定では、コンピューターの Administrators グループのメンバーだけが既定のセッション構成に対する実行アクセス許可を持っていますが、既定のセッション構成および作成したセッション構成のセキュリティ記述子を変更できます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-160">Also, by default, only members of the Administrators group on the computer have Execute permission to the default session configurations, but you can change the security descriptors on the default session configurations and on any session configurations that you create.</span></span>

<span data-ttu-id="07cf2-161">コンピューターにリモートで接続するアクセス許可を他のユーザーに付与するには、Set-PSSessionConfiguration コマンドレットを使用して、Microsoft.powershell32 セッション構成のセキュリティ記述子にそれらのユーザーの "実行" アクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-161">To give other users permission to connect to the computer remotely, use the Set-PSSessionConfiguration cmdlet to add "Execute" permissions for those users to the security descriptors of the Microsoft.PowerShell and Microsoft.PowerShell32 session configurations.</span></span>

<span data-ttu-id="07cf2-162">たとえば、次のコマンドを実行すると、既定の PowerShell セッション構成のセキュリティ記述子を変更できるプロパティページが開きます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-162">For example, the following command opens a property page that lets you change the security descriptor for the Microsoft.PowerShell default session configuration.</span></span>

```powershell
Set-PSSessionConfiguration -name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="07cf2-163">コンピューター上のすべてのセッション構成に対するすべてのアクセス許可を拒否するには、Disable-PSSessionConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-163">To deny everyone permission to all the session configurations on the computer, use the Disable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="07cf2-164">たとえば、次のコマンドは、コンピューター上の既定のセッション構成を無効にします。</span><span class="sxs-lookup"><span data-stu-id="07cf2-164">For example, the following command disables the default session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSSessionConfiguration -Name Microsoft.PowerShell
```

<span data-ttu-id="07cf2-165">リモートユーザーがコンピューターに接続できないようにし、ローカルユーザーが接続できるようにするには、Disable-PSRemoting コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-165">To prevent remote users from connecting to the computer, but allow local users to connect, use the Disable-PSRemoting cmdlet.</span></span> <span data-ttu-id="07cf2-166">Disable-PSRemoting は、コンピューター上のすべてのセッション構成に "Network_Deny_All" エントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-166">Disable-PSRemoting adds a "Network_Deny_All" entry to all session configurations on the computer.</span></span>

```powershell
PS C:> Disable-PSRemoting
```

<span data-ttu-id="07cf2-167">リモートユーザーがコンピューター上のすべてのセッション構成を使用できるようにするには、Enable-PSRemoting または Enable-PSSessionConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-167">To allow remote users to use all session configurations on the computer, use the Enable-PSRemoting or Enable-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="07cf2-168">たとえば、次のコマンドは、組み込みのセッション構成へのリモートアクセスを可能にします。</span><span class="sxs-lookup"><span data-stu-id="07cf2-168">For example, the following command enables remote access to the built-in session configurations.</span></span>

```powershell
PS C:> Enable-PSSessionConfiguration -name Microsoft.Power*
```

<span data-ttu-id="07cf2-169">セッション構成のセキュリティ記述子にその他の変更を加えるには、Set-PSSessionConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-169">To make other changes to the security descriptor of a session configuration, use the Set-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="07cf2-170">SDDL 文字列値を送信するには、Security記述子 Sddl パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-170">Use the SecurityDescriptorSDDL parameter to submit an SDDL string value.</span></span> <span data-ttu-id="07cf2-171">Showsecurity記述子 Ui パラメーターを使用して、新しい SDDL の作成に役立つユーザーインターフェイスプロパティシートを表示します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-171">Use the ShowSecurityDescriptorUI parameter to display a user interface property sheet that helps you to create a new SDDL.</span></span>

<span data-ttu-id="07cf2-172">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-172">For example:</span></span>

```powershell
Set-PSSessionConfiguration -Name Microsoft.PowerShell `
  -ShowSecurityDescriptorUI
```

<span data-ttu-id="07cf2-173">新しいセッション構成の作成</span><span class="sxs-lookup"><span data-stu-id="07cf2-173">Creating a New Session Configuration</span></span>

<span data-ttu-id="07cf2-174">ローカルコンピューターで新しいセッション構成を作成するには、Register-PSSessionConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-174">To create a new session configuration on the local computer, use the Register-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="07cf2-175">新しいセッション構成を定義するには、C# アセンブリ、PowerShell スクリプト、および Register-PSSessionConfiguration コマンドレットのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-175">To define the new session configuration, you can use a C# assembly, a PowerShell script, and the parameters of the Register-PSSessionConfiguration cmdlet.</span></span>

<span data-ttu-id="07cf2-176">たとえば、次のコマンドは、リモートコマンドから受信したデータを20メガバイト (MB) に制限する点を除いて、Microsoft PowerShell セッション構成と同じセッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-176">For example, the following command creates a session configuration that is identical the Microsoft.PowerShell session configuration, except that it limits the data received from a remote command to 20 megabytes (MB).</span></span> <span data-ttu-id="07cf2-177">(既定値は 50 MB)。</span><span class="sxs-lookup"><span data-stu-id="07cf2-177">(The default is 50 MB).</span></span>

```powershell
Register-PSSessionConfiguration -Name NewConfig `
  -MaximumReceivedDataSizePerCommandMB 20
```

<span data-ttu-id="07cf2-178">セッション構成を作成する場合は、他のセッション構成コマンドレットを使用して管理でき、WSMAN: ドライブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-178">When you create a session configuration, you can manage it by using the other session configuration cmdlets, and it appears in the WSMAN: drive.</span></span>

<span data-ttu-id="07cf2-179">詳細については、「Register-pssessionconfiguration」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07cf2-179">For more information, see Register-PSSessionConfiguration.</span></span>

<span data-ttu-id="07cf2-180">セッション構成の削除</span><span class="sxs-lookup"><span data-stu-id="07cf2-180">Removing a Session Configuration</span></span>

<span data-ttu-id="07cf2-181">セッション構成をローカルコンピューターから削除するには、Unregister-PSSessionConfiguration コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-181">To remove a session configuration from the local computer, use the Unregister-PSSessionConfiguration cmdlet.</span></span> <span data-ttu-id="07cf2-182">たとえば、次のコマンドは、NewConfig セッション構成をコンピューターから削除します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-182">For example, the following command removes the NewConfig session configuration from the computer.</span></span>

```powershell
PS C:> Unregister-PSSessionConfiguration -Name NewConfig
```

<span data-ttu-id="07cf2-183">詳細については、「Register-pssessionconfiguration」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07cf2-183">For more information, see Unregister-PSSessionConfiguration.</span></span>

<span data-ttu-id="07cf2-184">セッション構成の復元</span><span class="sxs-lookup"><span data-stu-id="07cf2-184">Restoring a Session Configuration</span></span>

<span data-ttu-id="07cf2-185">誤って削除 (登録解除) された既定のセッション構成を復元するには、Enable-PSRemoting コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-185">To restore a default session configuration that was deleted (unregistered) accidentally, use the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="07cf2-186">Enable-PSRemoting コマンドレットは、コンピューター上に存在しないすべての既定のセッション構成を再作成します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-186">The Enable-PSRemoting cmdlet recreates all default sessions configurations that do not exist on the computer.</span></span> <span data-ttu-id="07cf2-187">既存のセッション構成のプロパティ値を上書きしたり変更したりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="07cf2-187">It does not overwrite or change the property values of existing session configurations.</span></span>

<span data-ttu-id="07cf2-188">既定のセッション構成の元のプロパティ値を復元するには、Unregister-PSSessionConfiguration を使用してセッション構成を削除し、Enable-PSRemoting コマンドレットを使用してその構成を再作成します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-188">To restore the original property values of a default session configuration, use the Unregister-PSSessionConfiguration to delete the session configuration and then use the Enable-PSRemoting cmdlet to recreate it.</span></span>

<span data-ttu-id="07cf2-189">セッション構成の選択</span><span class="sxs-lookup"><span data-stu-id="07cf2-189">Selecting a Session Configuration</span></span>

<span data-ttu-id="07cf2-190">セッションの特定のセッション構成を選択するには、新しい PSSession、Enter-PSSession、または Invoke コマンドの ConfigurationName パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-190">To select a particular session configuration for a session, use the ConfigurationName parameter of New-PSSession, Enter-PSSession, or Invoke-Command.</span></span>

<span data-ttu-id="07cf2-191">たとえば、次のコマンドは、New-PSSession コマンドレットを使用して、Server01 コンピューター上の PSSession を開始します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-191">For example, this command uses the New-PSSession cmdlet to start a PSSession on the Server01 computer.</span></span> <span data-ttu-id="07cf2-192">このコマンドは、ConfigurationName パラメーターを使用して、Server01 コンピューターで WithProfile 構成を選択します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-192">The command uses the ConfigurationName parameter to select the WithProfile configuration on the Server01 computer.</span></span>

```powershell
PS C:> New-PSSession -ComputerName Server01 -ConfigurationName WithProfile
```

<span data-ttu-id="07cf2-193">このコマンドは、現在のユーザーに WithProfile セッション構成を使用するアクセス許可がある場合、または必要なアクセス許可を持つユーザーの資格情報を指定できる場合にのみ成功します。</span><span class="sxs-lookup"><span data-stu-id="07cf2-193">This command will succeed only if the current user has permission to use the WithProfile session configuration or can supply the credentials of a user who has the required permissions.</span></span>

<span data-ttu-id="07cf2-194">また、$PSSessionConfigurationName ユーザー設定変数を使用して、コンピューター上の既定のセッション構成を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="07cf2-194">You can also use the $PSSessionConfigurationName preference variable to change the default session configuration on the computer.</span></span> <span data-ttu-id="07cf2-195">$PSSessionConfigurationName ユーザー設定変数の詳細については、「about_Preference_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07cf2-195">For more information about the $PSSessionConfigurationName preference variable, see about_Preference_Variables.</span></span>

## <a name="keywords"></a><span data-ttu-id="07cf2-196">KEYWORDS</span><span class="sxs-lookup"><span data-stu-id="07cf2-196">KEYWORDS</span></span>

<span data-ttu-id="07cf2-197">about_Endpoints about_SessionConfigurations</span><span class="sxs-lookup"><span data-stu-id="07cf2-197">about_Endpoints about_SessionConfigurations</span></span>

## <a name="see-also"></a><span data-ttu-id="07cf2-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="07cf2-198">SEE ALSO</span></span>

[<span data-ttu-id="07cf2-199">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="07cf2-199">about_Preference_Variables</span></span>](about_Preference_Variables.md)

[<span data-ttu-id="07cf2-200">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="07cf2-200">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="07cf2-201">about_Remote</span><span class="sxs-lookup"><span data-stu-id="07cf2-201">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="07cf2-202">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="07cf2-202">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)

[<span data-ttu-id="07cf2-203">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="07cf2-203">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="07cf2-204">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="07cf2-204">Disable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Disable-PSSessionConfiguration)

[<span data-ttu-id="07cf2-205">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="07cf2-205">Enable-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Enable-PSSessionConfiguration)

[<span data-ttu-id="07cf2-206">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="07cf2-206">Get-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSessionConfiguration)

[<span data-ttu-id="07cf2-207">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="07cf2-207">New-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.New-PSSessionConfigurationFile)

[<span data-ttu-id="07cf2-208">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="07cf2-208">Register-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Register-PSSessionConfiguration)

[<span data-ttu-id="07cf2-209">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="07cf2-209">Set-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Set-PSSessionConfiguration)

[<span data-ttu-id="07cf2-210">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="07cf2-210">Test-PSSessionConfigurationFile</span></span>](xref:Microsoft.PowerShell.Core.Test-PSSessionConfigurationFile)

[<span data-ttu-id="07cf2-211">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="07cf2-211">Unregister-PSSessionConfiguration</span></span>](xref:Microsoft.PowerShell.Core.Unregister-PSSessionConfiguration)
