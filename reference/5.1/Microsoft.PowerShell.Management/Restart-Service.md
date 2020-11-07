---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: 491940351042843af60fe85f8f1b39d41688675f
ms.sourcegitcommit: 177ae45034b58ead716853096b2e72e4864e6df6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2020
ms.locfileid: "94342843"
---
# <span data-ttu-id="a36d9-103">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="a36d9-103">Restart-Service</span></span>

## <span data-ttu-id="a36d9-104">概要</span><span class="sxs-lookup"><span data-stu-id="a36d9-104">SYNOPSIS</span></span>
<span data-ttu-id="a36d9-105">1 つ以上のサービスを停止し、再起動します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-105">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="a36d9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a36d9-106">SYNTAX</span></span>

### <span data-ttu-id="a36d9-107">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="a36d9-107">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a36d9-108">Default</span><span class="sxs-lookup"><span data-stu-id="a36d9-108">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="a36d9-109">DisplayName</span><span class="sxs-lookup"><span data-stu-id="a36d9-109">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="a36d9-110">Description</span><span class="sxs-lookup"><span data-stu-id="a36d9-110">DESCRIPTION</span></span>

<span data-ttu-id="a36d9-111">`Restart-Service`コマンドレットは、指定されたサービスの Windows サービスコントローラーに停止メッセージを送信した後、開始メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-111">The `Restart-Service` cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span> <span data-ttu-id="a36d9-112">サービスが既に停止している場合は、エラーを通知せずに起動されます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-112">If a service was already stopped, it is started without notifying you of an error.</span></span> <span data-ttu-id="a36d9-113">サービスは、サービス名または表示名で指定できます。また、 **InputObject** パラメーターを使用して、再起動する各サービスを表すオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-113">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="a36d9-114">例</span><span class="sxs-lookup"><span data-stu-id="a36d9-114">EXAMPLES</span></span>

### <span data-ttu-id="a36d9-115">例 1: ローカルコンピューター上のサービスを再起動する</span><span class="sxs-lookup"><span data-stu-id="a36d9-115">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="a36d9-116">このコマンドを実行すると、ローカル コンピューター上の Windows Management Instrumentation サービス (WinMgmt) が再起動されます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-116">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="a36d9-117">例 2: サービスを除外する</span><span class="sxs-lookup"><span data-stu-id="a36d9-117">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="a36d9-118">このコマンドは、net Logon サービスを除き、Net で始まる表示名を持つサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-118">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="a36d9-119">例 3: 停止したすべてのネットワークサービスを開始する</span><span class="sxs-lookup"><span data-stu-id="a36d9-119">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="a36d9-120">このコマンドを実行すると、コンピューター上で停止しているネットワーク サービスがすべて開始されます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-120">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="a36d9-121">このコマンドは、 `Get-Service` コマンドレットを使用して、サービス名が net で始まるサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-121">This command uses the `Get-Service` cmdlet to get objects that represent the services whose service name starts with net.</span></span> <span data-ttu-id="a36d9-122">パイプライン演算子 () は、 `|` サービスオブジェクトをコマンドレットに送信し `Where-Object` ます。これにより、status が stopped のサービスだけが選択されます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-122">The pipeline operator (`|`) sends the services object to the `Where-Object` cmdlet, which selects only the services that have a status of stopped.</span></span> <span data-ttu-id="a36d9-123">もう1つのパイプライン演算子は、選択したサービスをに送信し `Restart-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-123">Another pipeline operator sends the selected services to `Restart-Service`.</span></span>

<span data-ttu-id="a36d9-124">実際には、 **WhatIf** パラメーターを使用して、コマンドを実行する前にその効果を判断します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-124">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="a36d9-125">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a36d9-125">PARAMETERS</span></span>

### <span data-ttu-id="a36d9-126">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="a36d9-126">-DisplayName</span></span>

<span data-ttu-id="a36d9-127">再起動するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-127">Specifies the display names of services to restarted.</span></span> <span data-ttu-id="a36d9-128">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-128">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a36d9-129">-除外</span><span class="sxs-lookup"><span data-stu-id="a36d9-129">-Exclude</span></span>

<span data-ttu-id="a36d9-130">このコマンドレットで省略されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-130">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="a36d9-131">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-131">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="a36d9-132">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-132">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="a36d9-133">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-133">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a36d9-134">-Force</span><span class="sxs-lookup"><span data-stu-id="a36d9-134">-Force</span></span>

<span data-ttu-id="a36d9-135">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-135">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="a36d9-136">-Include</span><span class="sxs-lookup"><span data-stu-id="a36d9-136">-Include</span></span>

<span data-ttu-id="a36d9-137">このコマンドレットによって再起動されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-137">Specifies services that this cmdlet restarts.</span></span> <span data-ttu-id="a36d9-138">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-138">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="a36d9-139">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-139">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="a36d9-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="a36d9-141">-InputObject</span><span class="sxs-lookup"><span data-stu-id="a36d9-141">-InputObject</span></span>

<span data-ttu-id="a36d9-142">再起動するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-142">Specifies **ServiceController** objects that represent the services to restart.</span></span> <span data-ttu-id="a36d9-143">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-143">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="a36d9-144">-Name</span><span class="sxs-lookup"><span data-stu-id="a36d9-144">-Name</span></span>

<span data-ttu-id="a36d9-145">再起動するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-145">Specifies the service names of the services to restart.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Default
Aliases: ServiceName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="a36d9-146">-PassThru</span><span class="sxs-lookup"><span data-stu-id="a36d9-146">-PassThru</span></span>

<span data-ttu-id="a36d9-147">サービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-147">Returns an object that represents the service.</span></span> <span data-ttu-id="a36d9-148">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a36d9-148">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="a36d9-149">-Confirm</span><span class="sxs-lookup"><span data-stu-id="a36d9-149">-Confirm</span></span>

<span data-ttu-id="a36d9-150">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-150">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="a36d9-151">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="a36d9-151">-WhatIf</span></span>

<span data-ttu-id="a36d9-152">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-152">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="a36d9-153">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="a36d9-153">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="a36d9-154">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a36d9-154">CommonParameters</span></span>

<span data-ttu-id="a36d9-155">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a36d9-155">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a36d9-156">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a36d9-156">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a36d9-157">入力</span><span class="sxs-lookup"><span data-stu-id="a36d9-157">INPUTS</span></span>

### <span data-ttu-id="a36d9-158">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="a36d9-158">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="a36d9-159">このコマンドレットには、サービス名を含むサービスオブジェクトまたは文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-159">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="a36d9-160">出力</span><span class="sxs-lookup"><span data-stu-id="a36d9-160">OUTPUTS</span></span>

### <span data-ttu-id="a36d9-161">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="a36d9-161">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="a36d9-162">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、再起動されたサービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-162">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="a36d9-163">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="a36d9-163">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="a36d9-164">注</span><span class="sxs-lookup"><span data-stu-id="a36d9-164">NOTES</span></span>


- <span data-ttu-id="a36d9-165">`Restart-Service` 現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-165">`Restart-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="a36d9-166">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a36d9-166">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="a36d9-167">システム上のサービスのサービス名と表示名を確認するには、 `Get-Service` 「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="a36d9-167">To find the service names and display names of the services on your system, type `Get-Service`".</span></span>
  <span data-ttu-id="a36d9-168">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a36d9-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="a36d9-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a36d9-169">RELATED LINKS</span></span>

[<span data-ttu-id="a36d9-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="a36d9-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="a36d9-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="a36d9-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="a36d9-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="a36d9-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="a36d9-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="a36d9-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="a36d9-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="a36d9-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="a36d9-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="a36d9-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="a36d9-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="a36d9-176">Suspend-Service</span></span>](Suspend-Service.md)
