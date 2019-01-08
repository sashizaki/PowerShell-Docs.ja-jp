---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 取得-テスト-設定
ms.openlocfilehash: e46710954679bf20f4536c6efbcbd4dafd9e629e
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402574"
---
# <a name="get-test-set"></a><span data-ttu-id="14627-103">取得-テスト-設定</span><span class="sxs-lookup"><span data-stu-id="14627-103">Get-Test-Set</span></span>

><span data-ttu-id="14627-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="14627-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

![取得、テスト、および設定](/media/get-test-set.png)

<span data-ttu-id="14627-106">PowerShell Desired State Configuration は構築、**取得**、**テスト**、および**設定**プロセス。</span><span class="sxs-lookup"><span data-stu-id="14627-106">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="14627-107">DSC[リソース](resources.md)それぞれにこれらの各操作を完了する方法が含まれています。</span><span class="sxs-lookup"><span data-stu-id="14627-107">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span> <span data-ttu-id="14627-108">[構成](../configurations/configurations.md)、リソースのためのパラメーターになるキーを入力するリソースのブロックを定義する**取得**、**テスト**、および**設定**メソッド。</span><span class="sxs-lookup"><span data-stu-id="14627-108">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="14627-109">構文は、**サービス**リソース ブロック。</span><span class="sxs-lookup"><span data-stu-id="14627-109">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="14627-110">**サービス**リソースは、Windows サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="14627-110">The **Service** resource configures Windows services.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

<span data-ttu-id="14627-111">**取得**、**テスト**、および**設定**のメソッド、**サービス**リソースでこれらの値をそのまま使用するパラメーターのブロックが必要があります。</span><span class="sxs-lookup"><span data-stu-id="14627-111">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

```powershell
    param
    (
        [parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [System.String]
        $Name,

        [System.String]
        [ValidateSet("Automatic", "Manual", "Disabled")]
        $StartupType,

        [System.String]
        [ValidateSet("LocalSystem", "LocalService", "NetworkService")]
        $BuiltInAccount,

        [System.Management.Automation.PSCredential]
        [ValidateNotNull()]
        $Credential,

        [System.String]
        [ValidateSet("Running", "Stopped")]
        $State="Running",

        [System.String]
        [ValidateNotNullOrEmpty()]
        $DisplayName,

        [System.String]
        [ValidateNotNullOrEmpty()]
        $Description,

        [System.String]
        [ValidateNotNullOrEmpty()]
        $Path,

        [System.String[]]
        [ValidateNotNullOrEmpty()]
        $Dependencies,

        [System.String]
        [ValidateSet("Present", "Absent")]
        $Ensure="Present"
    )
```

> [!NOTE]
> <span data-ttu-id="14627-112">言語とリソースを定義するために使用する方法を決定する方法、**取得**、**テスト**、および**設定**メソッドが定義されます。</span><span class="sxs-lookup"><span data-stu-id="14627-112">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="14627-113">**サービス**リソースの 1 つの必須キーのみが (`Name`)、**サービス**ブロックのリソースのように単純な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="14627-113">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

```powershell
Configuration TestConfig
{
    Import-DSCResource -Name Service
    Node localhost
    {
        Service "MyService"
        {
            Name = "Spooler"
        }
    }
}
```

<span data-ttu-id="14627-114">上記の構成をコンパイルするときに、キーの指定した値が生成される".mof"ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="14627-114">When you compile the Configuration above, the values you specify for a key are stored in the ".mof" file that is generated.</span></span> <span data-ttu-id="14627-115">詳細については、次を参照してください。 [MOF](/windows/desktop/wmisdk/managed-object-format--mof-)します。</span><span class="sxs-lookup"><span data-stu-id="14627-115">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

```
instance of MSFT_ServiceResource as $MSFT_ServiceResource1ref
{
SourceInfo = "::5::1::Service";
 ModuleName = "PsDesiredStateConfiguration";
 ResourceID = "[Service]MyService";
 Name = "Spooler";

ModuleVersion = "1.0";

 ConfigurationName = "Test";

};
```

<span data-ttu-id="14627-116">適用すると、[ローカル構成マネージャー](../managing-nodes/metaConfig.md)に渡すし、値"Spooler"、".mof"ファイルから読み取るは、`-Name`のパラメーター、**取得**、**テスト**、**設定**の"MyService"のインスタンスのメソッド、**サービス**リソース。</span><span class="sxs-lookup"><span data-stu-id="14627-116">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) will read the value "Spooler" from the ".mof" file, and pass it to the `-Name` parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="14627-117">取得</span><span class="sxs-lookup"><span data-stu-id="14627-117">Get</span></span>

<span data-ttu-id="14627-118">**取得**リソースのメソッドは、ターゲット ノードで構成されているように、リソースの状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="14627-118">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="14627-119">この状態として返されます、 [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables)します。</span><span class="sxs-lookup"><span data-stu-id="14627-119">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span> <span data-ttu-id="14627-120">キー、 **hashtable**リソースは、構成可能な値、またはパラメーターになります。</span><span class="sxs-lookup"><span data-stu-id="14627-120">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="14627-121">**取得**メソッドは、マップに直接、 [Get-dscconfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="14627-121">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="14627-122">呼び出すと`Get-DSCConfiguration`、LCM の実行、**取得**現在適用されている構成内の各リソースのメソッド。</span><span class="sxs-lookup"><span data-stu-id="14627-122">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="14627-123">LCM は、対応する各リソース インスタンスにパラメーターとして".mof"ファイルに格納されているキーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="14627-123">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="14627-124">これはサンプルの出力から、**サービス**"Spooler"サービスを構成するリソース。</span><span class="sxs-lookup"><span data-stu-id="14627-124">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

```output
ConfigurationName    : Test
DependsOn            :
ModuleName           : PsDesiredStateConfiguration
ModuleVersion        : 1.1
PsDscRunAsCredential :
ResourceId           : [Service]Spooler
SourceInfo           :
BuiltInAccount       : LocalSystem
Credential           :
Dependencies         : {RPCSS, http}
Description          : This service spools print jobs and handles interaction with the printer.  If you turn off
                       this service, you won’t be able to print or see your printers.
DisplayName          : Print Spooler
Ensure               :
Name                 : Spooler
Path                 : C:\WINDOWS\System32\spoolsv.exe
StartupType          : Automatic
State                : Running
Status               :
PSComputerName       :
CimClassName         : MSFT_ServiceResource
```

<span data-ttu-id="14627-125">現在の値のプロパティを表示で構成可能な出力、**サービス**リソース。</span><span class="sxs-lookup"><span data-stu-id="14627-125">The output shows the current value properties configurable by the **Service** resource.</span></span>

```syntax
Service [String] #ResourceName
{
    Name = [string]
    [BuiltInAccount = [string]{ LocalService | LocalSystem | NetworkService }]
    [Credential = [PSCredential]]
    [Dependencies = [string[]]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [DisplayName = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Path = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [StartupType = [string]{ Automatic | Disabled | Manual }]
    [State = [string]{ Running | Stopped }]
}
```

## <a name="test"></a><span data-ttu-id="14627-126">Server1</span><span class="sxs-lookup"><span data-stu-id="14627-126">Test</span></span>

<span data-ttu-id="14627-127">**テスト**リソースのメソッドは、ターゲット ノードが現在に準拠して、リソースのかどうかを判断*目的の状態を*します。</span><span class="sxs-lookup"><span data-stu-id="14627-127">The **Test** method of a resource determines if the target node is currently compliant with the resource's *desired state*.</span></span> <span data-ttu-id="14627-128">**テスト**メソッドを返します。`$True`または`$False`ノードが準拠しているかどうかを示すためにのみです。</span><span class="sxs-lookup"><span data-stu-id="14627-128">The **Test** method returns `$True` or `$False` only to indicate whether the Node is compliant.</span></span>
<span data-ttu-id="14627-129">呼び出すと[Test-dscconfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)、LCM の呼び出し、**テスト**現在適用されている構成内の各リソースのメソッド。</span><span class="sxs-lookup"><span data-stu-id="14627-129">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="14627-130">LCM は、対応する各リソース インスタンスにパラメーターとして".mof"ファイルに格納されているキーの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="14627-130">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="14627-131">場合、結果の個々 のリソースの**テスト**は`$False`、`Test-DSCConfiguration`返します`$False`ノードが準拠していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="14627-131">If the result of any individual resource's **Test** is `$False`, `Test-DSCConfiguration` returns `$False` indicating that the Node is not compliant.</span></span> <span data-ttu-id="14627-132">場合すべてのリソースの**テスト**メソッドが返す`$True`、`Test-DSCConfiguration`返します`$True`ノードが準拠していることを示します。</span><span class="sxs-lookup"><span data-stu-id="14627-132">If all resource's **Test** methods return `$True`, `Test-DSCConfiguration` returns `$True` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="14627-133">PowerShell 5.0 以降、`-Detailed`パラメーターが追加されました。</span><span class="sxs-lookup"><span data-stu-id="14627-133">Beginning in PowerShell 5.0, the `-Detailed` parameter was added.</span></span> <span data-ttu-id="14627-134">指定する`-Detailed`により`Test-DSCConfiguration`を準拠、および非準拠リソースの検索結果のコレクションを格納するオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="14627-134">Specifying `-Detailed` causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="14627-135">詳細については、次を参照してください[Test-dscconfiguration。](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span><span class="sxs-lookup"><span data-stu-id="14627-135">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="14627-136">設定</span><span class="sxs-lookup"><span data-stu-id="14627-136">Set</span></span>

<span data-ttu-id="14627-137">**設定**リソースのメソッドが、リソースの準拠するためのノードを強制しようとしています。*目的の状態を*します。</span><span class="sxs-lookup"><span data-stu-id="14627-137">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="14627-138">**設定**メソッドがするものでは**べき等である**、つまり**設定**を複数回実行して、エラーのない同じ結果を常に取得できます。</span><span class="sxs-lookup"><span data-stu-id="14627-138">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span>  <span data-ttu-id="14627-139">実行すると[Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration)、現在適用されている構成内の各リソースを LCM 切り替えます。</span><span class="sxs-lookup"><span data-stu-id="14627-139">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="14627-140">LCM が".mof"ファイルから現在のリソース インスタンスのキーの値を取得し、それらをパラメーターとして使用、**テスト**メソッド。</span><span class="sxs-lookup"><span data-stu-id="14627-140">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="14627-141">場合、**テスト**メソッドを返します。 `$True`、ノードが現在のリソースに準拠して、**設定**メソッドはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="14627-141">If the **Test** method returns `$True`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="14627-142">場合、**テスト**返します`$False`ノードが非対応です。</span><span class="sxs-lookup"><span data-stu-id="14627-142">If the **Test** returns `$False`, the Node is non-compliant.</span></span>  <span data-ttu-id="14627-143">LCM は、リソース インスタンスのキー値としてパラメーターに渡す、リソースの**設定**ノード コンプライアンスを復元する方法。</span><span class="sxs-lookup"><span data-stu-id="14627-143">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="14627-144">指定することによって、`-Verbose`と`-Wait`パラメーターの進行状況を見ることができます、`Start-DSCConfiguration`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="14627-144">By specifying the `-Verbose` and `-Wait` parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="14627-145">この例では、ノードは準拠では既にです。</span><span class="sxs-lookup"><span data-stu-id="14627-145">In this example, the Node is already compliant.</span></span> <span data-ttu-id="14627-146">`Verbose`出力には、ことを示します、**設定**メソッドはスキップされました。</span><span class="sxs-lookup"><span data-stu-id="14627-146">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

```
PS> Start-DSCConfiguration -Verbose -Wait -UseExisting

VERBOSE: Perform operation 'Invoke CimMethod' with following parameters, ''methodName' =
ApplyConfiguration,'className' = MSFT_DSCLocalConfigurationManager,'namespaceName' =
root/Microsoft/Windows/DesiredStateConfiguration'.
VERBOSE: An LCM method call arrived from computer SERVER01 with user sid
S-1-5-21-124525095-708259637-1543119021-1282804.
VERBOSE: [SERVER01]:                            [] Starting consistency engine.
VERBOSE: [SERVER01]:                            [] Checking consistency for current configuration.
VERBOSE: [SERVER01]:                            [DSCEngine] Importing the module
C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\DscResources\MSFT_ServiceResource\MSFT
_ServiceResource.psm1 in force mode.
VERBOSE: [SERVER01]: LCM:  [ Start  Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ Start  Test     ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [[Service]Spooler] Importing the module MSFT_ServiceResource in
force mode.
VERBOSE: [SERVER01]: LCM:  [ End    Test     ]  [[Service]Spooler]  in 0.2540 seconds.
VERBOSE: [SERVER01]: LCM:  [ Skip   Set      ]  [[Service]Spooler]
VERBOSE: [SERVER01]: LCM:  [ End    Resource ]  [[Service]Spooler]
VERBOSE: [SERVER01]:                            [] Consistency check completed.
VERBOSE: Operation 'Invoke CimMethod' complete.
VERBOSE: Time taken for configuration job to complete is 1.379 seconds
```

## <a name="see-also"></a><span data-ttu-id="14627-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="14627-147">See also</span></span>

- [<span data-ttu-id="14627-148">Azure Automation DSC の概要</span><span class="sxs-lookup"><span data-stu-id="14627-148">Azure Automation DSC Overview</span></span>](https://docs.microsoft.com/en-us/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="14627-149">Setting up an SMB pull server (SMB プル サーバーのセットアップ)</span><span class="sxs-lookup"><span data-stu-id="14627-149">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="14627-150">Configuring a pull client (プル クライアントの構成)</span><span class="sxs-lookup"><span data-stu-id="14627-150">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)
