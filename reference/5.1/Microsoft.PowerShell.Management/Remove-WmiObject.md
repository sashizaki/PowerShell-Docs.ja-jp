---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/remove-wmiobject?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmiObject
ms.openlocfilehash: 287eb02e7de2f4182e0ecfd7f6b6a7cafb66969e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214544"
---
# <span data-ttu-id="df82c-103">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="df82c-103">Remove-WmiObject</span></span>

## <span data-ttu-id="df82c-104">概要</span><span class="sxs-lookup"><span data-stu-id="df82c-104">SYNOPSIS</span></span>
<span data-ttu-id="df82c-105">既存の Windows Management Instrumentation (WMI) クラスのインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="df82c-105">Deletes an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="df82c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="df82c-106">SYNTAX</span></span>

### <span data-ttu-id="df82c-107">クラス (既定値)</span><span class="sxs-lookup"><span data-stu-id="df82c-107">class (Default)</span></span>

```
Remove-WmiObject [-Class] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="df82c-108">object</span><span class="sxs-lookup"><span data-stu-id="df82c-108">object</span></span>

```
Remove-WmiObject -InputObject <ManagementObject> [-AsJob] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="df82c-109">path</span><span class="sxs-lookup"><span data-stu-id="df82c-109">path</span></span>

```
Remove-WmiObject -Path <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="df82c-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="df82c-110">WQLQuery</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="df82c-111">query</span><span class="sxs-lookup"><span data-stu-id="df82c-111">query</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="df82c-112">list</span><span class="sxs-lookup"><span data-stu-id="df82c-112">list</span></span>

```
Remove-WmiObject [-AsJob] [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>]
 [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>]
 [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="df82c-113">Description</span><span class="sxs-lookup"><span data-stu-id="df82c-113">DESCRIPTION</span></span>
<span data-ttu-id="df82c-114">**Get-wmiobject** コマンドレットは、既存の WINDOWS MANAGEMENT INSTRUMENTATION (WMI) クラスのインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="df82c-114">The **Remove-WmiObject** cmdlet deletes an instance of an existing Windows Management Instrumentation (WMI)class.</span></span>

## <span data-ttu-id="df82c-115">例</span><span class="sxs-lookup"><span data-stu-id="df82c-115">EXAMPLES</span></span>

### <span data-ttu-id="df82c-116">例 1: Win32 プロセスのすべてのインスタンスを閉じる</span><span class="sxs-lookup"><span data-stu-id="df82c-116">Example 1: Close all instances of a Win32 process</span></span>

```
PS C:\> notepad
PS C:\> $np = Get-WmiObject -Query "select * from win32_process where name='notepad.exe'"
PS C:\> $np | Remove-WmiObject
```

<span data-ttu-id="df82c-117">この例では、Notepad.exe のすべてのインスタンスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="df82c-117">This example closes all the instances of Notepad.exe.</span></span>

<span data-ttu-id="df82c-118">最初のコマンドは、メモ帳のインスタンスを起動します。</span><span class="sxs-lookup"><span data-stu-id="df82c-118">The first command starts an instance of Notepad.</span></span>

<span data-ttu-id="df82c-119">2番目のコマンドは、Get-WmiObject コマンドレットを使用して Notepad.exe に対応する Win32_Process のインスタンスを取得し、$np 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="df82c-119">The second command uses the Get-WmiObject cmdlet to retrieve the instances of the Win32_Process that correspond to Notepad.exe, and then stores them in the $np variable.</span></span>

<span data-ttu-id="df82c-120">3番目のコマンドは、$np 変数内のオブジェクトを **get-wmiobject** に渡して、Notepad.exe のすべてのインスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="df82c-120">The third command passes the object in the $np variable to **Remove-WmiObject** , which deletes all the instances of Notepad.exe.</span></span>

### <span data-ttu-id="df82c-121">例 2: フォルダーを削除する</span><span class="sxs-lookup"><span data-stu-id="df82c-121">Example 2: Delete a folder</span></span>

```
PS C:\> $a = Get-WMIObject -Query "Select * From Win32_Directory Where Name ='C:\\Test'"
PS C:\> $a | Remove-WMIObject
```

<span data-ttu-id="df82c-122">このコマンドは、C:\Test フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="df82c-122">This command deletes the C:\Test folder.</span></span>

<span data-ttu-id="df82c-123">最初のコマンドは、 **get-wmiobject** を使用して C:\Test フォルダーに対してクエリを実行し、そのオブジェクトを $a 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="df82c-123">The first command uses **Get-WMIObject** to query for the C:\Test folder, and then stores the object in the $a variable.</span></span>

<span data-ttu-id="df82c-124">2番目のコマンドは、$a 変数を **get-wmiobject** にパイプして、フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="df82c-124">The second command pipes the $a variable to **Remove-WMIObject** , which deletes the folder.</span></span>

## <span data-ttu-id="df82c-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="df82c-125">PARAMETERS</span></span>

### <span data-ttu-id="df82c-126">-AsJob</span><span class="sxs-lookup"><span data-stu-id="df82c-126">-AsJob</span></span>
<span data-ttu-id="df82c-127">このコマンドレットがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="df82c-127">Indicates that this cmdlet run as a background job.</span></span>
<span data-ttu-id="df82c-128">完了に時間のかかるコマンドを実行するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="df82c-128">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="df82c-129">Windows PowerShell 3.0 で導入された新しい CIM コマンドレットは、WMI コマンドレットと同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="df82c-129">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="df82c-130">CIM コマンドレットは、WS-Management (WSMan) 標準と Common Information Model (CIM) 標準に準拠しています。これにより、コマンドレットは、Windows オペレーティングシステムを実行しているコンピューターと他のオペレーティングシステムを実行しているコンピューターを管理するのと同じ手法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="df82c-130">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard, which enables the cmdlets to use the same techniques to manage computers that run the Windows operating system and those running other operating systems.</span></span>
<span data-ttu-id="df82c-131">**Remove-WmiObject** を使用する代わりに、Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 コマンドレットを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="df82c-131">Instead of using **Remove-WmiObject** , consider using the Remove-CimInstancehttps://go.microsoft.com/fwlink/?LinkId=227964 cmdlet.</span></span>

<span data-ttu-id="df82c-132">*AsJob* パラメーターを使用すると、バックグラウンド ジョブを表すオブジェクトが返され、その後コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-132">When you use the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="df82c-133">ジョブが完了しても、引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="df82c-133">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="df82c-134">**Remove-WmiObject** がリモート コンピューターに対して使用された場合、ジョブはローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-134">If **Remove-WmiObject** is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="df82c-135">ジョブを管理するには **、ジョブの名詞を** 含むコマンドレット ( **job** コマンドレット) を使用します。</span><span class="sxs-lookup"><span data-stu-id="df82c-135">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="df82c-136">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="df82c-136">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="df82c-137">リモートコンピューターでこのパラメーターを使用するには、ローカルコンピューターとリモートコンピューターをリモート処理用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df82c-137">To use this parameter for remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="df82c-138">[管理者として実行] オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="df82c-138">Start Windows PowerShell by using the Run as administrator option.</span></span>
<span data-ttu-id="df82c-139">詳細については、「about_Remote_Requirements」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df82c-139">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="df82c-140">Windows PowerShell のバックグラウンドジョブの詳細については、「about_Jobs」および「about_Remote_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df82c-140">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-141">-認証</span><span class="sxs-lookup"><span data-stu-id="df82c-141">-Authentication</span></span>
<span data-ttu-id="df82c-142">WMI 接続に使用する認証レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-142">Specifies the authentication level to use for the WMI connection.</span></span>
<span data-ttu-id="df82c-143">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df82c-143">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="df82c-144">-1: 変更なし。</span><span class="sxs-lookup"><span data-stu-id="df82c-144">-1: Unchanged.</span></span>
- <span data-ttu-id="df82c-145">0: Default。</span><span class="sxs-lookup"><span data-stu-id="df82c-145">0: Default.</span></span>
- <span data-ttu-id="df82c-146">1: なし。</span><span class="sxs-lookup"><span data-stu-id="df82c-146">1: None.</span></span>
<span data-ttu-id="df82c-147">の認証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="df82c-147">No authentication in performed.</span></span>
- <span data-ttu-id="df82c-148">2: 接続します。</span><span class="sxs-lookup"><span data-stu-id="df82c-148">2: Connect.</span></span>
<span data-ttu-id="df82c-149">認証は、クライアントがアプリケーションとの関係を確立した場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-149">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="df82c-150">3: を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="df82c-150">3: Call.</span></span>
<span data-ttu-id="df82c-151">認証は、アプリケーションが要求を受信したときに各呼び出しの開始時にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-151">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="df82c-152">4: パケット。</span><span class="sxs-lookup"><span data-stu-id="df82c-152">4: Packet.</span></span>
<span data-ttu-id="df82c-153">認証は、クライアントから受信したすべてのデータに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-153">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="df82c-154">5: PacketIntegrity。</span><span class="sxs-lookup"><span data-stu-id="df82c-154">5: PacketIntegrity.</span></span>
<span data-ttu-id="df82c-155">クライアントとアプリケーションの間で転送されるすべてのデータが認証され、検証されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-155">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="df82c-156">6: PacketPrivacy。</span><span class="sxs-lookup"><span data-stu-id="df82c-156">6: PacketPrivacy.</span></span>
<span data-ttu-id="df82c-157">他の認証レベルのプロパティが使用され、すべてのデータが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-157">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

```yaml
Type: System.Management.AuthenticationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, None, Connect, Call, Packet, PacketIntegrity, PacketPrivacy, Unchanged

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-158">-Authority</span><span class="sxs-lookup"><span data-stu-id="df82c-158">-Authority</span></span>
<span data-ttu-id="df82c-159">WMI 接続の認証に使用する機関を指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-159">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="df82c-160">標準の NTLM 認証または Kerberos 認証を指定できます。</span><span class="sxs-lookup"><span data-stu-id="df82c-160">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="df82c-161">NTLM を使用するには、認証設定に「ntlmdomain:\<DomainName\>」と指定します。\<DomainName\> には、有効な NTLM ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-161">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="df82c-162">Kerberos を使用するには、「kerberos:」と指定し \<DomainName\> \\ \<ServerName\> ます。</span><span class="sxs-lookup"><span data-stu-id="df82c-162">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="df82c-163">ローカル コンピューターへの接続時に認証設定を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="df82c-163">You cannot include the authority setting when you connect to the local computer.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-164">-クラス</span><span class="sxs-lookup"><span data-stu-id="df82c-164">-Class</span></span>
<span data-ttu-id="df82c-165">このコマンドレットが削除する WMI クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-165">Specifies the name of a WMI class that this cmdlet deletes.</span></span>

```yaml
Type: System.String
Parameter Sets: class
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-166">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="df82c-166">-ComputerName</span></span>
<span data-ttu-id="df82c-167">このコマンドレットが実行されるコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-167">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="df82c-168">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="df82c-168">The default is the local computer.</span></span>

<span data-ttu-id="df82c-169">1 台または複数のコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="df82c-169">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="df82c-170">ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="df82c-170">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="df82c-171">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="df82c-171">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="df82c-172">コンピューターがリモート コマンドを実行するように構成されていない場合でも、 *ComputerName* パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="df82c-172">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: class, path, WQLQuery, query, list
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-173">-Credential</span><span class="sxs-lookup"><span data-stu-id="df82c-173">-Credential</span></span>
<span data-ttu-id="df82c-174">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-174">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="df82c-175">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="df82c-175">The default is the current user.</span></span>

<span data-ttu-id="df82c-176">User01 や Domain01\user01」などのユーザー名を入力するか、Get-Credential コマンドレットによって生成された **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="df82c-176">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="df82c-177">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="df82c-177">If you type a user name, this cmdlet prompts you for a password.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-178">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="df82c-178">-EnableAllPrivileges</span></span>
<span data-ttu-id="df82c-179">このコマンドレットが、WMI 呼び出しを行うコマンドの前に、現在のユーザーのすべてのアクセス許可を有効にすることを示します。</span><span class="sxs-lookup"><span data-stu-id="df82c-179">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-180">-偽装</span><span class="sxs-lookup"><span data-stu-id="df82c-180">-Impersonation</span></span>
<span data-ttu-id="df82c-181">使用する偽装レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-181">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="df82c-182">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="df82c-182">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="df82c-183">0: Default。</span><span class="sxs-lookup"><span data-stu-id="df82c-183">0: Default.</span></span>
<span data-ttu-id="df82c-184">既定の偽装レベルのローカルレジストリを読み取ります。これは通常、3: Impersonate に設定されています。</span><span class="sxs-lookup"><span data-stu-id="df82c-184">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="df82c-185">1: Anonymous。</span><span class="sxs-lookup"><span data-stu-id="df82c-185">1: Anonymous.</span></span>
<span data-ttu-id="df82c-186">呼び出し元の資格情報は非表示になります。</span><span class="sxs-lookup"><span data-stu-id="df82c-186">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="df82c-187">2: Identify。</span><span class="sxs-lookup"><span data-stu-id="df82c-187">2: Identify.</span></span>
<span data-ttu-id="df82c-188">オブジェクトによる呼び出し元の資格情報のクエリが許可されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-188">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="df82c-189">3: Impersonate。</span><span class="sxs-lookup"><span data-stu-id="df82c-189">3: Impersonate.</span></span>
<span data-ttu-id="df82c-190">オブジェクトによる呼び出し元の資格情報の使用が許可されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-190">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="df82c-191">4: Delegate。</span><span class="sxs-lookup"><span data-stu-id="df82c-191">4: Delegate.</span></span>
<span data-ttu-id="df82c-192">オブジェクトが呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします。</span><span class="sxs-lookup"><span data-stu-id="df82c-192">Allows objects to permit other objects to use the credentials of the caller.</span></span>

```yaml
Type: System.Management.ImpersonationLevel
Parameter Sets: class, path, WQLQuery, query, list
Aliases:
Accepted values: Default, Anonymous, Identify, Impersonate, Delegate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-193">-InputObject</span><span class="sxs-lookup"><span data-stu-id="df82c-193">-InputObject</span></span>
<span data-ttu-id="df82c-194">入力として使用する **system.management.managementobject** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-194">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="df82c-195">このパラメーターを使用する場合、他のすべてのパラメーターが無視されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-195">When this parameter is used, all other parameters are ignored.</span></span>

```yaml
Type: System.Management.ManagementObject
Parameter Sets: object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-196">-ロケール</span><span class="sxs-lookup"><span data-stu-id="df82c-196">-Locale</span></span>
<span data-ttu-id="df82c-197">WMI オブジェクトの優先ロケールを指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-197">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="df82c-198">*Locale* パラメーターは、MS_ 形式の配列として、優先順位に従って指定し \<LCID\> ます。</span><span class="sxs-lookup"><span data-stu-id="df82c-198">The *Locale* parameter is specified as an array in the MS_\<LCID\> format in the preferred order.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-199">-Namespace</span><span class="sxs-lookup"><span data-stu-id="df82c-199">-Namespace</span></span>
<span data-ttu-id="df82c-200">*クラス* パラメーターと共に使用する場合に、参照先の wmi クラスが配置されている wmi リポジトリの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-200">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: class, path, WQLQuery, query, list
Aliases: NS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-201">-Path</span><span class="sxs-lookup"><span data-stu-id="df82c-201">-Path</span></span>
<span data-ttu-id="df82c-202">削除する WMI クラスの WMI オブジェクト パス、または WMI クラスのインスタンスの WMI オブジェクト パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-202">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class to delete.</span></span>

```yaml
Type: System.String
Parameter Sets: path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-203">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="df82c-203">-ThrottleLimit</span></span>
<span data-ttu-id="df82c-204">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="df82c-204">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="df82c-205">このパラメーターは、 *AsJob* パラメーターと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-205">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="df82c-206">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="df82c-206">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="df82c-207">-Confirm</span><span class="sxs-lookup"><span data-stu-id="df82c-207">-Confirm</span></span>
<span data-ttu-id="df82c-208">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="df82c-208">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="df82c-209">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="df82c-209">-WhatIf</span></span>
<span data-ttu-id="df82c-210">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="df82c-210">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="df82c-211">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="df82c-211">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="df82c-212">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="df82c-212">CommonParameters</span></span>
<span data-ttu-id="df82c-213">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="df82c-213">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="df82c-214">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df82c-214">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="df82c-215">入力</span><span class="sxs-lookup"><span data-stu-id="df82c-215">INPUTS</span></span>

### <span data-ttu-id="df82c-216">System.management.managementobject</span><span class="sxs-lookup"><span data-stu-id="df82c-216">System.Management.ManagementObject</span></span>
<span data-ttu-id="df82c-217">このコマンドレットには、管理オブジェクトをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="df82c-217">You can pipe a management object to this cmdlet.</span></span>

## <span data-ttu-id="df82c-218">出力</span><span class="sxs-lookup"><span data-stu-id="df82c-218">OUTPUTS</span></span>

### <span data-ttu-id="df82c-219">なし、システムの管理. RemotingJob</span><span class="sxs-lookup"><span data-stu-id="df82c-219">None, System.Management.Automation.RemotingJob</span></span>
<span data-ttu-id="df82c-220">*AsJob* パラメーターを指定した場合、このコマンドレットはジョブオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="df82c-220">This cmdlet returns a job object, if you specify the *AsJob* parameter.</span></span>
<span data-ttu-id="df82c-221">それ以外の場合、出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="df82c-221">Otherwise, it does not generate any output.</span></span>

## <span data-ttu-id="df82c-222">注</span><span class="sxs-lookup"><span data-stu-id="df82c-222">NOTES</span></span>

## <span data-ttu-id="df82c-223">関連リンク</span><span class="sxs-lookup"><span data-stu-id="df82c-223">RELATED LINKS</span></span>

[<span data-ttu-id="df82c-224">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="df82c-224">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="df82c-225">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="df82c-225">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="df82c-226">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="df82c-226">Set-WmiInstance</span></span>](Set-WmiInstance.md)
