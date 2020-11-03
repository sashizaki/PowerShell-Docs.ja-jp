---
external help file: Get-DSCConfiguration.cdxml-help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/get-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-DscConfiguration
ms.openlocfilehash: 42b24e72de4c4bcc9326d52861c08a05853b18e0
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215355"
---
# <span data-ttu-id="bc6c3-103">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bc6c3-103">Get-DscConfiguration</span></span>

## <span data-ttu-id="bc6c3-104">概要</span><span class="sxs-lookup"><span data-stu-id="bc6c3-104">SYNOPSIS</span></span>
<span data-ttu-id="bc6c3-105">ノードの現在の構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-105">Gets the current configuration of the nodes.</span></span>

## <span data-ttu-id="bc6c3-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="bc6c3-106">SYNTAX</span></span>

```
Get-DscConfiguration [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## <span data-ttu-id="bc6c3-107">Description</span><span class="sxs-lookup"><span data-stu-id="bc6c3-107">DESCRIPTION</span></span>
<span data-ttu-id="bc6c3-108">構成が存在する場合、 **start-dscconfiguration** コマンドレットは、ノードの現在の構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-108">The **Get-DscConfiguration** cmdlet gets the current configuration of the nodes, if the configuration exists.</span></span>
<span data-ttu-id="bc6c3-109">Common Information Model (CIM) セッションを使用してコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-109">Specify computers by using Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="bc6c3-110">ターゲット コンピューターを指定しない場合、コマンドレットではローカル コンピューターから構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-110">If you do not specify a target computer, the cmdlet gets the configuration from the local computer.</span></span>

## <span data-ttu-id="bc6c3-111">例</span><span class="sxs-lookup"><span data-stu-id="bc6c3-111">EXAMPLES</span></span>

### <span data-ttu-id="bc6c3-112">例 1: ローカルコンピューターの構成を取得する</span><span class="sxs-lookup"><span data-stu-id="bc6c3-112">Example 1: Get the configuration for the local computer</span></span>

```
PS C:\> Get-DscConfiguration
```

<span data-ttu-id="bc6c3-113">このコマンドは、ローカルコンピューターの現在の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-113">This command gets the current state for the local computer.</span></span>

### <span data-ttu-id="bc6c3-114">例 2: 指定したコンピューターの構成を取得する</span><span class="sxs-lookup"><span data-stu-id="bc6c3-114">Example 2: Get the configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Get-DscConfiguration -CimSession $Session
```

<span data-ttu-id="bc6c3-115">この例では、CIM セッションによって指定されたコンピューターから現在の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-115">This example gets the current state from a computer specified by a CIM session.</span></span>
<span data-ttu-id="bc6c3-116">例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-116">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="bc6c3-117">または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-117">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="bc6c3-118">最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを **$Session** 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-118">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the **$Session** variable.</span></span>
<span data-ttu-id="bc6c3-119">コマンドはパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-119">The command prompts you for a password.</span></span>
<span data-ttu-id="bc6c3-120">詳細を表示するには「`Get-Help New-CimSession`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-120">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="bc6c3-121">2 番目のコマンドは、 **$Session** 変数に格納された **CimSession** オブジェクトによって識別されるコンピューター (この場合は、Server01 という名前のコンピューター) の現在の構成を取得します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-121">The second command gets the current configuration for the computers identified by the **CimSession** objects stored in the **$Session** variable, in this case, the computer named Server01.</span></span>

## <span data-ttu-id="bc6c3-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="bc6c3-122">PARAMETERS</span></span>

### <span data-ttu-id="bc6c3-123">-AsJob</span><span class="sxs-lookup"><span data-stu-id="bc6c3-123">-AsJob</span></span>
<span data-ttu-id="bc6c3-124">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-124">Indicates that this cmdlet runs the command as a background job.</span></span>

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

### <span data-ttu-id="bc6c3-125">-CimSession</span><span class="sxs-lookup"><span data-stu-id="bc6c3-125">-CimSession</span></span>
<span data-ttu-id="bc6c3-126">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-126">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="bc6c3-127">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-127">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="bc6c3-128">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-128">The default is the current session on the local computer.</span></span>

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

### <span data-ttu-id="bc6c3-129">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="bc6c3-129">-ThrottleLimit</span></span>
<span data-ttu-id="bc6c3-130">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-130">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="bc6c3-131">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-131">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="bc6c3-132">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-132">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="bc6c3-133">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="bc6c3-133">CommonParameters</span></span>
<span data-ttu-id="bc6c3-134">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-134">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="bc6c3-135">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc6c3-135">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="bc6c3-136">入力</span><span class="sxs-lookup"><span data-stu-id="bc6c3-136">INPUTS</span></span>

## <span data-ttu-id="bc6c3-137">出力</span><span class="sxs-lookup"><span data-stu-id="bc6c3-137">OUTPUTS</span></span>

## <span data-ttu-id="bc6c3-138">注</span><span class="sxs-lookup"><span data-stu-id="bc6c3-138">NOTES</span></span>

## <span data-ttu-id="bc6c3-139">関連リンク</span><span class="sxs-lookup"><span data-stu-id="bc6c3-139">RELATED LINKS</span></span>

[<span data-ttu-id="bc6c3-140">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="bc6c3-140">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="bc6c3-141">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="bc6c3-141">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="bc6c3-142">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bc6c3-142">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="bc6c3-143">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bc6c3-143">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)

[<span data-ttu-id="bc6c3-144">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="bc6c3-144">Test-DscConfiguration</span></span>](Test-DscConfiguration.md)
