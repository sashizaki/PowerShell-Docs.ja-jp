---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/invoke-wmimethod?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-WmiMethod
ms.openlocfilehash: e9743488e86429e5cc3252162e51268a7978b79d
ms.sourcegitcommit: b0488ca6557501184f20c8343b0ed5147b09e3fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "93217992"
---
# <span data-ttu-id="3062a-103">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="3062a-103">Invoke-WmiMethod</span></span>

## <span data-ttu-id="3062a-104">概要</span><span class="sxs-lookup"><span data-stu-id="3062a-104">SYNOPSIS</span></span>
<span data-ttu-id="3062a-105">WMI メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3062a-105">Calls WMI methods.</span></span>

## <span data-ttu-id="3062a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3062a-106">SYNTAX</span></span>

### <span data-ttu-id="3062a-107">クラス (既定値)</span><span class="sxs-lookup"><span data-stu-id="3062a-107">class (Default)</span></span>

```
Invoke-WmiMethod [-Class] <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3062a-108">object</span><span class="sxs-lookup"><span data-stu-id="3062a-108">object</span></span>

```
Invoke-WmiMethod -InputObject <ManagementObject> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3062a-109">path</span><span class="sxs-lookup"><span data-stu-id="3062a-109">path</span></span>

```
Invoke-WmiMethod -Path <String> [-Name] <String> [-ArgumentList <Object[]>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3062a-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="3062a-110">WQLQuery</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3062a-111">query</span><span class="sxs-lookup"><span data-stu-id="3062a-111">query</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="3062a-112">list</span><span class="sxs-lookup"><span data-stu-id="3062a-112">list</span></span>

```
Invoke-WmiMethod [-Name] <String> [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="3062a-113">Description</span><span class="sxs-lookup"><span data-stu-id="3062a-113">DESCRIPTION</span></span>

<span data-ttu-id="3062a-114">この `Invoke-WmiMethod` コマンドレットは、Windows Management Instrumentation (WMI) オブジェクトのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="3062a-114">The `Invoke-WmiMethod` cmdlet calls the methods of Windows Management Instrumentation (WMI) objects.</span></span>

<span data-ttu-id="3062a-115">Windows PowerShell 3.0 で導入された新しい Common Information Model (CIM) コマンドレットは、WMI コマンドレットと同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="3062a-115">New Common Information Model (CIM) cmdlets, introduced in Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span> <span data-ttu-id="3062a-116">CIM コマンドレットは、WS-Management (WSMan) 標準と CIM 標準に準拠しています。これにより、コマンドレットは、Windows コンピューターや他のオペレーティングシステムを実行しているものと同じ手法を使用して管理できます。</span><span class="sxs-lookup"><span data-stu-id="3062a-116">The CIM cmdlets comply with WS-Management (WSMan) standards and with the CIM standard, which enables the cmdlets to use the same techniques to manage Windows computers and those running other operating systems.</span></span> <span data-ttu-id="3062a-117">を使用する代わり `Invoke-WmiMethod` に、 [invoke-cimmethod](../cimcmdlets/invoke-cimmethod.md)の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="3062a-117">Instead of using `Invoke-WmiMethod`, consider using [Invoke-CimMethod](../cimcmdlets/invoke-cimmethod.md).</span></span>

## <span data-ttu-id="3062a-118">例</span><span class="sxs-lookup"><span data-stu-id="3062a-118">EXAMPLES</span></span>

### <span data-ttu-id="3062a-119">例 1: WMI オブジェクトの必要な順序を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="3062a-119">Example 1: List the required order of WMI objects</span></span>

```powershell
([wmiclass]'Win32_Volume').GetMethodParameters('Format')
```

```Output
__GENUS           : 2
__CLASS           : __PARAMETERS
__SUPERCLASS      :
__DYNASTY         : __PARAMETERS
__RELPATH         :
__PROPERTY_COUNT  : 6
__DERIVATION      : {}
__SERVER          :
__NAMESPACE       :
__PATH            :
ClusterSize       : 0
EnableCompression : False
FileSystem        : NTFS
Label             :
QuickFormat       : False
Version           : 0
PSComputerName    :
```

<span data-ttu-id="3062a-120">このコマンドは、必要なオブジェクトの順序を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3062a-120">This command lists the required order of the objects.</span></span> <span data-ttu-id="3062a-121">PowerShell 3.0 での WMI の呼び出しは他の方法とは異なり、オブジェクト値を特定の順序で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3062a-121">To invoke WMI in PowerShell 3.0 differs from alternate methods, and requires that object values are entered in a specific order.</span></span>

### <span data-ttu-id="3062a-122">例 2: アプリケーションのインスタンスを起動する</span><span class="sxs-lookup"><span data-stu-id="3062a-122">Example 2: Start an instance of an application</span></span>

```powershell
([Wmiclass]'Win32_Process').GetMethodParameters('Create')
```

```Output
__GENUS                   : 2
__CLASS                   : __PARAMETERS
__SUPERCLASS              :
__DYNASTY                 : __PARAMETERS
__RELPATH                 :
__PROPERTY_COUNT          : 3
__DERIVATION              : {}
__SERVER                  :
__NAMESPACE               :
__PATH                    :
CommandLine               :
CurrentDirectory          :
ProcessStartupInformation :
PSComputerName            :
```

```powershell
Invoke-WmiMethod -Path win32_process -Name create -ArgumentList notepad.exe
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 2
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ProcessId        : 11312
ReturnValue      : 0
PSComputerName   :
```

<span data-ttu-id="3062a-123">このコマンドは、Win32_Process クラスのメソッドを呼び出すことによって、メモ帳のインスタンスを起動 `Create` します。 **Win32_Process**</span><span class="sxs-lookup"><span data-stu-id="3062a-123">This command starts an instance of Notepad by calling the `Create` method of the **Win32_Process** class.</span></span>

<span data-ttu-id="3062a-124">**戻り** 値のプロパティに0が設定され、 **ProcessId** プロパティに整数 (次のプロセス ID 番号) が設定されます (コマンドが完了した場合)。</span><span class="sxs-lookup"><span data-stu-id="3062a-124">The **ReturnValue** property is populated with a 0, and the **ProcessId** property is populated with an integer (the next process ID number) if the command is completed.</span></span>

### <span data-ttu-id="3062a-125">例 3: ファイル名を変更する</span><span class="sxs-lookup"><span data-stu-id="3062a-125">Example 3: Rename a file</span></span>

```powershell
Invoke-WmiMethod -Path "CIM_DataFile.Name='C:\scripts\test.txt'" -Name Rename -ArgumentList "C:\scripts\test_bu.txt"
```

```Output
__GENUS          : 2
__CLASS          : __PARAMETERS
__SUPERCLASS     :
__DYNASTY        : __PARAMETERS
__RELPATH        :
__PROPERTY_COUNT : 1
__DERIVATION     : {}
__SERVER         :
__NAMESPACE      :
__PATH           :
ReturnValue      : 0
```

<span data-ttu-id="3062a-126">このコマンドは、ファイル名を変更します。</span><span class="sxs-lookup"><span data-stu-id="3062a-126">This command renames a file.</span></span> <span data-ttu-id="3062a-127">**Path** パラメーターを使用して、 **CIM_DataFile** クラスのインスタンスを参照します。</span><span class="sxs-lookup"><span data-stu-id="3062a-127">It uses the **Path** parameter to reference an instance of the **CIM_DataFile** class.</span></span> <span data-ttu-id="3062a-128">次に、その特定のインスタンスに対して Rename メソッドを適用します。</span><span class="sxs-lookup"><span data-stu-id="3062a-128">Then, it applies the Rename method to that particular instance.</span></span>

<span data-ttu-id="3062a-129">コマンドが完了すると、 **戻り** 値のプロパティに0が設定されます。</span><span class="sxs-lookup"><span data-stu-id="3062a-129">The **ReturnValue** property is populated with a 0 if the command is completed.</span></span>

### <span data-ttu-id="3062a-130">例 4: を使用して値の配列を渡す `-ArgumentList`</span><span class="sxs-lookup"><span data-stu-id="3062a-130">Example 4: Passing an array of values using `-ArgumentList`</span></span>

<span data-ttu-id="3062a-131">オブジェクトの配列を使用し、 `$binSD` その後に `$null` 値を指定する例。</span><span class="sxs-lookup"><span data-stu-id="3062a-131">An example using an array of objects `$binSD` followed by a `$null` value.</span></span>

```powershell
$acl = get-acl test.txt
$binSD = $acl.GetSecurityDescriptorBinaryForm()
Invoke-WmiMethod -class Win32_SecurityDescriptorHelper -Name BinarySDToSDDL -ArgumentList $binSD, $null
```

## <span data-ttu-id="3062a-132">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3062a-132">PARAMETERS</span></span>

### <span data-ttu-id="3062a-133">-ArgumentList</span><span class="sxs-lookup"><span data-stu-id="3062a-133">-ArgumentList</span></span>

<span data-ttu-id="3062a-134">呼び出したメソッドに渡すパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-134">Specifies the parameters to pass to the called method.</span></span> <span data-ttu-id="3062a-135">このパラメーターの値は、オブジェクトの配列である必要があり、呼び出されたメソッドによって要求された順序で表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="3062a-135">The value of this parameter must be an array of objects, and they must appear in the order required by the called method.</span></span> <span data-ttu-id="3062a-136">`Invoke-CimCommand`コマンドレットには、これらの制限はありません。</span><span class="sxs-lookup"><span data-stu-id="3062a-136">The `Invoke-CimCommand` cmdlet does not have these limitations.</span></span>

<span data-ttu-id="3062a-137">これらのオブジェクトを一覧表示する順序を決定するには、 `GetMethodParameters()` このトピックの最後にある例1に示すように、WMI クラスでメソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="3062a-137">To determine the order in which to list those objects, run the `GetMethodParameters()` method on the WMI class, as illustrated in Example 1, near the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3062a-138">最初の値が複数の要素を含む配列である場合は、2 つ目の値を $null にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3062a-138">If the first value is an array that contains more than one element, a second value of $null is required.</span></span> <span data-ttu-id="3062a-139">これを指定しないと、"型 'System.Byte' のオブジェクトを型 'System.Array' にキャストできません" などのエラーがコマンドで生成されます。</span><span class="sxs-lookup"><span data-stu-id="3062a-139">Otherwise, the command generates an error, such as "Unable to cast object of type 'System.Byte' to type 'System.Array'.".</span></span> <span data-ttu-id="3062a-140">上記の例4を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3062a-140">See example 4 above.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: class, object, path
Aliases: Args

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3062a-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="3062a-141">-AsJob</span></span>

<span data-ttu-id="3062a-142">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="3062a-142">Indicates that this cmdlet runs the command as a background job.</span></span> <span data-ttu-id="3062a-143">完了に時間のかかるコマンドを実行するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3062a-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="3062a-144">**AsJob** パラメーターを使用すると、バックグラウンド ジョブを表すオブジェクトが返され、その後コマンド プロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3062a-144">When you use the **AsJob** parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span> <span data-ttu-id="3062a-145">ジョブが完了しても、引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="3062a-145">You can continue to work in the session while the job finishes.</span></span> <span data-ttu-id="3062a-146">`Invoke-WmiMethod`がリモートコンピューターに対して使用されている場合、ジョブはローカルコンピューター上に作成され、リモートコンピューターからの結果は自動的にローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="3062a-146">If `Invoke-WmiMethod` is used against a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span> <span data-ttu-id="3062a-147">ジョブを管理するには、Job という名詞を含むコマンドレット (Job コマンドレット) を使用します。</span><span class="sxs-lookup"><span data-stu-id="3062a-147">To manage the job, use the cmdlets that contain the Job noun (the Job cmdlets).</span></span> <span data-ttu-id="3062a-148">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3062a-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="3062a-149">このパラメーターをリモート コンピューターで使用するには、ローカル コンピューターおよびリモート コンピューターをリモート処理用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3062a-149">To use this parameter with remote computers, the local and remote computers must be configured for remoting.</span></span> <span data-ttu-id="3062a-150">さらに、windows Vista 以降のバージョンの Windows で [管理者として実行] オプションを使用して Windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3062a-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of Windows.</span></span> <span data-ttu-id="3062a-151">詳細については、「about_Remote_Requirements」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3062a-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="3062a-152">Windows PowerShell のバックグラウンドジョブの詳細については、「about_Jobs」および「about_Remote_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3062a-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="3062a-153">-認証</span><span class="sxs-lookup"><span data-stu-id="3062a-153">-Authentication</span></span>

<span data-ttu-id="3062a-154">WMI 接続に使用する認証レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-154">Specifies the authentication level to be used with the WMI connection.</span></span> <span data-ttu-id="3062a-155">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3062a-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3062a-156">-1: Unchanged</span><span class="sxs-lookup"><span data-stu-id="3062a-156">-1: Unchanged</span></span>
- <span data-ttu-id="3062a-157">0: Default</span><span class="sxs-lookup"><span data-stu-id="3062a-157">0: Default</span></span>
- <span data-ttu-id="3062a-158">1: None (認証は行われません)</span><span class="sxs-lookup"><span data-stu-id="3062a-158">1: None (No authentication in performed.)</span></span>
- <span data-ttu-id="3062a-159">2: Connect (認証は、クライアントとアプリケーションの関係が確立されるときのみ実行されます)</span><span class="sxs-lookup"><span data-stu-id="3062a-159">2: Connect (Authentication is performed only when the client establishes a relationship with the application.)</span></span>
- <span data-ttu-id="3062a-160">3: Call (認証は、アプリケーションが要求を受信するときに各呼び出しの始めにだけ実行されます)</span><span class="sxs-lookup"><span data-stu-id="3062a-160">3: Call (Authentication is performed only at the beginning of each call when the application receives the request.)</span></span>
- <span data-ttu-id="3062a-161">4: Packet (認証はクライアントから受信されるすべてのデータで実行されます)</span><span class="sxs-lookup"><span data-stu-id="3062a-161">4: Packet (Authentication is performed on all the data that is received from the client.)</span></span>
- <span data-ttu-id="3062a-162">5: PacketIntegrity (クライアントとアプリケーション間で転送されるすべてのデータが認証および検証されます)。</span><span class="sxs-lookup"><span data-stu-id="3062a-162">5: PacketIntegrity (All the data that is transferred between the client and the application is authenticated and verified.)</span></span>
- <span data-ttu-id="3062a-163">6: PacketPrivacy (他の認証レベルのプロパティが使用され、すべてのデータが暗号化されます)</span><span class="sxs-lookup"><span data-stu-id="3062a-163">6: PacketPrivacy (The properties of the other authentication levels are used, and all the data is encrypted.)</span></span>

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

### <span data-ttu-id="3062a-164">-Authority</span><span class="sxs-lookup"><span data-stu-id="3062a-164">-Authority</span></span>

<span data-ttu-id="3062a-165">WMI 接続の認証に使用する機関を指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-165">Specifies the authority to use to authenticate the WMI connection.</span></span> <span data-ttu-id="3062a-166">標準の Windows NT LAN Manager (NTLM) 認証または Kerberos 認証を指定できます。</span><span class="sxs-lookup"><span data-stu-id="3062a-166">You can specify standard Windows NT LAN Manager (NTLM) or Kerberos authentication.</span></span> <span data-ttu-id="3062a-167">NTLM を使用するには、認証設定に「ntlmdomain:\<DomainName\>」と指定します。\<DomainName\> には、有効な NTLM ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-167">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span> <span data-ttu-id="3062a-168">Kerberos を使用するには、「kerberos:\<DomainName\ServerName\>」と指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-168">To use Kerberos, specify kerberos:\<DomainName\ServerName\>.</span></span> <span data-ttu-id="3062a-169">ローカル コンピューターへの接続時に認証設定を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="3062a-169">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="3062a-170">-クラス</span><span class="sxs-lookup"><span data-stu-id="3062a-170">-Class</span></span>

<span data-ttu-id="3062a-171">静的な呼び出しメソッドが含まれている WMI クラスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-171">Specifies the WMI class that contains a static method to call.</span></span>

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

### <span data-ttu-id="3062a-172">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="3062a-172">-ComputerName</span></span>

<span data-ttu-id="3062a-173">文字列配列として、このコマンドレットでコマンドを実行するコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-173">Specifies, as a string array, the computers that this cmdlet runs the command on.</span></span> <span data-ttu-id="3062a-174">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="3062a-174">The default is the local computer.</span></span>

<span data-ttu-id="3062a-175">1 台または複数のコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="3062a-175">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span> <span data-ttu-id="3062a-176">ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="3062a-176">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="3062a-177">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="3062a-177">This parameter does not rely on Windows PowerShell remoting.</span></span> <span data-ttu-id="3062a-178">コンピューターがリモート コマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="3062a-178">You can use the **ComputerName** parameter even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="3062a-179">-Credential</span><span class="sxs-lookup"><span data-stu-id="3062a-179">-Credential</span></span>

<span data-ttu-id="3062a-180">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-180">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="3062a-181">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="3062a-181">The default is the current user.</span></span> <span data-ttu-id="3062a-182">、、などのユーザー名を入力し `User01` `Domain01\User01` `User@Contoso.com` ます。</span><span class="sxs-lookup"><span data-stu-id="3062a-182">Type a user name, such as `User01`, `Domain01\User01`, or `User@Contoso.com`.</span></span> <span data-ttu-id="3062a-183">または、Get-Credential コマンドレットによって返されるオブジェクトなどの **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="3062a-183">Or, enter a **PSCredential** object, such as an object that is returned by the Get-Credential cmdlet.</span></span> <span data-ttu-id="3062a-184">ユーザー名を入力すると、パスワードの入力を促すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3062a-184">When you type a user name, you will be prompted for a password.</span></span>

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

### <span data-ttu-id="3062a-185">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="3062a-185">-EnableAllPrivileges</span></span>

<span data-ttu-id="3062a-186">コマンドが WMI 呼び出しを行う前に、このコマンドレットによって現在のユーザーのすべての特権が有効になることを示します。</span><span class="sxs-lookup"><span data-stu-id="3062a-186">Indicates that this cmdlet enables all the privileges of the current user before the command makes the WMI call.</span></span>

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

### <span data-ttu-id="3062a-187">-偽装</span><span class="sxs-lookup"><span data-stu-id="3062a-187">-Impersonation</span></span>

<span data-ttu-id="3062a-188">使用する偽装レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-188">Specifies the impersonation level to use.</span></span> <span data-ttu-id="3062a-189">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3062a-189">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="3062a-190">0: Default (既定の偽装レベルのローカル レジストリを読み取ります。通常は "3: Impersonate" に設定されます)</span><span class="sxs-lookup"><span data-stu-id="3062a-190">0: Default (Reads the local registry for the default impersonation level, which is usually set to "3: Impersonate".)</span></span>
- <span data-ttu-id="3062a-191">1: Anonymous (呼び出し元の資格情報は非表示になります)</span><span class="sxs-lookup"><span data-stu-id="3062a-191">1: Anonymous (Hides the credentials of the caller.)</span></span>
- <span data-ttu-id="3062a-192">2: Identify (オブジェクトによる呼び出し元の資格情報のクエリが許可されます)</span><span class="sxs-lookup"><span data-stu-id="3062a-192">2: Identify (Allows objects to query the credentials of the caller.)</span></span>
- <span data-ttu-id="3062a-193">3: Impersonate (オブジェクトによる呼び出し元の資格情報の使用が許可されます)</span><span class="sxs-lookup"><span data-stu-id="3062a-193">3: Impersonate (Allows objects to use the credentials of the caller.)</span></span>
- <span data-ttu-id="3062a-194">4: Delegate (オブジェクトが呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします)</span><span class="sxs-lookup"><span data-stu-id="3062a-194">4: Delegate (Allows objects to permit other objects to use the credentials of the caller.)</span></span>

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

### <span data-ttu-id="3062a-195">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3062a-195">-InputObject</span></span>

<span data-ttu-id="3062a-196">入力として使用する **system.management.managementobject** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-196">Specifies a **ManagementObject** object to use as input.</span></span> <span data-ttu-id="3062a-197">このパラメーターを使用すると、 **フラグ** と **引数** のパラメーターを除く他のすべてのパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="3062a-197">When this parameter is used, all other parameters except the **Flag** and **Argument** parameters are ignored.</span></span>

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

### <span data-ttu-id="3062a-198">-ロケール</span><span class="sxs-lookup"><span data-stu-id="3062a-198">-Locale</span></span>

<span data-ttu-id="3062a-199">WMI オブジェクトの優先ロケールを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-199">Specifies the preferred locale for WMI objects.</span></span> <span data-ttu-id="3062a-200">**ロケール** パラメーターの値は、形式の配列として `MS_<LCID>` 適切な順序で指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-200">Specify the value of the **Locale** parameter as an array in the `MS_<LCID>` format in the preferred order.</span></span>

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

### <span data-ttu-id="3062a-201">-Name</span><span class="sxs-lookup"><span data-stu-id="3062a-201">-Name</span></span>

<span data-ttu-id="3062a-202">呼び出すメソッドの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-202">Specifies the name of the method to be invoked.</span></span> <span data-ttu-id="3062a-203">このパラメーターは必須です。Null や空にはできません。</span><span class="sxs-lookup"><span data-stu-id="3062a-203">This parameter is mandatory and cannot be null or empty.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3062a-204">-Namespace</span><span class="sxs-lookup"><span data-stu-id="3062a-204">-Namespace</span></span>

<span data-ttu-id="3062a-205">このパラメーターを **class** パラメーターと共に使用すると、参照先の wmi クラスまたはオブジェクトが配置されている wmi リポジトリの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-205">When used with the **Class** parameter, this parameter specifies the WMI repository namespace where the referenced WMI class or object is located.</span></span>

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

### <span data-ttu-id="3062a-206">-Path</span><span class="sxs-lookup"><span data-stu-id="3062a-206">-Path</span></span>

<span data-ttu-id="3062a-207">WMI クラスの WMI オブジェクト パス、または WMI クラスのインスタンスの WMI オブジェクト パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-207">Specifies the WMI object path of a WMI class, or specifies the WMI object path of an instance of a WMI class.</span></span> <span data-ttu-id="3062a-208">指定するクラスまたはインスタンスには、 **Name** パラメーターに指定されているメソッドが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3062a-208">The class or the instance that you specify must contain the method that is specified in the **Name** parameter.</span></span>

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

### <span data-ttu-id="3062a-209">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="3062a-209">-ThrottleLimit</span></span>

<span data-ttu-id="3062a-210">同時に実行できる WMI 操作の数のスロットル値を指定します。</span><span class="sxs-lookup"><span data-stu-id="3062a-210">Specifies a throttle value for the number of WMI operations that can be executed simultaneously.</span></span>
<span data-ttu-id="3062a-211">このパラメーターは、 **AsJob** パラメーターと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3062a-211">This parameter is used together with the **AsJob** parameter.</span></span> <span data-ttu-id="3062a-212">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="3062a-212">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="3062a-213">-Confirm</span><span class="sxs-lookup"><span data-stu-id="3062a-213">-Confirm</span></span>

<span data-ttu-id="3062a-214">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3062a-214">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="3062a-215">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="3062a-215">-WhatIf</span></span>

<span data-ttu-id="3062a-216">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="3062a-216">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="3062a-217">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="3062a-217">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="3062a-218">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="3062a-218">CommonParameters</span></span>

<span data-ttu-id="3062a-219">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="3062a-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3062a-220">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3062a-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3062a-221">入力</span><span class="sxs-lookup"><span data-stu-id="3062a-221">INPUTS</span></span>

### <span data-ttu-id="3062a-222">なし</span><span class="sxs-lookup"><span data-stu-id="3062a-222">None</span></span>

<span data-ttu-id="3062a-223">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="3062a-223">This cmdlet does not accept any input.</span></span>

## <span data-ttu-id="3062a-224">出力</span><span class="sxs-lookup"><span data-stu-id="3062a-224">OUTPUTS</span></span>

### <span data-ttu-id="3062a-225">なし</span><span class="sxs-lookup"><span data-stu-id="3062a-225">None</span></span>

<span data-ttu-id="3062a-226">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="3062a-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="3062a-227">注</span><span class="sxs-lookup"><span data-stu-id="3062a-227">NOTES</span></span>

## <span data-ttu-id="3062a-228">関連リンク</span><span class="sxs-lookup"><span data-stu-id="3062a-228">RELATED LINKS</span></span>

[<span data-ttu-id="3062a-229">Get-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3062a-229">Get-WSManInstance</span></span>](../Microsoft.WsMan.Management/Get-WSManInstance.md)

[<span data-ttu-id="3062a-230">Invoke-WSManAction</span><span class="sxs-lookup"><span data-stu-id="3062a-230">Invoke-WSManAction</span></span>](../Microsoft.WsMan.Management/Invoke-WSManAction.md)

[<span data-ttu-id="3062a-231">New-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3062a-231">New-WSManInstance</span></span>](../Microsoft.WsMan.Management/New-WSManInstance.md)

[<span data-ttu-id="3062a-232">Remove-WSManInstance</span><span class="sxs-lookup"><span data-stu-id="3062a-232">Remove-WSManInstance</span></span>](../Microsoft.WsMan.Management/Remove-WSManInstance.md)

[<span data-ttu-id="3062a-233">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="3062a-233">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="3062a-234">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="3062a-234">Remove-WmiObject</span></span>](Remove-WmiObject.md)

[<span data-ttu-id="3062a-235">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="3062a-235">Set-WmiInstance</span></span>](Set-WmiInstance.md)
