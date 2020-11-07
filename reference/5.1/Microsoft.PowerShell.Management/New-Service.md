---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/new-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-Service
ms.openlocfilehash: 5647f9bfa909cba9740e7be17f262b6be0e5c8e9
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342928"
---
# <span data-ttu-id="11076-103">New-Service</span><span class="sxs-lookup"><span data-stu-id="11076-103">New-Service</span></span>

## <span data-ttu-id="11076-104">概要</span><span class="sxs-lookup"><span data-stu-id="11076-104">SYNOPSIS</span></span>
<span data-ttu-id="11076-105">新しい Windows サービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="11076-105">Creates a new Windows service.</span></span>

## <span data-ttu-id="11076-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11076-106">SYNTAX</span></span>

```
New-Service [-Name] <String> [-BinaryPathName] <String> [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Credential <PSCredential>] [-DependsOn <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="11076-107">Description</span><span class="sxs-lookup"><span data-stu-id="11076-107">DESCRIPTION</span></span>

<span data-ttu-id="11076-108">コマンドレットにより、 `New-Service` レジストリとサービスデータベースに Windows サービスの新しいエントリが作成されます。</span><span class="sxs-lookup"><span data-stu-id="11076-108">The `New-Service` cmdlet creates a new entry for a Windows service in the registry and in the service database.</span></span> <span data-ttu-id="11076-109">新しいサービスには、サービス中に実行される実行可能ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="11076-109">A new service requires an executable file that runs during the service.</span></span>

<span data-ttu-id="11076-110">このコマンドレットのパラメーターを使用すると、サービスの表示名、説明、スタートアップの種類と依存関係を設定できます。</span><span class="sxs-lookup"><span data-stu-id="11076-110">The parameters of this cmdlet let you set the display name, description, startup type, and dependencies of the service.</span></span>

## <span data-ttu-id="11076-111">例</span><span class="sxs-lookup"><span data-stu-id="11076-111">EXAMPLES</span></span>

### <span data-ttu-id="11076-112">例 1: サービスを作成する</span><span class="sxs-lookup"><span data-stu-id="11076-112">Example 1: Create a service</span></span>

```powershell
New-Service -Name "TestService" -BinaryPathName "C:\WINDOWS\System32\svchost.exe -k netsvcs"
```

<span data-ttu-id="11076-113">このコマンドは、TestService という名前のサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="11076-113">This command creates a service named TestService.</span></span>

### <span data-ttu-id="11076-114">例 2: 説明、スタートアップの種類、および表示名を含むサービスを作成する</span><span class="sxs-lookup"><span data-stu-id="11076-114">Example 2: Create a service that includes description, startup type, and display name</span></span>

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

<span data-ttu-id="11076-115">このコマンドは、TestService という名前のサービスを作成します。</span><span class="sxs-lookup"><span data-stu-id="11076-115">This command creates a service named TestService.</span></span> <span data-ttu-id="11076-116">この例では、のパラメーターを使用して、 `New-Service` 新しいサービスの説明、スタートアップの種類、および表示名を指定しています。</span><span class="sxs-lookup"><span data-stu-id="11076-116">It uses the parameters of `New-Service` to specify a description, startup type, and display name for the new service.</span></span>

### <span data-ttu-id="11076-117">例 3: 新しいサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="11076-117">Example 3: View the new service</span></span>

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

<span data-ttu-id="11076-118">このコマンドは `Get-CimInstance` 、を使用して、新しいサービスの **Win32_Service** オブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="11076-118">This command uses `Get-CimInstance` to get the **Win32_Service** object for the new service.</span></span> <span data-ttu-id="11076-119">このオブジェクトには開始モードとサービスの説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="11076-119">This object includes the start mode and the service description.</span></span>

### <span data-ttu-id="11076-120">例 4: サービスを削除する</span><span class="sxs-lookup"><span data-stu-id="11076-120">Example 4: Delete a service</span></span>

```powershell
sc.exe delete TestService
# - or -
(Get-CimInstance -Class Win32_Service -Filter "name='TestService'").delete()
```

<span data-ttu-id="11076-121">この例では、TestService サービスを削除する 2 つの方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="11076-121">This example shows two ways to delete the TestService service.</span></span> <span data-ttu-id="11076-122">最初のコマンドは、の delete オプションを使用し `Sc.exe` ます。</span><span class="sxs-lookup"><span data-stu-id="11076-122">The first command uses the delete option of `Sc.exe`.</span></span> <span data-ttu-id="11076-123">2番目のコマンドは、を返す **Win32_Service** オブジェクトの **Delete** メソッドを使用し `Get-CimInstance` ます。</span><span class="sxs-lookup"><span data-stu-id="11076-123">The second command uses the **Delete** method of the **Win32_Service** objects that `Get-CimInstance` returns.</span></span>

## <span data-ttu-id="11076-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11076-124">PARAMETERS</span></span>

### <span data-ttu-id="11076-125">-ビン名</span><span class="sxs-lookup"><span data-stu-id="11076-125">-BinaryPathName</span></span>

<span data-ttu-id="11076-126">サービスの実行可能ファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="11076-126">Specifies the path of the executable file for the service.</span></span> <span data-ttu-id="11076-127">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="11076-127">This parameter is required.</span></span>

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

### <span data-ttu-id="11076-128">-Credential</span><span class="sxs-lookup"><span data-stu-id="11076-128">-Credential</span></span>

<span data-ttu-id="11076-129">サービスが [サービスログオンアカウント](/windows/desktop/ad/about-service-logon-accounts)として使用するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="11076-129">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="11076-130">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="11076-130">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="11076-131">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="11076-131">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="11076-132">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="11076-132">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="11076-133">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11076-133">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

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

### <span data-ttu-id="11076-134">-DependsOn</span><span class="sxs-lookup"><span data-stu-id="11076-134">-DependsOn</span></span>

<span data-ttu-id="11076-135">新しいサービスが依存する他のサービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="11076-135">Specifies the names of other services upon which the new service depends.</span></span> <span data-ttu-id="11076-136">複数のサービス名を入力するには、コンマを使用して名前を区切ります。</span><span class="sxs-lookup"><span data-stu-id="11076-136">To enter multiple service names, use a comma to separate the names.</span></span>

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

### <span data-ttu-id="11076-137">-Description</span><span class="sxs-lookup"><span data-stu-id="11076-137">-Description</span></span>

<span data-ttu-id="11076-138">サービスの説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="11076-138">Specifies a description of the service.</span></span>

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

### <span data-ttu-id="11076-139">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="11076-139">-DisplayName</span></span>

<span data-ttu-id="11076-140">サービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="11076-140">Specifies a display name for the service.</span></span>

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

### <span data-ttu-id="11076-141">-Name</span><span class="sxs-lookup"><span data-stu-id="11076-141">-Name</span></span>

<span data-ttu-id="11076-142">サービスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="11076-142">Specifies the name of the service.</span></span> <span data-ttu-id="11076-143">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="11076-143">This parameter is required.</span></span>

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

### <span data-ttu-id="11076-144">-StartupType</span><span class="sxs-lookup"><span data-stu-id="11076-144">-StartupType</span></span>

<span data-ttu-id="11076-145">サービスのスタートアップの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="11076-145">Sets the startup type of the service.</span></span> <span data-ttu-id="11076-146">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11076-146">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="11076-147">**自動** -サービスが開始されているか、システムの起動時にオペレーティングシステムによって開始されました。</span><span class="sxs-lookup"><span data-stu-id="11076-147">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="11076-148">自動的に開始されるサービスが手動で開始されるサービスに依存する場合は、手動で開始されるサービスもシステムの起動時に自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="11076-148">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="11076-149">[ **無効** ]-サービスは無効になっており、ユーザーまたはアプリケーションが開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="11076-149">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="11076-150">**手動** -サービスは、ユーザー、サービスコントロールマネージャー、またはアプリケーションによって手動でのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="11076-150">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="11076-151">**ブート** -サービスがシステムローダーによって開始されたデバイスドライバーであることを示します。</span><span class="sxs-lookup"><span data-stu-id="11076-151">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="11076-152">この値は、デバイス ドライバーに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="11076-152">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="11076-153">**システム** -サービスが、' IOInitSystem () ' 関数によって開始されたデバイスドライバーであることを示します。</span><span class="sxs-lookup"><span data-stu-id="11076-153">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="11076-154">この値は、デバイス ドライバーに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="11076-154">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="11076-155">既定値は **Automatic** です。</span><span class="sxs-lookup"><span data-stu-id="11076-155">The default value is **Automatic**.</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases:
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11076-156">-Confirm</span><span class="sxs-lookup"><span data-stu-id="11076-156">-Confirm</span></span>

<span data-ttu-id="11076-157">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="11076-157">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="11076-158">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="11076-158">-WhatIf</span></span>

<span data-ttu-id="11076-159">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="11076-159">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="11076-160">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="11076-160">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="11076-161">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="11076-161">CommonParameters</span></span>

<span data-ttu-id="11076-162">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="11076-162">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11076-163">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11076-163">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="11076-164">入力</span><span class="sxs-lookup"><span data-stu-id="11076-164">INPUTS</span></span>

### <span data-ttu-id="11076-165">なし</span><span class="sxs-lookup"><span data-stu-id="11076-165">None</span></span>

<span data-ttu-id="11076-166">パイプを使用してこのコマンドレットに入力を渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="11076-166">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="11076-167">出力</span><span class="sxs-lookup"><span data-stu-id="11076-167">OUTPUTS</span></span>

### <span data-ttu-id="11076-168">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="11076-168">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="11076-169">このコマンドレットは、新しいサービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="11076-169">This cmdlet returns an object that represents the new service.</span></span>

## <span data-ttu-id="11076-170">注</span><span class="sxs-lookup"><span data-stu-id="11076-170">NOTES</span></span>

<span data-ttu-id="11076-171">このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="11076-171">To run this cmdlet, start PowerShell by using the **Run as administrator** option.</span></span>

<span data-ttu-id="11076-172">サービスを削除するには、Sc.exe を使用するか、コマンドレットを使用して `Get-CimInstance` サービスを表す **Win32_Service** オブジェクトを取得し、 **delete** メソッドを使用してサービスを削除します。</span><span class="sxs-lookup"><span data-stu-id="11076-172">To delete a service, use Sc.exe, or use the `Get-CimInstance` cmdlet to get the **Win32_Service** object that represents the service and then use the **Delete** method to delete the service.</span></span> <span data-ttu-id="11076-173">`Get-Service`を返すオブジェクトには、delete メソッドがありません。</span><span class="sxs-lookup"><span data-stu-id="11076-173">The object that `Get-Service` returns does not have a delete method.</span></span>

## <span data-ttu-id="11076-174">関連リンク</span><span class="sxs-lookup"><span data-stu-id="11076-174">RELATED LINKS</span></span>

[<span data-ttu-id="11076-175">Get-Service</span><span class="sxs-lookup"><span data-stu-id="11076-175">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="11076-176">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="11076-176">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="11076-177">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="11076-177">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="11076-178">Set-Service</span><span class="sxs-lookup"><span data-stu-id="11076-178">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="11076-179">Start-Service</span><span class="sxs-lookup"><span data-stu-id="11076-179">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="11076-180">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="11076-180">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="11076-181">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="11076-181">Suspend-Service</span></span>](Suspend-Service.md)
