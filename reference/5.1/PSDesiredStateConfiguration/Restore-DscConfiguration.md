---
external help file: Restore-DSCConfiguration.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/restore-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Restore-DscConfiguration
ms.openlocfilehash: 823032f7665d9ec83faa59c37560510e049efdd2
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215296"
---
# <span data-ttu-id="d49c8-103">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="d49c8-103">Restore-DscConfiguration</span></span>

## <span data-ttu-id="d49c8-104">概要</span><span class="sxs-lookup"><span data-stu-id="d49c8-104">SYNOPSIS</span></span>
<span data-ttu-id="d49c8-105">ノードの以前の構成を再適用します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-105">Reapplies the previous configuration for the node.</span></span>

## <span data-ttu-id="d49c8-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d49c8-106">SYNTAX</span></span>

```
Restore-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## <span data-ttu-id="d49c8-107">Description</span><span class="sxs-lookup"><span data-stu-id="d49c8-107">DESCRIPTION</span></span>
<span data-ttu-id="d49c8-108">前の構成が存在する場合は、 **start-dscconfiguration** コマンドレットによって、以前の構成がノードに再適用されます。</span><span class="sxs-lookup"><span data-stu-id="d49c8-108">The **Restore-DscConfiguration** cmdlet reapplies the previous configuration for the node, if a previous configuration exists.</span></span>
<span data-ttu-id="d49c8-109">Common Information Model (CIM) セッションを使用してコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="d49c8-110">ターゲット コンピューターを指定しない場合、コマンドレットではローカル コンピューターの構成を復元します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-110">If you do not specify a target computer, the cmdlet restores the configuration of the local computer.</span></span>
<span data-ttu-id="d49c8-111">特定のノードの以前の構成がない場合、このコマンドレットはエラーメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-111">If there is no previous configuration for a particular node, this cmdlet returns an error message.</span></span>

<span data-ttu-id="d49c8-112">このコマンドレットでは **Confirm** パラメーターはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d49c8-112">This cmdlet does not support the **Confirm** parameter.</span></span>

## <span data-ttu-id="d49c8-113">例</span><span class="sxs-lookup"><span data-stu-id="d49c8-113">EXAMPLES</span></span>

### <span data-ttu-id="d49c8-114">例 1: ローカルコンピューターの構成を復元する</span><span class="sxs-lookup"><span data-stu-id="d49c8-114">Example 1: Restore the configuration for the local computer</span></span>

```
PS C:\> Restore-DscConfiguration
```

<span data-ttu-id="d49c8-115">以下のコマンドは、ローカル コンピューターの構成を復元します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-115">This command restores the configuration for the local computer.</span></span>

### <span data-ttu-id="d49c8-116">例 2: 指定したコンピューターの構成を復元する</span><span class="sxs-lookup"><span data-stu-id="d49c8-116">Example 2: Restore configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Restore-DscConfiguration -CimSession $Session
```

<span data-ttu-id="d49c8-117">この例では、CIM セッションによって指定されたコンピューター上で構成を復元します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-117">This example restores configuration on a computer specified by a CIM session.</span></span>
<span data-ttu-id="d49c8-118">例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-118">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="d49c8-119">または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-119">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="d49c8-120">最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-120">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="d49c8-121">コマンドはパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="d49c8-121">The command prompts you for a password.</span></span>
<span data-ttu-id="d49c8-122">詳細を表示するには「`Get-Help New-CimSession`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-122">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="d49c8-123">2 番目のコマンドは、 **$Session** 変数に格納された CimSession オブジェクトによって識別されるコンピューター (この場合は、Server01 という名前のコンピューター) の構成を復元します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-123">The second command restores the configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="d49c8-124">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d49c8-124">PARAMETERS</span></span>

### <span data-ttu-id="d49c8-125">-AsJob</span><span class="sxs-lookup"><span data-stu-id="d49c8-125">-AsJob</span></span>
<span data-ttu-id="d49c8-126">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-126">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="d49c8-127">-CimSession</span><span class="sxs-lookup"><span data-stu-id="d49c8-127">-CimSession</span></span>
<span data-ttu-id="d49c8-128">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-128">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="d49c8-129">コンピューター名またはセッションオブジェクト ( **CimSession** または **CimSession** コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-129">Enter a computer name or a session object, such as the output of a **New-CimSession** or **Get-CimSession** cmdlet.</span></span>

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

### <span data-ttu-id="d49c8-130">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="d49c8-130">-ThrottleLimit</span></span>
<span data-ttu-id="d49c8-131">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-131">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>

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

### <span data-ttu-id="d49c8-132">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d49c8-132">-Confirm</span></span>
<span data-ttu-id="d49c8-133">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d49c8-133">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d49c8-134">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d49c8-134">-WhatIf</span></span>
<span data-ttu-id="d49c8-135">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="d49c8-135">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d49c8-136">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="d49c8-136">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d49c8-137">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d49c8-137">CommonParameters</span></span>
<span data-ttu-id="d49c8-138">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d49c8-138">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d49c8-139">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d49c8-139">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d49c8-140">入力</span><span class="sxs-lookup"><span data-stu-id="d49c8-140">INPUTS</span></span>

## <span data-ttu-id="d49c8-141">出力</span><span class="sxs-lookup"><span data-stu-id="d49c8-141">OUTPUTS</span></span>

## <span data-ttu-id="d49c8-142">注</span><span class="sxs-lookup"><span data-stu-id="d49c8-142">NOTES</span></span>

## <span data-ttu-id="d49c8-143">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d49c8-143">RELATED LINKS</span></span>

[<span data-ttu-id="d49c8-144">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="d49c8-144">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="d49c8-145">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="d49c8-145">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="d49c8-146">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="d49c8-146">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="d49c8-147">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="d49c8-147">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="d49c8-148">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="d49c8-148">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
