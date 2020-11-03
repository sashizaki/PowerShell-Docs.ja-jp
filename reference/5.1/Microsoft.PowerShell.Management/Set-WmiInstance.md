---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-wmiinstance?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmiInstance
ms.openlocfilehash: 03288a2ffbef416937b2c92a7d08a5aed49ffb43
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214411"
---
# <span data-ttu-id="9dd57-103">Set-WmiInstance</span><span class="sxs-lookup"><span data-stu-id="9dd57-103">Set-WmiInstance</span></span>

## <span data-ttu-id="9dd57-104">概要</span><span class="sxs-lookup"><span data-stu-id="9dd57-104">SYNOPSIS</span></span>
<span data-ttu-id="9dd57-105">既存の Windows Management Instrumentation (WMI) クラスのインスタンスを作成または更新します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-105">Creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>

## <span data-ttu-id="9dd57-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9dd57-106">SYNTAX</span></span>

### <span data-ttu-id="9dd57-107">クラス (既定値)</span><span class="sxs-lookup"><span data-stu-id="9dd57-107">class (Default)</span></span>

```
Set-WmiInstance [-Class] <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9dd57-108">object</span><span class="sxs-lookup"><span data-stu-id="9dd57-108">object</span></span>

```
Set-WmiInstance -InputObject <ManagementObject> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9dd57-109">path</span><span class="sxs-lookup"><span data-stu-id="9dd57-109">path</span></span>

```
Set-WmiInstance -Path <String> [-Arguments <Hashtable>] [-PutType <PutType>] [-AsJob]
 [-Impersonation <ImpersonationLevel>] [-Authentication <AuthenticationLevel>] [-Locale <String>]
 [-EnableAllPrivileges] [-Authority <String>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-ComputerName <String[]>] [-Namespace <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9dd57-110">WQLQuery</span><span class="sxs-lookup"><span data-stu-id="9dd57-110">WQLQuery</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9dd57-111">query</span><span class="sxs-lookup"><span data-stu-id="9dd57-111">query</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="9dd57-112">list</span><span class="sxs-lookup"><span data-stu-id="9dd57-112">list</span></span>

```
Set-WmiInstance [-PutType <PutType>] [-AsJob] [-Impersonation <ImpersonationLevel>]
 [-Authentication <AuthenticationLevel>] [-Locale <String>] [-EnableAllPrivileges] [-Authority <String>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-ComputerName <String[]>] [-Namespace <String>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="9dd57-113">Description</span><span class="sxs-lookup"><span data-stu-id="9dd57-113">DESCRIPTION</span></span>
<span data-ttu-id="9dd57-114">`Set-WmiInstance`コマンドレットでは、既存の Windows Management Instrumentation (WMI) クラスのインスタンスを作成または更新します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-114">The `Set-WmiInstance` cmdlet creates or updates an instance of an existing Windows Management Instrumentation (WMI) class.</span></span>
<span data-ttu-id="9dd57-115">作成または更新されたインスタンスは、WMI リポジトリに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-115">The created or updated instance is written to the WMI repository.</span></span>

<span data-ttu-id="9dd57-116">Windows PowerShell 3.0 で導入された新しい CIM コマンドレットは、WMI コマンドレットと同じタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-116">New CIM cmdlets, introduced Windows PowerShell 3.0, perform the same tasks as the WMI cmdlets.</span></span>
<span data-ttu-id="9dd57-117">CIM コマンドレットは、WS-Management (WSMan) 標準と Common Information Model (CIM) 標準に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="9dd57-117">The CIM cmdlets comply with WS-Management (WSMan) standards and with the Common Information Model (CIM) standard.</span></span>
<span data-ttu-id="9dd57-118">これにより、コマンドレットで同じ手法を使用して、Windows ベースのコンピューターと他のオペレーティングシステムを実行しているコンピューターを管理できます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-118">this enables cmdlets to use the same techniques to manage Windows-based computers and those running other operating systems.</span></span>
<span data-ttu-id="9dd57-119">を使用する代わり `Set-WmiInstance` に、 [CimInstance](/powershell/module/cimcmdlets/set-ciminstance) または [CimInstance](/powershell/module/cimcmdlets/new-ciminstance) コマンドレットを使用することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9dd57-119">Instead of using `Set-WmiInstance`, consider using the [Set-CimInstance](/powershell/module/cimcmdlets/set-ciminstance) or [New-CimInstance](/powershell/module/cimcmdlets/new-ciminstance) cmdlets.</span></span>

## <span data-ttu-id="9dd57-120">例</span><span class="sxs-lookup"><span data-stu-id="9dd57-120">EXAMPLES</span></span>

### <span data-ttu-id="9dd57-121">例 1: WMI ログレベルを設定する</span><span class="sxs-lookup"><span data-stu-id="9dd57-121">Example 1: Set WMI logging level</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2}
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
```

<span data-ttu-id="9dd57-122">このコマンドは、WMI のログ レベルを 2 に設定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-122">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="9dd57-123">このコマンドは、設定するプロパティを渡し、値を引数パラメーターに値のペアとしてまとめて渡します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-123">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="9dd57-124">このパラメーターは、@{property = value} という構造で定義されたハッシュ テーブルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9dd57-124">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="9dd57-125">返されるクラス情報には、新しい値が反映されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-125">The class information that is returned reflects the new value.</span></span>

### <span data-ttu-id="9dd57-126">例 2: 環境変数とその値を作成する</span><span class="sxs-lookup"><span data-stu-id="9dd57-126">Example 2: Create an environment variable and its value</span></span>

```
PS C:\> Set-WmiInstance -Class win32_environment -Argument @{Name="testvar";VariableValue="testvalue";UserName="<SYSTEM>"}
__GENUS          : 2
__CLASS          : Win32_Environment
__SUPERCLASS     : CIM_SystemResource
__DYNASTY        : CIM_ManagedSystemElement
__RELPATH        : Win32_Environment.Name="testvar",UserName="<SYSTEM>"
__PROPERTY_COUNT : 8
__DERIVATION     : {CIM_SystemResource, CIM_LogicalElement, CIM_ManagedSystemElement}
__SERVER         : SYSTEM01
__NAMESPACE      : root\cimv2
__PATH           : \\SYSTEM01\root\cimv2:Win32_Environment.Name="testvar",UserName="<SYSTEM>"
Caption          : <SYSTEM>\testvar
Description      : <SYSTEM>\testvar
InstallDate      :
Name             : testvar
Status           : OK
SystemVariable   : True
UserName         : <SYSTEM>
VariableValue    : testvalue
```

<span data-ttu-id="9dd57-127">このコマンドは、持つ testvar という値を持つ持つ testvar 環境変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-127">This command creates the testvar environment variable that has the value testvalue.</span></span>
<span data-ttu-id="9dd57-128">これを行うには、 **Win32_Environment** WMI クラスの新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-128">It does this by creating a new instance of the **Win32_Environment** WMI class.</span></span>
<span data-ttu-id="9dd57-129">この操作には適切な資格情報が必要であり、新しい環境変数を表示するには、Windows PowerShell を再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9dd57-129">This operation requires appropriate credentials and that you may have to restart Windows PowerShell to see the new environment variable.</span></span>

### <span data-ttu-id="9dd57-130">例 3: 複数のリモートコンピューターの WMI ログ記録レベルを設定する</span><span class="sxs-lookup"><span data-stu-id="9dd57-130">Example 3: Set WMI logging level for several remote computers</span></span>

```
PS C:\> Set-WmiInstance -Class Win32_WMISetting -Argument @{LoggingLevel=2} -Computername "system01", "system02", "system03"
__GENUS                        : 2
__CLASS                        : Win32_WMISetting
__SUPERCLASS                   : CIM_Setting
__DYNASTY                      : CIM_Setting
__RELPATH                      : Win32_WMISetting=@
__PROPERTY_COUNT               : 27
__DERIVATION                   : {CIM_Setting}
__SERVER                       : SYSTEM01
__NAMESPACE                    : root\cimv2
__PATH                         : \\SYSTEM01\root\cimv2:Win32_WMISetting=@
ASPScriptDefaultNamespace      : \\root\cimv2
ASPScriptEnabled               : False
AutorecoverMofs                : {%windir%\system32\wbem\cimwin32.mof, %windir%\system32\wbem\ncprov.mof, %windir%\syst
em32\wbem\wmipcima.mof, %windir%\system32\wbem\secrcw32.mof...}
AutoStartWin9X                 :
BackupInterval                 :
BackupLastTime                 :
BuildVersion                   : 6001.18000
Caption                        :
DatabaseDirectory              : C:\Windows\system32\wbem\repository
DatabaseMaxSize                :
Description                    :
EnableAnonWin9xConnections     :
EnableEvents                   : False
EnableStartupHeapPreallocation : False
HighThresholdOnClientObjects   :
HighThresholdOnEvents          : 20000000
InstallationDirectory          : C:\Windows\system32\wbem
LastStartupHeapPreallocation   :
LoggingDirectory               : C:\Windows\system32\wbem\Logs\
LoggingLevel                   : 2
LowThresholdOnClientObjects    :
LowThresholdOnEvents           : 10000000
MaxLogFileSize                 : 65536
MaxWaitOnClientObjects         :
MaxWaitOnEvents                : 2000
MofSelfInstallDirectory        :
SettingID                      :
...
```

<span data-ttu-id="9dd57-131">このコマンドは、WMI のログ レベルを 2 に設定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-131">This command sets the WMI logging level to 2.</span></span>
<span data-ttu-id="9dd57-132">このコマンドは、設定するプロパティを渡し、値を引数パラメーターに値のペアとしてまとめて渡します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-132">The command passes the property to be set and the value, together considered a value pair, in the argument parameter.</span></span>
<span data-ttu-id="9dd57-133">このパラメーターは、@{property = value} という構造で定義されたハッシュ テーブルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9dd57-133">The parameter takes a hash table that is defined by the @{property = value} construction.</span></span>
<span data-ttu-id="9dd57-134">返されるクラス情報には、新しい値が反映されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-134">The returned class information reflects the new value.</span></span>

## <span data-ttu-id="9dd57-135">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9dd57-135">PARAMETERS</span></span>

### <span data-ttu-id="9dd57-136">-Arguments</span><span class="sxs-lookup"><span data-stu-id="9dd57-136">-Arguments</span></span>
<span data-ttu-id="9dd57-137">変更するプロパティの名前と、そのプロパティの新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-137">Specifies the name of the property to be changed and the new value for that property.</span></span>
<span data-ttu-id="9dd57-138">名前と値は、名前と値のペアである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dd57-138">The name and value must be a name-value pair.</span></span>
<span data-ttu-id="9dd57-139">名前と値のペアは、コマンドラインでハッシュテーブルとして渡されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-139">The name-value pair is passed on the command line as a hash table.</span></span>
<span data-ttu-id="9dd57-140">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-140">For example:</span></span>

`@{Setting1=1; Setting2=5; Setting3="test"}`

```yaml
Type: System.Collections.Hashtable
Parameter Sets: class, object, path
Aliases: Args, Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9dd57-141">-AsJob</span><span class="sxs-lookup"><span data-stu-id="9dd57-141">-AsJob</span></span>
<span data-ttu-id="9dd57-142">この cmdket がバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-142">Indicates that this cmdket runs as a background job.</span></span>
<span data-ttu-id="9dd57-143">完了に時間のかかるコマンドを実行するには、このパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-143">Use this parameter to run commands that take a long time to finish.</span></span>

<span data-ttu-id="9dd57-144">*AsJob* パラメーターを指定すると、バックグラウンドジョブを表すオブジェクトが返され、コマンドプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-144">When you specify the *AsJob* parameter, the command returns an object that represents the background job and then displays the command prompt.</span></span>
<span data-ttu-id="9dd57-145">ジョブが完了しても、引き続きセッションで作業できます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-145">You can continue to work in the session while the job finishes.</span></span>
<span data-ttu-id="9dd57-146">リモートコンピューターに対して設定された **設定のインスタンス** が使用されている場合、ジョブはローカルコンピューター上に作成され、リモートコンピューターからの結果は自動的にローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-146">If **Set-WmiInstance** is used for a remote computer, the job is created on the local computer, and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="9dd57-147">ジョブを管理するには **、ジョブの名詞を** 含むコマンドレット ( **job** コマンドレット) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-147">To manage the job, use the cmdlets that contain the **Job** noun (the **Job** cmdlets).</span></span>
<span data-ttu-id="9dd57-148">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-148">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="9dd57-149">このパラメーターをリモートコンピューターと共に使用するには、ローカルコンピューターとリモートコンピューターをリモート処理用に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dd57-149">To use this parameter together with remote computers, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="9dd57-150">さらに、windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[管理者として実行] オプションを使用して Windows PowerShell を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9dd57-150">Additionally, you must start Windows PowerShell by using the Run as administrator option in Windows Vista and later versions of the Windows operating system.</span></span>
<span data-ttu-id="9dd57-151">詳細については、「about_Remote_Requirements」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dd57-151">For more information, see about_Remote_Requirements.</span></span>

<span data-ttu-id="9dd57-152">Windows PowerShell のバックグラウンドジョブの詳細については、「about_Jobs」および「about_Remote_Jobs」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dd57-152">For more information about Windows PowerShell background jobs, see about_Jobs and about_Remote_Jobs.</span></span>

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

### <span data-ttu-id="9dd57-153">-認証</span><span class="sxs-lookup"><span data-stu-id="9dd57-153">-Authentication</span></span>
<span data-ttu-id="9dd57-154">WMI 接続で使用する必要がある認証レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-154">Specifies the authentication level that must be used with the WMI connection.</span></span>
<span data-ttu-id="9dd57-155">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9dd57-155">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9dd57-156">-1: 変更なし。</span><span class="sxs-lookup"><span data-stu-id="9dd57-156">-1: Unchanged.</span></span>
- <span data-ttu-id="9dd57-157">0: Default。</span><span class="sxs-lookup"><span data-stu-id="9dd57-157">0: Default.</span></span>
- <span data-ttu-id="9dd57-158">1: なし。</span><span class="sxs-lookup"><span data-stu-id="9dd57-158">1: None.</span></span>
<span data-ttu-id="9dd57-159">の認証は実行されません。</span><span class="sxs-lookup"><span data-stu-id="9dd57-159">No authentication in performed.</span></span>
- <span data-ttu-id="9dd57-160">2: 接続します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-160">2: Connect.</span></span>
<span data-ttu-id="9dd57-161">認証は、クライアントがアプリケーションとの関係を確立した場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-161">Authentication is performed only when the client establishes a relationship with the application.</span></span>
- <span data-ttu-id="9dd57-162">3: を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-162">3: Call.</span></span>
<span data-ttu-id="9dd57-163">認証は、アプリケーションが要求を受信したときに各呼び出しの開始時にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-163">Authentication is performed only at the start of each call when the application receives the request.</span></span>
- <span data-ttu-id="9dd57-164">4: パケット。</span><span class="sxs-lookup"><span data-stu-id="9dd57-164">4: Packet.</span></span>
<span data-ttu-id="9dd57-165">認証は、クライアントから受信したすべてのデータに対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-165">Authentication is performed on all the data that is received from the client.</span></span>
- <span data-ttu-id="9dd57-166">5: PacketIntegrity。</span><span class="sxs-lookup"><span data-stu-id="9dd57-166">5: PacketIntegrity.</span></span>
<span data-ttu-id="9dd57-167">クライアントとアプリケーションの間で転送されるすべてのデータが認証され、検証されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-167">All the data that is transferred between the client and the application is authenticated and verified.</span></span>
- <span data-ttu-id="9dd57-168">6: PacketPrivacy。</span><span class="sxs-lookup"><span data-stu-id="9dd57-168">6: PacketPrivacy.</span></span>
<span data-ttu-id="9dd57-169">他の認証レベルのプロパティが使用され、すべてのデータが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-169">The properties of the other authentication levels are used, and all the data is encrypted.</span></span>

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

### <span data-ttu-id="9dd57-170">-Authority</span><span class="sxs-lookup"><span data-stu-id="9dd57-170">-Authority</span></span>
<span data-ttu-id="9dd57-171">WMI 接続の認証に使用する機関を指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-171">Specifies the authority to use to authenticate the WMI connection.</span></span>
<span data-ttu-id="9dd57-172">標準の NTLM 認証または Kerberos 認証を指定できます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-172">You can specify standard NTLM or Kerberos authentication.</span></span>
<span data-ttu-id="9dd57-173">NTLM を使用するには、認証設定に「ntlmdomain:\<DomainName\>」と指定します。\<DomainName\> には、有効な NTLM ドメイン名を指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-173">To use NTLM, set the authority setting to ntlmdomain:\<DomainName\>, where \<DomainName\> identifies a valid NTLM domain name.</span></span>
<span data-ttu-id="9dd57-174">Kerberos を使用するには、「kerberos:」と指定し \<DomainName\> \\ \<ServerName\> ます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-174">To use Kerberos, specify kerberos:\<DomainName\>\\\<ServerName\>.</span></span>
<span data-ttu-id="9dd57-175">ローカル コンピューターへの接続時に認証設定を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-175">You cannot include the authority setting when you connect to the local computer.</span></span>

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

### <span data-ttu-id="9dd57-176">-クラス</span><span class="sxs-lookup"><span data-stu-id="9dd57-176">-Class</span></span>
<span data-ttu-id="9dd57-177">WMI クラスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-177">Specifies the name of a WMI class.</span></span>

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

### <span data-ttu-id="9dd57-178">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="9dd57-178">-ComputerName</span></span>
<span data-ttu-id="9dd57-179">このコマンドレットが実行されるコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-179">Specifies the name of the computer on which this cmdlet runs.</span></span>
<span data-ttu-id="9dd57-180">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="9dd57-180">The default is the local computer.</span></span>

<span data-ttu-id="9dd57-181">1 台または複数のコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-181">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more computers.</span></span>
<span data-ttu-id="9dd57-182">ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-182">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="9dd57-183">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="9dd57-183">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="9dd57-184">コンピューターがリモート コマンドを実行するように構成されていない場合でも、 *ComputerName* パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-184">You can use the *ComputerName* parameter even if your computer is not configured to run remote commands.</span></span>

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

### <span data-ttu-id="9dd57-185">-Credential</span><span class="sxs-lookup"><span data-stu-id="9dd57-185">-Credential</span></span>
<span data-ttu-id="9dd57-186">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-186">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="9dd57-187">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="9dd57-187">The default is the current user.</span></span>

<span data-ttu-id="9dd57-188">User01 や Domain01\user01」などのユーザー名を入力するか、Get-Credential コマンドレットによって生成された **PSCredential** オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-188">Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credential cmdlet.</span></span>
<span data-ttu-id="9dd57-189">ユーザー名を入力すると、このコマンドレットによってパスワードが要求されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-189">If you type a user name, this cmdlet prompts for a password.</span></span>

<span data-ttu-id="9dd57-190">このパラメーターは、Windows PowerShell でインストールされたプロバイダーでサポートされていないパラメーターを指定してインストールされたプロバイダーではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9dd57-190">This parameter is not supported by any providers installed with parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="9dd57-191">-EnableAllPrivileges</span><span class="sxs-lookup"><span data-stu-id="9dd57-191">-EnableAllPrivileges</span></span>
<span data-ttu-id="9dd57-192">このコマンドレットが、WMI 呼び出しを行うコマンドの前に、現在のユーザーのすべてのアクセス許可を有効にすることを示します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-192">Indicates that this cmdlet enables all the permissions of the current user before the command it makes the WMI call.</span></span>

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

### <span data-ttu-id="9dd57-193">-偽装</span><span class="sxs-lookup"><span data-stu-id="9dd57-193">-Impersonation</span></span>
<span data-ttu-id="9dd57-194">使用する偽装レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-194">Specifies the impersonation level to use.</span></span>
<span data-ttu-id="9dd57-195">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9dd57-195">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9dd57-196">0: Default。</span><span class="sxs-lookup"><span data-stu-id="9dd57-196">0: Default.</span></span>
<span data-ttu-id="9dd57-197">既定の偽装レベルのローカルレジストリを読み取ります。これは通常、3: Impersonate に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9dd57-197">Reads the local registry for the default impersonation level, which is usually set to 3: Impersonate.</span></span>
- <span data-ttu-id="9dd57-198">1: Anonymous。</span><span class="sxs-lookup"><span data-stu-id="9dd57-198">1: Anonymous.</span></span>
<span data-ttu-id="9dd57-199">呼び出し元の資格情報は非表示になります。</span><span class="sxs-lookup"><span data-stu-id="9dd57-199">Hides the credentials of the caller.</span></span>
- <span data-ttu-id="9dd57-200">2: Identify。</span><span class="sxs-lookup"><span data-stu-id="9dd57-200">2: Identify.</span></span>
<span data-ttu-id="9dd57-201">オブジェクトによる呼び出し元の資格情報のクエリが許可されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-201">Allows objects to query the credentials of the caller.</span></span>
- <span data-ttu-id="9dd57-202">3: Impersonate。</span><span class="sxs-lookup"><span data-stu-id="9dd57-202">3: Impersonate.</span></span>
<span data-ttu-id="9dd57-203">オブジェクトによる呼び出し元の資格情報の使用が許可されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-203">Allows objects to use the credentials of the caller.</span></span>
- <span data-ttu-id="9dd57-204">4: Delegate。</span><span class="sxs-lookup"><span data-stu-id="9dd57-204">4: Delegate.</span></span>
<span data-ttu-id="9dd57-205">オブジェクトが呼び出し元の資格情報の使用を他のオブジェクトに許可できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9dd57-205">Allows objects to permit other objects to use the credentials of the caller.</span></span>

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

### <span data-ttu-id="9dd57-206">-InputObject</span><span class="sxs-lookup"><span data-stu-id="9dd57-206">-InputObject</span></span>
<span data-ttu-id="9dd57-207">入力として使用する **system.management.managementobject** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-207">Specifies a **ManagementObject** object to use as input.</span></span>
<span data-ttu-id="9dd57-208">このパラメーターを使用すると、 *Arguments* パラメーターを除く他のすべてのパラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-208">When this parameter is used, all other parameters ,except the *Arguments* parameter, are ignored.</span></span>

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

### <span data-ttu-id="9dd57-209">-ロケール</span><span class="sxs-lookup"><span data-stu-id="9dd57-209">-Locale</span></span>
<span data-ttu-id="9dd57-210">WMI オブジェクトの優先ロケールを指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-210">Specifies the preferred locale for WMI objects.</span></span>
<span data-ttu-id="9dd57-211">*Locale* パラメーターは、配列内の MS_ 形式で、 \<LCID\> 優先順位に従って指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-211">The *Locale* parameter is specified in an array in the MS_\<LCID\> format in the preferred order.</span></span>

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

### <span data-ttu-id="9dd57-212">-Namespace</span><span class="sxs-lookup"><span data-stu-id="9dd57-212">-Namespace</span></span>
<span data-ttu-id="9dd57-213">*クラス* パラメーターと共に使用する場合に、参照先の wmi クラスが配置されている wmi リポジトリの名前空間を指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-213">Specifies the WMI repository namespace where the referenced WMI class is located when it is used with the *Class* parameter.</span></span>

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

### <span data-ttu-id="9dd57-214">-Path</span><span class="sxs-lookup"><span data-stu-id="9dd57-214">-Path</span></span>
<span data-ttu-id="9dd57-215">作成または更新するインスタンスの WMI オブジェクトパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-215">Specifies a WMI object path of the instance that you want to create or update.</span></span>

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

### <span data-ttu-id="9dd57-216">-PutType</span><span class="sxs-lookup"><span data-stu-id="9dd57-216">-PutType</span></span>
<span data-ttu-id="9dd57-217">WMI インスタンスを作成または更新するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-217">Indicates whether to create or update the WMI instance.</span></span>
<span data-ttu-id="9dd57-218">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9dd57-218">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="9dd57-219">UpdateOnly.</span><span class="sxs-lookup"><span data-stu-id="9dd57-219">UpdateOnly.</span></span>
<span data-ttu-id="9dd57-220">既存の WMI インスタンスを更新します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-220">Updates an existing WMI instance.</span></span>
- <span data-ttu-id="9dd57-221">CreateOnly.</span><span class="sxs-lookup"><span data-stu-id="9dd57-221">CreateOnly.</span></span>
<span data-ttu-id="9dd57-222">新しい WMI インスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-222">Creates a new WMI instance.</span></span>
- <span data-ttu-id="9dd57-223">UpdateOrCreate.</span><span class="sxs-lookup"><span data-stu-id="9dd57-223">UpdateOrCreate.</span></span>
<span data-ttu-id="9dd57-224">WMI インスタンスが存在する場合は更新し、存在しない場合には新しいインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-224">Updates the WMI instance if it exists or creates a new instance if an instance does not exist.</span></span>

```yaml
Type: System.Management.PutType
Parameter Sets: (All)
Aliases:
Accepted values: None, UpdateOnly, CreateOnly, UpdateOrCreate

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="9dd57-225">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="9dd57-225">-ThrottleLimit</span></span>
<span data-ttu-id="9dd57-226">このコマンドを実行するために確立できる最大コンカレント接続数を指定します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-226">Specifies the maximum number of concurrent connections that can be established to run this command.</span></span>
<span data-ttu-id="9dd57-227">このパラメーターは、 *AsJob* パラメーターと共に使用されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-227">This parameter is used together with the *AsJob* parameter.</span></span>
<span data-ttu-id="9dd57-228">スロットル制限は現在のコマンドのみに適用され、セッションまたはコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="9dd57-228">The throttle limit applies only to the current command, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="9dd57-229">-Confirm</span><span class="sxs-lookup"><span data-stu-id="9dd57-229">-Confirm</span></span>
<span data-ttu-id="9dd57-230">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9dd57-230">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="9dd57-231">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="9dd57-231">-WhatIf</span></span>
<span data-ttu-id="9dd57-232">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="9dd57-232">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="9dd57-233">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="9dd57-233">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="9dd57-234">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9dd57-234">CommonParameters</span></span>
<span data-ttu-id="9dd57-235">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="9dd57-235">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="9dd57-236">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9dd57-236">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="9dd57-237">入力</span><span class="sxs-lookup"><span data-stu-id="9dd57-237">INPUTS</span></span>

### <span data-ttu-id="9dd57-238">なし</span><span class="sxs-lookup"><span data-stu-id="9dd57-238">None</span></span>
<span data-ttu-id="9dd57-239">このコマンドレットは入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="9dd57-239">This cmdlet does not accept input.</span></span>

## <span data-ttu-id="9dd57-240">出力</span><span class="sxs-lookup"><span data-stu-id="9dd57-240">OUTPUTS</span></span>

### <span data-ttu-id="9dd57-241">なし</span><span class="sxs-lookup"><span data-stu-id="9dd57-241">None</span></span>
<span data-ttu-id="9dd57-242">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="9dd57-242">This cmdlet does not generate output.</span></span>

## <span data-ttu-id="9dd57-243">注</span><span class="sxs-lookup"><span data-stu-id="9dd57-243">NOTES</span></span>

## <span data-ttu-id="9dd57-244">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9dd57-244">RELATED LINKS</span></span>

[<span data-ttu-id="9dd57-245">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9dd57-245">Get-WmiObject</span></span>](Get-WmiObject.md)

[<span data-ttu-id="9dd57-246">Invoke-WmiMethod</span><span class="sxs-lookup"><span data-stu-id="9dd57-246">Invoke-WmiMethod</span></span>](Invoke-WmiMethod.md)

[<span data-ttu-id="9dd57-247">Remove-WmiObject</span><span class="sxs-lookup"><span data-stu-id="9dd57-247">Remove-WmiObject</span></span>](Remove-WmiObject.md)
