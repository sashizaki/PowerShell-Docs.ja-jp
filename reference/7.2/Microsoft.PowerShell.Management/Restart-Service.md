---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/restart-service?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-Service
ms.openlocfilehash: f88e07e36ec7c6adf7f24e2c6e57ae5864eb1a60
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600399"
---
# <span data-ttu-id="cfd4a-102">Restart-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-102">Restart-Service</span></span>

## <span data-ttu-id="cfd4a-103">概要</span><span class="sxs-lookup"><span data-stu-id="cfd4a-103">SYNOPSIS</span></span>
<span data-ttu-id="cfd4a-104">1 つ以上のサービスを停止し、再起動します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-104">Stops and then starts one or more services.</span></span>

## <span data-ttu-id="cfd4a-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cfd4a-105">SYNTAX</span></span>

### <span data-ttu-id="cfd4a-106">InputObject (既定値)</span><span class="sxs-lookup"><span data-stu-id="cfd4a-106">InputObject (Default)</span></span>

```
Restart-Service [-Force] [-InputObject] <ServiceController[]> [-PassThru] [-Include <String[]>]
 [-Exclude <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cfd4a-107">Default</span><span class="sxs-lookup"><span data-stu-id="cfd4a-107">Default</span></span>

```
Restart-Service [-Force] [-Name] <String[]> [-PassThru] [-Include <String[]>] [-Exclude <String[]>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cfd4a-108">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cfd4a-108">DisplayName</span></span>

```
Restart-Service [-Force] [-PassThru] -DisplayName <String[]> [-Include <String[]>] [-Exclude <String[]>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cfd4a-109">Description</span><span class="sxs-lookup"><span data-stu-id="cfd4a-109">DESCRIPTION</span></span>

<span data-ttu-id="cfd4a-110">`Restart-Service`コマンドレットは、指定されたサービスの Windows サービスコントローラーに停止メッセージを送信した後、開始メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-110">The `Restart-Service` cmdlet sends a stop message and then a start message to the Windows Service Controller for a specified service.</span></span> <span data-ttu-id="cfd4a-111">サービスが既に停止している場合は、エラーを通知せずに起動されます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-111">If a service was already stopped, it is started without notifying you of an error.</span></span> <span data-ttu-id="cfd4a-112">サービスは、サービス名または表示名で指定できます。また、 **InputObject** パラメーターを使用して、再起動する各サービスを表すオブジェクトを渡すこともできます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-112">You can specify the services by their service names or display names, or you can use the **InputObject** parameter to pass an object that represents each service that you want to restart.</span></span>

## <span data-ttu-id="cfd4a-113">例</span><span class="sxs-lookup"><span data-stu-id="cfd4a-113">EXAMPLES</span></span>

### <span data-ttu-id="cfd4a-114">例 1: ローカルコンピューター上のサービスを再起動する</span><span class="sxs-lookup"><span data-stu-id="cfd4a-114">Example 1: Restart a service on the local computer</span></span>

```powershell
PS C:\> Restart-Service -Name winmgmt
```

<span data-ttu-id="cfd4a-115">このコマンドを実行すると、ローカル コンピューター上の Windows Management Instrumentation サービス (WinMgmt) が再起動されます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-115">This command restarts the Windows Management Instrumentation service (WinMgmt) on the local computer.</span></span>

### <span data-ttu-id="cfd4a-116">例 2: サービスを除外する</span><span class="sxs-lookup"><span data-stu-id="cfd4a-116">Example 2: Exclude a service</span></span>

```powershell
PS C:\> Restart-Service -DisplayName "net*" -Exclude "net logon"
```

<span data-ttu-id="cfd4a-117">このコマンドは、net Logon サービスを除き、Net で始まる表示名を持つサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-117">This command restarts the services that have a display name that starts with Net, except for the Net Logon service.</span></span>

### <span data-ttu-id="cfd4a-118">例 3: 停止したすべてのネットワークサービスを開始する</span><span class="sxs-lookup"><span data-stu-id="cfd4a-118">Example 3: Start all stopped network services</span></span>

```powershell
PS C:\> Get-Service -Name "net*" | Where-Object {$_.Status -eq "Stopped"} | Restart-Service
```

<span data-ttu-id="cfd4a-119">このコマンドを実行すると、コンピューター上で停止しているネットワーク サービスがすべて開始されます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-119">This command starts all of the stopped network services on the computer.</span></span>

<span data-ttu-id="cfd4a-120">このコマンドは、 `Get-Service` コマンドレットを使用して、サービス名が net で始まるサービスを表すオブジェクトを取得します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-120">This command uses the `Get-Service` cmdlet to get objects that represent the services whose service name starts with net.</span></span> <span data-ttu-id="cfd4a-121">パイプライン演算子 () は、 `|` サービスオブジェクトをコマンドレットに送信し `Where-Object` ます。これにより、status が stopped のサービスだけが選択されます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-121">The pipeline operator (`|`) sends the services object to the `Where-Object` cmdlet, which selects only the services that have a status of stopped.</span></span> <span data-ttu-id="cfd4a-122">もう1つのパイプライン演算子は、選択したサービスをに送信し `Restart-Service` ます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-122">Another pipeline operator sends the selected services to `Restart-Service`.</span></span>

<span data-ttu-id="cfd4a-123">実際には、 **WhatIf** パラメーターを使用して、コマンドを実行する前にその効果を判断します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-123">In practice, you would use the **WhatIf** parameter to determine the effect of the command before you run it.</span></span>

## <span data-ttu-id="cfd4a-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cfd4a-124">PARAMETERS</span></span>

### <span data-ttu-id="cfd4a-125">-DisplayName</span><span class="sxs-lookup"><span data-stu-id="cfd4a-125">-DisplayName</span></span>

<span data-ttu-id="cfd4a-126">再起動するサービスの表示名を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-126">Specifies the display names of services to restarted.</span></span> <span data-ttu-id="cfd4a-127">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-127">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="cfd4a-128">-除外</span><span class="sxs-lookup"><span data-stu-id="cfd4a-128">-Exclude</span></span>

<span data-ttu-id="cfd4a-129">このコマンドレットで省略されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-129">Specifies services that this cmdlet omits.</span></span> <span data-ttu-id="cfd4a-130">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-130">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="cfd4a-131">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-131">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="cfd4a-132">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-132">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="cfd4a-133">-Force</span><span class="sxs-lookup"><span data-stu-id="cfd4a-133">-Force</span></span>

<span data-ttu-id="cfd4a-134">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-134">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="cfd4a-135">-Include</span><span class="sxs-lookup"><span data-stu-id="cfd4a-135">-Include</span></span>

<span data-ttu-id="cfd4a-136">このコマンドレットによって再起動されるサービスを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-136">Specifies services that this cmdlet restarts.</span></span> <span data-ttu-id="cfd4a-137">このパラメーターの値は、 **Name** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-137">The value of this parameter qualifies the **Name** parameter.</span></span> <span data-ttu-id="cfd4a-138">「S \*」のように、名前要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-138">Enter a name element or pattern, such as s\*.</span></span> <span data-ttu-id="cfd4a-139">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-139">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="cfd4a-140">-InputObject</span><span class="sxs-lookup"><span data-stu-id="cfd4a-140">-InputObject</span></span>

<span data-ttu-id="cfd4a-141">再起動するサービスを表す **ServiceController** オブジェクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-141">Specifies **ServiceController** objects that represent the services to restart.</span></span> <span data-ttu-id="cfd4a-142">オブジェクトが格納されている変数を入力するか、オブジェクトを取得するコマンドまたは式を入力します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-142">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="cfd4a-143">-Name</span><span class="sxs-lookup"><span data-stu-id="cfd4a-143">-Name</span></span>

<span data-ttu-id="cfd4a-144">再起動するサービスのサービス名を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-144">Specifies the service names of the services to restart.</span></span>

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

### <span data-ttu-id="cfd4a-145">-PassThru</span><span class="sxs-lookup"><span data-stu-id="cfd4a-145">-PassThru</span></span>

<span data-ttu-id="cfd4a-146">サービスを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-146">Returns an object that represents the service.</span></span> <span data-ttu-id="cfd4a-147">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-147">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="cfd4a-148">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cfd4a-148">-Confirm</span></span>

<span data-ttu-id="cfd4a-149">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-149">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="cfd4a-150">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cfd4a-150">-WhatIf</span></span>

<span data-ttu-id="cfd4a-151">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-151">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="cfd4a-152">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-152">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="cfd4a-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfd4a-153">CommonParameters</span></span>

<span data-ttu-id="cfd4a-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cfd4a-155">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-155">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cfd4a-156">入力</span><span class="sxs-lookup"><span data-stu-id="cfd4a-156">INPUTS</span></span>

### <span data-ttu-id="cfd4a-157">ServiceController (System.string)、System.string</span><span class="sxs-lookup"><span data-stu-id="cfd4a-157">System.ServiceProcess.ServiceController, System.String</span></span>

<span data-ttu-id="cfd4a-158">このコマンドレットには、サービス名を含むサービスオブジェクトまたは文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-158">You can pipe a service object or a string that contains a service name to this cmdlet.</span></span>

## <span data-ttu-id="cfd4a-159">出力</span><span class="sxs-lookup"><span data-stu-id="cfd4a-159">OUTPUTS</span></span>

### <span data-ttu-id="cfd4a-160">None、ServiceController。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-160">None, System.ServiceProcess.ServiceController</span></span>

<span data-ttu-id="cfd4a-161">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、再起動されたサービスを表す **ServiceController** オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-161">This cmdlet generates a **System.ServiceProcess.ServiceController** object that represents the restarted service, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="cfd4a-162">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-162">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="cfd4a-163">注</span><span class="sxs-lookup"><span data-stu-id="cfd4a-163">NOTES</span></span>

<span data-ttu-id="cfd4a-164">このコマンドレットは、Windows プラットフォームでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-164">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="cfd4a-165">`Restart-Service` 現在のユーザーがこの操作を行うためのアクセス許可を持っている場合にのみ、サービスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-165">`Restart-Service` can control services only when the current user has permission to do this.</span></span> <span data-ttu-id="cfd4a-166">コマンドが正常に機能しない場合は、必要なアクセス許可が与えられていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-166">If a command does not work correctly, you might not have the required permissions.</span></span>
- <span data-ttu-id="cfd4a-167">システム上のサービスのサービス名と表示名を確認するには、 `Get-Service` 「」と入力します。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-167">To find the service names and display names of the services on your system, type `Get-Service`".</span></span>
  <span data-ttu-id="cfd4a-168">サービス名は [ **名前** ] 列に表示され、表示名は [ **DisplayName** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfd4a-168">The service names appear in the **Name** column, and the display names appear in the **DisplayName** column.</span></span>

## <span data-ttu-id="cfd4a-169">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cfd4a-169">RELATED LINKS</span></span>

[<span data-ttu-id="cfd4a-170">Get-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-170">Get-Service</span></span>](Get-Service.md)

[<span data-ttu-id="cfd4a-171">New-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-171">New-Service</span></span>](New-Service.md)

[<span data-ttu-id="cfd4a-172">Resume-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-172">Resume-Service</span></span>](Resume-Service.md)

[<span data-ttu-id="cfd4a-173">Set-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-173">Set-Service</span></span>](Set-Service.md)

[<span data-ttu-id="cfd4a-174">Start-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-174">Start-Service</span></span>](Start-Service.md)

[<span data-ttu-id="cfd4a-175">Stop-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-175">Stop-Service</span></span>](Stop-Service.md)

[<span data-ttu-id="cfd4a-176">Suspend-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-176">Suspend-Service</span></span>](Suspend-Service.md)

[<span data-ttu-id="cfd4a-177">Remove-Service</span><span class="sxs-lookup"><span data-stu-id="cfd4a-177">Remove-Service</span></span>](Remove-Service.md)
