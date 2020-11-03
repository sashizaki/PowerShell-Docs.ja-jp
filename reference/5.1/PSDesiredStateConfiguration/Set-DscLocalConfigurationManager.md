---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 04/29/2020
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/set-dsclocalconfigurationmanager?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DscLocalConfigurationManager
ms.openlocfilehash: 0d35aa56a52f0e6c17abd0e7b2707869e780324c
ms.sourcegitcommit: 0d4d3e47f6979876550591f62061096e7a568f7e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2020
ms.locfileid: "93218016"
---
# <span data-ttu-id="4545a-103">Set-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="4545a-103">Set-DscLocalConfigurationManager</span></span>

## <span data-ttu-id="4545a-104">概要</span><span class="sxs-lookup"><span data-stu-id="4545a-104">SYNOPSIS</span></span>

<span data-ttu-id="4545a-105">ローカル Configuration Manager (LCM) 設定をノードに適用します。</span><span class="sxs-lookup"><span data-stu-id="4545a-105">Applies Local Configuration Manager (LCM) settings to nodes.</span></span>

## <span data-ttu-id="4545a-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4545a-106">SYNTAX</span></span>

### <span data-ttu-id="4545a-107">ComputerNameSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="4545a-107">ComputerNameSet (Default)</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [[-ComputerName] <String[]>]
 [-Credential <PSCredential>] [-ThrottleLimit <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="4545a-108">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="4545a-108">CimSessionSet</span></span>

```
Set-DscLocalConfigurationManager [-Path] <String> [-Force] [-ThrottleLimit <Int32>] -CimSession <CimSession[]>
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="4545a-109">Description</span><span class="sxs-lookup"><span data-stu-id="4545a-109">DESCRIPTION</span></span>

<span data-ttu-id="4545a-110">`Set-DscLocalConfigurationManager`コマンドレットは、LCM 設定またはメタ構成をノードに適用します。</span><span class="sxs-lookup"><span data-stu-id="4545a-110">The `Set-DscLocalConfigurationManager` cmdlet applies LCM settings, or meta-configuration, to nodes.</span></span> <span data-ttu-id="4545a-111">コンピューターの名前を指定するか、または Common Information Model (CIM) セッションを使用してコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="4545a-111">Specify computers by specifying computer names or by using Common Information Model (CIM) sessions.</span></span> <span data-ttu-id="4545a-112">ターゲット コンピューターを指定しない場合、コマンドレットは、ローカル コンピューターに設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="4545a-112">If you do not specify a target computer, the cmdlet applies settings to the local computer.</span></span>

## <span data-ttu-id="4545a-113">例</span><span class="sxs-lookup"><span data-stu-id="4545a-113">EXAMPLES</span></span>

### <span data-ttu-id="4545a-114">例 1: LCM 設定を適用する</span><span class="sxs-lookup"><span data-stu-id="4545a-114">Example 1: Apply LCM settings</span></span>

```
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\"
```

<span data-ttu-id="4545a-115">このコマンドは、からターゲットノードに LCM 設定を適用し `C:\DSC\Configurations\` ます。</span><span class="sxs-lookup"><span data-stu-id="4545a-115">This command applies the LCM settings from `C:\DSC\Configurations\` to the targeted nodes.</span></span> <span data-ttu-id="4545a-116">設定を受け取った後、LCM はそれらを処理します。</span><span class="sxs-lookup"><span data-stu-id="4545a-116">After receiving the settings, LCM processes them.</span></span>

> [!WARNING]
> <span data-ttu-id="4545a-117">指定されたフォルダーに格納されている同じコンピューターに複数の meta mof が存在する場合は、最初のメタ mof のみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="4545a-117">If there are multiple meta mofs for the same computer stored in the specified folder, only the first meta mof will be applied.</span></span>

### <span data-ttu-id="4545a-118">例 2: CIM セッションを使用して LCM 設定を適用する</span><span class="sxs-lookup"><span data-stu-id="4545a-118">Example 2: Apply LCM settings by using a CIM session</span></span>

```
$Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
Set-DscLocalConfigurationManager -Path "C:\DSC\Configurations\" -CimSession $Session
```

<span data-ttu-id="4545a-119">この例では、LCM 設定をコンピューターに適用し、設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="4545a-119">This example applies LCM settings to a computer and applies the settings.</span></span> <span data-ttu-id="4545a-120">例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="4545a-120">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span> <span data-ttu-id="4545a-121">または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。</span><span class="sxs-lookup"><span data-stu-id="4545a-121">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="4545a-122">最初のコマンドは、コマンドレットを使用して CIM セッションを作成し、 `New-CimSession` **CimSession** オブジェクトを変数に格納し `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="4545a-122">The first command creates a CIM session by using the `New-CimSession` cmdlet, and then stores the **CimSession** object in the `$Session` variable.</span></span> <span data-ttu-id="4545a-123">コマンドはパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="4545a-123">The command prompts you for a password.</span></span> <span data-ttu-id="4545a-124">詳細を表示するには「`Get-Help New-CimSession`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="4545a-124">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="4545a-125">2番目のコマンドは、ターゲットノードの LCM 設定をから、 `C:\DSC\Configurations\` 変数に格納されている **CimSession** オブジェクトによって識別されるコンピューターに適用し `$Session` ます。</span><span class="sxs-lookup"><span data-stu-id="4545a-125">The second command applies LCM settings for the targeted node from `C:\DSC\Configurations\` to the computer identified by the **CimSession** objects stored in the `$Session` variable.</span></span> <span data-ttu-id="4545a-126">この例では、 `$Session` 変数には Server01 という名前のコンピューターに対してのみ CIM セッションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4545a-126">In this example, the `$Session` variable contains a CIM session only for the computer named Server01.</span></span> <span data-ttu-id="4545a-127">コマンドは設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="4545a-127">The command applies the settings.</span></span> <span data-ttu-id="4545a-128">設定を受け取った後、LCM はそれらを処理します。</span><span class="sxs-lookup"><span data-stu-id="4545a-128">After receiving the settings, LCM processes them.</span></span>

## <span data-ttu-id="4545a-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4545a-129">PARAMETERS</span></span>

### <span data-ttu-id="4545a-130">-CimSession</span><span class="sxs-lookup"><span data-stu-id="4545a-130">-CimSession</span></span>

<span data-ttu-id="4545a-131">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="4545a-131">Runs the cmdlet in a remote session or on a remote computer.</span></span> <span data-ttu-id="4545a-132">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/CimCmdlets/New-CimSession) または [CimSession](/powershell/module/CimCmdlets/Get-CimSession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4545a-132">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/CimCmdlets/New-CimSession) or [Get-CimSession](/powershell/module/CimCmdlets/Get-CimSession) cmdlet.</span></span>
<span data-ttu-id="4545a-133">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="4545a-133">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4545a-134">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="4545a-134">-ComputerName</span></span>

<span data-ttu-id="4545a-135">コンピューター名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="4545a-135">Specifies an array of computer names.</span></span> <span data-ttu-id="4545a-136">このパラメーターは、 **Path** パラメーターにメタ構成ドキュメントが含まれるコンピューターを、配列で指定されているものに制限します。</span><span class="sxs-lookup"><span data-stu-id="4545a-136">This parameter restricts the computers that have meta-configuration documents in the **Path** parameter to those specified in the array.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="4545a-137">-Credential</span><span class="sxs-lookup"><span data-stu-id="4545a-137">-Credential</span></span>

<span data-ttu-id="4545a-138">ターゲット コンピューターに対して、ユーザー名とパスワードを、 **PSCredential** オブジェクトとして指定します。</span><span class="sxs-lookup"><span data-stu-id="4545a-138">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span> <span data-ttu-id="4545a-139">**PSCredential** オブジェクトを取得するには、Get-Credential コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4545a-139">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span> <span data-ttu-id="4545a-140">詳細を表示するには「`Get-Help Get-Credential`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="4545a-140">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4545a-141">-Force</span><span class="sxs-lookup"><span data-stu-id="4545a-141">-Force</span></span>

<span data-ttu-id="4545a-142">ユーザーに確認せずに、直ちにコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="4545a-142">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="4545a-143">-Path</span><span class="sxs-lookup"><span data-stu-id="4545a-143">-Path</span></span>

<span data-ttu-id="4545a-144">構成設定ファイルを含むフォルダーのファイル パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4545a-144">Specifies a file path of a folder that contains configuration settings files.</span></span> <span data-ttu-id="4545a-145">このコマンドレットは、指定されたパスに設定ファイルがあるコンピューターに、これらの LCM 設定を発行して適用します。</span><span class="sxs-lookup"><span data-stu-id="4545a-145">The cmdlet publishes and applies these LCM settings to computers that have settings files in the specified path.</span></span> <span data-ttu-id="4545a-146">各ターゲットノードには、という形式の設定ファイルが必要 `NetBIOS Name.meta.mof` です。</span><span class="sxs-lookup"><span data-stu-id="4545a-146">Each target node must have a settings file of the following format: `NetBIOS Name.meta.mof`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4545a-147">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="4545a-147">-ThrottleLimit</span></span>

<span data-ttu-id="4545a-148">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="4545a-148">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span> <span data-ttu-id="4545a-149">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="4545a-149">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span> <span data-ttu-id="4545a-150">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="4545a-150">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="4545a-151">-Confirm</span><span class="sxs-lookup"><span data-stu-id="4545a-151">-Confirm</span></span>

<span data-ttu-id="4545a-152">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4545a-152">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="4545a-153">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="4545a-153">-WhatIf</span></span>

<span data-ttu-id="4545a-154">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="4545a-154">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="4545a-155">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="4545a-155">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="4545a-156">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="4545a-156">CommonParameters</span></span>

<span data-ttu-id="4545a-157">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="4545a-157">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4545a-158">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4545a-158">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4545a-159">入力</span><span class="sxs-lookup"><span data-stu-id="4545a-159">INPUTS</span></span>

## <span data-ttu-id="4545a-160">出力</span><span class="sxs-lookup"><span data-stu-id="4545a-160">OUTPUTS</span></span>

## <span data-ttu-id="4545a-161">注</span><span class="sxs-lookup"><span data-stu-id="4545a-161">NOTES</span></span>

## <span data-ttu-id="4545a-162">関連リンク</span><span class="sxs-lookup"><span data-stu-id="4545a-162">RELATED LINKS</span></span>

[<span data-ttu-id="4545a-163">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="4545a-163">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/overview)

[<span data-ttu-id="4545a-164">Get-DscLocalConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="4545a-164">Get-DscLocalConfigurationManager</span></span>](Get-DscLocalConfigurationManager.md)
