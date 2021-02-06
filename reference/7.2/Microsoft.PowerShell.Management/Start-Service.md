---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/start-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Service
ms.openlocfilehash: b1df4490da501111ccb44dea2645a333fdf5c27e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603235"
---
# <span data-ttu-id="a58b2-102">Start-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-102">Start-Service</span></span>

## <span data-ttu-id="a58b2-103">概要</span><span class="sxs-lookup"><span data-stu-id="a58b2-103">SYNOPSIS</span></span>
<span data-ttu-id="a58b2-104">停止しているサービスを 1 つ以上開始します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-104">Starts one or more stopped services.</span></span>

## <span data-ttu-id="a58b2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a58b2-105">SYNTAX</span></span>

### <span data-ttu-id="a58b2-106">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="a58b2-106">InputObject (Default)</span></span>

```
Start-Service [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a58b2-107">Default</span><span class="sxs-lookup"><span data-stu-id="a58b2-107">Default</span></span>

```
Start-Service [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### <span data-ttu-id="a58b2-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a58b2-108">DisplayName</span></span>

```
Start-Service [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a58b2-109">Description</span><span class="sxs-lookup"><span data-stu-id="a58b2-109">DESCRIPTION</span></span>

<span data-ttu-id="a58b2-110">`Start-Service`コマンドレットは、指定された各サービスについて、Windows サービスコントローラーに開始メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-110">The `Start-Service` cmdlet sends a start message to the Windows Service Controller for each of the specified services.</span></span> <span data-ttu-id="a58b2-111">サービスが既に実行中の場合は、メッセージが無視されます。エラーにはなりません。</span><span class="sxs-lookup"><span data-stu-id="a58b2-111">If a service is already running, the message is ignored without error.</span></span> <span data-ttu-id="a58b2-112">サービスは、サービス名または表示名で指定できます。また、 **InputObject** パラメーターを使用して、開始するサービスを表すサービスオブジェクトを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to supply a service object that represents the services that you want to start.</span></span>

## <span data-ttu-id="a58b2-113">例</span><span class="sxs-lookup"><span data-stu-id="a58b2-113">EXAMPLES</span></span>

### <span data-ttu-id="a58b2-114">例 1: 名前を使用してサービスを開始する</span><span class="sxs-lookup"><span data-stu-id="a58b2-114">Example 1: Start a service by using its name</span></span>

<span data-ttu-id="a58b2-115">この例では、ローカルコンピューターで EventLog サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-115">This example starts the EventLog service on the local computer.</span></span> <span data-ttu-id="a58b2-116">**Name** パラメーターは、サービス名でサービスを識別します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-116">The **Name** parameter identifies the service by its service name.</span></span>

```powershell
Start-Service -Name "eventlog"
```

### <span data-ttu-id="a58b2-117">例 2: サービスを開始せずに情報を表示する</span><span class="sxs-lookup"><span data-stu-id="a58b2-117">Example 2: Display information without starting a service</span></span>

<span data-ttu-id="a58b2-118">この例では、表示名に "remote" を含むサービスを開始した場合の動作を示します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-118">This example shows what would occur if you started the services that have a display name that includes "remote".</span></span>

```powershell
Start-Service -DisplayName *remote* -WhatIf
```

<span data-ttu-id="a58b2-119">**DisplayName** パラメーターは、サービス名ではなく、表示名でサービスを識別します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-119">The **DisplayName** parameter identifies the services by their display name instead of their service name.</span></span> <span data-ttu-id="a58b2-120">**WhatIf** パラメーターを指定すると、コマンドを実行したときに何が起こるかがコマンドレットによって表示されますが、変更は行われません。</span><span class="sxs-lookup"><span data-stu-id="a58b2-120">The **WhatIf** parameter causes the cmdlet to display what would happen when you run the command but does not make changes.</span></span>

### <span data-ttu-id="a58b2-121">例 3: サービスを開始し、テキストファイルにアクションを記録する</span><span class="sxs-lookup"><span data-stu-id="a58b2-121">Example 3: Start a service and record the action in a text file</span></span>

<span data-ttu-id="a58b2-122">この例では、コンピューター上の Windows Management Instrumentation (WMI) サービスを開始し、services.txt ファイルにアクションのレコードを追加します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-122">This example starts the Windows Management Instrumentation (WMI) service on the computer and adds a record of the action to the services.txt file.</span></span>

```powershell
$s = Get-Service wmi
Start-Service -InputObject $s -PassThru | Format-List >> services.txt
```

<span data-ttu-id="a58b2-123">まず、を使用して、 `Get-Service` WMI サービスを表すオブジェクトを取得し、それを変数に格納し `$s` ます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-123">First we use `Get-Service` to get an object that represent the WMI service and store it in the `$s` variable.</span></span> <span data-ttu-id="a58b2-124">次に、サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-124">Next, we start the service.</span></span> <span data-ttu-id="a58b2-125">**PassThru** パラメーターを指定しない場合、で `Start-Service` は出力は作成されません。</span><span class="sxs-lookup"><span data-stu-id="a58b2-125">Without the **PassThru** parameter, `Start-Service` does not create any output.</span></span> <span data-ttu-id="a58b2-126">パイプライン演算子 (|) は、によってオブジェクトの出力を `Start-Service` コマンドレットに渡して、 `Format-List` オブジェクトをプロパティの一覧として書式設定します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-126">The pipeline operator (|) passes the object output by `Start-Service` to the `Format-List` cmdlet to format the object as a list of its properties.</span></span> <span data-ttu-id="a58b2-127">追加リダイレクト演算子 () は、 \> \> services.txt ファイルに出力をリダイレクトします。</span><span class="sxs-lookup"><span data-stu-id="a58b2-127">The append redirection operator (\>\>) redirects the output to the services.txt file.</span></span> <span data-ttu-id="a58b2-128">既存のファイルの末尾に出力が追加されます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-128">The output is added to the end of the existing file.</span></span>

### <span data-ttu-id="a58b2-129">例 4: 無効なサービスを開始する</span><span class="sxs-lookup"><span data-stu-id="a58b2-129">Example 4: Start a disabled service</span></span>

<span data-ttu-id="a58b2-130">この例は、サービスのスタートアップの種類が **無効になっ** ている場合にサービスを開始する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="a58b2-130">This example shows how to start a service when the start type of the service is **Disabled**.</span></span>

```
PS> Start-Service tlntsvr
Start-Service : Service 'Telnet (TlntSvr)' cannot be started due to the following error: Cannot start service TlntSvr on computer '.'.
At line:1 char:14
+ Start-Service  <<<< tlntsvr

PS> Get-CimInstance win32_service | Where-Object Name -eq "tlntsvr"
ExitCode  : 0
Name      : TlntSvr
ProcessId : 0
StartMode : Disabled
State     : Stopped
Status    : OK

PS> Set-Service tlntsvr -StartupType manual
PS> Start-Service tlntsvr
```

<span data-ttu-id="a58b2-131">Telnet サービス (tlntsvr) を最初に起動しようとして失敗します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-131">The first attempt to start the Telnet service (tlntsvr) fails.</span></span> <span data-ttu-id="a58b2-132">この `Get-CimInstance` コマンドは、Tlntsvr サービスの **StartMode** プロパティが無効に **なっ** ていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="a58b2-132">The `Get-CimInstance` command shows that the **StartMode** property of the Tlntsvr service is **Disabled**.</span></span> <span data-ttu-id="a58b2-133">コマンドレットにより、 `Set-Service` 開始の種類が **手動** に変更されます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-133">The `Set-Service` cmdlet changes the start type to **Manual**.</span></span> <span data-ttu-id="a58b2-134">次に、コマンドを再送信し `Start-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-134">Now, we can resubmit the `Start-Service` command.</span></span> <span data-ttu-id="a58b2-135">今度はコマンドが成功します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-135">This time, the command succeeds.</span></span> <span data-ttu-id="a58b2-136">コマンドが成功したことを確認するには、を実行 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-136">To verify that the command succeeded, run `Get-Service`.</span></span>

## <span data-ttu-id="a58b2-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a58b2-137">PARAMETERS</span></span>

### <span data-ttu-id="a58b2-138">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="a58b2-138">-DisplayName</span></span>

<span data-ttu-id="a58b2-139">開始するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-139">Specifies the display names of the services to start.</span></span> <span data-ttu-id="a58b2-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a58b2-141">-除外</span><span class="sxs-lookup"><span data-stu-id="a58b2-141">-Exclude</span></span>

<span data-ttu-id="a58b2-142">このコマンドレットで省略されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-142">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="a58b2-143">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-143">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="a58b2-144">などの名前要素またはパターンを入力し `s*` ます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-144">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="a58b2-145">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-145">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a58b2-146">-Include</span><span class="sxs-lookup"><span data-stu-id="a58b2-146">-Include</span></span>

<span data-ttu-id="a58b2-147">このコマンドレットが開始するサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-147">Specifies services that this cmdlet starts.</span></span> <span data-ttu-id="a58b2-148">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-148">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="a58b2-149">などの名前要素またはパターンを入力し `s*` ます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-149">Enter a name element or pattern, such as `s*`.</span></span> <span data-ttu-id="a58b2-150">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-150">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a58b2-151">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a58b2-151">-InputObject</span></span>

<span data-ttu-id="a58b2-152">開始するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-152">Specifies **ServiceController** objects representing the services to be started.</span></span> <span data-ttu-id="a58b2-153">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-153">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.ServiceProcess.ServiceController[]
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a58b2-154">-Name</span><span class="sxs-lookup"><span data-stu-id="a58b2-154">-Name</span></span>

<span data-ttu-id="a58b2-155">開始するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-155">Specifies the service names for the service to be started.</span></span>

<span data-ttu-id="a58b2-156">パラメーター名は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="a58b2-156">The parameter name is optional.</span></span> <span data-ttu-id="a58b2-157">**名前** またはそのエイリアスである **ServiceName** を使用することも、パラメーター名を省略することもできます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-157">You can use **Name** or its alias, **ServiceName**, or you can omit the parameter name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="a58b2-158">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a58b2-158">-PassThru</span></span>

<span data-ttu-id="a58b2-159">サービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-159">Returns an object that represents the service.</span></span> <span data-ttu-id="a58b2-160">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a58b2-160">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a58b2-161">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a58b2-161">-Confirm</span></span>

<span data-ttu-id="a58b2-162">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-162">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a58b2-163">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a58b2-163">-WhatIf</span></span>

<span data-ttu-id="a58b2-164">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-164">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="a58b2-165">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a58b2-165">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a58b2-166">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a58b2-166">CommonParameters</span></span>

<span data-ttu-id="a58b2-167">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a58b2-167">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a58b2-168">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a58b2-168">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a58b2-169">入力</span><span class="sxs-lookup"><span data-stu-id="a58b2-169">INPUTS</span></span>

### <span data-ttu-id="a58b2-170">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="a58b2-170">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="a58b2-171">パイプを使用して、サービスを表すオブジェクト、またはサービス名を含む文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-171">You can pipe objects that represent the services or strings that contain the service names to this cmdlet.</span></span>

## <span data-ttu-id="a58b2-172">出力</span><span class="sxs-lookup"><span data-stu-id="a58b2-172">OUTPUTS</span></span>

### <span data-ttu-id="a58b2-173">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="a58b2-173">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="a58b2-174">このコマンドレットは、 **PassThru** を指定した場合に、サービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-174">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the service, if you specify **PassThru**.</span></span> <span data-ttu-id="a58b2-175">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a58b2-175">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a58b2-176">注</span><span class="sxs-lookup"><span data-stu-id="a58b2-176">NOTES</span></span>

<span data-ttu-id="a58b2-177">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-177">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="a58b2-178">また、組み込みエイリアスであるを参照することもでき `Start-Service` `sasv` ます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-178">You can also refer to `Start-Service` by its built-in alias, `sasv`.</span></span> <span data-ttu-id="a58b2-179">詳細については、「 [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a58b2-179">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="a58b2-180">`Start-Service` 現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-180">`Start-Service` can control services only if the current user has permission to do this.</span></span> <span data-ttu-id="a58b2-181">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a58b2-181">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="a58b2-182">システム上のサービスのサービス名と表示名を確認するには、「」と入力 `Get-Service` します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-182">To find the service names and display names of the services on your system, type `Get-Service`.</span></span>
  <span data-ttu-id="a58b2-183">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a58b2-183">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>
- <span data-ttu-id="a58b2-184">開始できるのは、開始の種類が [手動]、[自動]、または [自動 (遅延開始)] のサービスだけです。</span><span class="sxs-lookup"><span data-stu-id="a58b2-184">You can start only the services that have a start type of Manual, Automatic, or Automatic (Delayed Start).</span></span> <span data-ttu-id="a58b2-185">開始の種類が無効になっているサービスを開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="a58b2-185">You cannot start the services that have a start type of Disabled.</span></span> <span data-ttu-id="a58b2-186">コマンドが失敗し、メッセージが表示されない場合は `Start-Service` `Cannot start service \<service-name\> on computer` 、を使用して `Get-CimInstance` サービスの開始の種類を検索し、必要に応じて、コマンドレットを使用して `Set-Service` サービスの開始の種類を変更します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-186">If a `Start-Service` command fails with the message `Cannot start service \<service-name\> on computer`, use `Get-CimInstance` to find the start type of the service and, if you have to, use the `Set-Service` cmdlet to change the start type of the service.</span></span>
- <span data-ttu-id="a58b2-187">Performance Logs and Alerts (SysmonLog) などのいくつかのサービスは、処理しなければならない作業がないと自動的に停止します。</span><span class="sxs-lookup"><span data-stu-id="a58b2-187">Some services, such as Performance Logs and Alerts (SysmonLog) stop automatically if they have no work to do.</span></span> <span data-ttu-id="a58b2-188">PowerShell がサービスを開始するときに、すぐに停止すると、次のメッセージが表示されます。 `Service \<display-name\> start failed.`</span><span class="sxs-lookup"><span data-stu-id="a58b2-188">When PowerShell starts a service that stops itself almost immediately, it displays the following message: `Service \<display-name\> start failed.`</span></span>

## <span data-ttu-id="a58b2-189">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a58b2-189">RELATED LINKS</span></span>

[<span data-ttu-id="a58b2-190">Get-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-190">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="a58b2-191">New-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-191">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="a58b2-192">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-192">Restart-Service</span></span>](Restart-Service.md)

[<span data-ttu-id="a58b2-193">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-193">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="a58b2-194">Set-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-194">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="a58b2-195">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-195">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="a58b2-196">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-196">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="a58b2-197">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="a58b2-197">Remove-Service</span></span>](Remove-Service.md)
