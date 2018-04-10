---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 の DSC 機能強化
ms.openlocfilehash: 04bf8ed820d24f1062e05d19c8f3b0c041298979
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="improvements-in-desired-state-configuration-dsc-in-wmf-51"></a><span data-ttu-id="81025-103">WMF 5.1 の Desired State Configuration (DSC) の機能強化</span><span class="sxs-lookup"><span data-stu-id="81025-103">Improvements in Desired State Configuration (DSC) in WMF 5.1</span></span>

## <a name="dsc-class-resource-improvements"></a><span data-ttu-id="81025-104">DSC クラス リソースの機能強化</span><span class="sxs-lookup"><span data-stu-id="81025-104">DSC class resource improvements</span></span>

<span data-ttu-id="81025-105">WMF 5.1 で、次の既知の問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="81025-105">In WMF 5.1, we have fixed the following known issues:</span></span>
* <span data-ttu-id="81025-106">クラスベースの DSC リソースの Get() 関数によって複合/ハッシュ テーブル型が返される場合、Get-DscConfiguration は空の値 (null) やエラーを返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="81025-106">Get-DscConfiguration may return empty values (null) or errors if a complex/hash table type is returned by Get() function of a class-based DSC resource.</span></span>
* <span data-ttu-id="81025-107">Get-DscConfiguration は、RunAs 資格情報が DSC 構成で使用される場合、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="81025-107">Get-DscConfiguration returns error if RunAs credential is used in DSC configuration.</span></span>
* <span data-ttu-id="81025-108">コンポジット構成では、クラス ベースのリソースは使用できません。</span><span class="sxs-lookup"><span data-stu-id="81025-108">Class-based resource cannot be used in a composite configuration.</span></span>
* <span data-ttu-id="81025-109">Start-DscConfiguration は、クラス ベースのリソースに独自の型のプロパティがあると、応答を停止します。</span><span class="sxs-lookup"><span data-stu-id="81025-109">Start-DscConfiguration hangs if class-based resource has a property of its own type.</span></span>
* <span data-ttu-id="81025-110">クラス ベースのリソースは排他リソースとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="81025-110">Class-based resource cannot be used as an exclusive resource.</span></span>


## <a name="dsc-resource-debugging-improvements"></a><span data-ttu-id="81025-111">DSC リソースのデバッグの機能強化</span><span class="sxs-lookup"><span data-stu-id="81025-111">DSC resource debugging improvements</span></span>
<span data-ttu-id="81025-112">WMF 5.0 では、PowerShell デバッガーは、クラス ベースのリソース メソッド (Get/Set/Test) で直接停止しませんでした。</span><span class="sxs-lookup"><span data-stu-id="81025-112">In WMF 5.0, the PowerShell debugger did not stop at the class-based resource method (Get/Set/Test) directly.</span></span>
<span data-ttu-id="81025-113">WMF 5.1 では、このデバッガーは、MOF ベースのリソース メソッドと同様に、クラス ベースのリソース メソッドで停止します。</span><span class="sxs-lookup"><span data-stu-id="81025-113">In WMF 5.1, the debugger stops at the class-based resource method in the same way as for MOF-based resources methods.</span></span>

## <a name="dsc-pull-client-supports-tls-11-and-tls-12"></a><span data-ttu-id="81025-114">DSC プル クライアントは TLS 1.1 と TLS 1.2 をサポート</span><span class="sxs-lookup"><span data-stu-id="81025-114">DSC pull client supports TLS 1.1 and TLS 1.2</span></span>
<span data-ttu-id="81025-115">以前、DSC プル クライアントは HTTPS 接続で SSL3.0 と TLS1.0 にのみ対応していました。</span><span class="sxs-lookup"><span data-stu-id="81025-115">Previously, the DSC pull client only supported SSL3.0 and TLS1.0 over HTTPS connections.</span></span>
<span data-ttu-id="81025-116">より安全なプロトコルを使用するように強制されると、このプル クライアントは動作を停止しました。</span><span class="sxs-lookup"><span data-stu-id="81025-116">When forced to use more secure protocols, the pull client would stop functioning.</span></span>
<span data-ttu-id="81025-117">WMF 5.1 では、DSC プル クライアントは SSL 3.0 をサポートせず、より安全な TLS 1.1 プロトコルと TLS 1.2 プロトコルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="81025-117">In WMF 5.1, the DSC pull client no longer supports SSL 3.0 and adds support for the more secure TLS 1.1 and TLS 1.2 protocols.</span></span>

## <a name="improved-pull-server-registration"></a><span data-ttu-id="81025-118">プル サーバー登録の機能強化</span><span class="sxs-lookup"><span data-stu-id="81025-118">Improved pull server registration</span></span> ##

<span data-ttu-id="81025-119">以前のバージョンの WMF では、ESENT データベースを使用しながら同時に DSC プル サーバーに登録/レポートを要求すると、LCM は登録またはレポートに失敗していました。</span><span class="sxs-lookup"><span data-stu-id="81025-119">In the earlier versions of WMF, simultaneous registrations/reporting requests to a DSC pull server while using the ESENT database would lead to LCM failing to register and/or report.</span></span>
<span data-ttu-id="81025-120">そのような場合、プル サーバーのイベント ログに "既に使用されているインスタンス名" というエラーが記録されました。</span><span class="sxs-lookup"><span data-stu-id="81025-120">In such cases, the event logs on the pull server has the error "Instance Name already in use."</span></span>
<span data-ttu-id="81025-121">これは、マルチスレッド シナリオで ESENT データベースにアクセスするとき、間違ったパターンが使用されることに起因していました。</span><span class="sxs-lookup"><span data-stu-id="81025-121">This was due to an incorrect pattern being used to access the ESENT database in a multi-threaded scenario.</span></span>
<span data-ttu-id="81025-122">WMF 5.1 では、この問題は修正されました。</span><span class="sxs-lookup"><span data-stu-id="81025-122">In WMF 5.1, this issue has been fixed.</span></span>
<span data-ttu-id="81025-123">同時登録または同時レポート (ESENT データベースを含む) が WMF 5.1 では正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="81025-123">Concurrent registrations or reporting (involving ESENT database) works fine in WMF 5.1.</span></span>
<span data-ttu-id="81025-124">この問題は ESENT データベースにのみ関連し、OLEDB データベースには関連しません。</span><span class="sxs-lookup"><span data-stu-id="81025-124">This issue is applicable only to the ESENT database and does not apply to the OLEDB database.</span></span>

## <a name="enable-circular-log-on-esent-database-instance"></a><span data-ttu-id="81025-125">ESENT データベース インスタンスでの循環ログの有効化</span><span class="sxs-lookup"><span data-stu-id="81025-125">Enable Circular log on ESENT database instance</span></span>
<span data-ttu-id="81025-126">以前のバージョンの DSC-PullServer では、データベース インスタンスが循環ログなしで作成されていたため、ESENT データベース ログ ファイルがプルサーバーのディスク領域を占有していました。</span><span class="sxs-lookup"><span data-stu-id="81025-126">In eariler version of DSC-PullServer, the ESENT database log files were filling up the disk space of the pullserver becouse the database instance was being created without circular logging.</span></span> <span data-ttu-id="81025-127">このリリースには、プルサーバーの web.config を使用してインスタンスの循環ログ動作を制御するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="81025-127">In this release, you have the option to control the circular logging behavior of the instance using the web.config of the pullserver.</span></span> <span data-ttu-id="81025-128">既定では、CircularLogging が TRUE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="81025-128">By default CircularLogging is set to TRUE.</span></span>
```
<appSettings>
    <add key="dbprovider" value="ESENT" />
    <add key="dbconnectionstr" value="C:\Program Files\WindowsPowerShell\DscService\Devices.edb" />
    <add key="CheckpointDepthMaxKB" value="512" />
    <add key="UseCircularESENTLogs" value="TRUE" />
  </appSettings>
```
## <a name="pull-partial-configuration-naming-convention"></a><span data-ttu-id="81025-129">部分構成命名規則のプル</span><span class="sxs-lookup"><span data-stu-id="81025-129">Pull partial configuration naming convention</span></span>
<span data-ttu-id="81025-130">以前のリリースでは、部分構成の命名規則は、プル サーバー/サービスの MOF ファイル名はローカル構成マネージャー設定に指定されている部分構成名に一致する必要があり、ローカル構成マネージャー設定は MOF ファイルに組み込まれている構成名に一致する必要があるというものでした。</span><span class="sxs-lookup"><span data-stu-id="81025-130">In the previous release, the naming convention for a partial configuration was that the MOF file name in the pull server/service should match the partial configuration name specified in the local configuration manager settings that in turn must match the configuration name embedded in the MOF file.</span></span>

<span data-ttu-id="81025-131">下のスナップショットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="81025-131">See the snapshots below:</span></span>

<span data-ttu-id="81025-132">•   ローカル構成設定により、あるノードに受信を許可する部分構成が定義されます。</span><span class="sxs-lookup"><span data-stu-id="81025-132">•   Local configuration settings which defines a partial configuration that a node is allowed to receive.</span></span>

![サンプルのメタ構成](../images/MetaConfigPartialOne.png)

<span data-ttu-id="81025-134">•   サンプルの部分構成定義</span><span class="sxs-lookup"><span data-stu-id="81025-134">•   Sample partial configuration definition</span></span>

```powershell
Configuration PartialOne
{
    Node('localhost')
    {
        File test
        {
            DestinationPath = "$env:TEMP\partialconfigexample.txt"
            Contents = 'Partial Config Example'
        }
    }
}
PartialOne
```

<span data-ttu-id="81025-135">•   生成された MOF ファイルに組み込まれている 'ConfigurationName'。</span><span class="sxs-lookup"><span data-stu-id="81025-135">•   'ConfigurationName' embedded in the generated MOF file.</span></span>

![生成された mof ファイルのサンプル](../images/PartialGeneratedMof.png)

<span data-ttu-id="81025-137">•   プル構成リポジトリの FileName</span><span class="sxs-lookup"><span data-stu-id="81025-137">•   FileName in the pull configuration repository</span></span>

![構成リポジトリの FileName](../images/PartialInConfigRepository.png)

<span data-ttu-id="81025-139">Azure Automation サービス名により、MOF ファイルが `<ConfigurationName>.<NodeName>.mof` として生成されました。</span><span class="sxs-lookup"><span data-stu-id="81025-139">Azure Automation service name generated MOF files as `<ConfigurationName>.<NodeName>.mof`.</span></span>
<span data-ttu-id="81025-140">そのため、下の構成は PartialOne.localhost.mof にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="81025-140">So the configuration below compiles to PartialOne.localhost.mof.</span></span>

<span data-ttu-id="81025-141">これで、Azure Automation サービスから部分構成をプルできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="81025-141">This made it impossible to pull one of your partial configuration from Azure Automation service.</span></span>

```powershell
Configuration PartialOne
{
    Node('localhost')
    {
        File test
        {
            DestinationPath = "$env:TEMP\partialconfigexample.txt"
            Contents = 'Partial Config Example'
        }
    }
}
PartialOne
```

<span data-ttu-id="81025-142">WMF 5.1 では、プル サーバー/サービスの部分構成の名前を `<ConfigurationName>.<NodeName>.mof` にできます。</span><span class="sxs-lookup"><span data-stu-id="81025-142">In WMF 5.1, a partial configuration in the pull server/service can be named as `<ConfigurationName>.<NodeName>.mof`.</span></span>
<span data-ttu-id="81025-143">さらに、コンピューターがプル サーバー/サービスから 1 つの構成をプルする場合、プル サーバー構成リポジトリの構成ファイルに任意のファイル名を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="81025-143">Moreover, if a machine is pulling a single configuration from a pull server/service then the configuration file on the pull server configuration repository can have any file name.</span></span>
<span data-ttu-id="81025-144">このように命名規則が柔軟なことから、ノードを部分的に Azure Automation サービスで管理し (ノードの一部の構成が Azure Automation DSC から誘導されます)、部分構成をローカル管理できます。</span><span class="sxs-lookup"><span data-stu-id="81025-144">This naming flexibility allows you to manage your nodes partially by Azure Automation service, where some configuration for your node is coming from Azure Automation DSC and with a partial configuration that you manage locally.</span></span>

<span data-ttu-id="81025-145">以下のメタ構成では、ローカルと Azure Automation サービスの両方で管理されるようにノードが設定されます。</span><span class="sxs-lookup"><span data-stu-id="81025-145">The metaconfiguration below sets up a node to be managed both locally as well as by Azure Automation service.</span></span>

```powershell
  [DscLocalConfigurationManager()]
   Configuration RegistrationMetaConfig
   {
        Settings
        {
            RefreshFrequencyMins = 30
            RefreshMode = "PULL"
        }

        ConfigurationRepositoryWeb web
        {
            ServerURL =  $endPoint
            RegistrationKey = $registrationKey
            ConfigurationNames = $configurationName
        }

        # Partial configuration managed by Azure Automation service.
        PartialConfiguration PartialConfigurationManagedByAzureAutomation
        {
            ConfigurationSource = "[ConfigurationRepositoryWeb]Web"
        }

        # This partial configuration is managed locally.
        PartialConfiguration OnPremisesConfig
        {
            RefreshMode = "PUSH"
            ExclusiveResources = @("Script")
        }

   }

   RegistrationMetaConfig
   Set-DscLocalConfigurationManager -Path .\RegistrationMetaConfig -Verbose
 ```

# <a name="using-psdscrunascredential-with-dsc-composite-resources"></a><span data-ttu-id="81025-146">PsDscRunAsCredential と DSC 複合リソースを使用する</span><span class="sxs-lookup"><span data-stu-id="81025-146">Using PsDscRunAsCredential with DSC composite resources</span></span>

<span data-ttu-id="81025-147">[*PsDscRunAsCredential*](https://msdn.microsoft.com/cs-cz/powershell/dsc/runasuser) と DSC [複合](https://msdn.microsoft.com/en-us/powershell/dsc/authoringresourcecomposite)リソースが使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="81025-147">We have added support for using [*PsDscRunAsCredential*](https://msdn.microsoft.com/cs-cz/powershell/dsc/runasuser) with DSC [Composite](https://msdn.microsoft.com/en-us/powershell/dsc/authoringresourcecomposite) resources.</span></span>

<span data-ttu-id="81025-148">構成内で複合リソースを使用するとき、PsDscRunAsCredential の値を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="81025-148">You can now specify a value for PsDscRunAsCredential when using composite resources inside configurations.</span></span>
<span data-ttu-id="81025-149">指定されると、すべてのリソースが複合リソース内で RunAs ユーザーとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="81025-149">When specified, all resources run inside a composite resource as a RunAs user.</span></span>
<span data-ttu-id="81025-150">複合リソースが別の複合リソースを呼び出す場合、そのリソースのすべても RunAs ユーザーとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="81025-150">If a composite resource calls another composite resource, all of its resources are also executed as RunAs user.</span></span>
<span data-ttu-id="81025-151">RunAs 資格情報が複合リソース階層のあらゆるレベルに配信されます。</span><span class="sxs-lookup"><span data-stu-id="81025-151">RunAs credentials are propagated to any level of the composite resource hierarchy.</span></span>
<span data-ttu-id="81025-152">複合リソース内の何らかのリソースにより PsDscRunAsCredential の独自の値が指定される場合、構成コンパイル中に結合エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="81025-152">If any resource inside a composite resource specifies its own value for PsDscRunAsCredential, a merge error results during configuration compilation.</span></span>

<span data-ttu-id="81025-153">この例は、PSDesiredStateConfiguration モジュールに含まれている [WindowsFeatureSet](https://msdn.microsoft.com/en-us/powershell/wmf/dsc_newresources) 複合リソースの利用を示しています。</span><span class="sxs-lookup"><span data-stu-id="81025-153">This example shows usage with [WindowsFeatureSet](https://msdn.microsoft.com/en-us/powershell/wmf/dsc_newresources) composite resource included in PSDesiredStateConfiguration module.</span></span>



```powershell

Configuration InstallWindowsFeature
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    Node $AllNodes.NodeName
    {
        WindowsFeatureSet features
        {
            Name = @("Telnet-Client","SNMP-Service")
            Ensure = "Present"
            IncludeAllSubFeature = $true
            PsDscRunAsCredential = Get-Credential
        }
    }

}

$configData = @{
    AllNodes = @(
        @{
            NodeName             = 'localhost'
            PSDscAllowDomainUser = $true
            CertificateFile      = 'C:\publicKeys\targetNode.cer'
            Thumbprint           = '7ee7f09d-4be0-41aa-a47f-96b9e3bdec25'
        }
    )
}


InstallWindowsFeature -ConfigurationData $configData

```

##<a name="dsc-module-and-configuration-signing-validations"></a><span data-ttu-id="81025-154">DSC のモジュールと構成の署名検証</span><span class="sxs-lookup"><span data-stu-id="81025-154">DSC module and configuration signing validations</span></span>
<span data-ttu-id="81025-155">DSC では、プル サーバーから管理対象コンピューターに構成とモジュールが配信されます。</span><span class="sxs-lookup"><span data-stu-id="81025-155">In DSC, configurations and modules are distributed to managed computers from the pull server.</span></span>
<span data-ttu-id="81025-156">プル サーバーが侵害された場合、攻撃者はプル サーバーで構成とモジュールを改ざんし、すべての管理対象ノードに配信し、侵害する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81025-156">If the pull server is compromised, an attacker can potentially modify the configurations and modules on the pull server and have it distributed to all managed nodes, compromising all of them.</span></span>

 <span data-ttu-id="81025-157">WMF 5.1 では、DSC はカタログ ファイルと構成 (.MOF) ファイルのデジタル署名の検証に対応しています。</span><span class="sxs-lookup"><span data-stu-id="81025-157">In WMF 5.1, DSC supports validating the digital signatures on catalog and configuration (.MOF) files.</span></span>
<span data-ttu-id="81025-158">この機能では、信頼できる署名者が署名していない、あるいは信頼できる署名者が署名した後に改ざんされた構成ファイルまたはモジュール ファイルの実行が防止されます。</span><span class="sxs-lookup"><span data-stu-id="81025-158">This feature prevents nodes from executing configurations or module files which are not signed by a trusted signer or which have been tampered with after they have been signed by trusted signer.</span></span>



###<a name="how-to-sign-configuration-and-module"></a><span data-ttu-id="81025-159">構成とモジュールに署名する方法</span><span class="sxs-lookup"><span data-stu-id="81025-159">How to sign configuration and module</span></span>
***
* <span data-ttu-id="81025-160">構成ファイル (.MOF): 既存の PowerShell コマンドレット [Set-AuthenticodeSignature](https://technet.microsoft.com/library/hh849819.aspx) が拡張され、MOF ファイルの署名に対応しています。</span><span class="sxs-lookup"><span data-stu-id="81025-160">Configuration Files (.MOFs): The existing PowerShell cmdlet [Set-AuthenticodeSignature](https://technet.microsoft.com/library/hh849819.aspx) is extended to support signing of MOF files.</span></span>
* <span data-ttu-id="81025-161">モジュール: モジュールの署名は、次の手順を利用し、対応するモジュール カタログに署名することで完了します:</span><span class="sxs-lookup"><span data-stu-id="81025-161">Modules: Signing of modules is done by signing the corresponding module catalog using the following steps:</span></span>
    1. <span data-ttu-id="81025-162">カタログ ファイルの作成: カタログ ファイルには、暗号法のハッシュまたは拇印の集まりが含まれています。</span><span class="sxs-lookup"><span data-stu-id="81025-162">Create a catalog file: A catalog file contains a collection of cryptographic hashes or thumbprints.</span></span>
       <span data-ttu-id="81025-163">拇印はそれぞれ、モジュールに含まれるファイルに対応します。</span><span class="sxs-lookup"><span data-stu-id="81025-163">Each thumbprint corresponds to a file that is included in the module.</span></span>
       <span data-ttu-id="81025-164">新しいコマンドレット [New-FileCatalog](https://technet.microsoft.com/library/cc732148.aspx) が追加され、ユーザーは自分のモジュールのカタログ ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="81025-164">The new cmdlet [New-FileCatalog](https://technet.microsoft.com/library/cc732148.aspx), has been added to enable users to create a catalog file for their module.</span></span>
    2. <span data-ttu-id="81025-165">カタログ ファイルの署名: [Set-AuthenticodeSignature](https://technet.microsoft.com/library/hh849819.aspx) を利用し、カタログ ファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="81025-165">Sign the catalog file: Use [Set-AuthenticodeSignature](https://technet.microsoft.com/library/hh849819.aspx) to sign the catalog file.</span></span>
    3. <span data-ttu-id="81025-166">モジュール フォルダー内にカタログ ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="81025-166">Place the catalog file inside the module folder.</span></span>
<span data-ttu-id="81025-167">慣例では、モジュール カタログ ファイルは、モジュールと同じ名前のモジュール フォルダーの下に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81025-167">By convention, module catalog file should be placed under the module folder with the same name as the module.</span></span>

###<a name="localconfigurationmanager-settings-to-enable-signing-validations"></a><span data-ttu-id="81025-168">LocalConfigurationManager 設定で署名検証を有効にする</span><span class="sxs-lookup"><span data-stu-id="81025-168">LocalConfigurationManager settings to enable signing validations</span></span>

####<a name="pull"></a><span data-ttu-id="81025-169">プル</span><span class="sxs-lookup"><span data-stu-id="81025-169">Pull</span></span>
<span data-ttu-id="81025-170">ノードの LocalConfigurationManager は、その現在の設定に基づき、モジュールと構成の署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="81025-170">The LocalConfigurationManager of a node performs signing validation of modules and configurations based on its current settings.</span></span>
<span data-ttu-id="81025-171">既定では、署名検証は無効です。</span><span class="sxs-lookup"><span data-stu-id="81025-171">By default, signature validation is disabled.</span></span>
<span data-ttu-id="81025-172">署名検証は、‘SignatureValidation’ ブロックを下の図のようにノードのメタ構成定義に追加することで有効にできます:</span><span class="sxs-lookup"><span data-stu-id="81025-172">Signature validation can enabled by adding the ‘SignatureValidation’ block to the meta-configuration definition of the node as shown below:</span></span>

```powershell
[DSCLocalConfigurationManager()]
Configuration EnableSignatureValidation
{
    Settings
    {
        RefreshMode = 'PULL'
    }

    ConfigurationRepositoryWeb pullserver{
      ConfigurationNames = 'sql'
      ServerURL = 'http://localhost:8080/PSDSCPullServer/PSDSCPullServer.svc'
      AllowUnsecureConnection = $true
      RegistrationKey = 'd6750ff1-d8dd-49f7-8caf-7471ea9793fc' # Replace this with correct registration key.
    }
    SignatureValidation validations{
        # By default, LCM uses the default Windows trusted publisher store to validate the certificate chain. If TrustedStorePath property is specified, LCM uses this custom store for retrieving the trusted publishers to validate the content.
        TrustedStorePath = 'Cert:\LocalMachine\DSCStore'
        SignedItemType = 'Configuration','Module'         # This is a list of DSC artifacts, for which LCM need to verify their digital signature before executing them on the node.
    }

}
EnableSignatureValidation
Set-DscLocalConfigurationManager -Path .\EnableSignatureValidation -Verbose
 ```

<span data-ttu-id="81025-173">ノードに上記のメタ構成を設定すると、ダウンロードした構成とモジュールで署名を検証できます。</span><span class="sxs-lookup"><span data-stu-id="81025-173">Setting the above metaconfiguration on a node enables signature validation on downloaded configurations and modules.</span></span>
<span data-ttu-id="81025-174">ローカル構成マネージャーは次の手順でデジタル署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="81025-174">The Local Configuration Manager performs the following steps to verify the digital signatures.</span></span>

1. <span data-ttu-id="81025-175">構成ファイル (.MOF) の署名が有効であることを検証します。</span><span class="sxs-lookup"><span data-stu-id="81025-175">Verify the signature on a configuration file (.MOF) is valid.</span></span>
   <span data-ttu-id="81025-176">これは PowerShell コマンドレット [Get-AuthenticodeSignature](https://technet.microsoft.com/library/hh849805.aspx) を使用します。このコマンドレットは 5.1 で拡張され、MOF 署名検証に対応しています。</span><span class="sxs-lookup"><span data-stu-id="81025-176">It uses the PowerShell cmdlet [Get-AuthenticodeSignature](https://technet.microsoft.com/library/hh849805.aspx), which is extended in 5.1 to support MOF signature validation.</span></span>
2. <span data-ttu-id="81025-177">署名者が信頼できることを認定した証明機関を検証します。</span><span class="sxs-lookup"><span data-stu-id="81025-177">Verify the certificate authority that authorized the signer is trusted.</span></span>
3. <span data-ttu-id="81025-178">構成のモジュール/リソース依存性を一時的な場所にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="81025-178">Download module/resource dependencies of the configuration to a temp location.</span></span>
4. <span data-ttu-id="81025-179">モジュール内に含まれるカタログの署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="81025-179">Verify the signature of the catalog included inside the module.</span></span>
    * <span data-ttu-id="81025-180">`<moduleName>.cat` ファイルを見つけ、コマンドレット [Get-AuthenticodeSignature](https://technet.microsoft.com/library/hh849805.aspx) でその署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="81025-180">Find a `<moduleName>.cat` file and verify its signature using the cmdlet  [Get-AuthenticodeSignature](https://technet.microsoft.com/library/hh849805.aspx).</span></span>
    * <span data-ttu-id="81025-181">署名者が信頼できることを認定した証明機関を検証します。</span><span class="sxs-lookup"><span data-stu-id="81025-181">Verify the certification authority that authenticated the signer is trusted.</span></span>
    * <span data-ttu-id="81025-182">新しいコマンドレット [Test-FileCatalog](https://technet.microsoft.com/library/cc732148.aspx) を利用し、モジュールのコンテンツが改ざんされていないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="81025-182">Verify the content of the modules has not been tampered using the new cmdlet [Test-FileCatalog](https://technet.microsoft.com/library/cc732148.aspx).</span></span>
5. <span data-ttu-id="81025-183">$env:ProgramFiles\WindowsPowerShell\Modules\ にモジュールをインストールする</span><span class="sxs-lookup"><span data-stu-id="81025-183">Install-Module to $env:ProgramFiles\WindowsPowerShell\Modules\\</span></span>
6. <span data-ttu-id="81025-184">プロセス構成</span><span class="sxs-lookup"><span data-stu-id="81025-184">Process configuration</span></span>

> <span data-ttu-id="81025-185">注: モジュール カタログと構成の署名検証は、構成がシステムに最初に適用されるときか、モジュールがダウンロードされ、インストールされるときにのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="81025-185">Note: Signature validation on module-catalog and configuration is only performed when the configuration is applied to the system for the first time or when the module is downloaded and installed.</span></span>
<span data-ttu-id="81025-186">整合性実行では、Current.mof やそのモジュール依存性の署名は検証されません。</span><span class="sxs-lookup"><span data-stu-id="81025-186">Consistency runs do not validate the signature of Current.mof or its module dependencies.</span></span>
<span data-ttu-id="81025-187">何らかの段階で検証に失敗した場合、たとえば、プル サーバーからプルされた構成に署名がされていない場合、構成の処理が中止となり、下にエラーが表示されます。一時ファイルはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="81025-187">If verification has failed at any stage, for instance, if the configuration pulled from the pull server is unsigned, then processing of the configuration terminates with the error shown below and all temporary files are deleted.</span></span>

![構成のエラー出力のサンプル](../images/PullUnsignedConfigFail.png)

<span data-ttu-id="81025-189">同様に、カタログに署名のないモジュールがプルされると次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="81025-189">Similarly, pulling a module whose catalog is not signed results in the following error:</span></span>

![モジュールのエラー出力のサンプル](../images/PullUnisgnedCatalog.png)

####<a name="push"></a><span data-ttu-id="81025-191">プッシュ</span><span class="sxs-lookup"><span data-stu-id="81025-191">Push</span></span>
<span data-ttu-id="81025-192">プッシュで配信された構成は、ノードに届く前にその出所で改ざんされていた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="81025-192">A configuration delivered by using push might be tampered with at its source before it delivered to the node.</span></span>
<span data-ttu-id="81025-193">ローカル構成マネージャーは、プッシュまたは公開された構成に対して同様の署名検証手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="81025-193">The Local Configuration Manager performs similar signature validation steps for pushed or published configuration(s).</span></span>
<span data-ttu-id="81025-194">以下は、プッシュの署名検証の完全例です。</span><span class="sxs-lookup"><span data-stu-id="81025-194">Below is a complete example of signature validation for push.</span></span>

* <span data-ttu-id="81025-195">ノードで署名検証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="81025-195">Enable signature validation on the node.</span></span>

```powershell
[DSCLocalConfigurationManager()]
Configuration EnableSignatureValidation
{
    Settings
    {
        RefreshMode = 'PUSH'
    }
    SignatureValidation validations{
        TrustedStorePath = 'Cert:\LocalMachine\DSCStore'
        SignedItemType =  'Configuration','Module'
    }

}
EnableSignatureValidation
Set-DscLocalConfigurationManager -Path .\EnableSignatureValidation -Verbose
```
* <span data-ttu-id="81025-196">サンプル構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="81025-196">Create a sample configuration file.</span></span>

```powershell
# Sample configuration
Configuration Test
{

    File foo
    {
        DestinationPath =  "$env:TEMP\signingTest.txt"
        Contents = "ABC"
    }
}
Test
```

* <span data-ttu-id="81025-197">署名のない構成ファイルをノードにプッシュしてみます。</span><span class="sxs-lookup"><span data-stu-id="81025-197">Try pushing the unsigned configuration file in to the node.</span></span>

```powershell
Start-DscConfiguration -Path .\Test -Wait -Verbose -Force
```
![ErrorUnsignedMofPushed](../images/PushUnsignedMof.png)

* <span data-ttu-id="81025-199">コード署名証明書を利用し、構成ファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="81025-199">Sign the configuration file using code-signing certificate.</span></span>

![SignMofFile](../images/SignMofFile.png)

* <span data-ttu-id="81025-201">署名された MOF ファイルをプッシュしてみます。</span><span class="sxs-lookup"><span data-stu-id="81025-201">Try pushing the signed MOF file.</span></span>

![SignMofFile](../images/PushSignedMof.png)