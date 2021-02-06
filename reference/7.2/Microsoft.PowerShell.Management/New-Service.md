---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 11/18/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: d3c6d77db88683c134335cf05d0165b542644b7b
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602617"
---
# <span data-ttu-id="f473c-102">New-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-102">New-Service</span></span>

## <span data-ttu-id="f473c-103">概要</span><span class="sxs-lookup"><span data-stu-id="f473c-103">SYNOPSIS</span></span>
<span data-ttu-id="f473c-104">新しい Windows サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f473c-104">Creates a new Windows service.</span></span>

## <span data-ttu-id="f473c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f473c-105">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-SecurityDescriptorSddl <String>] [-StartupType <ServiceStartupType>] [-Credential <PSCredential>]
 [-DependsOn <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="f473c-106">Description</span><span class="sxs-lookup"><span data-stu-id="f473c-106">DESCRIPTION</span></span>

<span data-ttu-id="f473c-107">コマンドレットにより、 `New-Service` レジストリとサービスデータベースに Windows サービスの新しいエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f473c-107">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="f473c-108">新しいサービスには、サービス中に実行される実行可能ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="f473c-108">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="f473c-109">このコマンドレットのパラメーターを使用すると、サービスの表示名、説明、スタートアップの種類と依存関係を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f473c-109">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="f473c-110">例</span><span class="sxs-lookup"><span data-stu-id="f473c-110">EXAMPLES</span></span>

### <span data-ttu-id="f473c-111">例 1: サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="f473c-111">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
```

<span data-ttu-id="f473c-112">このコマンドは、TestService という名前のサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f473c-112">This command creates a service named TestService.</span></span>

### <span data-ttu-id="f473c-113">例 2: 説明、スタートアップの種類、および表示名を含むサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="f473c-113">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="f473c-114">このコマンドは、TestService という名前のサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f473c-114">This command creates a service named TestService.</span></span> <span data-ttu-id="f473c-115">この例では、のパラメーターを使用して、 `New-Service` 新しいサービスの説明、スタートアップの種類、および表示名を指定しています。</span><span class="sxs-lookup"><span data-stu-id="f473c-115">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="f473c-116">例 3: 新しいサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="f473c-116">Example 3: View the new service</span></span>

```powershell
Get-CimInstance -ClassName Win32_Service -Filter "Name='testservice'"
```

```Output
ExitCode  : 0
Name      : testservice
ProcessId : 0
StartMode : Auto
State     : Stopped
Status    : OK
```

<span data-ttu-id="f473c-117">このコマンドは `Get-CimInstance` 、を使用して、新しいサービスの **Win32_Service** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="f473c-117">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="f473c-118">このオブジェクトには開始モードとサービスの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f473c-118">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="f473c-119">例 4: 作成時にサービスの SecurityDescriptor を設定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-119">Example 4: Set the SecurityDescriptor of a service when creating.</span></span>

<span data-ttu-id="f473c-120">この例では、作成されるサービスの **SecurityDescriptor** コードを追加します。</span><span class="sxs-lookup"><span data-stu-id="f473c-120">This example adds the **SecurityDescriptor** of the service being created.</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
$params = @{
  BinaryPathName = '"C:\WINDOWS\System32\svchost.exe -k netsvcs"'
  DependsOn = "NetLogon"
  DisplayName "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
  SecurityDescriptorSddl = $SDDL
}
New-Service @params
```

<span data-ttu-id="f473c-121">**SecurityDescriptor** は変数に格納され `$SDDLToSet` ます。</span><span class="sxs-lookup"><span data-stu-id="f473c-121">The **SecurityDescriptor** is stored in the `$SDDLToSet` variable.</span></span> <span data-ttu-id="f473c-122">**Security記述子 sddl** パラメーターでは、を使用して、 `$SDDL` 新しいサービスの **SecurityDescriptor** を設定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-122">The **SecurityDescriptorSddl** parameter uses `$SDDL` to set the **SecurityDescriptor** of the new service.</span></span>

## <span data-ttu-id="f473c-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f473c-123">PARAMETERS</span></span>

### <span data-ttu-id="f473c-124">-ビン名</span><span class="sxs-lookup"><span data-stu-id="f473c-124">-BinaryPathName</span></span>

<span data-ttu-id="f473c-125">サービスの実行可能ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-125">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="f473c-126">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="f473c-126">This parameter is required.</span></span>

<span data-ttu-id="f473c-127">サービスバイナリファイルへの完全修飾パス。</span><span class="sxs-lookup"><span data-stu-id="f473c-127">The fully qualified path to the service binary file.</span></span> <span data-ttu-id="f473c-128">パスにスペースが含まれている場合は、正しく解釈されるように引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="f473c-128">If the path contains a space, it must be quoted so that it is correctly interpreted.</span></span> <span data-ttu-id="f473c-129">たとえば、は `d:\my share\myservice.exe` として指定する必要があり `'"d:\my share\myservice.exe"'` ます。</span><span class="sxs-lookup"><span data-stu-id="f473c-129">For example, `d:\my share\myservice.exe` should be specified as `'"d:\my share\myservice.exe"'`.</span></span>

<span data-ttu-id="f473c-130">パスには、自動開始サービスの引数を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="f473c-130">The path can also include arguments for an auto-start service.</span></span> <span data-ttu-id="f473c-131">たとえば、「 `'"d:\myshare\myservice.exe arg1 arg2"'` 」のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f473c-131">For example, `'"d:\myshare\myservice.exe arg1 arg2"'`.</span></span> <span data-ttu-id="f473c-132">これらの引数は、サービスのエントリポイントに渡されます。</span><span class="sxs-lookup"><span data-stu-id="f473c-132">These arguments are passed to the service entry point.</span></span>

<span data-ttu-id="f473c-133">詳細については、 [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API の **Lpbinaryp name** パラメーターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f473c-133">For more information, see the **lpBinaryPathName** parameter of [CreateServiceW](/windows/win32/api/winsvc/nf-winsvc-createservicew) API.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Path

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f473c-134">-Credential</span><span class="sxs-lookup"><span data-stu-id="f473c-134">-Credential</span></span>

<span data-ttu-id="f473c-135">サービスが [サービスログオンアカウント](/windows/desktop/ad/about-service-logon-accounts)として使用するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-135">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="f473c-136">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="f473c-136">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="f473c-137">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="f473c-137">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="f473c-138">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="f473c-138">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="f473c-139">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f473c-139">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f473c-140">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="f473c-140">-DependsOn</span></span>

<span data-ttu-id="f473c-141">新しいサービスが依存する他のサービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-141">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="f473c-142">複数のサービス名を入力するには、コンマを使用して名前を区切ります。</span><span class="sxs-lookup"><span data-stu-id="f473c-142">To enter multiple service names, use a comma to separate the names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f473c-143">-Description</span><span class="sxs-lookup"><span data-stu-id="f473c-143">-Description</span></span>

<span data-ttu-id="f473c-144">サービスの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-144">Specifies a description of the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f473c-145">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="f473c-145">-DisplayName</span></span>

<span data-ttu-id="f473c-146">サービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-146">Specifies a display name for the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f473c-147">-Name</span><span class="sxs-lookup"><span data-stu-id="f473c-147">-Name</span></span>

<span data-ttu-id="f473c-148">サービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-148">Specifies the name of the service.</span></span> <span data-ttu-id="f473c-149">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="f473c-149">This parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f473c-150">-StartupType</span><span class="sxs-lookup"><span data-stu-id="f473c-150">-StartupType</span></span>

<span data-ttu-id="f473c-151">サービスのスタートアップの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-151">Sets the startup type of the service.</span></span> <span data-ttu-id="f473c-152">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f473c-152">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f473c-153">**自動** -サービスが開始されているか、システムの起動時にオペレーティングシステムによって開始されました。</span><span class="sxs-lookup"><span data-stu-id="f473c-153">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="f473c-154">自動的に開始されるサービスが手動で開始されるサービスに依存する場合は、手動で開始されるサービスもシステムの起動時に自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="f473c-154">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="f473c-155">自動 **Delayedstart** -システムが起動した直後に開始します。</span><span class="sxs-lookup"><span data-stu-id="f473c-155">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="f473c-156">[**無効**]-サービスは無効になっており、ユーザーまたはアプリケーションが開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="f473c-156">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="f473c-157">**Invalidvalue** -この値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f473c-157">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="f473c-158">この値を使用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="f473c-158">Using this value results in an error.</span></span>
- <span data-ttu-id="f473c-159">**手動** -サービスは、ユーザー、サービスコントロールマネージャー、またはアプリケーションによって手動でのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="f473c-159">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="f473c-160">既定値は **Automatic** です。</span><span class="sxs-lookup"><span data-stu-id="f473c-160">The default value is **Automatic**.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f473c-161">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="f473c-161">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="f473c-162">**Sddl** 形式でサービスの **SecurityDescriptor** を指定します。</span><span class="sxs-lookup"><span data-stu-id="f473c-162">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: sd

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f473c-163">-Confirm</span><span class="sxs-lookup"><span data-stu-id="f473c-163">-Confirm</span></span>

<span data-ttu-id="f473c-164">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f473c-164">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="f473c-165">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="f473c-165">-WhatIf</span></span>

<span data-ttu-id="f473c-166">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="f473c-166">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="f473c-167">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="f473c-167">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="f473c-168">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f473c-168">CommonParameters</span></span>

<span data-ttu-id="f473c-169">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f473c-169">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f473c-170">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f473c-170">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f473c-171">入力</span><span class="sxs-lookup"><span data-stu-id="f473c-171">INPUTS</span></span>

### <span data-ttu-id="f473c-172">なし</span><span class="sxs-lookup"><span data-stu-id="f473c-172">None</span></span>

<span data-ttu-id="f473c-173">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f473c-173">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f473c-174">出力</span><span class="sxs-lookup"><span data-stu-id="f473c-174">OUTPUTS</span></span>

### <span data-ttu-id="f473c-175">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="f473c-175">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="f473c-176">このコマンドレットは、新しいサービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f473c-176">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="f473c-177">注</span><span class="sxs-lookup"><span data-stu-id="f473c-177">NOTES</span></span>

<span data-ttu-id="f473c-178">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f473c-178">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="f473c-179">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="f473c-179">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

## <span data-ttu-id="f473c-180">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f473c-180">RELATED LINKS</span></span>

[<span data-ttu-id="f473c-181">Get-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-181">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="f473c-182">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-182">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="f473c-183">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-183">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="f473c-184">Set-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-184">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="f473c-185">Start-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-185">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="f473c-186">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-186">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="f473c-187">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-187">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="f473c-188">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="f473c-188">Remove-Service</span></span>](Remove-Service.md)
