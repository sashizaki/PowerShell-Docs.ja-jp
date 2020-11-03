---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/25/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Service
ms.openlocfilehash: df4fda68508e21700235d2b772c6dd43c8e1fe1e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214416"
---
# <span data-ttu-id="e0663-103">Set-Service</span><span class="sxs-lookup"><span data-stu-id="e0663-103">Set-Service</span></span>

## <span data-ttu-id="e0663-104">概要</span><span class="sxs-lookup"><span data-stu-id="e0663-104">SYNOPSIS</span></span>
<span data-ttu-id="e0663-105">サービスを開始、停止、および中断し、そのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="e0663-105">Starts, stops, and suspends a service, and changes its properties.</span></span>

## <span data-ttu-id="e0663-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e0663-106">SYNTAX</span></span>

### <span data-ttu-id="e0663-107">名前 (既定値)</span><span class="sxs-lookup"><span data-stu-id="e0663-107">Name (Default)</span></span>

```
Set-Service [-ComputerName <String[]>] [-Name] <String> [-DisplayName <String>]
 [-Description <String>] [-StartupType <ServiceStartMode>] [-Status <String>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="e0663-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="e0663-108">InputObject</span></span>

```
Set-Service [-ComputerName <String[]>] [-DisplayName <String>] [-Description <String>]
 [-StartupType <ServiceStartMode>] [-Status <String>] [-InputObject <ServiceController>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="e0663-109">Description</span><span class="sxs-lookup"><span data-stu-id="e0663-109">DESCRIPTION</span></span>

<span data-ttu-id="e0663-110">`Set-Service`コマンドレットは、 **Status** 、 **Description** 、 **DisplayName** 、 **startuptype** などのサービスのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="e0663-110">The `Set-Service` cmdlet changes the properties of a service such as the **Status** , **Description** , **DisplayName** , and **StartupType** .</span></span> <span data-ttu-id="e0663-111">`Set-Service` サービスを開始、停止、一時停止、または一時停止できます。</span><span class="sxs-lookup"><span data-stu-id="e0663-111">`Set-Service` can start, stop, suspend, or pause a service.</span></span> <span data-ttu-id="e0663-112">サービスを識別するには、サービス名を入力するか、サービスオブジェクトを送信します。</span><span class="sxs-lookup"><span data-stu-id="e0663-112">To identify a service, enter its service name or submit a service object.</span></span> <span data-ttu-id="e0663-113">または、サービス名またはサービスオブジェクトをパイプラインからに送信 `Set-Service` します。</span><span class="sxs-lookup"><span data-stu-id="e0663-113">Or, send a service name or service object down the pipeline to `Set-Service`.</span></span>

## <span data-ttu-id="e0663-114">例</span><span class="sxs-lookup"><span data-stu-id="e0663-114">EXAMPLES</span></span>

### <span data-ttu-id="e0663-115">例 1: 表示名を変更する</span><span class="sxs-lookup"><span data-stu-id="e0663-115">Example 1: Change a display name</span></span>

<span data-ttu-id="e0663-116">この例では、サービスの表示名が変更されています。</span><span class="sxs-lookup"><span data-stu-id="e0663-116">In this example, a service's display name is changed.</span></span> <span data-ttu-id="e0663-117">元の表示名を表示するには、を使用 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="e0663-117">To view the original display name, use `Get-Service`.</span></span>

```powershell
Set-Service -Name LanmanWorkstation -DisplayName "LanMan Workstation"
```

<span data-ttu-id="e0663-118">`Set-Service`**name** パラメーターを使用して、サービスの名前 **LanmanWorkstation** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-118">`Set-Service` uses the **Name** parameter to specify the service's name, **LanmanWorkstation** .</span></span> <span data-ttu-id="e0663-119">**DisplayName** パラメーターでは、新しい表示名である **LanMan Workstation** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-119">The **DisplayName** parameter specifies the new display name, **LanMan Workstation** .</span></span>

### <span data-ttu-id="e0663-120">例 2: サービスのスタートアップの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="e0663-120">Example 2: Change the startup type of services</span></span>

<span data-ttu-id="e0663-121">この例では、サービスのスタートアップの種類を変更する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e0663-121">This example shows how to change a service's startup type.</span></span>

```powershell
Set-Service -Name BITS -StartupType Automatic
Get-Service BITS | Select-Object -Property Name, StartType, Status
```

```Output
Name  StartType   Status
----  ---------   ------
BITS  Automatic  Running
```

<span data-ttu-id="e0663-122">`Set-Service`**name** パラメーターを使用して、サービスの名前 ( **ビット** ) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-122">`Set-Service` uses the **Name** parameter to specify the service's name, **BITS** .</span></span> <span data-ttu-id="e0663-123">**Startuptype** パラメーターを指定すると、サービスが **自動** に設定されます。</span><span class="sxs-lookup"><span data-stu-id="e0663-123">The **StartupType** parameter sets the service to **Automatic** .</span></span>

<span data-ttu-id="e0663-124">`Get-Service`**Name** パラメーターを使用して、 **BITS** サービスを指定し、オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="e0663-124">`Get-Service` uses the **Name** parameter to specify the **BITS** service and sends the object down the pipeline.</span></span> <span data-ttu-id="e0663-125">`Select-Object`**Property** パラメーターを使用して、 **BITS** サービスの状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0663-125">`Select-Object` uses the **Property** parameter to display the **BITS** service's status.</span></span>

### <span data-ttu-id="e0663-126">例 3: サービスの説明を変更する</span><span class="sxs-lookup"><span data-stu-id="e0663-126">Example 3: Change the description of a service</span></span>

<span data-ttu-id="e0663-127">この例では、BITS サービスの説明を変更し、結果を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0663-127">This example changes the BITS service's description and displays the result.</span></span>

<span data-ttu-id="e0663-128">`Get-CimInstance`コマンドレットは、サービスの **説明** を含む **Win32_Service** オブジェクトを返すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0663-128">The `Get-CimInstance` cmdlet is used because it returns a **Win32_Service** object that includes the service's **Description** .</span></span>

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

<span data-ttu-id="e0663-129">`Get-CimInstance` オブジェクトをパイプライン内でに送信 `Format-List` し、サービスの名前と説明を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0663-129">`Get-CimInstance` sends the object down the pipeline to `Format-List` and displays the service's name and description.</span></span> <span data-ttu-id="e0663-130">比較のために、説明が更新される前と後にコマンドが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e0663-130">For comparison purposes, the command is run before and after the description is updated.</span></span>

<span data-ttu-id="e0663-131">`Set-Service`**Name** パラメーターを使用して、 **BITS** サービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-131">`Set-Service` uses the **Name** parameter to specify the **BITS** service.</span></span> <span data-ttu-id="e0663-132">**Description** パラメーターは、サービスの説明の更新されたテキストを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-132">The **Description** parameter specifies the updated text for the services' description.</span></span>

### <span data-ttu-id="e0663-133">例 4: サービスを開始する</span><span class="sxs-lookup"><span data-stu-id="e0663-133">Example 4: Start a service</span></span>

<span data-ttu-id="e0663-134">この例では、サービスが開始されています。</span><span class="sxs-lookup"><span data-stu-id="e0663-134">In this example, a service is started.</span></span>

```powershell
Set-Service -Name WinRM -Status Running -PassThru
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinRM              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="e0663-135">`Set-Service` では、 **Name** パラメーターを使用してサービス ( **WinRM** ) を指定しています。</span><span class="sxs-lookup"><span data-stu-id="e0663-135">`Set-Service` uses the **Name** parameter to specify the service, **WinRM** .</span></span> <span data-ttu-id="e0663-136">**Status** パラメーターは、 **実行されている** 値を使用してサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e0663-136">The **Status** parameter uses the value **Running** to start the service.</span></span> <span data-ttu-id="e0663-137">**PassThru** パラメーターは、結果を表示する **ServiceController** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="e0663-137">The **PassThru** parameter outputs a **ServiceController** object that displays the results.</span></span>

### <span data-ttu-id="e0663-138">例 5: サービスを中断する</span><span class="sxs-lookup"><span data-stu-id="e0663-138">Example 5: Suspend a service</span></span>

<span data-ttu-id="e0663-139">この例では、パイプラインを使用してサービスを一時停止します。</span><span class="sxs-lookup"><span data-stu-id="e0663-139">This example uses the pipeline to pause to service.</span></span>

```powershell
Get-Service -Name Schedule | Set-Service -Status Paused
```

<span data-ttu-id="e0663-140">`Get-Service`**Name** パラメーターを使用して **Schedule** サービスを指定し、オブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="e0663-140">`Get-Service` uses the **Name** parameter to specify the **Schedule** service, and sends the object down the pipeline.</span></span> <span data-ttu-id="e0663-141">`Set-Service`**Status** パラメーターを使用して、サービスを **一時停止** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-141">`Set-Service` uses the **Status** parameter to set the service to **Paused** .</span></span>

### <span data-ttu-id="e0663-142">例 6: サービスを停止する</span><span class="sxs-lookup"><span data-stu-id="e0663-142">Example 6: Stop a service</span></span>

<span data-ttu-id="e0663-143">この例では、変数を使用してサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="e0663-143">This example uses a variable to stop a service.</span></span>

```powershell
$S = Get-Service -Name Schedule
Set-Service -InputObject $S -Status Stopped
```

<span data-ttu-id="e0663-144">`Get-Service`**Name** パラメーターを使用して、サービス、 **スケジュール** を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-144">`Get-Service` uses the **Name** parameter to specify the service, **Schedule** .</span></span> <span data-ttu-id="e0663-145">オブジェクトは変数に格納され `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="e0663-145">The object is stored in the variable, `$S`.</span></span> <span data-ttu-id="e0663-146">`Set-Service`**InputObject** パラメーターを使用し、格納されているオブジェクトを指定し `$S` ます。</span><span class="sxs-lookup"><span data-stu-id="e0663-146">`Set-Service` uses the **InputObject** parameter and specifies the object stored `$S`.</span></span> <span data-ttu-id="e0663-147">**Status** パラメーターは、サービスを **Stopped** に設定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-147">The **Status** parameter sets the service to **Stopped** .</span></span>

## <span data-ttu-id="e0663-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e0663-148">PARAMETERS</span></span>

### <span data-ttu-id="e0663-149">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="e0663-149">-ComputerName</span></span>

<span data-ttu-id="e0663-150">1 台以上のコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-150">Specifies one or more computers.</span></span> <span data-ttu-id="e0663-151">リモートコンピューターの場合は、NetBIOS 名、IP アドレス、または完全修飾ドメイン名を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0663-151">For remote computers, type the NetBIOS name, an IP address, or a fully qualified domain name.</span></span> <span data-ttu-id="e0663-152">**ComputerName** パラメーターが指定されていない場合、コマンドはローカルコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e0663-152">If the **ComputerName** parameter isn't specified, the command runs on the local computer.</span></span>

<span data-ttu-id="e0663-153">このパラメーターは、PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="e0663-153">This parameter doesn't rely on PowerShell remoting.</span></span> <span data-ttu-id="e0663-154">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **ComputerName** パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0663-154">You can use the **ComputerName** parameter even if your computer isn't configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: cn

Required: False
Position: Named
Default value: Local computer
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="e0663-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="e0663-155">-Confirm</span></span>

<span data-ttu-id="e0663-156">実行前に確認メッセージを表示 `Set-Service` します。</span><span class="sxs-lookup"><span data-stu-id="e0663-156">Prompts you for confirmation before running `Set-Service`.</span></span>

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

### <span data-ttu-id="e0663-157">-Description</span><span class="sxs-lookup"><span data-stu-id="e0663-157">-Description</span></span>

<span data-ttu-id="e0663-158">サービスの新しい説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-158">Specifies a new description for the service.</span></span>

<span data-ttu-id="e0663-159">サービスの説明は **、[コンピューターの管理] の [サービス]** に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0663-159">The service description appears in **Computer Management, Services** .</span></span> <span data-ttu-id="e0663-160">**説明** は、 `Get-Service` **ServiceController** オブジェクトのプロパティではありません。</span><span class="sxs-lookup"><span data-stu-id="e0663-160">The **Description** isn't a property of the `Get-Service` **ServiceController** object.</span></span> <span data-ttu-id="e0663-161">サービスの説明を表示するには、 `Get-CimInstance` サービスを表す **Win32_Service** オブジェクトを返すを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0663-161">To see the service description, use `Get-CimInstance` that returns a **Win32_Service** object that represents the service.</span></span>

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

### <span data-ttu-id="e0663-162">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="e0663-162">-DisplayName</span></span>

<span data-ttu-id="e0663-163">サービスの新しい表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-163">Specifies a new display name for the service.</span></span>

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

### <span data-ttu-id="e0663-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="e0663-164">-InputObject</span></span>

<span data-ttu-id="e0663-165">変更するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-165">Specifies a **ServiceController** object that represents the service to change.</span></span> <span data-ttu-id="e0663-166">オブジェクトを含む変数を入力するか、コマンドなど、オブジェクトを取得するコマンドまたは式を入力し `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="e0663-166">Enter a variable that contains the object, or type a command or expression that gets the object, such as a `Get-Service` command.</span></span> <span data-ttu-id="e0663-167">パイプラインを使用して、サービスオブジェクトをに送信でき `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="e0663-167">You can use the pipeline to send a service object to `Set-Service`.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="e0663-168">-Name</span><span class="sxs-lookup"><span data-stu-id="e0663-168">-Name</span></span>

<span data-ttu-id="e0663-169">変更するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-169">Specifies the service name of the service to be changed.</span></span> <span data-ttu-id="e0663-170">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e0663-170">Wildcard characters aren't permitted.</span></span> <span data-ttu-id="e0663-171">パイプラインを使用して、サービス名をに送信でき `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="e0663-171">You can use the pipeline to send a service name to `Set-Service`.</span></span>

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

### <span data-ttu-id="e0663-172">-PassThru</span><span class="sxs-lookup"><span data-stu-id="e0663-172">-PassThru</span></span>

<span data-ttu-id="e0663-173">変更されたサービスを表す **ServiceController** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e0663-173">Returns a **ServiceController** object that represents the services that were changed.</span></span> <span data-ttu-id="e0663-174">既定では、は `Set-Service` 出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="e0663-174">By default, `Set-Service` doesn't generate any output.</span></span>

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

### <span data-ttu-id="e0663-175">-StartupType</span><span class="sxs-lookup"><span data-stu-id="e0663-175">-StartupType</span></span>

<span data-ttu-id="e0663-176">サービスのスタートアップの種類を設定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-176">Sets the startup type of the service.</span></span> <span data-ttu-id="e0663-177">このパラメーターの有効値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0663-177">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="e0663-178">**自動** -サービスが開始されているか、システムの起動時にオペレーティングシステムによって開始されました。</span><span class="sxs-lookup"><span data-stu-id="e0663-178">**Automatic** - The service is started or was started by the operating system, at system start-up.</span></span>
  <span data-ttu-id="e0663-179">自動的に開始されるサービスが手動で開始されるサービスに依存する場合は、手動で開始されるサービスもシステムの起動時に自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="e0663-179">If an automatically started service depends on a manually started service, the manually started service is also started automatically at system startup.</span></span>
- <span data-ttu-id="e0663-180">[ **無効** ]-サービスは無効になっており、ユーザーまたはアプリケーションが開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="e0663-180">**Disabled** - The service is disabled and cannot be started by a user or application.</span></span>
- <span data-ttu-id="e0663-181">**手動** -サービスは、ユーザー、サービスコントロールマネージャー、またはアプリケーションによって手動でのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="e0663-181">**Manual** - The service is started only manually, by a user, using the Service Control Manager, or by an application.</span></span>
- <span data-ttu-id="e0663-182">**ブート** -サービスがシステムローダーによって開始されたデバイスドライバーであることを示します。</span><span class="sxs-lookup"><span data-stu-id="e0663-182">**Boot** - Indicates that the service is a device driver started by the system loader.</span></span> <span data-ttu-id="e0663-183">この値は、デバイス ドライバーに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="e0663-183">This value is valid only for device drivers.</span></span>
- <span data-ttu-id="e0663-184">**システム** -サービスが、' IOInitSystem () ' 関数によって開始されたデバイスドライバーであることを示します。</span><span class="sxs-lookup"><span data-stu-id="e0663-184">**System** - Indicates that the service is a device driver started by the 'IOInitSystem()' function.</span></span> <span data-ttu-id="e0663-185">この値は、デバイス ドライバーに対してのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="e0663-185">This value is valid only for device drivers.</span></span>

 <span data-ttu-id="e0663-186">既定値は **Automatic** です。</span><span class="sxs-lookup"><span data-stu-id="e0663-186">The default value is **Automatic** .</span></span>

```yaml
Type: System.ServiceProcess.ServiceStartMode
Parameter Sets: (All)
Aliases: StartMode, SM, ST
Accepted values: Boot, System, Automatic, Manual, Disabled

Required: False
Position: Named
Default value: Automatic
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="e0663-187">-状態</span><span class="sxs-lookup"><span data-stu-id="e0663-187">-Status</span></span>

<span data-ttu-id="e0663-188">サービスの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0663-188">Specifies the status for the service.</span></span>

<span data-ttu-id="e0663-189">このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e0663-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="e0663-190">**一時停止** しました。</span><span class="sxs-lookup"><span data-stu-id="e0663-190">**Paused** .</span></span> <span data-ttu-id="e0663-191">サービスを中断します。</span><span class="sxs-lookup"><span data-stu-id="e0663-191">Suspends the service.</span></span>
- <span data-ttu-id="e0663-192">**実行中** 。</span><span class="sxs-lookup"><span data-stu-id="e0663-192">**Running** .</span></span> <span data-ttu-id="e0663-193">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="e0663-193">Starts the service.</span></span>
- <span data-ttu-id="e0663-194">**停止済み** 。</span><span class="sxs-lookup"><span data-stu-id="e0663-194">**Stopped** .</span></span> <span data-ttu-id="e0663-195">サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="e0663-195">Stops the service.</span></span>

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

### <span data-ttu-id="e0663-196">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="e0663-196">-WhatIf</span></span>

<span data-ttu-id="e0663-197">が実行された場合に何が起こるか `Set-Service` を示します。</span><span class="sxs-lookup"><span data-stu-id="e0663-197">Shows what would happen if `Set-Service` runs.</span></span> <span data-ttu-id="e0663-198">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e0663-198">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="e0663-199">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e0663-199">CommonParameters</span></span>

<span data-ttu-id="e0663-200">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e0663-200">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e0663-201">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0663-201">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e0663-202">入力</span><span class="sxs-lookup"><span data-stu-id="e0663-202">INPUTS</span></span>

### <span data-ttu-id="e0663-203">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="e0663-203">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="e0663-204">パイプラインを使用して、サービス名が含まれているサービスオブジェクトまたは文字列をに送信でき `Set-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="e0663-204">You can use the pipeline to send a service object or a string that contains a service name to `Set-Service`.</span></span>

## <span data-ttu-id="e0663-205">出力</span><span class="sxs-lookup"><span data-stu-id="e0663-205">OUTPUTS</span></span>

### <span data-ttu-id="e0663-206">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="e0663-206">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="e0663-207">既定では、は `Set-Service` オブジェクトを返しません。</span><span class="sxs-lookup"><span data-stu-id="e0663-207">By default, `Set-Service` doesn't return any objects.</span></span> <span data-ttu-id="e0663-208">**PassThru** パラメーターを使用して、 **ServiceController** オブジェクトを出力します。</span><span class="sxs-lookup"><span data-stu-id="e0663-208">Use the **PassThru** parameter to output a **ServiceController** object.</span></span>

## <span data-ttu-id="e0663-209">注</span><span class="sxs-lookup"><span data-stu-id="e0663-209">NOTES</span></span>

<span data-ttu-id="e0663-210">`Set-Service` 昇格されたアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0663-210">`Set-Service` requires elevated permissions.</span></span> <span data-ttu-id="e0663-211">[ **管理者として実行** ] オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0663-211">Use the **Run as administrator** option.</span></span>

<span data-ttu-id="e0663-212">`Set-Service` 現在のユーザーがサービスを管理するアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="e0663-212">`Set-Service` can only control services when the current user has permissions to manage services.</span></span> <span data-ttu-id="e0663-213">コマンドが正常に動作しない場合は、必要なアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0663-213">If a command doesn't work correctly, you might not have the required permissions.</span></span>

<span data-ttu-id="e0663-214">サービスのサービス名または表示名を検索するには、を使用 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="e0663-214">To find a service's service name or display name, use `Get-Service`.</span></span> <span data-ttu-id="e0663-215">サービス名は [ **名前** ] 列に、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0663-215">The service names are in the **Name** column and the display names are in the **DisplayName** column.</span></span>

## <span data-ttu-id="e0663-216">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e0663-216">RELATED LINKS</span></span>

[<span data-ttu-id="e0663-217">Get-Service</span><span class="sxs-lookup"><span data-stu-id="e0663-217">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="e0663-218">New-Service</span><span class="sxs-lookup"><span data-stu-id="e0663-218">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="e0663-219">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="e0663-219">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="e0663-220">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="e0663-220">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="e0663-221">Start-Service</span><span class="sxs-lookup"><span data-stu-id="e0663-221">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="e0663-222">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="e0663-222">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="e0663-223">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="e0663-223">Suspend-Service</span></span>](Suspend-Service.md)
