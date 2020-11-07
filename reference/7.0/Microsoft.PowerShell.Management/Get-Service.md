---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/30/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 15bfe1123ba005a7b326c234fad360d6d9d6cc4d
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94345733"
---
# <span data-ttu-id="104b4-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-103">Get-Service</span></span>

## <span data-ttu-id="104b4-104">概要</span><span class="sxs-lookup"><span data-stu-id="104b4-104">SYNOPSIS</span></span>
<span data-ttu-id="104b4-105">コンピューター上のサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="104b4-105">Gets the services on the computer.</span></span>

## <span data-ttu-id="104b4-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="104b4-106">SYNTAX</span></span>

### <span data-ttu-id="104b4-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="104b4-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="104b4-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="104b4-108">DisplayName</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] -DisplayName <String[]> [-Include <String[]>]
 [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="104b4-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="104b4-109">InputObject</span></span>

```
Get-Service [-DependentServices] [-RequiredServices] [-Include <String[]>] [-Exclude <String[]>]
 [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="104b4-110">Description</span><span class="sxs-lookup"><span data-stu-id="104b4-110">DESCRIPTION</span></span>

<span data-ttu-id="104b4-111">`Get-Service`コマンドレットは、コンピューター上のサービスを表すオブジェクトを取得します。これには、サービスの実行と停止も含まれます。</span><span class="sxs-lookup"><span data-stu-id="104b4-111">The `Get-Service` cmdlet gets objects that represent the services on a computer, including running and stopped services.</span></span> <span data-ttu-id="104b4-112">既定では、 `Get-Service` パラメーターを指定せずにを実行すると、すべてのローカルコンピューターのサービスが返されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-112">By default, when `Get-Service` is run without parameters, all the local computer's services are returned.</span></span>

<span data-ttu-id="104b4-113">サービス名またはサービスの表示名を指定して、特定のサービスのみを取得するようにこのコマンドレットに指示することも、このコマンドレットにサービスオブジェクトをパイプ処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="104b4-113">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="104b4-114">例</span><span class="sxs-lookup"><span data-stu-id="104b4-114">EXAMPLES</span></span>

### <span data-ttu-id="104b4-115">例 1: コンピューター上のすべてのサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="104b4-115">Example 1: Get all services on the computer</span></span>

<span data-ttu-id="104b4-116">この例では、コンピューター上のすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="104b4-116">This example gets all of the services on the computer.</span></span> <span data-ttu-id="104b4-117">入力した場合と同じように動作し `Get-Service *` ます。</span><span class="sxs-lookup"><span data-stu-id="104b4-117">It behaves as though you typed `Get-Service *`.</span></span> <span data-ttu-id="104b4-118">既定では、各サービスの状態、サービス名、表示名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-118">The default display shows the status, service name, and display name of each service.</span></span>

```powershell
Get-Service
```

### <span data-ttu-id="104b4-119">例 2: 検索文字列で始まるサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="104b4-119">Example 2: Get services that begin with a search string</span></span>

<span data-ttu-id="104b4-120">この例では、サービス名が WMI (Windows Management Instrumentation) で始まるサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="104b4-120">This example retrieves services with service names that begin with WMI (Windows Management Instrumentation).</span></span>

```powershell
Get-Service "wmi*"
```

### <span data-ttu-id="104b4-121">例 3: 検索文字列を含むサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="104b4-121">Example 3: Display services that include a search string</span></span>

<span data-ttu-id="104b4-122">この例では、"network" という単語を含む表示名を持つサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="104b4-122">This example displays services with a display name that includes the word network.</span></span> <span data-ttu-id="104b4-123">サービス名にネットワーク (xmlprov など) が含まれていない場合でも、表示名を検索するとネットワークに関連するサービスが検出されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-123">Searching the display name finds network-related services even when the service name doesn't include Net, such as xmlprov, the Network Provisioning Service.</span></span>

```powershell
Get-Service -Displayname "*network*"
```

### <span data-ttu-id="104b4-124">例 4: 検索文字列と除外で始まるサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="104b4-124">Example 4: Get services that begin with a search string and an exclusion</span></span>

<span data-ttu-id="104b4-125">この例では、WinRM サービスを除き、サービス名が **win** で始まるサービスのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="104b4-125">This example only gets the services with service names that begin with **win** , except for the WinRM service.</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

### <span data-ttu-id="104b4-126">例 5: 現在アクティブなサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="104b4-126">Example 5: Display services that are currently active</span></span>

<span data-ttu-id="104b4-127">この例では、状態が Running のサービスのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-127">This example displays only the services with a status of Running.</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="104b4-128">`Get-Service` コンピューター上のすべてのサービスを取得し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="104b4-128">`Get-Service` gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="104b4-129">`Where-Object`コマンドレットは、 **Status** プロパティが Running で実行されているサービスのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="104b4-129">The `Where-Object` cmdlet, selects only the services with a **Status** property that equals Running.</span></span>

<span data-ttu-id="104b4-130">Status は、サービス オブジェクトの 1 つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="104b4-130">Status is only one property of service objects.</span></span> <span data-ttu-id="104b4-131">すべてのプロパティを表示するには、「」と入力 `Get-Service | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="104b4-131">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="104b4-132">例 6: 依存サービスがあるコンピューター上のサービスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="104b4-132">Example 6: List the services on the computer that have dependent services</span></span>

<span data-ttu-id="104b4-133">この例では、依存サービスを持つサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="104b4-133">This example gets services that have dependent services.</span></span>

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

<span data-ttu-id="104b4-134">`Get-Service`コマンドレットは、コンピューター上のすべてのサービスを取得し、そのオブジェクトをパイプラインの下に送信します。</span><span class="sxs-lookup"><span data-stu-id="104b4-134">The `Get-Service` cmdlet gets all the services on the computer and sends the objects down the pipeline.</span></span> <span data-ttu-id="104b4-135">`Where-Object`コマンドレットでは、 **dependentservices** プロパティが null ではないサービスを選択します。</span><span class="sxs-lookup"><span data-stu-id="104b4-135">The `Where-Object` cmdlet selects the services whose **DependentServices** property isn't null.</span></span>

<span data-ttu-id="104b4-136">結果はパイプラインからコマンドレットに送信され `Format-List` ます。</span><span class="sxs-lookup"><span data-stu-id="104b4-136">The results are sent down the pipeline to the `Format-List` cmdlet.</span></span> <span data-ttu-id="104b4-137">**Property** パラメーターには、サービスの名前、依存サービスの名前、および各サービスの依存サービスの数を表示する計算されたプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-137">The **Property** parameter displays the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services for each service.</span></span>

### <span data-ttu-id="104b4-138">例 7: プロパティ値によってサービスを並べ替える</span><span class="sxs-lookup"><span data-stu-id="104b4-138">Example 7: Sort services by property value</span></span>

<span data-ttu-id="104b4-139">この例では、 **Status** プロパティの値によってサービスを昇順に並べ替えると、サービスを実行する前に停止したサービスが表示されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="104b4-139">This example shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span> <span data-ttu-id="104b4-140">この理由は、 **Status** の値が列挙型であり、Stopped の値が1で、実行中の値が4であるためです。</span><span class="sxs-lookup"><span data-stu-id="104b4-140">The reason is because the value of **Status** is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="104b4-141">詳細については、「 [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="104b4-141">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

<span data-ttu-id="104b4-142">最初に実行中のサービスを一覧表示するには、コマンドレットの **降順** のパラメーターを使用し `Sort-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="104b4-142">To list running services first, use the **Descending** parameter of the `Sort-Object` cmdlet.</span></span>

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

### <span data-ttu-id="104b4-143">例 8: サービスの依存サービスを取得する</span><span class="sxs-lookup"><span data-stu-id="104b4-143">Example 8: Get the dependent services of a service</span></span>

<span data-ttu-id="104b4-144">この例では、WinRM サービスが必要とするサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="104b4-144">This example gets the services that the WinRM service requires.</span></span> <span data-ttu-id="104b4-145">サービスの **ServicesDependedOn** プロパティの値が返されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-145">The value of the service's **ServicesDependedOn** property is returned.</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

### <span data-ttu-id="104b4-146">例 9: パイプライン演算子を使用してサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="104b4-146">Example 9: Get a service through the pipeline operator</span></span>

<span data-ttu-id="104b4-147">この例では、ローカルコンピューター上の WinRM サービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="104b4-147">This example gets the WinRM service on the local computer.</span></span> <span data-ttu-id="104b4-148">サービス名の文字列は、引用符で囲まれて、パイプラインの下に送信され `Get-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="104b4-148">The service name string, enclosed in quotation marks, is sent down the pipeline to `Get-Service`.</span></span>

```powershell
"WinRM" | Get-Service
```

## <span data-ttu-id="104b4-149">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="104b4-149">PARAMETERS</span></span>

### <span data-ttu-id="104b4-150">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="104b4-150">-DependentServices</span></span>

<span data-ttu-id="104b4-151">このコマンドレットが、指定されたサービスに依存するサービスのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="104b4-151">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

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

### <span data-ttu-id="104b4-152">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="104b4-152">-DisplayName</span></span>

<span data-ttu-id="104b4-153">取得するサービスの表示名を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="104b4-153">Specifies, as a string array, the display names of services to be retrieved.</span></span> <span data-ttu-id="104b4-154">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="104b4-154">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="104b4-155">-除外</span><span class="sxs-lookup"><span data-stu-id="104b4-155">-Exclude</span></span>

<span data-ttu-id="104b4-156">このコマンドレットによって操作から除外される1つ以上のサービスを、文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="104b4-156">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="104b4-157">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="104b4-157">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="104b4-158">などの名前要素またはパターンを入力し `s*` ます。</span><span class="sxs-lookup"><span data-stu-id="104b4-158">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="104b4-159">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="104b4-159">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="104b4-160">-Include</span><span class="sxs-lookup"><span data-stu-id="104b4-160">-Include</span></span>

<span data-ttu-id="104b4-161">このコマンドレットによって操作に含まれる1つ以上のサービスを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="104b4-161">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span> <span data-ttu-id="104b4-162">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="104b4-162">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="104b4-163">などの名前要素またはパターンを入力し `s*` ます。</span><span class="sxs-lookup"><span data-stu-id="104b4-163">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="104b4-164">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="104b4-164">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="104b4-165">-InputObject</span><span class="sxs-lookup"><span data-stu-id="104b4-165">-InputObject</span></span>

<span data-ttu-id="104b4-166">取得するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="104b4-166">Specifies **ServiceController** objects representing the services to be retrieved.</span></span> <span data-ttu-id="104b4-167">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="104b4-167">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span> <span data-ttu-id="104b4-168">このコマンドレットには、サービスオブジェクトをパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="104b4-168">You can pipe a service object to this cmdlet.</span></span>

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

### <span data-ttu-id="104b4-169">-Name</span><span class="sxs-lookup"><span data-stu-id="104b4-169">-Name</span></span>

<span data-ttu-id="104b4-170">取得するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="104b4-170">Specifies the service names of services to be retrieved.</span></span> <span data-ttu-id="104b4-171">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="104b4-171">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="104b4-172">-RequiredServices</span><span class="sxs-lookup"><span data-stu-id="104b4-172">-RequiredServices</span></span>

<span data-ttu-id="104b4-173">このコマンドレットが、このサービスが必要とするサービスのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="104b4-173">Indicates that this cmdlet gets only the services that this service requires.</span></span> <span data-ttu-id="104b4-174">このパラメーターは、サービスの **ServicesDependedOn** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="104b4-174">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>

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

### <span data-ttu-id="104b4-175">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="104b4-175">CommonParameters</span></span>

<span data-ttu-id="104b4-176">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="104b4-176">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="104b4-177">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="104b4-177">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="104b4-178">入力</span><span class="sxs-lookup"><span data-stu-id="104b4-178">INPUTS</span></span>

### <span data-ttu-id="104b4-179">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="104b4-179">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="104b4-180">このコマンドレットには、サービスオブジェクトまたはサービス名をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="104b4-180">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="104b4-181">出力</span><span class="sxs-lookup"><span data-stu-id="104b4-181">OUTPUTS</span></span>

### <span data-ttu-id="104b4-182">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="104b4-182">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="104b4-183">このコマンドレットは、コンピューター上のサービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="104b4-183">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="104b4-184">注</span><span class="sxs-lookup"><span data-stu-id="104b4-184">NOTES</span></span>

<span data-ttu-id="104b4-185">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="104b4-185">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="104b4-186">PowerShell 6.0 以降では、 **ServiceController** オブジェクトに、 **UserName** 、 **Description** 、 **delayedautostart** 、 **binaryp name** 、および **startuptype** というプロパティが追加されています。</span><span class="sxs-lookup"><span data-stu-id="104b4-186">Beginning in PowerShell 6.0, the following properties are added to the **ServiceController** objects: **UserName** , **Description** , **DelayedAutoStart** , **BinaryPathName** , and **StartupType** .</span></span>

<span data-ttu-id="104b4-187">また、組み込みエイリアスであるを参照することもでき `Get-Service` `gsv` ます。</span><span class="sxs-lookup"><span data-stu-id="104b4-187">You can also refer to `Get-Service` by its built-in alias, `gsv`.</span></span> <span data-ttu-id="104b4-188">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="104b4-188">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="104b4-189">このコマンドレットは、現在のユーザーがサービスを表示するアクセス許可を持っている場合にのみ、サービスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="104b4-189">This cmdlet can display services only when the current user has permission to see them.</span></span> <span data-ttu-id="104b4-190">このコマンドレットでサービスが表示されない場合は、サービスを表示するアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="104b4-190">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="104b4-191">システム上の各サービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="104b4-191">To find the service name and display name of each service on your system, type `Get-Service`.</span></span> <span data-ttu-id="104b4-192">サービス名は [名前] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-192">The service names appear in the Name column, and the display names appear in the **DisplayName** column.</span></span>

<span data-ttu-id="104b4-193">**Status** プロパティの値によって昇順に並べ替えた場合は、サービスを実行する前に停止したサービスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-193">When you sort in ascending order by the **Status** property's value, Stopped services appear before Running services.</span></span> <span data-ttu-id="104b4-194">サービスの **status** プロパティは列挙値であり、状態名は整数値を表します。</span><span class="sxs-lookup"><span data-stu-id="104b4-194">The service's **Status** property is an enumerated value and the status names represent integer values.</span></span> <span data-ttu-id="104b4-195">並べ替え順序は、名前ではなく整数値に基づいています。</span><span class="sxs-lookup"><span data-stu-id="104b4-195">The sort order is based on the integer value, not the name.</span></span> <span data-ttu-id="104b4-196">Stopped の値が1で、実行中の値が4であるため、[停止] が前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="104b4-196">Stopped appears before because Running because Stopped has a value of 1, and Running has a value of 4.</span></span> <span data-ttu-id="104b4-197">詳細については、「 [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="104b4-197">For more information, see [ServiceControllerStatus](/dotnet/api/system.serviceprocess.servicecontrollerstatus).</span></span>

## <span data-ttu-id="104b4-198">関連リンク</span><span class="sxs-lookup"><span data-stu-id="104b4-198">RELATED LINKS</span></span>

[<span data-ttu-id="104b4-199">New-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-199">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="104b4-200">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-200">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="104b4-201">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-201">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="104b4-202">Set-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-202">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="104b4-203">Start-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-203">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="104b4-204">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-204">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="104b4-205">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-205">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="104b4-206">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="104b4-206">Remove-Service</span></span>](Remove-Service.md)
