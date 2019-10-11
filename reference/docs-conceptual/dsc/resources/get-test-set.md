---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: Get-Test-Set
ms.openlocfilehash: 42c1df6df2fbf65cbbb8407db613cac2e5b81cfb
ms.sourcegitcommit: 18985d07ef024378c8590dc7a983099ff9225672
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2019
ms.locfileid: "71954289"
---
# <a name="get-test-set"></a><span data-ttu-id="e3c59-103">Get-Test-Set</span><span class="sxs-lookup"><span data-stu-id="e3c59-103">Get-Test-Set</span></span>

><span data-ttu-id="e3c59-104">適用先:Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="e3c59-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

![取得、テスト、および設定](../media/get-test-set.png)

<span data-ttu-id="e3c59-106">PowerShell の Desired State Configuration は、**Get**、**Test**、および **Set** プロセスを中心に構成されています。</span><span class="sxs-lookup"><span data-stu-id="e3c59-106">PowerShell Desired State Configuration is constructed around a **Get**, **Test**, and **Set** process.</span></span> <span data-ttu-id="e3c59-107">DSC の各[リソース](resources.md)には、これらの各操作を完了するためのメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e3c59-107">DSC [resources](resources.md) each contains methods to complete each of these operations.</span></span> <span data-ttu-id="e3c59-108">「[構成](../configurations/configurations.md)」では、リソースの **Get**、**Test**、および **Set** メソッドのパラメーターとなるキーを入力するリソース ブロックを定義します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-108">In a [Configuration](../configurations/configurations.md), you define resource blocks to fill in keys that become parameters for a resource's **Get**, **Test**, and **Set** methods.</span></span>

<span data-ttu-id="e3c59-109">これは **Service** リソース ブロックの構文です。</span><span class="sxs-lookup"><span data-stu-id="e3c59-109">This is the syntax for a **Service** resource block.</span></span> <span data-ttu-id="e3c59-110">**Service** リソースでは、Windows サービスを構成します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-110">The **Service** resource configures Windows services.</span></span>

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

<span data-ttu-id="e3c59-111">**Service** リソースの **Get**、**Test**、および **Set** メソッドには、その値を受け入れるパラメーター ブロックがあります。</span><span class="sxs-lookup"><span data-stu-id="e3c59-111">The **Get**, **Test**, and **Set** methods of the **Service** resource will have parameter blocks that accept these values.</span></span>

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
> <span data-ttu-id="e3c59-112">リソースの定義に使用される言語とメソッドによって、**Get**、**Test**、および **Set** の各メソッドの定義方法が決まります。</span><span class="sxs-lookup"><span data-stu-id="e3c59-112">The language and method used to define the resource determines how the **Get**, **Test**, and **Set** methods will be defined.</span></span>

<span data-ttu-id="e3c59-113">**Service** リソースには必要なキーが 1 つしかないため (`Name`)、**Service** ブロック リソースは次のように単純になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e3c59-113">Because the **Service** resource only has one required key (`Name`), a **Service** block resource could be as simple as this:</span></span>

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

<span data-ttu-id="e3c59-114">上記の Configuration をコンパイルすると、キーに指定した値は生成された ".mof" ファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="e3c59-114">When you compile the Configuration above, the values you specify for a key are stored in the ".mof" file that is generated.</span></span> <span data-ttu-id="e3c59-115">詳細については、[MOF](/windows/desktop/wmisdk/managed-object-format--mof-) に関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3c59-115">For more information, see [MOF](/windows/desktop/wmisdk/managed-object-format--mof-).</span></span>

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

<span data-ttu-id="e3c59-116">適用すると、[ローカル構成マネージャー](../managing-nodes/metaConfig.md) (LCM) によって ".mof" ファイルから値 "Spooler" が読み取られ、それが**サービス** リソースの "MyService" インスタンス用の **Get**、**Test**、および **Set** メソッドの `-Name` パラメーターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="e3c59-116">When applied, the [Local Configuration Manager](../managing-nodes/metaConfig.md) (LCM) will read the value "Spooler" from the ".mof" file, and pass it to the `-Name` parameter of the **Get**, **Test**, and **Set** methods for the "MyService" instance of the **Service** resource.</span></span>

## <a name="get"></a><span data-ttu-id="e3c59-117">取得</span><span class="sxs-lookup"><span data-stu-id="e3c59-117">Get</span></span>

<span data-ttu-id="e3c59-118">リソースの **Get** メソッドでは、ターゲット ノードに構成されているリソースの状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-118">The **Get** method of a resource, retrieves the state of the resource as it is configured on the target Node.</span></span> <span data-ttu-id="e3c59-119">この状態は[ハッシュテーブル](/powershell/module/microsoft.powershell.core/about/about_hash_tables)として返されます。</span><span class="sxs-lookup"><span data-stu-id="e3c59-119">This state is returned as a [hashtable](/powershell/module/microsoft.powershell.core/about/about_hash_tables).</span></span> <span data-ttu-id="e3c59-120">**ハッシュテーブル**のキーは、リソースが受け入れる構成可能な値、つまりパラメーターになります。</span><span class="sxs-lookup"><span data-stu-id="e3c59-120">The keys of the **hashtable** will be the configurable values, or parameters, the resource accepts.</span></span>

<span data-ttu-id="e3c59-121">**Get** メソッドは、[Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) コマンドレットに直接マップします。</span><span class="sxs-lookup"><span data-stu-id="e3c59-121">The **Get** method maps directly to the [Get-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/get-dscconfiguration) cmdlet.</span></span> <span data-ttu-id="e3c59-122">`Get-DSCConfiguration` を呼び出すと、LCM では現在適用されている構成内の各リソースの **Get** メソッドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-122">When you call `Get-DSCConfiguration`, the LCM runs the **Get** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="e3c59-123">LCM は、".mof" ファイルに格納されているキー値を、対応する各リソース インスタンスへのパラメーターとして使用します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-123">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="e3c59-124">これは、"Spooler" サービスを構成する **Service** リソースの出力例です。</span><span class="sxs-lookup"><span data-stu-id="e3c59-124">This is sample output from a **Service** resource that configures the "Spooler" service.</span></span>

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
                       this service, you won't be able to print or see your printers.
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

<span data-ttu-id="e3c59-125">出力には、**Service** リソースで構成できる現在の値のプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3c59-125">The output shows the current value properties configurable by the **Service** resource.</span></span>

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

## <a name="test"></a><span data-ttu-id="e3c59-126">Server1</span><span class="sxs-lookup"><span data-stu-id="e3c59-126">Test</span></span>

<span data-ttu-id="e3c59-127">リソースの **Test** メソッドでは、ターゲット ノードがリソースの "*望ましい状態*" に現在準拠しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-127">The **Test** method of a resource determines if the target node is currently compliant with the resource's *desired state*.</span></span> <span data-ttu-id="e3c59-128">**Test** メソッドは、Node が準拠しているかどうかのみを示す `$True` または `$False` を返します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-128">The **Test** method returns `$True` or `$False` only to indicate whether the Node is compliant.</span></span>
<span data-ttu-id="e3c59-129">[Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) を呼び出すと、LCM では現在適用されている構成内の各リソースの **Test** メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-129">When you call [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration), the LCM calls the **Test** method of each resource in the currently applied configuration.</span></span> <span data-ttu-id="e3c59-130">LCM は、".mof" ファイルに格納されているキー値を、対応する各リソース インスタンスへのパラメーターとして使用します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-130">The LCM uses the key values stored in the ".mof" file as parameters to each corresponding resource instance.</span></span>

<span data-ttu-id="e3c59-131">個々のリソースの **Test** の結果が `$False` の場合、`Test-DSCConfiguration` は Node が準拠していないことを示す `$False` を返します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-131">If the result of any individual resource's **Test** is `$False`, `Test-DSCConfiguration` returns `$False` indicating that the Node is not compliant.</span></span> <span data-ttu-id="e3c59-132">すべてのリソースの **Test** メソッドが `$True` を返す場合、`Test-DSCConfiguration` は Node が準拠していることを示す `$True` を返します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-132">If all resource's **Test** methods return `$True`, `Test-DSCConfiguration` returns `$True` to indicate that the Node is compliant.</span></span>

```powershell
Test-DSCConfiguration
```

```output
True
```

<span data-ttu-id="e3c59-133">PowerShell 5.0 以降では、`-Detailed` パラメーターが追加されています。</span><span class="sxs-lookup"><span data-stu-id="e3c59-133">Beginning in PowerShell 5.0, the `-Detailed` parameter was added.</span></span> <span data-ttu-id="e3c59-134">`-Detailed` を指定すると、`Test-DSCConfiguration` は準拠および非準拠リソースの結果のコレクションを含むオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-134">Specifying `-Detailed` causes `Test-DSCConfiguration` to return an object containing collections of results for compliant, and non-compliant resources.</span></span>

```powershell
Test-DSCConfiguration -Detailed
```

```output
PSComputerName  ResourcesInDesiredState        ResourcesNotInDesiredState     InDesiredState
--------------  -----------------------        --------------------------     --------------
localhost       {[Service]Spooler}                                            True
```

<span data-ttu-id="e3c59-135">詳細については、[Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration) を参照してください</span><span class="sxs-lookup"><span data-stu-id="e3c59-135">For more information, see [Test-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Test-DSCConfiguration)</span></span>

## <a name="set"></a><span data-ttu-id="e3c59-136">設定</span><span class="sxs-lookup"><span data-stu-id="e3c59-136">Set</span></span>

<span data-ttu-id="e3c59-137">リソースの **Set** メソッドは、Node がリソースの "*望ましい状態*" に準拠した状態になるように試行します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-137">The **Set** method of a resource attempts to force the Node to become compliant with the resource's *desired state*.</span></span> <span data-ttu-id="e3c59-138">**Set** メソッドは**べき等**であるように意図されています。つまり、**Set** を複数回実行し、エラーなしで常に同じ結果を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="e3c59-138">The **Set** method is meant to be **idempotent**, which means that **Set** could be run multiple times and always get the same result without errors.</span></span>  <span data-ttu-id="e3c59-139">[Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration) を実行すると、LCM では現在適用されている構成内の各リソースが循環処理されます。</span><span class="sxs-lookup"><span data-stu-id="e3c59-139">When you run [Start-DSCConfiguration](/powershell/module/psdesiredstateconfiguration/Start-DSCConfiguration), the LCM cycles through each resource in the currently applied configuration.</span></span> <span data-ttu-id="e3c59-140">LCM では ".mof" ファイルから現在のリソース インスタンスのキー値を取得し、それらを **Test** メソッドのパラメーターとして使用します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-140">The LCM retrieves key values for the current resource instance from the ".mof" file and uses them as parameters for the **Test** method.</span></span> <span data-ttu-id="e3c59-141">**Test** メソッドが `$True` を返した場合、Node は現在のリソースに準拠しているため、**Set** メソッドはスキップされます。</span><span class="sxs-lookup"><span data-stu-id="e3c59-141">If the **Test** method returns `$True`, the Node is compliant with the current resource, and the **Set** method is skipped.</span></span> <span data-ttu-id="e3c59-142">**Test** が `$False` を返した場合、Node は準拠していません。</span><span class="sxs-lookup"><span data-stu-id="e3c59-142">If the **Test** returns `$False`, the Node is non-compliant.</span></span>  <span data-ttu-id="e3c59-143">LCM はリソース インスタンスのキー値をパラメーターとしてリソースの **Set** メソッドに渡し、Node を準拠状態に復元します。</span><span class="sxs-lookup"><span data-stu-id="e3c59-143">The LCM passes the resource instance's key values as parameters to the resource's **Set** method, restoring the Node to compliance.</span></span>

<span data-ttu-id="e3c59-144">`-Verbose` および `-Wait` パラメーターを指定することで、`Start-DSCConfiguration` コマンドレットの進行状況を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e3c59-144">By specifying the `-Verbose` and `-Wait` parameters, you can watch the progress of the `Start-DSCConfiguration` cmdlet.</span></span> <span data-ttu-id="e3c59-145">この例では、Node は既に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="e3c59-145">In this example, the Node is already compliant.</span></span> <span data-ttu-id="e3c59-146">`Verbose` の出力は、**Set** メソッドがスキップされたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3c59-146">The `Verbose` output indicates that the **Set** method was skipped.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e3c59-147">関連項目</span><span class="sxs-lookup"><span data-stu-id="e3c59-147">See also</span></span>

- [<span data-ttu-id="e3c59-148">Azure Automation DSC の概要</span><span class="sxs-lookup"><span data-stu-id="e3c59-148">Azure Automation DSC Overview</span></span>](https://docs.microsoft.com/azure/automation/automation-dsc-overview)
- [<span data-ttu-id="e3c59-149">Setting up an SMB pull server (SMB プル サーバーのセットアップ)</span><span class="sxs-lookup"><span data-stu-id="e3c59-149">Setting up an SMB pull server</span></span>](../pull-server/pullServerSMB.md)
- [<span data-ttu-id="e3c59-150">Configuring a pull client (プル クライアントの構成)</span><span class="sxs-lookup"><span data-stu-id="e3c59-150">Configuring a pull client</span></span>](../pull-server/pullClientConfigID.md)
