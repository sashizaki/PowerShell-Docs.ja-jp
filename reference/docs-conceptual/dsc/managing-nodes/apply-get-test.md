---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: ノード上で構成を適用、取得、およびテストする
description: このガイドでは、ターゲット ノード上の構成を操作する方法を説明します。
ms.openlocfilehash: 6bc9262bc0e2ce8eea7b85bd46ecc0c0a691276d
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92651012"
---
# <a name="apply-get-and-test-configurations-on-a-node"></a><span data-ttu-id="03a46-104">ノード上で構成を適用、取得、およびテストする</span><span class="sxs-lookup"><span data-stu-id="03a46-104">Apply, Get, and Test Configurations on a Node</span></span>

<span data-ttu-id="03a46-105">このガイドでは、ターゲット ノード上の構成を操作する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="03a46-105">This guide will show you how to work with Configurations on a target Node.</span></span> <span data-ttu-id="03a46-106">このガイドは、次の手順に分かれています。</span><span class="sxs-lookup"><span data-stu-id="03a46-106">This guide is broken up into the following steps:</span></span>

## <a name="apply-a-configuration"></a><span data-ttu-id="03a46-107">構成を適用する</span><span class="sxs-lookup"><span data-stu-id="03a46-107">Apply a Configuration</span></span>

<span data-ttu-id="03a46-108">構成を適用したり管理したりするには、".mof" ファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03a46-108">In order to apply and manage a Configuration, we need to generate a ".mof" file.</span></span> <span data-ttu-id="03a46-109">次のコードは、このガイド全体で使用する簡単な構成を表したものです。</span><span class="sxs-lookup"><span data-stu-id="03a46-109">The following code will represent a simple Configuration that will be used throughout this guide.</span></span>

```powershell
Configuration Sample
{
    # This will generate two .mof files, a localhost.mof, and a server02.mof
    Node localhost, server02
    {
        File SampleFile
        {
            DestinationPath = 'C:\Temp\temp.txt'
            Contents = 'This is a simple resource to show Configuration functionality on a Node.'
        }
    }
}

# The -OutputPath parameter is built into every Configuration automatically.
# The value of -OutputPath determines where the .mof file should be stored, once compiled.
Sample -OutputPath "C:\Temp\"
```

<span data-ttu-id="03a46-110">この構成をコンパイルすると、2 つの ".mof" ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="03a46-110">Compiling this configuration will yield two ".mof" files.</span></span>

```Output
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----       11/27/2018   7:29 AM     2.13KB localhost.mof
-a----       11/27/2018   7:29 AM     2.13KB server02.mof
```

<span data-ttu-id="03a46-111">構成を適用するには、[Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="03a46-111">To apply a Configuration, use the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="03a46-112">`-Path` パラメーターでは、".mof" ファイルが存在するディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="03a46-112">The `-Path` parameter specifies a directory where ".mof" files reside.</span></span> <span data-ttu-id="03a46-113">`-Computername` を指定しないと、`Start-DSCConfiguration` では、".mof" ファイルの名前によって指定されているコンピューター名 (`<computername>.mof`) に対して、各構成の適用が試みられます。</span><span class="sxs-lookup"><span data-stu-id="03a46-113">If no `-Computername` is specified, `Start-DSCConfiguration` will attempt to apply each Configuration to the computer name specified by the name of the '.mof' file (`<computername>.mof`).</span></span> <span data-ttu-id="03a46-114">詳細な出力を表示するには、`Start-DSCConfiguration` に対して `-Verbose` を指定します。</span><span class="sxs-lookup"><span data-stu-id="03a46-114">Specify `-Verbose` to `Start-DSCConfiguration` to see more verbose output.</span></span>

```powershell
Start-DSCConfiguration -Path C:\Temp\ -Verbose
```

<span data-ttu-id="03a46-115">`-Wait` を指定しない場合、1 つのジョブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="03a46-115">If `-Wait` is not specified, you see one job created.</span></span> <span data-ttu-id="03a46-116">作成されたジョブには、`Start-DSCConfiguration` によって処理される ".mof" ファイルごとに 1 つの **ChildJob** があります。</span><span class="sxs-lookup"><span data-stu-id="03a46-116">The job created will have one **ChildJob** for each ".mof" file processed by `Start-DSCConfiguration`.</span></span>

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
45     Job45           Configuratio... Running       True            localhost,server02   Start-DSCConfiguration...
```

<span data-ttu-id="03a46-117">構成に長い時間がかかっていて停止したい場合は、[Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) を使ってローカル ノードでの適用を停止できます。</span><span class="sxs-lookup"><span data-stu-id="03a46-117">If a Configuration is taking a long time and you want to stop it, you can use [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) to stop application on the local Node.</span></span>

```powershell
Stop-DSCConfiguration -Force
```

<span data-ttu-id="03a46-118">完了した後は、[Get-Job](/powershell/module/microsoft.powershell.core/get-job) によって返されるジョブ オブジェクトにより、ジョブの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="03a46-118">Once complete, you can view the status of the jobs through the job object returned by [Get-Job](/powershell/module/microsoft.powershell.core/get-job).</span></span>

```powershell
$job = Get-Job
$job.ChildJobs
```

```Output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
49     Job49           Configuratio... Completed     True            localhost            Start-DSCConfiguration...
50     Job50           Configuratio... Completed     True            server02             Start-DSCConfiguration...
```

<span data-ttu-id="03a46-119">**詳細** な出力を見るには、次のコマンドを使って、各 **ChildJob** の **詳細** ストリームを表示します。</span><span class="sxs-lookup"><span data-stu-id="03a46-119">To see the **Verbose** output, use the following commands to view the **Verbose** stream for each **ChildJob**.</span></span> <span data-ttu-id="03a46-120">PowerShell のジョブについて詳しくは、「[About Jobs (ジョブについて)](/powershell/module/microsoft.powershell.core/about/about_jobs)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="03a46-120">For more about PowerShell jobs, see [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span></span>

```powershell
# View the verbose output of the localhost job using array indexing.
$job.ChildJobs[0].Verbose
```

```Output
Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,
'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
An LCM method call arrived from computer SERVER01 with user sid S-1-5-21-124525095-708259637-1543119021-1282804.
[SERVER01]: LCM:  [ Start  Set      ]
[SERVER01]: LCM:  [ Start  Resource ]  [[File]SampleFile]
[SERVER01]: LCM:  [ Start  Test     ]  [[File]SampleFile]
[SERVER01]:                            [[File]SampleFile] The destination object was found and no action is required.
[SERVER01]: LCM:  [ End    Test     ]  [[File]SampleFile]  in 0.0370 seconds.
[SERVER01]: LCM:  [ Skip   Set      ]  [[File]SampleFile]
[SERVER01]: LCM:  [ End    Resource ]  [[File]SampleFile]
[SERVER01]: LCM:  [ End    Set      ]
[SERVER01]: LCM:  [ End    Set      ]    in  0.2400 seconds.
Operation 'Invoke CimMethod' complete.
```

<span data-ttu-id="03a46-121">PowerShell 5.0 以降では、`Start-DSCConfiguration` に `-UseExisting` パラメーターが追加されています。</span><span class="sxs-lookup"><span data-stu-id="03a46-121">Beginning in PowerShell 5.0, the `-UseExisting` parameter was added to `Start-DSCConfiguration`.</span></span> <span data-ttu-id="03a46-122">`-UseExisting` を指定することにより、`-Path` パラメーターで指定したものではなく、既存適用されている構成を使うようコマンドレットに指示します。</span><span class="sxs-lookup"><span data-stu-id="03a46-122">By specifying `-UseExisting`, you instruct the cmdlet to use the existing applied Configuration instead of one specified by the `-Path` parameter.</span></span>

```powershell
Start-DSCConfiguration -UseExisting -Verbose -Wait
```

## <a name="test-a-configuration"></a><span data-ttu-id="03a46-123">構成をテストする</span><span class="sxs-lookup"><span data-stu-id="03a46-123">Test a Configuration</span></span>

<span data-ttu-id="03a46-124">[Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) を使って、現在適用されている構成をテストできます。</span><span class="sxs-lookup"><span data-stu-id="03a46-124">You can test a currently applied Configuration using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span>
<span data-ttu-id="03a46-125">`Test-DSCConfiguration` では、ノードが準拠している場合は `True` が返され、そうでない場合は `False` が返されます。</span><span class="sxs-lookup"><span data-stu-id="03a46-125">`Test-DSCConfiguration` will return `True` if the Node is compliant, and `False` if it is not.</span></span>

```powershell
Test-DSCConfiguration
```

<span data-ttu-id="03a46-126">PowerShell 5.0 で初めて追加された`-Detailed` パラメーターでは、 **ResourcesInDesiredState** および **ResourcesNotInDesiredState** のコレクションを含むオブジェクトが返されます</span><span class="sxs-lookup"><span data-stu-id="03a46-126">Beginning in PowerShell 5.0, the `-Detailed` parameter was added which returns an object with collections for **ResourcesInDesiredState** and **ResourcesNotInDesiredState**</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

<span data-ttu-id="03a46-127">PowerShell 5.0 以降では、適用しないで構成をテストできます。</span><span class="sxs-lookup"><span data-stu-id="03a46-127">Beginning in PowerShell 5.0 you can test a Configuration without applying it.</span></span> <span data-ttu-id="03a46-128">`-ReferenceConfiguration` パラメーターは、ノードのテスト対象の ".mof" ファイルのパスを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="03a46-128">The `-ReferenceConfiguration` parameter accepts the path of a ".mof" file to test the Node against.</span></span> <span data-ttu-id="03a46-129">ノードに対して **設定** アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="03a46-129">No **Set** actions are taken against the Node.</span></span> <span data-ttu-id="03a46-130">PowerShell 4.0 では、適用しないで構成をテストする回避策がありますが、ここでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="03a46-130">In PowerShell 4.0, there are workarounds to test a Configuration without applying it, but they are not discussed here.</span></span>

## <a name="get-configuration-values"></a><span data-ttu-id="03a46-131">構成の値を取得する</span><span class="sxs-lookup"><span data-stu-id="03a46-131">Get Configuration Values</span></span>

<span data-ttu-id="03a46-132">[Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) コマンドレットでは、現在適用されている構成で構成されるリソースの現在の値が返されます。</span><span class="sxs-lookup"><span data-stu-id="03a46-132">The [Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet returns the current values for any configured resources in the currently applied Configuration.</span></span>

```powershell
Get-DSCConfiguration
```

<span data-ttu-id="03a46-133">正しく適用されている場合、サンプルの構成からの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="03a46-133">Output from our sample Configuration would look like this if applied successfully.</span></span>

```Output
ConfigurationName    : Sample
DependsOn            :
ModuleName           : PSDesiredStateConfiguration
ModuleVersion        :
PsDscRunAsCredential :
ResourceId           : [File]SampleFile
SourceInfo           :
Attributes           : {archive}
Checksum             :
Contents             :
CreatedDate          : 11/27/2018 7:16:06 AM
Credential           :
DestinationPath      : C:\Temp\temp.txt
Ensure               : present
Force                :
MatchSource          :
ModifiedDate         : 11/27/2018 7:16:06 AM
Recurse              :
Size                 : 75
SourcePath           :
SubItems             :
Type                 : file
PSComputerName       :
CimClassName         : MSFT_FileDirectoryConfiguration
```

## <a name="get-configuration-status"></a><span data-ttu-id="03a46-134">構成の状態を取得する</span><span class="sxs-lookup"><span data-stu-id="03a46-134">Get Configuration Status</span></span>

<span data-ttu-id="03a46-135">PowerShell 5.0 以降の [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) コマンドレットでは、ノードに適用された構成の履歴を参照できます。</span><span class="sxs-lookup"><span data-stu-id="03a46-135">Beginning in PowerShell 5.0 the [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) cmdlet allows you to see the history of applied Configurations to the node.</span></span> <span data-ttu-id="03a46-136">PowerShell DSC では、 **プッシュ** または **プル** モードで適用された直近 {{N}} 個の構成が追跡されています。</span><span class="sxs-lookup"><span data-stu-id="03a46-136">PowerShell DSC keeps track of the last {{N}} Configurations applied in **Push** or **Pull** mode.</span></span> <span data-ttu-id="03a46-137">これには、LCM によって実行された " *整合性* " チェックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="03a46-137">This includes any *consistency* checks executed by the LCM.</span></span> <span data-ttu-id="03a46-138">既定の `Get-DSCConfigurationStatus` では、最後の履歴エントリだけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="03a46-138">By default, `Get-DSCConfigurationStatus` shows you the last history entry only.</span></span>

```powershell
Get-DSCConfigurationStatus
```

```Output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
```

<span data-ttu-id="03a46-139">すべての構成状態の履歴を表示するには、`-All` パラメーターを使います。</span><span class="sxs-lookup"><span data-stu-id="03a46-139">Use the `-All` parameter to see all Configuration Status history.</span></span>

> [!NOTE]
> <span data-ttu-id="03a46-140">簡潔にするため出力は切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="03a46-140">Output is truncated for brevity.</span></span>

```powershell
Get-DSCConfigurationStatus -All
```

```Output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
Success    11/27/2018 7:16:06 AM     Initial         PUSH  False                1
Success    11/27/2018 7:04:53 AM     Initial         PUSH  False                1
Success    11/27/2018 7:03:45 AM     Consistency     PUSH  False                2
Success    11/27/2018 7:03:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:48:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:33:44 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:33:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:18:40 AM     Consistency     PUSH  False                2
Success    11/27/2018 6:03:44 AM     Consistency     PUSH  False                2
```

## <a name="manage-configuration-documents"></a><span data-ttu-id="03a46-141">構成ドキュメントを管理する</span><span class="sxs-lookup"><span data-stu-id="03a46-141">Manage Configuration Documents</span></span>

<span data-ttu-id="03a46-142">LCM では、 **構成ドキュメント** を処理することによって、ノードの構成が管理されます。</span><span class="sxs-lookup"><span data-stu-id="03a46-142">The LCM manages the Configuration of the Node by working with **Configuration Documents**.</span></span> <span data-ttu-id="03a46-143">これらの ".mof" ファイルは、`C:\Windows\System32\Configuration` ディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="03a46-143">These ".mof" files reside in the `C:\Windows\System32\Configuration` directory.</span></span>

<span data-ttu-id="03a46-144">PowerShell 5.0 以降では、[Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) を使って ".mof" ファイルを削除することで、将来の整合性チェックを停止したり、適用されるときにエラーがある構成を削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="03a46-144">Beginning in PowerShell 5.0 the [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) allows you to remove the ".mof" files to stop future consistency checks or remove a Configuration that has errors when applied.</span></span> <span data-ttu-id="03a46-145">`-Stage` パラメーターで、削除する ".mof" ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="03a46-145">The `-Stage` parameter allows you to specify which ".mof" file you want to remove.</span></span>

```powershell
Remove-DSCConfigurationDocument -Stage Current
```

> [!NOTE]
> <span data-ttu-id="03a46-146">PowerShell 4.0 ではまだ、[Remove-Item](/powershell/module/microsoft.powershell.management/remove-item) を使って直接これらの ".mof" ファイルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="03a46-146">In PowerShell 4.0, you can still remove these ".mof" files directly using [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).</span></span>

## <a name="publish-configurations"></a><span data-ttu-id="03a46-147">構成を発行する</span><span class="sxs-lookup"><span data-stu-id="03a46-147">Publish Configurations</span></span>

<span data-ttu-id="03a46-148">PowerShell 5.0 以降では、[Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) コマンドレットが追加されています。</span><span class="sxs-lookup"><span data-stu-id="03a46-148">Beginning in PowerShell 5.0, the [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) cmdlet was added.</span></span> <span data-ttu-id="03a46-149">このコマンドレットを使うと、適用することなく、リモート コンピューターに ".mof" ファイルを発行できます。</span><span class="sxs-lookup"><span data-stu-id="03a46-149">This cmdlet allows you to publish a ".mof" file to remote computers, without applying it.</span></span>

```powershell
Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

## <a name="see-also"></a><span data-ttu-id="03a46-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="03a46-150">See also</span></span>

- [<span data-ttu-id="03a46-151">取得、テスト、および設定</span><span class="sxs-lookup"><span data-stu-id="03a46-151">Get, Test, and Set</span></span>](../resources/get-test-set.md)
