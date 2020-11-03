---
external help file: Microsoft.Windows.DSC.CoreConfProviders.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSDesiredStateConfiguration
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/psdesiredstateconfiguration/test-dscconfiguration?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-DscConfiguration
ms.openlocfilehash: 25c8bc61976ce3940e0b9bd949fa3ee60728450d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213576"
---
# <span data-ttu-id="b66c6-103">Test-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="b66c6-103">Test-DscConfiguration</span></span>

## <span data-ttu-id="b66c6-104">概要</span><span class="sxs-lookup"><span data-stu-id="b66c6-104">SYNOPSIS</span></span>
<span data-ttu-id="b66c6-105">ノード上の実際の構成が必要な構成と一致するかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-105">Tests whether the actual configuration on the nodes matches the desired configuration.</span></span>

## <span data-ttu-id="b66c6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b66c6-106">SYNTAX</span></span>

### <span data-ttu-id="b66c6-107">ComputerNameSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="b66c6-107">ComputerNameSet (Default)</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Detailed] [<CommonParameters>]
```

### <span data-ttu-id="b66c6-108">ComputerNameAndPathSet</span><span class="sxs-lookup"><span data-stu-id="b66c6-108">ComputerNameAndPathSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] [-Path] <String> [<CommonParameters>]
```

### <span data-ttu-id="b66c6-109">ComputerNameAndReferenceConfigurationSet</span><span class="sxs-lookup"><span data-stu-id="b66c6-109">ComputerNameAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [[-ComputerName] <String[]>] [-Credential <PSCredential>] [-ThrottleLimit <Int32>]
 [-AsJob] -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="b66c6-110">CimSessionAndPathSet</span><span class="sxs-lookup"><span data-stu-id="b66c6-110">CimSessionAndPathSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Path] <String>
 [<CommonParameters>]
```

### <span data-ttu-id="b66c6-111">CimSessionAndReferenceConfigurationSet</span><span class="sxs-lookup"><span data-stu-id="b66c6-111">CimSessionAndReferenceConfigurationSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob]
 -ReferenceConfiguration <String> [<CommonParameters>]
```

### <span data-ttu-id="b66c6-112">CimSessionSet</span><span class="sxs-lookup"><span data-stu-id="b66c6-112">CimSessionSet</span></span>

```
Test-DscConfiguration [-ThrottleLimit <Int32>] -CimSession <CimSession[]> [-AsJob] [-Detailed]
 [<CommonParameters>]
```

## <span data-ttu-id="b66c6-113">Description</span><span class="sxs-lookup"><span data-stu-id="b66c6-113">DESCRIPTION</span></span>
<span data-ttu-id="b66c6-114">**Test-DscConfiguration** コマンドレットは、ノード上の実際の構成が、必要な構成と一致するかどうかをテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-114">The **Test-DscConfiguration** cmdlet tests whether the actual configuration on the nodes matches the desired configuration.</span></span>
<span data-ttu-id="b66c6-115">コンピューター名または Common Information Model (CIM) セッションを使用して、構成をテストするコンピューターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-115">Specify which computers for which you want to test configurations by using computer names or Common Information Model (CIM) sessions.</span></span>
<span data-ttu-id="b66c6-116">ターゲット コンピューターを指定しない場合、コマンドレットではローカル コンピューターの構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-116">If you do not specify a target computer, the cmdlet tests configuration of the local computer.</span></span>

<span data-ttu-id="b66c6-117">必要な構成と実際の構成が一致する場合、コマンドレットは文字列値 "True" を返します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-117">If the desired and actual configurations match, the cmdlet returns a string value of 'True'.</span></span>
<span data-ttu-id="b66c6-118">それ以外の場合は、文字列値 ' False ' を返します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-118">Otherwise, it returns a string value of 'False'.</span></span>

## <span data-ttu-id="b66c6-119">例</span><span class="sxs-lookup"><span data-stu-id="b66c6-119">EXAMPLES</span></span>

### <span data-ttu-id="b66c6-120">例 1: ローカルコンピューターの構成をテストする</span><span class="sxs-lookup"><span data-stu-id="b66c6-120">Example 1: Test configuration for the local computer</span></span>

```
PS C:\> Test-DscConfiguration
```

<span data-ttu-id="b66c6-121">以下のコマンドは、ローカル コンピューターの構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-121">This command tests configuration for the local computer.</span></span>

### <span data-ttu-id="b66c6-122">例 2: 指定したコンピューターの構成をテストする</span><span class="sxs-lookup"><span data-stu-id="b66c6-122">Example 2: Test configuration for a specified computer</span></span>

```
PS C:\> $Session = New-CimSession -ComputerName "Server01" -Credential ACCOUNTS\PattiFuller
PS C:\> Test-DscConfiguration -CimSession $Session
```

<span data-ttu-id="b66c6-123">この例では、CIM セッションによって指定されたコンピューターからの構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-123">This example test configuration from a computer specified by a CIM session.</span></span>
<span data-ttu-id="b66c6-124">例では、コマンドレットで使用するために、Server01 という名前のコンピューター用に CIM セッションを作成します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-124">The example creates a CIM session for a computer named Server01 for use with the cmdlet.</span></span>
<span data-ttu-id="b66c6-125">または、CIM セッションの配列を作成して、指定した複数のコンピューターにコマンドレットを適用します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-125">Alternatively, create an array of CIM sessions to apply the cmdlet to multiple specified computers.</span></span>

<span data-ttu-id="b66c6-126">最初のコマンドは、 **New-CimSession** コマンドレットを使用して CIM セッションを作成し、 **CimSession** オブジェクトを $Session 変数に格納します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-126">The first command creates a CIM session by using the **New-CimSession** cmdlet, and then stores the **CimSession** object in the $Session variable.</span></span>
<span data-ttu-id="b66c6-127">コマンドはパスワードの入力をユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="b66c6-127">The command prompts you for a password.</span></span>
<span data-ttu-id="b66c6-128">詳細を表示するには「`Get-Help New-CimSession`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-128">For more information, type `Get-Help New-CimSession`.</span></span>

<span data-ttu-id="b66c6-129">2 番目のコマンドは、 **$Session** 変数に格納された CimSession オブジェクトによって識別されるコンピューター (この場合は、Server01 という名前のコンピューター) の構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-129">The second command tests configuration for the computers identified by the **CimSession** objects stored in the $Session variable, in this case, the computer named Server01.</span></span>

### <span data-ttu-id="b66c6-130">例 3: 詳細な結果を含むテスト構成</span><span class="sxs-lookup"><span data-stu-id="b66c6-130">Example 3: Test configurations with detailed results</span></span>

```
PS C:\> Test-DscConfiguration -ComputerName "Server01", "Server02", "Server03" -Detailed
```

<span data-ttu-id="b66c6-131">このコマンドは、 *ComputerName* パラメーターで指定された一連のコンピューターの構成をテストし、全体的な状態、目的の状態にあるリソース、目的の状態ではないリソース、およびコンピューター名などの詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-131">This command tests configurations for a set of computers specified by the *ComputerName* parameter and returns detailed information that includes the overall state, resources that are in the desired state, resources that are not in the desired state and computer name.</span></span>

### <span data-ttu-id="b66c6-132">例 4: フォルダーで指定された構成をテストする</span><span class="sxs-lookup"><span data-stu-id="b66c6-132">Example 4: Test configurations specified in a folder</span></span>

```
PS C:\> Test-DscConfiguration -Path "C:\Dsc\Configurations"
```

<span data-ttu-id="b66c6-133">このコマンドは、 *Path* パラメーターで指定されたフォルダーで定義されている構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-133">This command tests configurations that are defined in a folder specified by the *Path* parameter.</span></span>
<span data-ttu-id="b66c6-134">これらの構成は、構成ファイルのファイル名で識別される一連のコンピューターに対してテストされます。</span><span class="sxs-lookup"><span data-stu-id="b66c6-134">The configurations are tested against a set of computers, each identified by the file name of the configuration file.</span></span>

### <span data-ttu-id="b66c6-135">例 5: ファイルに指定されている構成をテストする</span><span class="sxs-lookup"><span data-stu-id="b66c6-135">Example 5: Test configurations specified in a file</span></span>

```
PS C:\> Test-DscConfiguration -ReferenceConfiguration "C:\Dsc\Configurations\WebServer.mof" -ComputerName "Server01", "Server02", "Server03"
```

<span data-ttu-id="b66c6-136">このコマンドは、 *ComputerName* パラメーターで指定されたコンピューターのセットに対して、ファイルで定義された構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-136">This command tests a configuration defined in a file against a set of computers specified by the *ComputerName* parameter.</span></span>

## <span data-ttu-id="b66c6-137">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b66c6-137">PARAMETERS</span></span>

### <span data-ttu-id="b66c6-138">-AsJob</span><span class="sxs-lookup"><span data-stu-id="b66c6-138">-AsJob</span></span>
<span data-ttu-id="b66c6-139">このコマンドレットによってコマンドがバックグラウンドジョブとして実行されることを示します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-139">Indicates that this cmdlet runs the command as a background job.</span></span>

<span data-ttu-id="b66c6-140">*AsJob* パラメーターを指定すると、このコマンドはジョブを表すオブジェクトを返し、コマンドプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-140">If you specify the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.</span></span>
<span data-ttu-id="b66c6-141">ジョブが完了するまで、引き続きセッションで作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b66c6-141">You can continue to work in the session until the job finishes.</span></span>
<span data-ttu-id="b66c6-142">ジョブは、ローカル コンピューターで作成され、リモート コンピューターでの結果は自動的にローカル コンピューターに返されます。</span><span class="sxs-lookup"><span data-stu-id="b66c6-142">The job is created on the local computer and the results from remote computers are automatically returned to the local computer.</span></span>
<span data-ttu-id="b66c6-143">ジョブを管理するには、Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-143">To manage the job, use the Job cmdlets.</span></span>
<span data-ttu-id="b66c6-144">ジョブの結果を取得するには、Receive-Job コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-144">To get the job results, use the Receive-Job cmdlet.</span></span>

<span data-ttu-id="b66c6-145">このパラメーターを使用するには、ローカルコンピューターとリモートコンピューターがリモート処理用に構成されている必要があります。また、windows Vista 以降のバージョンの Windows オペレーティングシステムでは、[管理者として実行] オプションを使用して Windows PowerShell を開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="b66c6-145">To use this parameter, the local and remote computers must be configured for remoting, and on Windows Vista and later versions of the Windows operating system, you must open Windows PowerShell with the Run as administrator option.</span></span>
<span data-ttu-id="b66c6-146">詳細については、「[about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b66c6-146">For more information, see [about_Remote_Requirements](../Microsoft.PowerShell.Core/About/about_Remote_Requirements.md).</span></span>

<span data-ttu-id="b66c6-147">Windows PowerShell のバックグラウンドジョブの詳細については、「 [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) 」および「 [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b66c6-147">For more information about Windows PowerShell background jobs, see [about_Jobs](../Microsoft.PowerShell.Core/About/about_Jobs.md) and [about_Remote_Jobs](../Microsoft.PowerShell.Core/About/about_Remote_Jobs.md).</span></span>

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

### <span data-ttu-id="b66c6-148">-CimSession</span><span class="sxs-lookup"><span data-stu-id="b66c6-148">-CimSession</span></span>
<span data-ttu-id="b66c6-149">リモート セッションまたはリモート コンピューターでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-149">Runs the cmdlet in a remote session or on a remote computer.</span></span>
<span data-ttu-id="b66c6-150">コンピューター名またはセッションオブジェクト ( [CimSession](/powershell/module/cimcmdlets/new-cimsession) または [CimSession](/powershell/module/cimcmdlets/get-cimsession) コマンドレットの出力など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-150">Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet.</span></span>
<span data-ttu-id="b66c6-151">既定値は、ローカル コンピューターで実行中の現在のセッションです。</span><span class="sxs-lookup"><span data-stu-id="b66c6-151">The default is the current session on the local computer.</span></span>

```yaml
Type: Microsoft.Management.Infrastructure.CimSession[]
Parameter Sets: CimSessionAndPathSet, CimSessionAndReferenceConfigurationSet, CimSessionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b66c6-152">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="b66c6-152">-ComputerName</span></span>
<span data-ttu-id="b66c6-153">このコマンドレットによって構成がテストされるコンピューター名の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-153">Specifies an array of computer names on which this cmdlet tests the configuration.</span></span>
<span data-ttu-id="b66c6-154">コマンドレットは、 *Path* パラメーターによって指定された場所にある構成ドキュメントをこれらのコンピューターに対してテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-154">The cmdlet tests the configuration document in the location specified by the *Path* parameter to these computers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases: CN, ServerName

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b66c6-155">-Credential</span><span class="sxs-lookup"><span data-stu-id="b66c6-155">-Credential</span></span>
<span data-ttu-id="b66c6-156">ターゲット コンピューターに対して、ユーザー名とパスワードを、 **PSCredential** オブジェクトとして指定します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-156">Specifies a user name and password, as a **PSCredential** object, for the target computer.</span></span>
<span data-ttu-id="b66c6-157">**PSCredential** オブジェクトを取得するには、Get-Credential コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-157">To obtain a **PSCredential** object, use the Get-Credential cmdlet.</span></span>
<span data-ttu-id="b66c6-158">詳細を表示するには「`Get-Help Get-Credential`」を入力します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-158">For more information, type `Get-Help Get-Credential`.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: ComputerNameSet, ComputerNameAndPathSet, ComputerNameAndReferenceConfigurationSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b66c6-159">-Detailed</span><span class="sxs-lookup"><span data-stu-id="b66c6-159">-Detailed</span></span>
<span data-ttu-id="b66c6-160">このコマンドレットが、構成ドキュメントとノードの目的の状態を比較した結果を詳細に返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-160">Indicates that this cmdlet returns a detailed result of comparing the configuration document with the desired state of the nodes.</span></span>
<span data-ttu-id="b66c6-161">結果には、全体的な状態、目的の状態にあるリソース、目的の状態にないリソース、コンピューター名などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b66c6-161">The result includes information such as overall state, resources that are in the desired state, resources that are not in desired state, and computer name.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ComputerNameSet, CimSessionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b66c6-162">-Path</span><span class="sxs-lookup"><span data-stu-id="b66c6-162">-Path</span></span>
<span data-ttu-id="b66c6-163">構成ドキュメントファイルが格納されているフォルダーのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-163">Specifies the path of a folder that contains configuration document files.</span></span>
<span data-ttu-id="b66c6-164">コマンドレットは、 *ComputerName* パラメーターまたは *CimSession* パラメーターで指定されたコンピューターの目的の状態に対して構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-164">The cmdlet tests the configuration against the desired state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndPathSet, CimSessionAndPathSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b66c6-165">-ReferenceConfiguration</span><span class="sxs-lookup"><span data-stu-id="b66c6-165">-ReferenceConfiguration</span></span>
<span data-ttu-id="b66c6-166">構成ドキュメントファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-166">Specifies the path of the configuration document file.</span></span>
<span data-ttu-id="b66c6-167">このコマンドレットは、 *ComputerName* パラメーターまたは *CimSession* パラメーターによって指定されたコンピューターの実際の状態に対して構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="b66c6-167">This cmdlet tests the configuration against the actual state of computers specified by the *ComputerName* or *CimSession* parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: ComputerNameAndReferenceConfigurationSet, CimSessionAndReferenceConfigurationSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b66c6-168">-ThrottleLimit</span><span class="sxs-lookup"><span data-stu-id="b66c6-168">-ThrottleLimit</span></span>
<span data-ttu-id="b66c6-169">コマンドレットを実行するために確立できる最大並行処理数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-169">Specifies the maximum number of concurrent operations that can be established to run the cmdlet.</span></span>
<span data-ttu-id="b66c6-170">このパラメーターを省略した場合、または値を入力した場合 `0` 、Windows PowerShell は、コンピューターで実行されている CIM コマンドレットの数に基づいて、コマンドレットに最適なスロットル制限を計算します。</span><span class="sxs-lookup"><span data-stu-id="b66c6-170">If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.</span></span>
<span data-ttu-id="b66c6-171">調整限度は、現在のコマンドレットのみに適用されます。セッションやコンピューターには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b66c6-171">The throttle limit applies only to the current cmdlet, not to the session or to the computer.</span></span>

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

### <span data-ttu-id="b66c6-172">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="b66c6-172">CommonParameters</span></span>
<span data-ttu-id="b66c6-173">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="b66c6-173">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b66c6-174">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b66c6-174">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b66c6-175">入力</span><span class="sxs-lookup"><span data-stu-id="b66c6-175">INPUTS</span></span>

## <span data-ttu-id="b66c6-176">出力</span><span class="sxs-lookup"><span data-stu-id="b66c6-176">OUTPUTS</span></span>

## <span data-ttu-id="b66c6-177">注</span><span class="sxs-lookup"><span data-stu-id="b66c6-177">NOTES</span></span>

## <span data-ttu-id="b66c6-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="b66c6-178">RELATED LINKS</span></span>

[<span data-ttu-id="b66c6-179">Windows PowerShell Desired State Configuration の概要</span><span class="sxs-lookup"><span data-stu-id="b66c6-179">Windows PowerShell Desired State Configuration Overview</span></span>](/powershell/scripting/dsc/overview/dscforengineers)

[<span data-ttu-id="b66c6-180">Get-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="b66c6-180">Get-DscConfiguration</span></span>](Get-DscConfiguration.md)

[<span data-ttu-id="b66c6-181">Get-DscConfigurationStatus</span><span class="sxs-lookup"><span data-stu-id="b66c6-181">Get-DscConfigurationStatus</span></span>](Get-DscConfigurationStatus.md)

[<span data-ttu-id="b66c6-182">Restore-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="b66c6-182">Restore-DscConfiguration</span></span>](Restore-DscConfiguration.md)

[<span data-ttu-id="b66c6-183">Start-DscConfiguration</span><span class="sxs-lookup"><span data-stu-id="b66c6-183">Start-DscConfiguration</span></span>](Start-DscConfiguration.md)
