---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: c27dac11cdd8ebbf1705ac3bba0c0aa5147d4fa8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605173"
---
# <span data-ttu-id="f2c21-102">Get-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-102">Get-Service</span></span>

## <span data-ttu-id="f2c21-103">概要</span><span class="sxs-lookup"><span data-stu-id="f2c21-103">SYNOPSIS</span></span>
<span data-ttu-id="f2c21-104">コンピューター上のサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-104">Gets the services on the computer.</span></span>

## <span data-ttu-id="f2c21-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f2c21-105">SYNTAX</span></span>

### <span data-ttu-id="f2c21-106">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="f2c21-106">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f2c21-107">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f2c21-107">DisplayName</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="f2c21-108">InputObject</span><span class="sxs-lookup"><span data-stu-id="f2c21-108">InputObject</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="f2c21-109">Description</span><span class="sxs-lookup"><span data-stu-id="f2c21-109">DESCRIPTION</span></span>

<span data-ttu-id="f2c21-110">`Get-Service`コマンドレットは、コンピューター上のサービスを表すオブジェクトを取得します。これには、サービスの実行と停止も含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-110">The `Get-Service` cmdlet gets objects that represent the services on a computer, including running and stopped services.</span></span> <span data-ttu-id="f2c21-111">既定では、 `Get-Service` パラメーターを指定せずにを実行すると、すべてのローカルコンピューターのサービスが返されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-111">By default, when `Get-Service` is run without parameters, all the local computer's services are returned.</span></span>

<span data-ttu-id="f2c21-112">サービス名またはサービスの表示名を指定して、特定のサービスのみを取得するようにこのコマンドレットに指示することも、このコマンドレットにサービスオブジェクトをパイプ処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="f2c21-113">例</span><span class="sxs-lookup"><span data-stu-id="f2c21-113">EXAMPLES</span></span>

### <span data-ttu-id="f2c21-114">例 1: コンピューター上のすべてのサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="f2c21-114">Example 1: Get all services on the computer</span></span>

<span data-ttu-id="f2c21-115">この例では、コンピューター上のすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-115">This example gets all of the services on the computer.</span></span> <span data-ttu-id="f2c21-116">入力した場合と同じように動作し `Get-Service *` ます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-116">It behaves as though you typed `Get-Service *`.</span></span> <span data-ttu-id="f2c21-117">既定では、各サービスの状態、サービス名、表示名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-117">The default display shows the status, service name, and display name of each service.</span></span>

```powershell
Get-Service
```

### <span data-ttu-id="f2c21-118">例 2: 検索文字列で始まるサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="f2c21-118">Example 2: Get services that begin with a search string</span></span>

<span data-ttu-id="f2c21-119">この例では、サービス名が WMI (Windows Management Instrumentation) で始まるサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-119">This example retrieves services with service names that begin with WMI (Windows Management Instrumentation).</span></span>

```powershell
Get-Service "wmi*"
```

### <span data-ttu-id="f2c21-120">例 3: 検索文字列を含むサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="f2c21-120">Example 3: Display services that include a search string</span></span>

<span data-ttu-id="f2c21-121">この例では、"network" という単語を含む表示名を持つサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-121">This example displays services with a display name that includes the word network.</span></span> <span data-ttu-id="f2c21-122">サービス名にネットワーク (xmlprov など) が含まれていない場合でも、表示名を検索するとネットワークに関連するサービスが検出されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-122">Searching the display name finds network-related services even when the service name doesn't include Net, such as xmlprov, the Network Provisioning Service.</span></span>

```powershell
Get-Service -Displayname "*network*"
```

### <span data-ttu-id="f2c21-123">例 4: 検索文字列と除外で始まるサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="f2c21-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

<span data-ttu-id="f2c21-124">この例では、WinRM サービスを除き、サービス名が **win** で始まるサービスのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-124">This example only gets the services with service names that begin with **win**, except for the WinRM service.</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### <span data-ttu-id="f2c21-125">例 5: 現在アクティブなサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="f2c21-125">Example 5: Display services that are currently active</span></span>

<span data-ttu-id="f2c21-126">この例では、状態が Running のサービスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-126">This example displays only the services with a status of Running.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="f2c21-127">`Get-Service` コンピューター上のすべてのサービスを取得し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-127">`Get-Service` gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="f2c21-128">`Where-Object`コマンドレットは、 **Status** プロパティが Running で実行されているサービスのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-128">The `Where-Object` cmdlet, selects only the services with a **Status** property that equals Running.</span></span>

<span data-ttu-id="f2c21-129">Status は、サービス オブジェクトの 1 つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="f2c21-129">Status is only one property of service objects.</span></span> <span data-ttu-id="f2c21-130">すべてのプロパティを表示するには、「」と入力 `Get-Service | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="f2c21-131">例 6: 依存サービスがあるコンピューター上のサービスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="f2c21-131">Example 6: List the services on the computer that have dependent services</span></span>

<span data-ttu-id="f2c21-132">この例では、依存サービスを持つサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-132">This example gets services that have dependent services.</span></span>

```powershell
Get-Service |
  Where-Object {$_.DependentServices} |
    Format-List -Property Name, DependentServices, @{
      Label="NoOfDependentServices"; Expression={$_.dependentservices.count}
    }
```

```Output
Name                  : AudioEndpointBuilder
DependentServices     : {AudioSrv}
NoOfDependentServices : 1

Name                  : Dhcp
DependentServices     : {WinHttpAutoProxySvc}
NoOfDependentServices : 1
...
```

<span data-ttu-id="f2c21-133">`Get-Service`コマンドレットは、コンピューター上のすべてのサービスを取得し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-133">The `Get-Service` cmdlet gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="f2c21-134">`Where-Object`コマンドレットでは、 **dependentservices** プロパティが null ではないサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-134">The `Where-Object` cmdlet selects the services whose **DependentServices** property isn't null.</span></span>

<span data-ttu-id="f2c21-135">結果はパイプラインからコマンドレットに送信され `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-135">The results are sent down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="f2c21-136">**Property** パラメーターには、サービスの名前、依存サービスの名前、および各サービスの依存サービスの数を表示する計算されたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-136">The **Property** parameter displays the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services for each service.</span></span>

### <span data-ttu-id="f2c21-137">例 7: プロパティ値によってサービスを並べ替える</span><span class="sxs-lookup"><span data-stu-id="f2c21-137">Example 7: Sort services by property value</span></span>

<span data-ttu-id="f2c21-138">この例では、 **Status** プロパティの値によってサービスを昇順に並べ替えると、サービスを実行する前に停止したサービスが表示されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="f2c21-138">This example shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span> <span data-ttu-id="f2c21-139">この理由は、 **Status** の値が列挙型であり、Stopped の値が1で、実行中の値が4であるためです。</span><span class="sxs-lookup"><span data-stu-id="f2c21-139">The reason is because the value of **Status** is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="f2c21-140">詳細については、「 [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c21-140">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="f2c21-141">最初に実行中のサービスを一覧表示するには、コマンドレットの **降順** のパラメーターを使用し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-141">To list running services first, use the **Descending** parameter of the `Sort-Object` cmdlet.</span></span>

```powershell
Get-Service "s*" | Sort-Object status
```

```Output
Status   Name               DisplayName
------   ----               -----------
Stopped  stisvc             Windows Image Acquisition (WIA)
Stopped  SwPrv              MS Software Shadow Copy Provider
Stopped  SysmonLog          Performance Logs and Alerts
Running  Spooler            Print Spooler
Running  srservice          System Restore Service
Running  SSDPSRV            SSDP Discovery Service
Running  ShellHWDetection   Shell Hardware Detection
Running  Schedule           Task Scheduler
Running  SCardSvr           Smart Card
Running  SamSs              Security Accounts Manager
Running  SharedAccess       Windows Firewall/Internet Connectio...
Running  SENS               System Event Notification
Running  seclogon           Secondary Logon
```

### <span data-ttu-id="f2c21-142">例 8: サービスの依存サービスを取得する</span><span class="sxs-lookup"><span data-stu-id="f2c21-142">Example 8: Get the dependent services of a service</span></span>

<span data-ttu-id="f2c21-143">この例では、WinRM サービスが必要とするサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-143">This example gets the services that the WinRM service requires.</span></span> <span data-ttu-id="f2c21-144">サービスの **ServicesDependedOn** プロパティの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-144">The value of the service's **ServicesDependedOn** property is returned.</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

### <span data-ttu-id="f2c21-145">例 9: パイプライン演算子を使用してサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="f2c21-145">Example 9: Get a service through the pipeline operator</span></span>

<span data-ttu-id="f2c21-146">この例では、ローカルコンピューター上の WinRM サービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-146">This example gets the WinRM service on the local computer.</span></span> <span data-ttu-id="f2c21-147">サービス名の文字列は、引用符で囲まれて、パイプラインの下に送信され `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-147">The service name string, enclosed in quotation marks, is sent down the pipeline to `Get-Service`.</span></span>

```powershell
"WinRM" | Get-Service
```

## <span data-ttu-id="f2c21-148">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f2c21-148">PARAMETERS</span></span>

### <span data-ttu-id="f2c21-149">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="f2c21-149">-DependentServices</span></span>

<span data-ttu-id="f2c21-150">このコマンドレットが、指定されたサービスに依存するサービスのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-150">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f2c21-151">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="f2c21-151">-DisplayName</span></span>

<span data-ttu-id="f2c21-152">取得するサービスの表示名を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-152">Specifies, as a string array, the display names of services to be retrieved.</span></span> <span data-ttu-id="f2c21-153">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-153">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: DisplayName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f2c21-154">-除外</span><span class="sxs-lookup"><span data-stu-id="f2c21-154">-Exclude</span></span>

<span data-ttu-id="f2c21-155">このコマンドレットによって操作から除外される1つ以上のサービスを、文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-155">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="f2c21-156">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-156">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="f2c21-157">などの名前要素またはパターンを入力し `s*` ます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-157">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="f2c21-158">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-158">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f2c21-159">-Include</span><span class="sxs-lookup"><span data-stu-id="f2c21-159">-Include</span></span>

<span data-ttu-id="f2c21-160">このコマンドレットによって操作に含まれる1つ以上のサービスを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-160">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span> <span data-ttu-id="f2c21-161">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-161">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="f2c21-162">などの名前要素またはパターンを入力し `s*` ます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-162">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="f2c21-163">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-163">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f2c21-164">-InputObject</span><span class="sxs-lookup"><span data-stu-id="f2c21-164">-InputObject</span></span>

<span data-ttu-id="f2c21-165">取得するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-165">Specifies **ServiceController** objects representing the services to be retrieved.</span></span> <span data-ttu-id="f2c21-166">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-166">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="f2c21-167">このコマンドレットには、サービスオブジェクトをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-167">You can pipe a service object to this cmdlet.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="f2c21-168">-Name</span><span class="sxs-lookup"><span data-stu-id="f2c21-168">-Name</span></span>

<span data-ttu-id="f2c21-169">取得するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-169">Specifies the service names of services to be retrieved.</span></span> <span data-ttu-id="f2c21-170">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-170">Wildcards are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="f2c21-171">-RequiredServices</span><span class="sxs-lookup"><span data-stu-id="f2c21-171">-RequiredServices</span></span>

<span data-ttu-id="f2c21-172">このコマンドレットが、このサービスが必要とするサービスのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-172">Indicates that this cmdlet gets only the services that this service requires.</span></span> <span data-ttu-id="f2c21-173">このパラメーターは、サービスの **ServicesDependedOn** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-173">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="f2c21-174">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f2c21-174">CommonParameters</span></span>

<span data-ttu-id="f2c21-175">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f2c21-175">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f2c21-176">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c21-176">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f2c21-177">入力</span><span class="sxs-lookup"><span data-stu-id="f2c21-177">INPUTS</span></span>

### <span data-ttu-id="f2c21-178">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="f2c21-178">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="f2c21-179">このコマンドレットには、サービスオブジェクトまたはサービス名をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-179">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="f2c21-180">出力</span><span class="sxs-lookup"><span data-stu-id="f2c21-180">OUTPUTS</span></span>

### <span data-ttu-id="f2c21-181">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="f2c21-181">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="f2c21-182">このコマンドレットは、コンピューター上のサービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-182">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="f2c21-183">注</span><span class="sxs-lookup"><span data-stu-id="f2c21-183">NOTES</span></span>

<span data-ttu-id="f2c21-184">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-184">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="f2c21-185">PowerShell 6.0 以降では、 **ServiceController** オブジェクトに、 **UserName**、 **Description**、 **delayedautostart**、 **binaryp name**、および **startuptype** というプロパティが追加されています。</span><span class="sxs-lookup"><span data-stu-id="f2c21-185">Beginning in PowerShell 6.0, the following properties are added to the **ServiceController** objects: **UserName**, **Description**, **DelayedAutoStart**, **BinaryPathName**, and **StartupType** .</span></span>

<span data-ttu-id="f2c21-186">また、組み込みエイリアスであるを参照することもでき `Get-Service` `gsv` ます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-186">You can also refer to `Get-Service` by its built-in alias, `gsv`.</span></span> <span data-ttu-id="f2c21-187">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c21-187">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="f2c21-188">このコマンドレットは、現在のユーザーがサービスを表示するアクセス許可を持っている場合にのみ、サービスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-188">This cmdlet can display services only when the current user has permission to see them.</span></span> <span data-ttu-id="f2c21-189">このコマンドレットでサービスが表示されない場合は、サービスを表示するアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2c21-189">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="f2c21-190">システム上の各サービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-190">To find the service name and display name of each service on your system, type `Get-Service`.</span></span> <span data-ttu-id="f2c21-191">サービス名は [名前] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-191">The service names appear in the Name column, and the display names appear in the **DisplayName** column.</span></span>

<span data-ttu-id="f2c21-192">**Status** プロパティの値によって昇順に並べ替えた場合は、サービスを実行する前に停止したサービスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-192">When you sort in ascending order by the **Status** property's value, Stopped services appear before Running services.</span></span> <span data-ttu-id="f2c21-193">サービスの **status** プロパティは列挙値であり、状態名は整数値を表します。</span><span class="sxs-lookup"><span data-stu-id="f2c21-193">The service's **Status** property is an enumerated value and the status names represent integer values.</span></span> <span data-ttu-id="f2c21-194">並べ替え順序は、名前ではなく整数値に基づいています。</span><span class="sxs-lookup"><span data-stu-id="f2c21-194">The sort order is based on the integer value, not the name.</span></span> <span data-ttu-id="f2c21-195">Stopped の値が1で、実行中の値が4であるため、[停止] が前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2c21-195">Stopped appears before because Running because Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="f2c21-196">詳細については、「 [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2c21-196">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="f2c21-197">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f2c21-197">RELATED LINKS</span></span>

[<span data-ttu-id="f2c21-198">New-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-198">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="f2c21-199">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-199">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="f2c21-200">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-200">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="f2c21-201">Set-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-201">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="f2c21-202">Start-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-202">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="f2c21-203">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-203">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="f2c21-204">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-204">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="f2c21-205">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="f2c21-205">Remove-Service</span></span>](Remove-Service.md)
