---
external help file: Get-DscConfigurationStatus.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfigurationstatus?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfigurationStatus
ms.openlocfilehash: 0d59ce58a70eab68441ea1fe6097bbdf7792a54f
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215363"
---
# <span data-ttu-id="cfcb0-103">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="cfcb0-103">Get-DscConfigurationStatus</span></span>

## <span data-ttu-id="cfcb0-104">概要</span><span class="sxs-lookup"><span data-stu-id="cfcb0-104">SYNOPSIS</span></span>
<span data-ttu-id="cfcb0-105">完了した構成の実行に関するデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-105">Retrieves data about completed configuration runs.</span></span>

## <span data-ttu-id="cfcb0-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cfcb0-106">SYNTAX</span></span>

```
Get-DscConfigurationStatus [-All] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## <span data-ttu-id="cfcb0-107">Description</span><span class="sxs-lookup"><span data-stu-id="cfcb0-107">DESCRIPTION</span></span>
<span data-ttu-id="cfcb0-108">**Get DscConfigurationStatus** コマンドレットは、システムで完了した構成の実行に関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-108">The **Get-DscConfigurationStatus** cmdlet retrieves detailed information about completed configuration runs on the system.</span></span>
<span data-ttu-id="cfcb0-109">既定では、最後の構成の実行に関する情報が返されます。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-109">By default, it returns the information about the last configuration run.</span></span>
<span data-ttu-id="cfcb0-110">このコマンドレットは、構成が実行された日時、実行の状態、構成内のリソースの数、成功または失敗したリソースなど、構成の実行に関する履歴情報を見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-110">This cmdlet is useful for finding historical information about configuration runs, such as when the configurations were run, the status of the runs, the number of resources in the configurations, and which resources succeeded or failed.</span></span>

## <span data-ttu-id="cfcb0-111">例</span><span class="sxs-lookup"><span data-stu-id="cfcb0-111">EXAMPLES</span></span>

### <span data-ttu-id="cfcb0-112">例 1: 最後の構成の実行に関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="cfcb0-112">Example 1: Get information on the last configuration run</span></span>

```
PS C:\> Get-DscConfigurationStatus
```

<span data-ttu-id="cfcb0-113">このコマンドは、最後の構成の実行に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-113">This command gets information on the last configuration run.</span></span>

### <span data-ttu-id="cfcb0-114">例 2: すべての構成に関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="cfcb0-114">Example 2: Get information on all configurations</span></span>

```
PS C:\> Get-DscConfigurationStatus -All
```

<span data-ttu-id="cfcb0-115">このコマンドは、Windows PowerShell Desired State Configuration (DSC) 整合性チェックを含む、システムで実行されたすべての構成に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-115">This command gets information about all the configurations that were run on the system, including the Windows PowerShell Desired State Configuration (DSC) consistency check.</span></span>

### <span data-ttu-id="cfcb0-116">例 3: リモートコンピューターでの構成の実行に関する情報を取得する</span><span class="sxs-lookup"><span data-stu-id="cfcb0-116">Example 3: Get information on the configuration run on a remote computer</span></span>

```
PS C:\> Get-DscConfigurationStatus -CimSession "Server01"
```

<span data-ttu-id="cfcb0-117">このコマンドは、Server01 という名前のリモートコンピューターの構成実行の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-117">This command gets the configuration run details of the remote computer named Server01.</span></span>
<span data-ttu-id="cfcb0-118">これは、WSMan トランスポートを使用してリモートコンピューターに接続し、接続しているユーザーがリモートコンピューターの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-118">This uses the WSMan transport to connect to the remote computer and requires that the connecting user be an administrator on the remote computer.</span></span>

## <span data-ttu-id="cfcb0-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cfcb0-119">PARAMETERS</span></span>

### <span data-ttu-id="cfcb0-120">-All</span><span class="sxs-lookup"><span data-stu-id="cfcb0-120">-All</span></span>
<span data-ttu-id="cfcb0-121">このコマンドレットが、構成アプリケーションや整合性チェックなど、コンピューター上のすべての構成の実行に関する情報を取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-121">Indicates that this cmdlet retrieves information about all the configuration runs on the computer, including the configuration application and the consistency check.</span></span>

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

### <span data-ttu-id="cfcb0-122">-AsJob</span><span class="sxs-lookup"><span data-stu-id="cfcb0-122">-AsJob</span></span>
<span data-ttu-id="cfcb0-123">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-123">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="cfcb0-124">-CimSession</span><span class="sxs-lookup"><span data-stu-id="cfcb0-124">-CimSession</span></span>
<span data-ttu-id="cfcb0-125">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-125">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="cfcb0-126">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-126">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="cfcb0-127">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-127">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfcb0-128">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="cfcb0-128">-ThrottleLimit</span></span>
<span data-ttu-id="cfcb0-129">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-129">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="cfcb0-130">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-130">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="cfcb0-131">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-131">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cfcb0-132">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="cfcb0-132">CommonParameters</span></span>
<span data-ttu-id="cfcb0-133">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-133">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cfcb0-134">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfcb0-134">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cfcb0-135">入力</span><span class="sxs-lookup"><span data-stu-id="cfcb0-135">INPUTS</span></span>

## <span data-ttu-id="cfcb0-136">出力</span><span class="sxs-lookup"><span data-stu-id="cfcb0-136">OUTPUTS</span></span>

## <span data-ttu-id="cfcb0-137">注</span><span class="sxs-lookup"><span data-stu-id="cfcb0-137">NOTES</span></span>

## <span data-ttu-id="cfcb0-138">関連リンク</span><span class="sxs-lookup"><span data-stu-id="cfcb0-138">RELATED LINKS</span></span>

[<span data-ttu-id="cfcb0-139">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="cfcb0-139">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="cfcb0-140">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="cfcb0-140">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="cfcb0-141">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="cfcb0-141">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)

[<span data-ttu-id="cfcb0-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="cfcb0-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="cfcb0-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="cfcb0-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="cfcb0-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="cfcb0-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
