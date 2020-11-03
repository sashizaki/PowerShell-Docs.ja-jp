---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 04a2d18b9d663f612e8819c1d81bbfe490f4931a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213147"
---
# <span data-ttu-id="29304-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="29304-103">New-Service</span></span>

## <span data-ttu-id="29304-104">概要</span><span class="sxs-lookup"><span data-stu-id="29304-104">SYNOPSIS</span></span>
<span data-ttu-id="29304-105">新しい Windows サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="29304-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="29304-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="29304-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartupType>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="29304-107">Description</span><span class="sxs-lookup"><span data-stu-id="29304-107">DESCRIPTION</span></span>

<span data-ttu-id="29304-108">コマンドレットにより、 `New-Service` レジストリとサービスデータベースに Windows サービスの新しいエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="29304-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="29304-109">新しいサービスには、サービス中に実行される実行可能ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="29304-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="29304-110">このコマンドレットのパラメーターを使用すると、サービスの表示名、説明、スタートアップの種類と依存関係を設定できます。</span><span class="sxs-lookup"><span data-stu-id="29304-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="29304-111">例</span><span class="sxs-lookup"><span data-stu-id="29304-111">EXAMPLES</span></span>

### <span data-ttu-id="29304-112">例 1: サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="29304-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="29304-113">このコマンドは、TestService という名前のサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="29304-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="29304-114">例 2: 説明、スタートアップの種類、および表示名を含むサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="29304-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

```powershell
$params = @{
  Name = "TestService"
  BinaryPathName = "C:\WINDOWS\System32\svchost.exe -k netsvcs"
  DependsOn = "NetLogon"
  DisplayName = "Test Service"
  StartupType = "Manual"
  Description = "This is a test service."
}
New-Service @params
```

<span data-ttu-id="29304-115">このコマンドは、TestService という名前のサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="29304-115">This command creates a service named TestService.</span></span> <span data-ttu-id="29304-116">この例では、のパラメーターを使用して、 `New-Service` 新しいサービスの説明、スタートアップの種類、および表示名を指定しています。</span><span class="sxs-lookup"><span data-stu-id="29304-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="29304-117">例 3: 新しいサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="29304-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="29304-118">このコマンドは `Get-CimInstance` 、を使用して、新しいサービスの **Win32_Service** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="29304-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="29304-119">このオブジェクトには開始モードとサービスの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="29304-119">This object includes the start mode and the service description.</span></span>

## <span data-ttu-id="29304-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="29304-120">PARAMETERS</span></span>

### <span data-ttu-id="29304-121">-ビン名</span><span class="sxs-lookup"><span data-stu-id="29304-121">-BinaryPathName</span></span>

<span data-ttu-id="29304-122">サービスの実行可能ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="29304-122">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="29304-123">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="29304-123">This parameter is required.</span></span>

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

### <span data-ttu-id="29304-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="29304-124">-Credential</span></span>

<span data-ttu-id="29304-125">サービスが [サービスログオンアカウント](/windows/desktop/ad/about-service-logon-accounts)として使用するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="29304-125">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="29304-126">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="29304-126">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="29304-127">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="29304-127">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="29304-128">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="29304-128">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="29304-129">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29304-129">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="29304-130">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="29304-130">-DependsOn</span></span>

<span data-ttu-id="29304-131">新しいサービスが依存する他のサービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="29304-131">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="29304-132">複数のサービス名を入力するには、コンマを使用して名前を区切ります。</span><span class="sxs-lookup"><span data-stu-id="29304-132">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="29304-133">-Description</span><span class="sxs-lookup"><span data-stu-id="29304-133">-Description</span></span>

<span data-ttu-id="29304-134">サービスの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="29304-134">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="29304-135">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="29304-135">-DisplayName</span></span>

<span data-ttu-id="29304-136">サービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="29304-136">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="29304-137">-Name</span><span class="sxs-lookup"><span data-stu-id="29304-137">-Name</span></span>

<span data-ttu-id="29304-138">サービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="29304-138">Specifies the name of the service.</span></span>
<span data-ttu-id="29304-139">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="29304-139">This parameter is required.</span></span>

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

### <span data-ttu-id="29304-140">-StartupType</span><span class="sxs-lookup"><span data-stu-id="29304-140">-StartupType</span></span>

<span data-ttu-id="29304-141">サービスのスタートアップの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="29304-141">Sets the startup type of the service.</span></span> <span data-ttu-id="29304-142">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="29304-142">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="29304-143">**自動** -サービスが開始されているか、システムの起動時にオペレーティングシステムによって開始されました。</span><span class="sxs-lookup"><span data-stu-id="29304-143">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="29304-144">自動的に開始されるサービスが手動で開始されるサービスに依存する場合は、手動で開始されるサービスもシステムの起動時に自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="29304-144">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="29304-145">自動 **Delayedstart** -システムが起動した直後に開始します。</span><span class="sxs-lookup"><span data-stu-id="29304-145">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="29304-146">[ **無効** ]-サービスは無効になっており、ユーザーまたはアプリケーションが開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="29304-146">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="29304-147">**Invalidvalue** -この値はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="29304-147">**InvalidValue** - This value is not supported.</span></span> <span data-ttu-id="29304-148">この値を使用すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="29304-148">Using this value results in an error.</span></span>
- <span data-ttu-id="29304-149">**手動** -サービスは、ユーザー、サービスコントロールマネージャー、またはアプリケーションによって手動でのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="29304-149">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

 <span data-ttu-id="29304-150">既定値は **Automatic** です。</span><span class="sxs-lookup"><span data-stu-id="29304-150">The default value is **Automatic** .</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases:
Accepted values: Automatic, Manual, Disabled, AutomaticDelayedStart, InvalidValue

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="29304-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="29304-151">-Confirm</span></span>

<span data-ttu-id="29304-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="29304-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="29304-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="29304-153">-WhatIf</span></span>

<span data-ttu-id="29304-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="29304-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="29304-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="29304-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="29304-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="29304-156">CommonParameters</span></span>

<span data-ttu-id="29304-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="29304-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="29304-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29304-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="29304-159">入力</span><span class="sxs-lookup"><span data-stu-id="29304-159">INPUTS</span></span>

### <span data-ttu-id="29304-160">なし</span><span class="sxs-lookup"><span data-stu-id="29304-160">None</span></span>

<span data-ttu-id="29304-161">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="29304-161">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="29304-162">出力</span><span class="sxs-lookup"><span data-stu-id="29304-162">OUTPUTS</span></span>

### <span data-ttu-id="29304-163">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="29304-163">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="29304-164">このコマンドレットは、新しいサービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="29304-164">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="29304-165">注</span><span class="sxs-lookup"><span data-stu-id="29304-165">NOTES</span></span>

<span data-ttu-id="29304-166">Windows Vista 以降のバージョンの Windows オペレーティングシステムでこのコマンドレットを実行するには、[管理者として実行] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="29304-166">To run this cmdlet on Windows Vista and later versions of the Windows operating system, start PowerShell by using the Run as administrator option.</span></span>

## <span data-ttu-id="29304-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="29304-167">RELATED LINKS</span></span>

[<span data-ttu-id="29304-168">Get-Service</span><span class="sxs-lookup"><span data-stu-id="29304-168">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="29304-169">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="29304-169">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="29304-170">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="29304-170">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="29304-171">Set-Service</span><span class="sxs-lookup"><span data-stu-id="29304-171">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="29304-172">Start-Service</span><span class="sxs-lookup"><span data-stu-id="29304-172">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="29304-173">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="29304-173">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="29304-174">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="29304-174">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="29304-175">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="29304-175">Remove-Service</span></span>](Remove-Service.md)
