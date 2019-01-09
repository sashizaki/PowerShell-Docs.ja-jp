---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: ノード上で構成を適用、取得、およびテストする
ms.openlocfilehash: 41f8d2d75d3dd9621de615e7999c2690cb8ce44a
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402949"
---
# <a name="apply-get-and-test-configurations-on-a-node"></a><span data-ttu-id="31d77-103">ノード上で構成を適用、取得、およびテストする</span><span class="sxs-lookup"><span data-stu-id="31d77-103">Apply, Get, and Test Configurations on a Node</span></span>

<span data-ttu-id="31d77-104">このガイドでは、ターゲット ノードで構成を使用する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="31d77-104">This guide will show you how to work with Configurations on a target Node.</span></span> <span data-ttu-id="31d77-105">このガイドは、次の手順に分割されます。</span><span class="sxs-lookup"><span data-stu-id="31d77-105">This guide is broken up into the following steps:</span></span>

## <a name="apply-a-configuration"></a><span data-ttu-id="31d77-106">構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="31d77-106">Apply a Configuration</span></span>

<span data-ttu-id="31d77-107">適用しの構成を管理するためには、".mof"ファイルを生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31d77-107">In order to apply and manage a Configuration, we need to generate a ".mof" file.</span></span> <span data-ttu-id="31d77-108">次のコードでは、このガイド全体で使用される単純な構成を表します。</span><span class="sxs-lookup"><span data-stu-id="31d77-108">The following code will represent a simple Configuration that will be used throughout this guide.</span></span>

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

<span data-ttu-id="31d77-109">この構成をコンパイルすると、2 つの".mof"ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="31d77-109">Compiling this configuration will yield two ".mof" files.</span></span>

```output
Mode                LastWriteTime     Length Name
----                -------------     ------ ----
-a----       11/27/2018   7:29 AM     2.13KB localhost.mof
-a----       11/27/2018   7:29 AM     2.13KB server02.mof
```

<span data-ttu-id="31d77-110">構成を適用するには、使用、 [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="31d77-110">To apply a Configuration, use the [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/start-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="31d77-111">`-Path`パラメーターは、".mof"ファイルが存在するディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="31d77-111">The `-Path` parameter specifies a directory where ".mof" files reside.</span></span> <span data-ttu-id="31d77-112">ない場合は`-Computername`が指定されている`Start-DSCConfiguration`'.mof' ファイルの名前で指定したコンピューター名に各構成に適用されます (\<computername\>.mof)。</span><span class="sxs-lookup"><span data-stu-id="31d77-112">If no `-Computername` is specified, `Start-DSCConfiguration` will attempt to apply each Configuration to the computer name specified by the name of the '.mof' file (\<computername\>.mof).</span></span> <span data-ttu-id="31d77-113">指定`-Verbose`に`Start-DSCConfiguration`をより詳細な出力を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31d77-113">Specify `-Verbose` to `Start-DSCConfiguration` to see more verbose output.</span></span>

```powershell
Start-DSCConfiguration -Path C:\Temp\ -Verbose
```

<span data-ttu-id="31d77-114">場合`-Wait`が指定されていない、1 つのジョブを作成するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31d77-114">If `-Wait` is not specified, you see one job created.</span></span> <span data-ttu-id="31d77-115">作成されたジョブは 1 つが**ChildJob**によって処理される各".mof"ファイルの`Start-DSCConfiguration`します。</span><span class="sxs-lookup"><span data-stu-id="31d77-115">The job created will have one **ChildJob** for each ".mof" file processed by `Start-DSCConfiguration`.</span></span>

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
45     Job45           Configuratio... Running       True            localhost,server02   Start-DSCConfiguration...
```

<span data-ttu-id="31d77-116">構成には、長い時間がかかると保護を停止する場合は、使用することができる場合[Stop-dscconfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration)ローカル ノードでアプリケーションを停止します。</span><span class="sxs-lookup"><span data-stu-id="31d77-116">If a Configuration is taking a long time and you want to stop it, you can use [Stop-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Stop-DscConfiguration) to stop application on the local Node.</span></span>

```powershell
Stop-DSCConfiguration -Force
```

<span data-ttu-id="31d77-117">によって返されるジョブ オブジェクトを介したジョブの状態を表示するには完了すると、 [Get-job](/powershell/module/microsoft.powershell.core/get-job)します。</span><span class="sxs-lookup"><span data-stu-id="31d77-117">Once complete, you can view the status of the jobs through the job object returned by [Get-Job](/powershell/module/microsoft.powershell.core/get-job).</span></span>

```powershell
$job = Get-Job
$job.ChildJobs
```

```output
Id     Name            PSJobTypeName   State         HasMoreData     Location             Command
--     ----            -------------   -----         -----------     --------             -------
49     Job49           Configuratio... Completed     True            localhost            Start-DSCConfiguration...
50     Job50           Configuratio... Completed     True            server02             Start-DSCConfiguration...
```

<span data-ttu-id="31d77-118">参照してください、 **Verbose**出力を表示する、次のコマンドを使用して、 **Verbose**各ストリーム**ChildJob**します。</span><span class="sxs-lookup"><span data-stu-id="31d77-118">To see the **Verbose** output, use the following commands to view the **Verbose** stream for each **ChildJob**.</span></span> <span data-ttu-id="31d77-119">PowerShell ジョブの詳細についてを参照してください。 [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)します。</span><span class="sxs-lookup"><span data-stu-id="31d77-119">For more about PowerShell jobs, see [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs).</span></span>

```powershell
# View the verbose output of the localhost job using array indexing.
$job.ChildJobs[0].Verbose
```

```output
Perform operation 'Invoke CimMethod' with following parameters, ''methodName' = SendConfigurationApply,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' = root/Microsoft/Windows/DesiredStateConfiguration'.
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

<span data-ttu-id="31d77-120">PowerShell 5.0 以降、`-UseExisting`にパラメーターが追加された`Start-DSCConfiguration`します。</span><span class="sxs-lookup"><span data-stu-id="31d77-120">Beginning in PowerShell 5.0, the `-UseExisting` parameter was added to `Start-DSCConfiguration`.</span></span> <span data-ttu-id="31d77-121">指定して`-UseExisting`で指定されたいずれかの代わりに適用された既存の構成を使用するコマンドレットに指示する、`-Path`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="31d77-121">By specifying `-UseExisting`, you instruct the cmdlet to use the existing applied Configuration instead of one specified by the `-Path` parameter.</span></span>

```powershell
Start-DSCConfiguration -UseExisting -Verbose -Wait
```

## <a name="test-a-configuration"></a><span data-ttu-id="31d77-122">構成をテストします。</span><span class="sxs-lookup"><span data-stu-id="31d77-122">Test a Configuration</span></span>

<span data-ttu-id="31d77-123">使用して現在適用されている構成をテストする[Test-dscconfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)します。</span><span class="sxs-lookup"><span data-stu-id="31d77-123">You can test a currently applied Configuration using [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration).</span></span> <span data-ttu-id="31d77-124">`Test-DSCConfiguration` 戻ります`True`ノードが、準拠している場合と`False`でない場合。</span><span class="sxs-lookup"><span data-stu-id="31d77-124">`Test-DSCConfiguration` will return `True` if the Node is compliant, and `False` if it is not.</span></span>

```powershell
Test-DSCConfiguration
```

<span data-ttu-id="31d77-125">PowerShell 5.0 以降、`-Detailed`のコレクションを含むオブジェクトを返すパラメーターが追加された**ResourcesInDesiredState**と**ResourcesNotInDesiredState**</span><span class="sxs-lookup"><span data-stu-id="31d77-125">Beginning in PowerShell 5.0, the `-Detailed` parameter was added which returns an object with collections for **ResourcesInDesiredState** and **ResourcesNotInDesiredState**</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

<span data-ttu-id="31d77-126">PowerShell 5.0 以降を適用することがなく、構成をテストできます。</span><span class="sxs-lookup"><span data-stu-id="31d77-126">Beginning in PowerShell 5.0 you can test a Configuration without applying it.</span></span> <span data-ttu-id="31d77-127">`-ReferenceConfiguration`パラメーターは、テスト対象のノードに".mof"ファイルのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="31d77-127">The `-ReferenceConfiguration` parameter accepts the path of a ".mof" file to test the Node against.</span></span> <span data-ttu-id="31d77-128">いいえ**設定**ノードに対してアクションが実行されます。</span><span class="sxs-lookup"><span data-stu-id="31d77-128">No **Set** actions are taken against the Node.</span></span> <span data-ttu-id="31d77-129">PowerShell 4.0 では、それを適用せず、構成をテストする回避策がありますが、ここでは説明しません。</span><span class="sxs-lookup"><span data-stu-id="31d77-129">In PowerShell 4.0, there are workarounds to test a Configuration without applying it, but they are not discussed here.</span></span>

## <a name="get-configuration-values"></a><span data-ttu-id="31d77-130">構成値を取得します。</span><span class="sxs-lookup"><span data-stu-id="31d77-130">Get Configuration Values</span></span>

<span data-ttu-id="31d77-131">[Get-dscconfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration)コマンドレットは、現在適用されている構成で構成されているリソースの現在の値を返します。</span><span class="sxs-lookup"><span data-stu-id="31d77-131">The [Get-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Get-DscConfiguration) cmdlet returns the current values for any configured resources in the currently applied Configuration.</span></span>

```powershell
Get-DSCConfiguration
```

<span data-ttu-id="31d77-132">正常に適用されている場合、サンプルの構成からの出力は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="31d77-132">Output from our sample Configuration would look like this if applied successfully.</span></span>

```output
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

## <a name="get-configuration-status"></a><span data-ttu-id="31d77-133">構成を状態します。</span><span class="sxs-lookup"><span data-stu-id="31d77-133">Get Configuration Status</span></span>

<span data-ttu-id="31d77-134">PowerShell 5.0 以降、 [Get-dscconfigurationstatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus)コマンドレットを使用すると、ノードに適用される構成の履歴を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31d77-134">Beginning in PowerShell 5.0 the [Get-DSCConfigurationStatus](/powershell/module/PSDesiredStateConfiguration/Get-DscConfigurationStatus) cmdlet allows you to see the history of applied Configurations to the node.</span></span> <span data-ttu-id="31d77-135">PowerShell DSC の追跡に適用される最後の {{N}} 構成**プッシュ**または**プル**モード。</span><span class="sxs-lookup"><span data-stu-id="31d77-135">PowerShell DSC keeps track of the last {{N}} Configurations applied in **Push** or **Pull** mode.</span></span> <span data-ttu-id="31d77-136">これが含まれる*整合性*チェック、LCM によって実行します。</span><span class="sxs-lookup"><span data-stu-id="31d77-136">This includes any *consistency* checks executed by the LCM.</span></span> <span data-ttu-id="31d77-137">既定では、`Get-DSCConfigurationStatus`最後の履歴エントリのみを示します。</span><span class="sxs-lookup"><span data-stu-id="31d77-137">By default, `Get-DSCConfigurationStatus` shows you the last history entry only.</span></span>

```powershell
Get-DSCConfigurationStatus
```

```output
Status     StartDate                 Type            Mode  RebootRequested      NumberOfResources
------     ---------                 ----            ----  ---------------      -----------------
Success    11/27/2018 7:18:40 AM     Consistency     PUSH  False                1
```

<span data-ttu-id="31d77-138">使用して、`-All`パラメーターをすべての構成の状態の履歴を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31d77-138">Use the `-All` parameter to see all Configuration Status history.</span></span>

> [!NOTE]
> <span data-ttu-id="31d77-139">簡潔にするための出力が切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="31d77-139">Output is truncated for brevity.</span></span>

```powershell
Get-DSCConfigurationStatus -All
```

```output
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

## <a name="manage-configuration-documents"></a><span data-ttu-id="31d77-140">構成ドキュメントを管理します。</span><span class="sxs-lookup"><span data-stu-id="31d77-140">Manage Configuration Documents</span></span>

<span data-ttu-id="31d77-141">LCM と協力して、ノードの構成を管理**構成ドキュメント**します。</span><span class="sxs-lookup"><span data-stu-id="31d77-141">The LCM manages the Configuration of the Node by working with **Configuration Documents**.</span></span> <span data-ttu-id="31d77-142">これらの".mof"ファイルは、"C:\Windows\System32\Configuration"ディレクトリに存在します。</span><span class="sxs-lookup"><span data-stu-id="31d77-142">These ".mof" files reside in the "C:\Windows\System32\Configuration" directory.</span></span>

<span data-ttu-id="31d77-143">PowerShell 5.0 以降、 [Remove-dscconfigurationdocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument)将来の整合性チェックを停止するか、適用されるときにエラーがある構成を削除するには、".mof"ファイルを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="31d77-143">Beginning in PowerShell 5.0 the [Remove-DSCConfigurationDocument](/powershell/module/PSDesiredStateConfiguration/Remove-DscConfigurationDocument) allows you to remove the ".mof" files to stop future consistency checks or remove a Configuration that has errors when applied.</span></span> <span data-ttu-id="31d77-144">`-Stage`パラメーターを削除する".mof"ファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="31d77-144">The `-Stage` parameter allows you to specify which ".mof" file you want to remove.</span></span>

```powershell
Remove-DSCConfigurationDocument -Stage Current
```

> [!NOTE]
> <span data-ttu-id="31d77-145">PowerShell 4.0 を使用して直接これらの".mof"ファイルを削除することができますも[Remove-item](/powershell/module/microsoft.powershell.management/remove-item)します。</span><span class="sxs-lookup"><span data-stu-id="31d77-145">In PowerShell 4.0, you can still remove these ".mof" files directly using [Remove-Item](/powershell/module/microsoft.powershell.management/remove-item).</span></span>

## <a name="publish-configurations"></a><span data-ttu-id="31d77-146">発行の構成</span><span class="sxs-lookup"><span data-stu-id="31d77-146">Publish Configurations</span></span>

<span data-ttu-id="31d77-147">PowerShell 5.0 以降、 [Publish-dscconfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration)コマンドレットが追加されました。</span><span class="sxs-lookup"><span data-stu-id="31d77-147">Beginning in PowerShell 5.0, the [Publish-DSCConfiguration](/powershell/module/PSDesiredStateConfiguration/Publish-DscConfiguration) cmdlet was added.</span></span> <span data-ttu-id="31d77-148">このコマンドレットを使用すると、リモート コンピューターに適用することがなく".mof"ファイルを発行できます。</span><span class="sxs-lookup"><span data-stu-id="31d77-148">This cmdlet allows you to publish a ".mof" file to remote computers, without applying it.</span></span>

```powershell
Publish-DscConfiguration -Path '$home\WebServer' -ComputerName "ContosoWebServer" -Credential (get-credential Contoso\webadministrator)
```

## <a name="see-also"></a><span data-ttu-id="31d77-149">関連項目</span><span class="sxs-lookup"><span data-stu-id="31d77-149">See also</span></span>

- [<span data-ttu-id="31d77-150">取得、テスト、および設定</span><span class="sxs-lookup"><span data-stu-id="31d77-150">Get, Test, and Set</span></span>](../resources/get-test-set.md)
