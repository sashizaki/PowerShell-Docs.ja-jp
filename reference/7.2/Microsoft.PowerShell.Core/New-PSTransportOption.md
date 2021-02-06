---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pstransportoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionOption
ms.openlocfilehash: fa19ee7d1856eee91a6b1d6a8352017457031202
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600585"
---
# <span data-ttu-id="981db-102">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="981db-102">New-PSTransportOption</span></span>

## <span data-ttu-id="981db-103">概要</span><span class="sxs-lookup"><span data-stu-id="981db-103">SYNOPSIS</span></span>
<span data-ttu-id="981db-104">セッション構成の詳細設定オプションが格納されたオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="981db-104">Creates an object that contains advanced options for a session configuration.</span></span>

## <span data-ttu-id="981db-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="981db-105">SYNTAX</span></span>

```
New-PSTransportOption [-MaxIdleTimeoutSec <Int32>] [-ProcessIdleTimeoutSec <Int32>] [-MaxSessions <Int32>]
 [-MaxConcurrentCommandsPerSession <Int32>] [-MaxSessionsPerUser <Int32>] [-MaxMemoryPerSessionMB <Int32>]
 [-MaxProcessesPerSession <Int32>] [-MaxConcurrentUsers <Int32>] [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [<CommonParameters>]
```

## <span data-ttu-id="981db-106">Description</span><span class="sxs-lookup"><span data-stu-id="981db-106">DESCRIPTION</span></span>

<span data-ttu-id="981db-107">**New-PSTransportOption** コマンドレットは、セッション構成のトランスポート オプションを含むオブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="981db-107">The **New-PSTransportOption** cmdlet creates an object that contains transport options for session configurations.</span></span>
<span data-ttu-id="981db-108">オブジェクトは、Register-PSSessionConfiguration や Set-PSSessionConfiguration のコマンドレットなど、セッション構成を作成または変更するコマンドレットの *TransportOption* パラメーターの値として使用できます。</span><span class="sxs-lookup"><span data-stu-id="981db-108">You can use the object as the value of the *TransportOption* parameter of cmdlets that create or change a session configuration, such as the Register-PSSessionConfiguration and Set-PSSessionConfiguration cmdlets.</span></span>

<span data-ttu-id="981db-109">また、WSMan: ドライブのセッション構成のプロパティの値を編集することにより、トランスポート オプション設定を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="981db-109">You can also change the transport option settings by editing the values of the session configuration properties in the WSMan: drive.</span></span>
<span data-ttu-id="981db-110">詳細については、「WSMan Provider」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="981db-110">For more information, see WSMan Provider.</span></span>

<span data-ttu-id="981db-111">セッション構成オプションは、サーバー側またはリモート接続の受信側で設定されたセッション値を表します。</span><span class="sxs-lookup"><span data-stu-id="981db-111">The session configuration options represent the session values set on the server-side, or receiving end of a remote connection.</span></span>
<span data-ttu-id="981db-112">クライアント側または接続の送信側は、セッションが作成されたとき、またはクライアントがセッションから切断または再接続したときに、セッションオプションの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="981db-112">The client-side, or sending end of the connection, can set session option values when the session is created, or when the client disconnects from or reconnects to the session.</span></span>
<span data-ttu-id="981db-113">特に明記しない限り、設定値が競合した場合、クライアント側の値が優先されます。</span><span class="sxs-lookup"><span data-stu-id="981db-113">Unless stated otherwise, when the setting values conflict, the client-side values take precedence.</span></span>
<span data-ttu-id="981db-114">ただし、クライアント側の値は、セッション構成に設定された最大値とクォータを超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="981db-114">However, the client-side values cannot violate maximum values and quotas set in the session configuration.</span></span>

<span data-ttu-id="981db-115">パラメーターを指定しない場合、 **new-pstransportoption** は、すべてのオプションに対して null 値を持つトランスポートオプションオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="981db-115">Without parameters, **New-PSTransportOption** generates a transport option object that has null values for all of the options.</span></span>
<span data-ttu-id="981db-116">パラメーターを省略した場合、オブジェクトではパラメーターが表すプロパティに対して null 値が保持されます。</span><span class="sxs-lookup"><span data-stu-id="981db-116">If you omit a parameter, the object has a null value for the property that the parameter represents.</span></span>
<span data-ttu-id="981db-117">Null 値は、セッション構成には影響しません。</span><span class="sxs-lookup"><span data-stu-id="981db-117">A null value does not affect the session configuration.</span></span>

<span data-ttu-id="981db-118">セッションオプションの詳細については、「New-PSSessionOption」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="981db-118">For more information about session options, see New-PSSessionOption.</span></span>
<span data-ttu-id="981db-119">セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="981db-119">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="981db-120">このコマンドレットは、Windows PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="981db-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="981db-121">例</span><span class="sxs-lookup"><span data-stu-id="981db-121">EXAMPLES</span></span>

### <span data-ttu-id="981db-122">例 1: 既定のトランスポートオプションを生成する</span><span class="sxs-lookup"><span data-stu-id="981db-122">Example 1: Generate a default transport option</span></span>

```powershell
New-PSTransportOption
```

```Output
ProcessIdleTimeoutSec           :
MaxIdleTimeoutSec               :
MaxSessions                     :
MaxConcurrentCommandsPerSession :
MaxSessionsPerUser              :
MaxMemoryPerSessionMB           :
MaxProcessesPerSession          :
MaxConcurrentUsers              :
IdleTimeoutSec                  :
OutputBufferingMode             :
```

<span data-ttu-id="981db-123">このコマンドは、パラメーターを指定せずに **new-pstransportoption** を実行します。</span><span class="sxs-lookup"><span data-stu-id="981db-123">This command runs the **New-PSTransportOption** without parameters.</span></span>
<span data-ttu-id="981db-124">出力には、コマンドレットがすべてのプロパティに対して null 値を持つトランスポートオプションオブジェクトを生成することが示されています。</span><span class="sxs-lookup"><span data-stu-id="981db-124">The output shows that the cmdlet generates a transport option object that has null values for all properties.</span></span>

### <span data-ttu-id="981db-125">例 2: セッション構成オプションを取得する</span><span class="sxs-lookup"><span data-stu-id="981db-125">Example 2: Get session configuration options</span></span>

<span data-ttu-id="981db-126">この例では、トランスポートオプションオブジェクトを使用してセッション構成オプションを設定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="981db-126">This example shows how to use a transport options object to set session configuration options.</span></span>

```powershell
$t = New-PSTransportOption -MaxSessions 40
Register-PSSessionConfiguration -Name ITTasks -TransportOption $t
Get-PSSessionConfiguration -Name ITTasks | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITTasks
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 40
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 2
Name                          : ITTasks
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
Enabled                       : True
MaxShellsPerUser              : 25
Permission                    :
```

<span data-ttu-id="981db-127">最初のコマンドは、**New-PSTransportOption** コマンドレットを使用して、$t 変数に保存されるトランスポート オプション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="981db-127">The first command uses the **New-PSTransportOption** cmdlet to create a transport options object, which it saves in the $t variable.</span></span> <span data-ttu-id="981db-128">このコマンドは、*MaxSessions* パラメーターを使用して、セッションの最大数を 40 に増やします。</span><span class="sxs-lookup"><span data-stu-id="981db-128">The command uses the *MaxSessions* parameter to increase the maximum number of sessions to 40.</span></span>

<span data-ttu-id="981db-129">2 番目のコマンドは、**Register-PSSessionConfiguration** コマンドレットを使用して、ITTasks セッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="981db-129">The second command uses the **Register-PSSessionConfiguration** cmdlet create the ITTasks session configuration.</span></span> <span data-ttu-id="981db-130">このコマンドは、*TransportOption* パラメーターを使用して、$t 変数内のトランスポート オプション オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="981db-130">The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.</span></span>

<span data-ttu-id="981db-131">3番目のコマンドは、Get-PSSessionConfiguration コマンドレットを使用して ITTasks セッション構成を取得し、Format-List コマンドレットを使用して、セッション構成オブジェクトのすべてのプロパティを一覧に表示します。</span><span class="sxs-lookup"><span data-stu-id="981db-131">The third command uses the Get-PSSessionConfiguration cmdlet to get the ITTasks session configurations and the Format-List cmdlet to display all of the properties of the session configuration object in a list.</span></span> <span data-ttu-id="981db-132">出力には、セッション構成の **MaxShells** プロパティが 40 であることが示されます。</span><span class="sxs-lookup"><span data-stu-id="981db-132">The output shows that the value of the **MaxShells** property of the session configuration is 40.</span></span>

### <span data-ttu-id="981db-133">例 3: トランスポートオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="981db-133">Example 3: Setting a transport option</span></span>

<span data-ttu-id="981db-134">このコマンドは、セッション構成内のトランスポート オプションを設定することで、セッション構成を使用するセッションに与える影響を示します。</span><span class="sxs-lookup"><span data-stu-id="981db-134">This command shows the effect of setting a transport option in a session configuration on the sessions that use the session configuration.</span></span>

```powershell
$t = New-PSTransportOption -IdleTimeoutSec 3600
Set-PSSessionConfiguration -Name ITTasks -TransportOption $t
$s = New-PSSession -Name MyITTasks -ConfigurationName ITTasks
$s | Format-List -Property *
```

```Output
State                  : Opened
IdleTimeout            : 3600000
OutputBufferingMode    : Block
ComputerName           : localhost
ConfigurationName      : ITTasks
InstanceId             : 4110c3f5-68ea-40fa-9bbf-04a433dbb02d
Id                     : 1
Name                   : MyITTasks
Availability           : Available
ApplicationPrivateData : {PSVersionTable}
Runspace               : System.Management.Automation.RemoteRunspace
```

<span data-ttu-id="981db-135">最初のコマンドは、**New-PSTransportOption** コマンドレットを使用して、トランスポート オプション オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="981db-135">The first command uses the **New-PSTransportOption** cmdlet to create a transport option object.</span></span> <span data-ttu-id="981db-136">このコマンドは、*IdleTimeoutSec* パラメーターを使用して、オブジェクトの **IdleTimeoutSec** プロパティ値を 1 時間 (3,600 秒) に設定します。</span><span class="sxs-lookup"><span data-stu-id="981db-136">The command uses the *IdleTimeoutSec* parameter to set the **IdleTimeoutSec** property value of the object to one hour (3600 seconds).</span></span> <span data-ttu-id="981db-137">このコマンドは、トランスポート オブジェクトを $t 変数に保存します。</span><span class="sxs-lookup"><span data-stu-id="981db-137">The command saves the transport objects object in the $t variable.</span></span>

<span data-ttu-id="981db-138">2番目のコマンドは、Set-PSSessionConfiguration コマンドレットを使用して、ITTasks セッション構成のトランスポートオプションを変更します。</span><span class="sxs-lookup"><span data-stu-id="981db-138">The second command uses the Set-PSSessionConfiguration cmdlet to change the transport options of the ITTasks session configuration.</span></span> <span data-ttu-id="981db-139">このコマンドは、*TransportOption* パラメーターを使用して、$t 変数内のトランスポート オプション オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="981db-139">The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.</span></span>

<span data-ttu-id="981db-140">3番目のコマンドは、New-PSSession コマンドレットを使用して、ローカルコンピューター上に MyITTasks セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="981db-140">The third command uses the New-PSSession cmdlet to create the MyITTasks session on the local computer.</span></span> <span data-ttu-id="981db-141">このコマンドは、**ConfigurationName** プロパティを使用して、ITTasks セッション構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="981db-141">The command uses the **ConfigurationName** property to specify the ITTasks session configuration.</span></span> <span data-ttu-id="981db-142">このコマンドは、セッションを $s 変数に保存します。このコマンドでは、**新しい-PSSession** の *sessionoption* パラメーターを使用して、セッションのカスタムアイドルタイムアウトを設定していないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="981db-142">The command saves the session in the $s variable.Notice that the command does not use the *SessionOption* parameter of **New-PSSession** to set a custom idle time-out for the session.</span></span> <span data-ttu-id="981db-143">失敗した場合、セッションオプションで設定されているアイドルタイムアウト値は、セッション構成で設定されているアイドルタイムアウトよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="981db-143">If it did, the idle time-out value set in the session option would take precedence over the idle time-out set in the session configuration.</span></span>

<span data-ttu-id="981db-144">4番目のコマンドは、Format-List コマンドレットを使用して、セッションのすべてのプロパティを $s 変数に一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="981db-144">The fourth command uses the Format-List cmdlet to display all properties of the session in the $s variable in a list.</span></span> <span data-ttu-id="981db-145">出力には、セッションのアイドルタイムアウトが1時間 (36万ミリ秒) であることが示されています。</span><span class="sxs-lookup"><span data-stu-id="981db-145">The output shows that the session has an idle time-out of one hour (360,000 milliseconds).</span></span>

## <span data-ttu-id="981db-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="981db-146">PARAMETERS</span></span>

### <span data-ttu-id="981db-147">-IdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="981db-147">-IdleTimeoutSec</span></span>

<span data-ttu-id="981db-148">リモートコンピューターがローカルコンピューターからの通信を受信していない場合に、各セッションが開いたままになる期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="981db-148">Determines how long each session stays open if the remote computer does not receive any communication from the local computer.</span></span>
<span data-ttu-id="981db-149">これにはハートビート信号も含まれます。</span><span class="sxs-lookup"><span data-stu-id="981db-149">This includes the heartbeat signal.</span></span>
<span data-ttu-id="981db-150">この期間が経過すると、セッションは閉じられます。</span><span class="sxs-lookup"><span data-stu-id="981db-150">When the interval expires, the session closes.</span></span>

<span data-ttu-id="981db-151">アイドルタイムアウト値は、ユーザーがセッションを切断して再接続する場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="981db-151">The idle time-out value is of significant importance when the user intends to disconnect and reconnect to a session.</span></span>
<span data-ttu-id="981db-152">ユーザーは、セッションがまだタイムアウトしていない場合のみ再接続できます。</span><span class="sxs-lookup"><span data-stu-id="981db-152">The user can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="981db-153">*IdleTimeoutSec* パラメーターは、セッション構成の **IdleTimeoutMs** プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="981db-153">The *IdleTimeoutSec* parameter corresponds to the **IdleTimeoutMs** property of a session configuration.</span></span>

<span data-ttu-id="981db-154">値を秒単位で入力します。</span><span class="sxs-lookup"><span data-stu-id="981db-154">Enter a value in seconds.</span></span>
<span data-ttu-id="981db-155">既定値は 7,200 (2 時間) です。</span><span class="sxs-lookup"><span data-stu-id="981db-155">The default value is 7200 (2 hours).</span></span>
<span data-ttu-id="981db-156">最小値は 60 (1 分) です。</span><span class="sxs-lookup"><span data-stu-id="981db-156">The minimum value is 60 (1 minute).</span></span>
<span data-ttu-id="981db-157">最大値は、WSMan 構成 () 内のシェルオブジェクトの **IdleTimeout** プロパティの値です `WSMan:\\\<ComputerName\>\Shell\IdleTimeout` 。</span><span class="sxs-lookup"><span data-stu-id="981db-157">The maximum is the value of the **IdleTimeout** property of Shell objects in the WSMan configuration (`WSMan:\\\<ComputerName\>\Shell\IdleTimeout`).</span></span>
<span data-ttu-id="981db-158">既定値は 7,200,000 ミリ秒 (2 時間) です。</span><span class="sxs-lookup"><span data-stu-id="981db-158">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="981db-159">アイドルタイムアウト値がセッションオプションとセッション構成で設定されている場合、セッションオプションで設定された値が優先されますが、セッション構成の **MaxIdleTimeoutMs** プロパティの値を超えることはできません。</span><span class="sxs-lookup"><span data-stu-id="981db-159">If an idle time-out value is set in the session options and in the session configuration, value set in the session options takes precedence, but it cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span>
<span data-ttu-id="981db-160">**MaxIdleTimeoutMs** プロパティの値を設定するには、*MaxIdleTimeoutSec* パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="981db-160">To set the value of the **MaxIdleTimeoutMs** property, use the *MaxIdleTimeoutSec* parameter.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-161">-MaxConcurrentCommandsPerSession</span><span class="sxs-lookup"><span data-stu-id="981db-161">-MaxConcurrentCommandsPerSession</span></span>

<span data-ttu-id="981db-162">各セッションで同時に実行できるコマンドの数を指定された値に制限します。</span><span class="sxs-lookup"><span data-stu-id="981db-162">Limits the number of commands that can run at the same time in each session to the specified value.</span></span>
<span data-ttu-id="981db-163">既定値は 1000 です。</span><span class="sxs-lookup"><span data-stu-id="981db-163">The default value is 1000.</span></span>

<span data-ttu-id="981db-164">*MaxConcurrentCommandsPerSession* パラメーターは、セッション構成の **MaxConcurrentCommandsPerShell** プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="981db-164">The *MaxConcurrentCommandsPerSession* parameter corresponds to the **MaxConcurrentCommandsPerShell** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-165">-MaxConcurrentUsers</span><span class="sxs-lookup"><span data-stu-id="981db-165">-MaxConcurrentUsers</span></span>

<span data-ttu-id="981db-166">各セッションで同時にコマンドを実行できるユーザーの数を指定された値に制限します。</span><span class="sxs-lookup"><span data-stu-id="981db-166">Limits the number of users who can run commands at the same time in each session to the specified value.</span></span>
<span data-ttu-id="981db-167">既定値は 5 です。</span><span class="sxs-lookup"><span data-stu-id="981db-167">The default value is 5.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-168">-MaxIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="981db-168">-MaxIdleTimeoutSec</span></span>

<span data-ttu-id="981db-169">各セッションのアイドルタイムアウトセットを、指定された値に制限します。</span><span class="sxs-lookup"><span data-stu-id="981db-169">Limits the idle time-out set for each session to the specified value.</span></span>
<span data-ttu-id="981db-170">既定値は \[ Int \] :: MaxValue (~ 25 日) です。</span><span class="sxs-lookup"><span data-stu-id="981db-170">The default value is \[Int\]::MaxValue (~25 days).</span></span>

<span data-ttu-id="981db-171">アイドルタイムアウト値は、ユーザーがセッションを切断して再接続する場合に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="981db-171">The idle time-out value is of significant importance when the user intends to disconnect and reconnect to a session.</span></span>
<span data-ttu-id="981db-172">ユーザーは、セッションがまだタイムアウトしていない場合のみ再接続できます。</span><span class="sxs-lookup"><span data-stu-id="981db-172">The user can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="981db-173">*MaxIdleTimeoutSec* パラメーターは、セッション構成の **MaxIdleTimeoutMs** プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="981db-173">The *MaxIdleTimeoutSec* parameter corresponds to the **MaxIdleTimeoutMs** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-174">-MaxMemoryPerSessionMB</span><span class="sxs-lookup"><span data-stu-id="981db-174">-MaxMemoryPerSessionMB</span></span>

<span data-ttu-id="981db-175">各セッションで使用されるメモリを、指定された値に制限します。</span><span class="sxs-lookup"><span data-stu-id="981db-175">Limits the memory used by each session to the specified value.</span></span>
<span data-ttu-id="981db-176">値はメガバイトで入力します。</span><span class="sxs-lookup"><span data-stu-id="981db-176">Enter a value in megabytes.</span></span>
<span data-ttu-id="981db-177">既定値は 1,024 メガバイト (1 GB) です。</span><span class="sxs-lookup"><span data-stu-id="981db-177">The default value is 1024 megabytes (1 GB).</span></span>

<span data-ttu-id="981db-178">*Maxmemorypersessionmb* パラメーターは、セッション構成の **Maxmemorypersessionmb** プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="981db-178">The *MaxMemoryPerSessionMB* parameter corresponds to the **MaxMemoryPerShellMB** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-179">-MaxProcessesPerSession</span><span class="sxs-lookup"><span data-stu-id="981db-179">-MaxProcessesPerSession</span></span>

<span data-ttu-id="981db-180">各セッションで実行するプロセスの数を、指定された値に制限します。</span><span class="sxs-lookup"><span data-stu-id="981db-180">Limits the number of processes running in each session to the specified value.</span></span>
<span data-ttu-id="981db-181">既定値は 15 です。</span><span class="sxs-lookup"><span data-stu-id="981db-181">The default value is 15.</span></span>

<span data-ttu-id="981db-182">*MaxProcessesPerSession* パラメーターは、セッション構成の **Maxproces pershell** プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="981db-182">The *MaxProcessesPerSession* parameter corresponds to the **MaxProcessesPerShell** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-183">-MaxSessions</span><span class="sxs-lookup"><span data-stu-id="981db-183">-MaxSessions</span></span>

<span data-ttu-id="981db-184">セッション構成を使用するセッションの数を制限します。</span><span class="sxs-lookup"><span data-stu-id="981db-184">Limits the number of sessions that use the session configuration.</span></span>
<span data-ttu-id="981db-185">既定値は 25 です。</span><span class="sxs-lookup"><span data-stu-id="981db-185">The default value is 25.</span></span>

<span data-ttu-id="981db-186">*Maxsessions* パラメーターは、セッション構成の **maxsessions** プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="981db-186">The *MaxSessions* parameter corresponds to the **MaxShells** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-187">-MaxSessionsPerUser</span><span class="sxs-lookup"><span data-stu-id="981db-187">-MaxSessionsPerUser</span></span>

<span data-ttu-id="981db-188">セッション構成を使用して特定のユーザーの資格情報で実行するセッションの数を、指定された値に制限します。</span><span class="sxs-lookup"><span data-stu-id="981db-188">Limits the number of sessions that use the session configuration and run with the credentials of a given user to the specified value.</span></span>
<span data-ttu-id="981db-189">既定値は 25 です。</span><span class="sxs-lookup"><span data-stu-id="981db-189">The default value is 25.</span></span>

<span data-ttu-id="981db-190">この値を指定する場合は、多くのユーザーが実行ユーザーの資格情報を使用している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="981db-190">When you specify this value, consider that many users might be using the credentials of a run as user.</span></span>

<span data-ttu-id="981db-191">*Maxsessionsperuser* パラメーターは、セッション構成の **MaxShellsPerUser** プロパティに対応しています。</span><span class="sxs-lookup"><span data-stu-id="981db-191">The *MaxSessionsPerUser* parameter corresponds to the **MaxShellsPerUser** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-192">-OutputBufferingMode</span><span class="sxs-lookup"><span data-stu-id="981db-192">-OutputBufferingMode</span></span>

<span data-ttu-id="981db-193">出力バッファーがいっぱいになったときに切断されたセッションでコマンドの出力を管理する方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="981db-193">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>
<span data-ttu-id="981db-194">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="981db-194">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="981db-195">ブロック。</span><span class="sxs-lookup"><span data-stu-id="981db-195">Block.</span></span>
<span data-ttu-id="981db-196">出力バッファーがいっぱいのとき、バッファーが空くまで実行が中断されます。</span><span class="sxs-lookup"><span data-stu-id="981db-196">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="981db-197">Drop : </span><span class="sxs-lookup"><span data-stu-id="981db-197">Drop.</span></span>
<span data-ttu-id="981db-198">出力バッファーがいっぱいのとき、実行は続行されます。</span><span class="sxs-lookup"><span data-stu-id="981db-198">When the output buffer is full, execution continues.</span></span>
<span data-ttu-id="981db-199">新しい出力が保存されると、最も古い出力が破棄されます。</span><span class="sxs-lookup"><span data-stu-id="981db-199">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="981db-200">[なし] :</span><span class="sxs-lookup"><span data-stu-id="981db-200">None.</span></span>
<span data-ttu-id="981db-201">出力バッファー モードが指定されません。</span><span class="sxs-lookup"><span data-stu-id="981db-201">No output buffering mode is specified.</span></span>

<span data-ttu-id="981db-202">セッションの **OutputBufferingMode** プロパティの既定値は Block です。</span><span class="sxs-lookup"><span data-stu-id="981db-202">The default value of the **OutputBufferingMode** property of sessions is Block.</span></span>

```yaml
Type: System.Nullable`1[System.Management.Automation.Runspaces.OutputBufferingMode]
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-203">-ProcessIdleTimeoutSec</span><span class="sxs-lookup"><span data-stu-id="981db-203">-ProcessIdleTimeoutSec</span></span>

<span data-ttu-id="981db-204">各ホストプロセスのタイムアウトを、指定された値に制限します。</span><span class="sxs-lookup"><span data-stu-id="981db-204">Limits the time-out for each host process to the specified value.</span></span>
<span data-ttu-id="981db-205">既定値の0は、プロセスのタイムアウト値がないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="981db-205">The default value, 0, means that there is no time-out value for the process.</span></span>

<span data-ttu-id="981db-206">他のセッション構成には、プロセスごとのタイムアウト値があります。</span><span class="sxs-lookup"><span data-stu-id="981db-206">Other session configurations have per-process time-out values.</span></span>
<span data-ttu-id="981db-207">たとえば、28800秒 (8 時間) のプロセスごとのタイムアウト値が設定さ **れている** とします。</span><span class="sxs-lookup"><span data-stu-id="981db-207">For example, the **Microsoft.PowerShell.Workflow** session configuration has a per-process time-out value of 28800 seconds (8 hours).</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="981db-208">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="981db-208">CommonParameters</span></span>

<span data-ttu-id="981db-209">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="981db-209">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="981db-210">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="981db-210">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="981db-211">入力</span><span class="sxs-lookup"><span data-stu-id="981db-211">INPUTS</span></span>

### <span data-ttu-id="981db-212">なし</span><span class="sxs-lookup"><span data-stu-id="981db-212">None</span></span>

<span data-ttu-id="981db-213">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="981db-213">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="981db-214">出力</span><span class="sxs-lookup"><span data-stu-id="981db-214">OUTPUTS</span></span>

### <span data-ttu-id="981db-215">Microsoft. PowerShell. コマンド。 WSManConfigurationOption</span><span class="sxs-lookup"><span data-stu-id="981db-215">Microsoft.PowerShell.Commands.WSManConfigurationOption</span></span>

## <span data-ttu-id="981db-216">注</span><span class="sxs-lookup"><span data-stu-id="981db-216">NOTES</span></span>

- <span data-ttu-id="981db-217">セッション構成オブジェクトのプロパティは、セッション構成に設定されているオプションとその値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="981db-217">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="981db-218">また、セッション構成ファイルを使用するセッション構成には追加のプロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="981db-218">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="981db-219">関連リンク</span><span class="sxs-lookup"><span data-stu-id="981db-219">RELATED LINKS</span></span>

[<span data-ttu-id="981db-220">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="981db-220">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="981db-221">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="981db-221">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="981db-222">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="981db-222">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="981db-223">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="981db-223">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

