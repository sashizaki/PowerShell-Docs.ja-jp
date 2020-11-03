---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: d58d26a93e9b785bcba425537ea570feeffa1606
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210624"
---
# <span data-ttu-id="72b52-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-103">Set-Service</span></span>

## <span data-ttu-id="72b52-104">概要</span><span class="sxs-lookup"><span data-stu-id="72b52-104">SYNOPSIS</span></span>
<span data-ttu-id="72b52-105">サービスを開始、停止、および中断し、そのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="72b52-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="72b52-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="72b52-106">SYNTAX</span></span>

### <span data-ttu-id="72b52-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="72b52-107">Name (Default)</span></span>

```
Set-Service [-Name] <String> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-Status <String>]
 [-SecurityDescriptorSddl <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="72b52-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="72b52-108">InputObject</span></span>

```
Set-Service [-InputObject] <ServiceController> [-DisplayName <String>] [-Credential <PSCredential>]
 [-Description <String>] [-StartupType <ServiceStartupType>] [-SecurityDescriptorSddl <String>]
 [-Status <String>] [-Force] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="72b52-109">Description</span><span class="sxs-lookup"><span data-stu-id="72b52-109">DESCRIPTION</span></span>

<span data-ttu-id="72b52-110">`Set-Service`コマンドレットは、 **Status** 、 **Description** 、 **DisplayName** 、 **startuptype** などのサービスのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="72b52-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType** .</span></span> <span data-ttu-id="72b52-111">`Set-Service` サービスを開始、停止、一時停止、または一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="72b52-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="72b52-112">サービスを識別するには、サービス名を入力するか、サービスオブジェクトを送信します。</span><span class="sxs-lookup"><span data-stu-id="72b52-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="72b52-113">または、サービス名またはサービスオブジェクトをパイプラインからに送信 `Set-Service` します。</span><span class="sxs-lookup"><span data-stu-id="72b52-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="72b52-114">例</span><span class="sxs-lookup"><span data-stu-id="72b52-114">EXAMPLES</span></span>

### <span data-ttu-id="72b52-115">例 1: 表示名を変更する</span><span class="sxs-lookup"><span data-stu-id="72b52-115">Example 1: Change a display name</span></span>

<span data-ttu-id="72b52-116">この例では、サービスの表示名が変更されています。</span><span class="sxs-lookup"><span data-stu-id="72b52-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="72b52-117">元の表示名を表示するには、を使用 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="72b52-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="72b52-118">`Set-Service`**name** パラメーターを使用して、サービスの名前 **LanmanWorkstation** を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation** .</span></span> <span data-ttu-id="72b52-119">**DisplayName** パラメーターでは、新しい表示名である **LanMan Workstation** を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation** .</span></span>

### <span data-ttu-id="72b52-120">例 2: サービスのスタートアップの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="72b52-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="72b52-121">この例では、サービスのスタートアップの種類を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="72b52-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="72b52-122">`Set-Service`**name** パラメーターを使用して、サービスの名前 ( **ビット** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS** .</span></span> <span data-ttu-id="72b52-123">**Startuptype** パラメーターを指定すると、サービスが **自動** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-123">The **StartupType** parameter sets the service to **Automatic** .</span></span>

<span data-ttu-id="72b52-124">`Get-Service`**Name** パラメーターを使用して、 **BITS** サービスを指定し、オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="72b52-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="72b52-125">`Select-Object`**Property** パラメーターを使用して、 **BITS** サービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="72b52-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="72b52-126">例 3: サービスの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="72b52-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="72b52-127">この例では、BITS サービスの説明を変更し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="72b52-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="72b52-128">`Get-CimInstance`コマンドレットは、サービスの **説明** を含む **Win32_Service** オブジェクトを返すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description** .</span></span>

```powershell
Get-CimInstance Win32_Service -Filter 'Name = "BITS"'  | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth. If the service is
              disabled, then any applications that depend on BITS, such as Windows Update or MSN
              Explorer, will be unable to automatically download programs and other information.
```

```powershell
Set-Service -Name BITS -Description "Transfers files in the background using idle network bandwidth."
Get-CimInstance Win32_Service -Filter 'Name = "BITS"' | Format-List  Name, Description
```

```Output
Name        : BITS
Description : Transfers files in the background using idle network bandwidth.
```

<span data-ttu-id="72b52-129">`Get-CimInstance` オブジェクトをパイプライン内でに送信 `Format-List` し、サービスの名前と説明を表示します。</span><span class="sxs-lookup"><span data-stu-id="72b52-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="72b52-130">比較のために、説明が更新される前と後にコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="72b52-131">`Set-Service`**Name** パラメーターを使用して、 **BITS** サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="72b52-132">**Description** パラメーターは、サービスの説明の更新されたテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="72b52-133">例 4: サービスを開始する</span><span class="sxs-lookup"><span data-stu-id="72b52-133">Example 4: Start a service</span></span>

<span data-ttu-id="72b52-134">この例では、サービスが開始されています。</span><span class="sxs-lookup"><span data-stu-id="72b52-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="72b52-135">`Set-Service` では、 **Name** パラメーターを使用してサービス ( **WinRM** ) を指定しています。</span><span class="sxs-lookup"><span data-stu-id="72b52-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM** .</span></span> <span data-ttu-id="72b52-136">**Status** パラメーターは、 **実行されている** 値を使用してサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="72b52-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="72b52-137">**PassThru** パラメーターは、結果を表示する **ServiceController** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="72b52-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="72b52-138">例 5: サービスを中断する</span><span class="sxs-lookup"><span data-stu-id="72b52-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="72b52-139">この例では、パイプラインを使用してサービスを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="72b52-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="72b52-140">`Get-Service`**Name** パラメーターを使用して **Schedule** サービスを指定し、オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="72b52-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="72b52-141">`Set-Service`**Status** パラメーターを使用して、サービスを **一時停止** に設定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-141">`Set-Service` uses the **Status** parameter to set the service to **Paused** .</span></span>

### <span data-ttu-id="72b52-142">例 6: サービスを停止する</span><span class="sxs-lookup"><span data-stu-id="72b52-142">Example 6: Stop a service</span></span>

<span data-ttu-id="72b52-143">この例では、変数を使用してサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="72b52-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="72b52-144">`Get-Service`**Name** パラメーターを使用して、サービス、 **スケジュール** を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule** .</span></span> <span data-ttu-id="72b52-145">オブジェクトは変数に格納され `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="72b52-146">`Set-Service`**InputObject** パラメーターを使用し、格納されているオブジェクトを指定し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="72b52-147">**Status** パラメーターは、サービスを **Stopped** に設定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-147">The **Status** parameter sets the service to **Stopped** .</span></span>

### <span data-ttu-id="72b52-148">例 7: リモートシステムでサービスを停止する</span><span class="sxs-lookup"><span data-stu-id="72b52-148">Example 7: Stop a service on a remote system</span></span>

<span data-ttu-id="72b52-149">この例では、リモートコンピューター上のサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="72b52-149">This example stops a service on a remote computer.</span></span>
<span data-ttu-id="72b52-150">詳細については、「 [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72b52-150">For more information, see [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```powershell
$Cred = Get-Credential
$S = Get-Service -Name Schedule
Invoke-Command -ComputerName server01.contoso.com -Credential $Cred -ScriptBlock {
  Set-Service -InputObject $S -Status Stopped
}
```

<span data-ttu-id="72b52-151">`Get-Credential` ユーザー名とパスワードの入力を求め、資格情報を変数に格納し `$Cred` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-151">`Get-Credential` prompts for a username and password, and stores the credentials in the `$Cred` variable.</span></span> <span data-ttu-id="72b52-152">`Get-Service`**Name** パラメーターを使用して **Schedule** サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-152">`Get-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="72b52-153">オブジェクトは変数に格納され `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-153">The object is stored in the variable, `$S`.</span></span>

<span data-ttu-id="72b52-154">`Invoke-Command`**ComputerName** パラメーターを使用して、リモートコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-154">`Invoke-Command` uses the **ComputerName** parameter to specify a remote computer.</span></span> <span data-ttu-id="72b52-155">**Credential** パラメーターは、変数を使用して `$Cred` コンピューターにサインオンします。</span><span class="sxs-lookup"><span data-stu-id="72b52-155">The **Credential** parameter uses the `$Cred` variable to sign on to the computer.</span></span> <span data-ttu-id="72b52-156">**ScriptBlock** はを呼び出し `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-156">The **ScriptBlock** calls `Set-Service`.</span></span> <span data-ttu-id="72b52-157">**InputObject** パラメーターは、格納されているサービスオブジェクトを指定し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-157">The **InputObject** parameter specifies the service object stored `$S`.</span></span> <span data-ttu-id="72b52-158">**Status** パラメーターは、サービスを **Stopped** に設定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-158">The **Status** parameter sets the service to **Stopped** .</span></span>

### <span data-ttu-id="72b52-159">例 8: サービスの資格情報を変更する</span><span class="sxs-lookup"><span data-stu-id="72b52-159">Example 8: Change credential of a service</span></span>

<span data-ttu-id="72b52-160">この例では、サービスの管理に使用される資格情報を変更します。</span><span class="sxs-lookup"><span data-stu-id="72b52-160">This example changes the credentials that are used to manage a service.</span></span>

```powershell
$credential = Get-Credential
Set-Service -Name Schedule -Credential $credential
```

<span data-ttu-id="72b52-161">`Get-Credential` ユーザー名とパスワードの入力を求め、資格情報を変数に格納し `$credential` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-161">`Get-Credential` prompts for a username and password, and stores the credentials in the `$credential` variable.</span></span> <span data-ttu-id="72b52-162">`Set-Service`**Name** パラメーターを使用して **Schedule** サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-162">`Set-Service` uses the **Name** parameter to specify the **Schedule** service.</span></span> <span data-ttu-id="72b52-163">**Credential** パラメーターは変数を使用 `$credential` し、 **Schedule** サービスを更新します。</span><span class="sxs-lookup"><span data-stu-id="72b52-163">The **Credential** parameter uses the `$credential` variable and updates the **Schedule** service.</span></span>

### <span data-ttu-id="72b52-164">例 9: サービスの SecurityDescriptor コードを変更する</span><span class="sxs-lookup"><span data-stu-id="72b52-164">Example 9: Change the SecurityDescriptor of a service</span></span>

<span data-ttu-id="72b52-165">この例では、サービスの **SecurityDescriptor** を変更します。</span><span class="sxs-lookup"><span data-stu-id="72b52-165">This example changes a service's **SecurityDescriptor** .</span></span>

```powershell
$SDDL = "D:(A;;CCLCSWRPWPDTLOCRRC;;;SY)(A;;CCDCLCSWRPWPDTLOCRSDRCWDWO;;;BA)(A;;CCLCSWLOCRRC;;;SU)"
Set-Service -Name "BITS" -SecurityDescriptorSddl $SDDL
```

<span data-ttu-id="72b52-166">**SecurityDescriptor** は変数に格納され `$SDDL` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-166">The **SecurityDescriptor** is stored in the `$SDDL` variable.</span></span> <span data-ttu-id="72b52-167">`Set-Service`**Name** パラメーターを使用して、 **BITS** サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-167">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="72b52-168">**Security記述子 sddl** パラメーターでは、を使用して、 `$SDDL` **BITS** サービスの **SecurityDescriptor** を変更します。</span><span class="sxs-lookup"><span data-stu-id="72b52-168">The **SecurityDescriptorSddl** parameter uses `$SDDL` to change the **SecurityDescriptor** for the **BITS** service.</span></span>

## <span data-ttu-id="72b52-169">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="72b52-169">PARAMETERS</span></span>

### <span data-ttu-id="72b52-170">-Confirm</span><span class="sxs-lookup"><span data-stu-id="72b52-170">-Confirm</span></span>

<span data-ttu-id="72b52-171">実行前に確認メッセージを表示 `Set-Service` します。</span><span class="sxs-lookup"><span data-stu-id="72b52-171">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="72b52-172">-Credential</span><span class="sxs-lookup"><span data-stu-id="72b52-172">-Credential</span></span>

<span data-ttu-id="72b52-173">サービスが [サービスログオンアカウント](/windows/desktop/ad/about-service-logon-accounts)として使用するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-173">Specifies the account used by the service as the [Service Logon Account](/windows/desktop/ad/about-service-logon-accounts).</span></span>

<span data-ttu-id="72b52-174">**User01** や **domain01\user01」** などのユーザー名を入力するか、コマンドレットによって生成されるような **PSCredential** オブジェクトを入力し `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-174">Type a user name, such as **User01** or **Domain01\User01** , or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="72b52-175">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="72b52-175">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="72b52-176">資格情報は [PSCredential](/dotnet/api/system.management.automation.pscredential) オブジェクトに格納され、パスワードは [SecureString](/dotnet/api/system.security.securestring)として格納されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-176">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="72b52-177">**SecureString** data protection の詳細については、「 [How To secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72b52-177">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

<span data-ttu-id="72b52-178">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="72b52-178">This parameter was introduced in PowerShell 6.0.</span></span>

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

### <span data-ttu-id="72b52-179">-Description</span><span class="sxs-lookup"><span data-stu-id="72b52-179">-Description</span></span>

<span data-ttu-id="72b52-180">サービスの新しい説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-180">Specifies a new description for the service.</span></span>

<span data-ttu-id="72b52-181">サービスの説明は **、[コンピューターの管理] の [サービス]** に表示されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-181">The service description appears in **Computer Management, Services** .</span></span> <span data-ttu-id="72b52-182">**説明** は、 `Get-Service` **ServiceController** オブジェクトのプロパティではありません。</span><span class="sxs-lookup"><span data-stu-id="72b52-182">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="72b52-183">サービスの説明を表示するには、 `Get-CimInstance` サービスを表す **Win32_Service** オブジェクトを返すを使用します。</span><span class="sxs-lookup"><span data-stu-id="72b52-183">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="72b52-184">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="72b52-184">-DisplayName</span></span>

<span data-ttu-id="72b52-185">サービスの新しい表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-185">Specifies a new display name for the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="72b52-186">-Force</span><span class="sxs-lookup"><span data-stu-id="72b52-186">-Force</span></span>

<span data-ttu-id="72b52-187">サービスの停止モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-187">Specifies the Stop mode of the service.</span></span> <span data-ttu-id="72b52-188">このパラメーターは、が使用されている場合にのみ機能 `-Status Stopped` します。</span><span class="sxs-lookup"><span data-stu-id="72b52-188">This parameter only works when `-Status Stopped` is used.</span></span> <span data-ttu-id="72b52-189">有効にすると、 `Set-Service` 対象サービスが停止する前に依存サービスが停止されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-189">If enabled, `Set-Service` stops the dependent services before the target service is stopped.</span></span> <span data-ttu-id="72b52-190">既定では、他の実行中のサービスが対象のサービスに依存している場合に例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="72b52-190">By default, exceptions are raised when other running services depend on the target service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="72b52-191">-InputObject</span><span class="sxs-lookup"><span data-stu-id="72b52-191">-InputObject</span></span>

<span data-ttu-id="72b52-192">変更するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-192">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="72b52-193">オブジェクトを含む変数を入力するか、コマンドなど、オブジェクトを取得するコマンドまたは式を入力し `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-193">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="72b52-194">パイプラインを使用して、サービスオブジェクトをに送信でき `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-194">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="72b52-195">-Name</span><span class="sxs-lookup"><span data-stu-id="72b52-195">-Name</span></span>

<span data-ttu-id="72b52-196">変更するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-196">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="72b52-197">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="72b52-197">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="72b52-198">パイプラインを使用して、サービス名をに送信でき `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-198">You can use the pipeline to send a service name to `Set-Service`.</span></span>

```yaml
Type: System.String
Parameter Sets: Name
Aliases: ServiceName, SN

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="72b52-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="72b52-199">-PassThru</span></span>

<span data-ttu-id="72b52-200">変更されたサービスを表す **ServiceController** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="72b52-200">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="72b52-201">既定では、は `Set-Service` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="72b52-201">By default, `Set-Service` doesn't generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="72b52-202">-StartupType</span><span class="sxs-lookup"><span data-stu-id="72b52-202">-StartupType</span></span>

<span data-ttu-id="72b52-203">サービスの開始モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-203">Specifies the start mode of the service.</span></span>

<span data-ttu-id="72b52-204">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="72b52-204">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="72b52-205">**自動** -サービスが開始されているか、システムの起動時にオペレーティングシステムによって開始されました。</span><span class="sxs-lookup"><span data-stu-id="72b52-205">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="72b52-206">自動的に開始されるサービスが手動で開始されるサービスに依存する場合は、手動で開始されるサービスもシステムの起動時に自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-206">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="72b52-207">自動 **Delayedstart** -システムが起動した直後に開始します。</span><span class="sxs-lookup"><span data-stu-id="72b52-207">**AutomaticDelayedStart** - Starts shortly after the system boots.</span></span>
- <span data-ttu-id="72b52-208">[ **無効** ]-サービスは無効になっており、ユーザーまたはアプリケーションが開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="72b52-208">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="72b52-209">**Invalidvalue** -何の効果もありません。</span><span class="sxs-lookup"><span data-stu-id="72b52-209">**InvalidValue** - Has no effect.</span></span> <span data-ttu-id="72b52-210">コマンドレットではエラーは返されませんが、サービスの StartupType は変更されません。</span><span class="sxs-lookup"><span data-stu-id="72b52-210">The cmdlet does not return an error but the StartupType of the service is not changed.</span></span>
- <span data-ttu-id="72b52-211">**手動** -サービスは、ユーザー、サービスコントロールマネージャー、またはアプリケーションによって手動でのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-211">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ServiceStartupType
Parameter Sets: (All)
Aliases: StartMode, SM, ST, StartType
Accepted values: Automatic, AutomaticDelayedStart, Disabled, InvalidValue, Manual

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="72b52-212">-状態</span><span class="sxs-lookup"><span data-stu-id="72b52-212">-Status</span></span>

<span data-ttu-id="72b52-213">サービスの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-213">Specifies the status for the service.</span></span>

<span data-ttu-id="72b52-214">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="72b52-214">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="72b52-215">**一時停止** しました。</span><span class="sxs-lookup"><span data-stu-id="72b52-215">**Paused** .</span></span> <span data-ttu-id="72b52-216">サービスを中断します。</span><span class="sxs-lookup"><span data-stu-id="72b52-216">Suspends the service.</span></span>
- <span data-ttu-id="72b52-217">**実行中** 。</span><span class="sxs-lookup"><span data-stu-id="72b52-217">**Running** .</span></span> <span data-ttu-id="72b52-218">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="72b52-218">Starts the service.</span></span>
- <span data-ttu-id="72b52-219">**停止済み** 。</span><span class="sxs-lookup"><span data-stu-id="72b52-219">**Stopped** .</span></span> <span data-ttu-id="72b52-220">サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="72b52-220">Stops the service.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Paused, Running, Stopped

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="72b52-221">-Security記述子 Sddl</span><span class="sxs-lookup"><span data-stu-id="72b52-221">-SecurityDescriptorSddl</span></span>

<span data-ttu-id="72b52-222">**Sddl** 形式でサービスの **SecurityDescriptor** を指定します。</span><span class="sxs-lookup"><span data-stu-id="72b52-222">Specifies the **SecurityDescriptor** for the service in **Sddl** format.</span></span>

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

### <span data-ttu-id="72b52-223">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="72b52-223">-WhatIf</span></span>

<span data-ttu-id="72b52-224">が実行された場合に何が起こるか `Set-Service` を示します。</span><span class="sxs-lookup"><span data-stu-id="72b52-224">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="72b52-225">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="72b52-225">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="72b52-226">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="72b52-226">CommonParameters</span></span>

<span data-ttu-id="72b52-227">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="72b52-227">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="72b52-228">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="72b52-228">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="72b52-229">入力</span><span class="sxs-lookup"><span data-stu-id="72b52-229">INPUTS</span></span>

### <span data-ttu-id="72b52-230">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="72b52-230">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="72b52-231">パイプラインを使用して、サービス名が含まれているサービスオブジェクトまたは文字列をに送信でき `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="72b52-231">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="72b52-232">出力</span><span class="sxs-lookup"><span data-stu-id="72b52-232">OUTPUTS</span></span>

### <span data-ttu-id="72b52-233">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="72b52-233">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="72b52-234">既定では、は `Set-Service` オブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="72b52-234">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="72b52-235">**PassThru** パラメーターを使用して、 **ServiceController** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="72b52-235">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="72b52-236">注</span><span class="sxs-lookup"><span data-stu-id="72b52-236">NOTES</span></span>

<span data-ttu-id="72b52-237">`Set-Service` 昇格されたアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="72b52-237">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="72b52-238">[ **管理者として実行** ] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="72b52-238">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="72b52-239">`Set-Service` 現在のユーザーがサービスを管理するアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="72b52-239">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="72b52-240">コマンドが正常に動作しない場合は、必要なアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="72b52-240">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="72b52-241">サービスのサービス名または表示名を検索するには、を使用 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="72b52-241">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="72b52-242">サービス名は [ **名前** ] 列に、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="72b52-242">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="72b52-243">関連リンク</span><span class="sxs-lookup"><span data-stu-id="72b52-243">RELATED LINKS</span></span>

[<span data-ttu-id="72b52-244">Get-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-244">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="72b52-245">New-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-245">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="72b52-246">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-246">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="72b52-247">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-247">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="72b52-248">Start-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-248">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="72b52-249">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-249">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="72b52-250">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-250">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="72b52-251">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="72b52-251">Remove-Service</span></span>](Remove-Service.md)
