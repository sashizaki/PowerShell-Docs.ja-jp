---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Service
ms.openlocfilehash: 0c007f1becd7364806cfd47e18cf05995b81e0f7
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215403"
---
# <span data-ttu-id="11cc1-103">Get-Service</span><span class="sxs-lookup"><span data-stu-id="11cc1-103">Get-Service</span></span>

## <span data-ttu-id="11cc1-104">概要</span><span class="sxs-lookup"><span data-stu-id="11cc1-104">SYNOPSIS</span></span>
<span data-ttu-id="11cc1-105">ローカルまたはリモート コンピューター上のサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-105">Gets the services on a local or remote computer.</span></span>

## <span data-ttu-id="11cc1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="11cc1-106">SYNTAX</span></span>

### <span data-ttu-id="11cc1-107">既定値 (既定値)</span><span class="sxs-lookup"><span data-stu-id="11cc1-107">Default (Default)</span></span>

```
Get-Service [[-Name] <String[]>] [-ComputerName <String[]>] [-DependentServices] [-RequiredServices]
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="11cc1-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="11cc1-108">DisplayName</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] -DisplayName <String[]>
 [-Include <String[]>] [-Exclude <String[]>] [<CommonParameters>]
```

### <span data-ttu-id="11cc1-109">InputObject</span><span class="sxs-lookup"><span data-stu-id="11cc1-109">InputObject</span></span>

```
Get-Service [-ComputerName <String[]>] [-DependentServices] [-RequiredServices] [-Include <String[]>]
 [-Exclude <String[]>] [-InputObject <ServiceController[]>] [<CommonParameters>]
```

## <span data-ttu-id="11cc1-110">Description</span><span class="sxs-lookup"><span data-stu-id="11cc1-110">DESCRIPTION</span></span>

<span data-ttu-id="11cc1-111">**Get Service** コマンドレットは、サービスの実行と停止を含む、ローカルコンピューターまたはリモートコンピューター上のサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-111">The **Get-Service** cmdlet gets objects that represent the services on a local computer or on a remote computer, including running and stopped services.</span></span>

<span data-ttu-id="11cc1-112">サービス名またはサービスの表示名を指定して、特定のサービスのみを取得するようにこのコマンドレットに指示することも、このコマンドレットにサービスオブジェクトをパイプ処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-112">You can direct this cmdlet to get only particular services by specifying the service name or the display name of the services, or you can pipe service objects to this cmdlet.</span></span>

## <span data-ttu-id="11cc1-113">例</span><span class="sxs-lookup"><span data-stu-id="11cc1-113">EXAMPLES</span></span>

### <span data-ttu-id="11cc1-114">例 1: コンピューター上のすべてのサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="11cc1-114">Example 1: Get all services on the computer</span></span>

```powershell
Get-Service
```

<span data-ttu-id="11cc1-115">このコマンドは、コンピューター上のすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-115">This command gets all of the services on the computer.</span></span>
<span data-ttu-id="11cc1-116">入力した場合と同じように動作し `Get-Service *` ます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-116">It behaves as though you typed `Get-Service *`.</span></span>
<span data-ttu-id="11cc1-117">既定では、各サービスの状態、サービス名、表示名が表示されます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-117">The default display shows the status, service name, and display name of each service.</span></span>

### <span data-ttu-id="11cc1-118">例 2: 検索文字列で始まるサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="11cc1-118">Example 2: Get services that begin with a search string</span></span>

```powershell
Get-Service "wmi*"
```

<span data-ttu-id="11cc1-119">このコマンドは、WMI で始まるサービス名 (Windows Management Instrumentation の頭字語) を使用してサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-119">This command retrieves services with service names that begin with WMI (the acronym for Windows Management Instrumentation).</span></span>

### <span data-ttu-id="11cc1-120">例 3: 検索文字列を含むサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="11cc1-120">Example 3: Display services that include a search string</span></span>

```powershell
Get-Service -Displayname "*network*"
```

<span data-ttu-id="11cc1-121">このコマンドは、"network" という単語を含む表示名を持つサービスを表示します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-121">This command displays services with a display name that includes the word network.</span></span>
<span data-ttu-id="11cc1-122">表示名を検索することにより、xmlprov (Network Provisioning Service) のようにサービス名に "Net" が含まれていない場合でも、ネットワーク関連のサービスを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-122">Searching the display name finds network-related services even when the service name does not include "Net", such as xmlprov, the Network Provisioning Service.</span></span>

### <span data-ttu-id="11cc1-123">例 4: 検索文字列と除外で始まるサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="11cc1-123">Example 4: Get services that begin with a search string and an exclusion</span></span>

```powershell
Get-Service -Name "win*" -Exclude "WinRM"
```

<span data-ttu-id="11cc1-124">これらのコマンドは、WinRM サービスを除き、サービス名が win で始まるサービスだけを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-124">These commands get only the services with service names that begin with win, except for the WinRM service.</span></span>

### <span data-ttu-id="11cc1-125">例 5: 現在アクティブなサービスを表示する</span><span class="sxs-lookup"><span data-stu-id="11cc1-125">Example 5: Display services that are currently active</span></span>

```powershell
Get-Service | Where-Object {$_.Status -eq "Running"}
```

<span data-ttu-id="11cc1-126">このコマンドは、現在アクティブなサービスのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-126">This command displays only the services that are currently active.</span></span>
<span data-ttu-id="11cc1-127">この例では、 **Get Service** コマンドレットを使用して、コンピューター上のすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-127">It uses the **Get-Service** cmdlet to get all of the services on the computer.</span></span>
<span data-ttu-id="11cc1-128">パイプライン演算子 (|) は、結果を Where-Object コマンドレットに渡します。このコマンドレットは、Status プロパティが Running であるサービスのみを選択します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-128">The pipeline operator (|) passes the results to the Where-Object cmdlet, which selects only the services with a Status property that equals Running.</span></span>

<span data-ttu-id="11cc1-129">Status は、サービス オブジェクトの 1 つのプロパティにすぎません。</span><span class="sxs-lookup"><span data-stu-id="11cc1-129">Status is only one property of service objects.</span></span>
<span data-ttu-id="11cc1-130">すべてのプロパティを表示するには、「」と入力 `Get-Service | Get-Member` します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-130">To see all of the properties, type `Get-Service | Get-Member`.</span></span>

### <span data-ttu-id="11cc1-131">例 6: リモートコンピューター上のサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="11cc1-131">Example 6: Get the services on a remote computer</span></span>

```powershell
Get-Service -ComputerName "Server02"
```

<span data-ttu-id="11cc1-132">このコマンドは、Server02 リモート コンピューター上のサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-132">This command gets the services on the Server02 remote computer.</span></span>

<span data-ttu-id="11cc1-133">**Get Service** の *ComputerName* パラメーターは windows powershell リモート処理を使用しないため、コンピューターが windows powershell のリモート処理用に構成されていない場合でも、このパラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-133">Because the *ComputerName* parameter of **Get-Service** does not use Windows PowerShell remoting, you can use this parameter even if the computer is not configured for remoting in Windows PowerShell.</span></span>

### <span data-ttu-id="11cc1-134">例 7: 依存サービスを持つローカルコンピューター上のサービスを一覧表示する</span><span class="sxs-lookup"><span data-stu-id="11cc1-134">Example 7: List the services on the local computer that have dependent services</span></span>

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

<span data-ttu-id="11cc1-135">最初のコマンドは、 **Get Service** コマンドレットを使用して、コンピューター上のサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-135">The first command uses the **Get-Service** cmdlet to get the services on the computer.</span></span>
<span data-ttu-id="11cc1-136">パイプライン演算子 (|) に **より** 、サービスが where-object コマンドレットに送信され、 **dependentservices** プロパティが null でないサービスが選択されます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-136">A pipeline operator (|) sends the services to the **Where-Object** cmdlet, which selects the services whose **DependentServices** property is not null.</span></span>

<span data-ttu-id="11cc1-137">もう一つのパイプライン演算子は、結果を Format-List コマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-137">Another pipeline operator sends the results to the Format-List cmdlet.</span></span>
<span data-ttu-id="11cc1-138">このコマンドは、 *Property* パラメーターを使用してサービスの名前、依存サービスの名前、および各サービスに依存するサービスの数を表示する計算されたプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-138">The command uses its *Property* parameter to display the name of the service, the name of the dependent services, and a calculated property that displays the number of dependent services that each service has.</span></span>

### <span data-ttu-id="11cc1-139">例 8: プロパティ値によってサービスを並べ替える</span><span class="sxs-lookup"><span data-stu-id="11cc1-139">Example 8: Sort services by property value</span></span>

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

<span data-ttu-id="11cc1-140">このコマンドは、 **Status** プロパティの値によってサービスを昇順に並べ替えると、サービスを実行する前に停止したサービスが表示されることを示しています。</span><span class="sxs-lookup"><span data-stu-id="11cc1-140">This command shows that when you sort services in ascending order by the value of their **Status** property, stopped services appear before running services.</span></span>
<span data-ttu-id="11cc1-141">これは、Status の値が列挙型であり、Stopped の値が1で、実行中の値が4であるために発生します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-141">This happens because the value of Status is an enumeration, in which Stopped has a value of 1, and Running has a value of 4.</span></span>

<span data-ttu-id="11cc1-142">最初に実行中のサービスを一覧表示するには、Sort-Object コマンドレットの *降順* のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-142">To list running services first, use the *Descending* parameter of the Sort-Object cmdlet.</span></span>

### <span data-ttu-id="11cc1-143">例 9: 複数のコンピューター上のサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="11cc1-143">Example 9: Get services on multiple computers</span></span>

```powershell
Get-Service -Name "WinRM" -ComputerName "localhost", "Server01", "Server02" |
 Format-Table -Property MachineName, Status, Name, DisplayName -auto
```

```Output
MachineName    Status  Name  DisplayName
------------   ------  ----  -----------
localhost      Running WinRM Windows Remote Management (WS-Management)
Server01       Running WinRM Windows Remote Management (WS-Management)
Server02       Running WinRM Windows Remote Management (WS-Management)
```

<span data-ttu-id="11cc1-144">このコマンドは、 **Get Service** コマンドレットを使用して、2台のリモートコンピューターとローカルコンピューター ("localhost") で Get-Service Winrm コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-144">This command uses the **Get-Service** cmdlet to run a Get-Service Winrm command on two remote computers and the local computer ("localhost").</span></span>

<span data-ttu-id="11cc1-145">コマンドはリモートコンピューター上で実行され、結果はローカルコンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-145">The command runs on the remote computers, and the results are returned to the local computer.</span></span>
<span data-ttu-id="11cc1-146">パイプライン演算子 (|) によって結果が **Format table** コマンドレットに送信され、サービスがテーブルとして書式設定されます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-146">A pipeline operator (|) sends the results to the **Format-Table** cmdlet, which formats the services as a table.</span></span>
<span data-ttu-id="11cc1-147">**Format table** コマンドでは、 *property* パラメーターを使用して、 **MachineName** プロパティを含む、テーブルに表示されるプロパティを指定します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-147">The **Format-Table** command uses the *Property* parameter to specify the properties displayed in the table, including the **MachineName** property.</span></span>

### <span data-ttu-id="11cc1-148">例 10: サービスの依存サービスを取得する</span><span class="sxs-lookup"><span data-stu-id="11cc1-148">Example 10: Get the dependent services of a service</span></span>

```powershell
Get-Service "WinRM" -RequiredServices
```

<span data-ttu-id="11cc1-149">このコマンドは、WinRM サービスが必要とするサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-149">This command gets the services that the WinRM service requires.</span></span>

<span data-ttu-id="11cc1-150">このコマンドは、サービスの **ServicesDependedOn** プロパティの値を返します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-150">The command returns the value of the **ServicesDependedOn** property of the service.</span></span>

### <span data-ttu-id="11cc1-151">例 11: パイプライン演算子を使用してサービスを取得する</span><span class="sxs-lookup"><span data-stu-id="11cc1-151">Example 11: Get a service through the pipeline operator</span></span>

```powershell
"WinRM" | Get-Service
```

<span data-ttu-id="11cc1-152">このコマンドは、ローカル コンピューター上の WinRM サービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-152">This command gets the WinRM service on the local computer.</span></span>
<span data-ttu-id="11cc1-153">この例では、サービス名の文字列 (引用符で囲まれている) を **Get service** にパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-153">This example shows that you can pipe a service name string (enclosed in quotation marks) to **Get-Service** .</span></span>

## <span data-ttu-id="11cc1-154">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="11cc1-154">PARAMETERS</span></span>

### <span data-ttu-id="11cc1-155">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="11cc1-155">-ComputerName</span></span>

<span data-ttu-id="11cc1-156">指定されたコンピューターで実行されているサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-156">Gets the services running on the specified computers.</span></span>
<span data-ttu-id="11cc1-157">既定値はローカル コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="11cc1-157">The default is the local computer.</span></span>

<span data-ttu-id="11cc1-158">リモートコンピューターの NetBIOS 名、IP アドレス、または完全修飾ドメイン名 (FQDN) を入力します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-158">Type the NetBIOS name, an IP address, or a fully qualified domain name (FQDN) of a remote computer.</span></span>
<span data-ttu-id="11cc1-159">ローカルコンピューターを指定するには、コンピューター名、ドット (.)、または localhost を入力します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-159">To specify the local computer, type the computer name, a dot (.), or localhost.</span></span>

<span data-ttu-id="11cc1-160">このパラメーターは、Windows PowerShell リモート処理に依存しません。</span><span class="sxs-lookup"><span data-stu-id="11cc1-160">This parameter does not rely on Windows PowerShell remoting.</span></span>
<span data-ttu-id="11cc1-161">コンピューターがリモートコマンドを実行するように構成されていない場合でも、 **Get Service** の *ComputerName* パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-161">You can use the *ComputerName* parameter of **Get-Service** even if your computer is not configured to run remote commands.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="11cc1-162">-DependentServices</span><span class="sxs-lookup"><span data-stu-id="11cc1-162">-DependentServices</span></span>

<span data-ttu-id="11cc1-163">このコマンドレットが、指定されたサービスに依存するサービスのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-163">Indicates that this cmdlet gets only the services that depend upon the specified service.</span></span>

<span data-ttu-id="11cc1-164">既定では、このコマンドレットはすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-164">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: DS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="11cc1-165">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="11cc1-165">-DisplayName</span></span>

<span data-ttu-id="11cc1-166">取得するサービスの表示名を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-166">Specifies, as a string array, the display names of services to be retrieved.</span></span>
<span data-ttu-id="11cc1-167">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-167">Wildcards are permitted.</span></span>
<span data-ttu-id="11cc1-168">既定では、このコマンドレットは、コンピューター上のすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-168">By default, this cmdlet gets all services on the computer.</span></span>

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

### <span data-ttu-id="11cc1-169">-除外</span><span class="sxs-lookup"><span data-stu-id="11cc1-169">-Exclude</span></span>

<span data-ttu-id="11cc1-170">このコマンドレットによって操作から除外される1つ以上のサービスを、文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-170">Specifies, as a string array, a service or services that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="11cc1-171">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-171">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="11cc1-172">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-172">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="11cc1-173">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-173">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="11cc1-174">-Include</span><span class="sxs-lookup"><span data-stu-id="11cc1-174">-Include</span></span>

<span data-ttu-id="11cc1-175">このコマンドレットによって操作に含まれる1つ以上のサービスを文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-175">Specifies, as a string array, a service or services that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="11cc1-176">このパラメーターの値は、 *Name* パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-176">The value of this parameter qualifies the *Name* parameter.</span></span>
<span data-ttu-id="11cc1-177">「s\*」などの名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-177">Enter a name element or pattern, such as "s\*".</span></span>
<span data-ttu-id="11cc1-178">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-178">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="11cc1-179">-InputObject</span><span class="sxs-lookup"><span data-stu-id="11cc1-179">-InputObject</span></span>

<span data-ttu-id="11cc1-180">取得するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-180">Specifies **ServiceController** objects representing the services to be retrieved.</span></span>
<span data-ttu-id="11cc1-181">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-181">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>
<span data-ttu-id="11cc1-182">このコマンドレットには、サービスオブジェクトをパイプ処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-182">You can also pipe a service object to this cmdlet.</span></span>

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

### <span data-ttu-id="11cc1-183">-Name</span><span class="sxs-lookup"><span data-stu-id="11cc1-183">-Name</span></span>

<span data-ttu-id="11cc1-184">取得するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-184">Specifies the service names of services to be retrieved.</span></span>
<span data-ttu-id="11cc1-185">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-185">Wildcards are permitted.</span></span>
<span data-ttu-id="11cc1-186">既定では、このコマンドレットは、コンピューター上のすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-186">By default, this cmdlet gets all of the services on the computer.</span></span>

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

### <span data-ttu-id="11cc1-187">-RequiredServices</span><span class="sxs-lookup"><span data-stu-id="11cc1-187">-RequiredServices</span></span>

<span data-ttu-id="11cc1-188">このコマンドレットが、このサービスが必要とするサービスのみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-188">Indicates that this cmdlet gets only the services that this service requires.</span></span>

<span data-ttu-id="11cc1-189">このパラメーターは、サービスの **ServicesDependedOn** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-189">This parameter gets the value of the **ServicesDependedOn** property of the service.</span></span>
<span data-ttu-id="11cc1-190">既定では、このコマンドレットはすべてのサービスを取得します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-190">By default, this cmdlet gets all services.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: SDO, ServicesDependedOn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="11cc1-191">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="11cc1-191">CommonParameters</span></span>

<span data-ttu-id="11cc1-192">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="11cc1-192">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="11cc1-193">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11cc1-193">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="11cc1-194">入力</span><span class="sxs-lookup"><span data-stu-id="11cc1-194">INPUTS</span></span>

### <span data-ttu-id="11cc1-195">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="11cc1-195">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="11cc1-196">このコマンドレットには、サービスオブジェクトまたはサービス名をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-196">You can pipe a service object or a service name to this cmdlet.</span></span>

## <span data-ttu-id="11cc1-197">出力</span><span class="sxs-lookup"><span data-stu-id="11cc1-197">OUTPUTS</span></span>

### <span data-ttu-id="11cc1-198">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="11cc1-198">System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="11cc1-199">このコマンドレットは、コンピューター上のサービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-199">This cmdlet returns objects that represent the services on the computer.</span></span>

## <span data-ttu-id="11cc1-200">注</span><span class="sxs-lookup"><span data-stu-id="11cc1-200">NOTES</span></span>

<span data-ttu-id="11cc1-201">**Get Service** は、その組み込みエイリアスである "gsv" で参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-201">You can also refer to **Get-Service** by its built-in alias, "gsv".</span></span> <span data-ttu-id="11cc1-202">詳細については、「about_Aliases」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11cc1-202">For more information, see about_Aliases.</span></span>

<span data-ttu-id="11cc1-203">このコマンドレットは、現在のユーザーがサービスを表示するアクセス許可を持っている場合にのみ、サービスを表示できます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-203">This cmdlet can display services only when the current user has permission to see them.</span></span>
<span data-ttu-id="11cc1-204">このコマンドレットでサービスが表示されない場合は、サービスを表示するアクセス許可がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11cc1-204">If this cmdlet does not display services, you might not have permission to see them.</span></span>

<span data-ttu-id="11cc1-205">システム上の各サービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="11cc1-205">To find the service name and display name of each service on your system, type `Get-Service`.</span></span>
<span data-ttu-id="11cc1-206">サービス名は [Name] 欄に表示され、表示名は [DisplayName] 欄に表示されます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-206">The service names appear in the Name column, and the display names appear in the DisplayName column.</span></span>

<span data-ttu-id="11cc1-207">Status の値により昇順に並べ替えると、状態が "Stopped (停止済み)" のサービスは "Running (実行中)" のサービスの前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-207">When you sort in ascending order by status value, "Stopped" services appear before "Running" services.</span></span>
<span data-ttu-id="11cc1-208">サービスの Status プロパティは、状態の名前が整数値を表す列挙値です。</span><span class="sxs-lookup"><span data-stu-id="11cc1-208">The Status property of a service is an enumerated value in which the names of the statuses represent integer values.</span></span>
<span data-ttu-id="11cc1-209">並べ替えは名前ではなく整数値に基づいて行われます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-209">The sort is based on the integer value, not the name.</span></span>
<span data-ttu-id="11cc1-210">"Stopped (停止済み)" の値は "1" であり、"Running (実行中)" の値は "4" であるため、"Running" は "Stopped" の前に表示されます。</span><span class="sxs-lookup"><span data-stu-id="11cc1-210">"Running" appears before "Stopped" because "Stopped" has a value of "1", and "Running" has a value of "4".</span></span>

## <span data-ttu-id="11cc1-211">関連リンク</span><span class="sxs-lookup"><span data-stu-id="11cc1-211">RELATED LINKS</span></span>

[<span data-ttu-id="11cc1-212">New-Service</span><span class="sxs-lookup"><span data-stu-id="11cc1-212">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="11cc1-213">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="11cc1-213">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="11cc1-214">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="11cc1-214">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="11cc1-215">Set-Service</span><span class="sxs-lookup"><span data-stu-id="11cc1-215">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="11cc1-216">Start-Service</span><span class="sxs-lookup"><span data-stu-id="11cc1-216">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="11cc1-217">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="11cc1-217">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="11cc1-218">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="11cc1-218">Suspend-Service</span></span>](Suspend-Service.md)
