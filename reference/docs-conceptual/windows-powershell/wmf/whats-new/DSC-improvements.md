---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 の DSC 機能強化
ms.openlocfilehash: 445d0f7bb54c6b21b6af26c4174f3d6422caf6dd
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771551"
---
# <a name="improvements-in-desired-state-configuration-dsc-in-wmf-51"></a><span data-ttu-id="5a9db-103">WMF 5.1 の Desired State Configuration (DSC) の機能強化</span><span class="sxs-lookup"><span data-stu-id="5a9db-103">Improvements in Desired State Configuration (DSC) in WMF 5.1</span></span>

## <a name="dsc-class-resource-improvements"></a><span data-ttu-id="5a9db-104">DSC クラス リソースの機能強化</span><span class="sxs-lookup"><span data-stu-id="5a9db-104">DSC class resource improvements</span></span>

<span data-ttu-id="5a9db-105">WMF 5.1 で、次の既知の問題を修正しました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-105">In WMF 5.1, we have fixed the following known issues:</span></span>

- <span data-ttu-id="5a9db-106">クラスベースの DSC リソースの Get() 関数によって複合/ハッシュ テーブル型が返される場合、Get-DscConfiguration は空の値 (null) やエラーを返すことがあります。</span><span class="sxs-lookup"><span data-stu-id="5a9db-106">Get-DscConfiguration may return empty values (null) or errors if a complex/hash table type is returned by Get() function of a class-based DSC resource.</span></span>
- <span data-ttu-id="5a9db-107">Get-DscConfiguration は、RunAs 資格情報が DSC 構成で使用される場合、エラーを返します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-107">Get-DscConfiguration returns error if RunAs credential is used in DSC configuration.</span></span>
- <span data-ttu-id="5a9db-108">コンポジット構成では、クラス ベースのリソースは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5a9db-108">Class-based resource cannot be used in a composite configuration.</span></span>
- <span data-ttu-id="5a9db-109">Start-DscConfiguration は、クラス ベースのリソースに独自の型のプロパティがあると、応答を停止します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-109">Start-DscConfiguration hangs if class-based resource has a property of its own type.</span></span>
- <span data-ttu-id="5a9db-110">クラス ベースのリソースは排他リソースとして使用できません。</span><span class="sxs-lookup"><span data-stu-id="5a9db-110">Class-based resource cannot be used as an exclusive resource.</span></span>

## <a name="dsc-resource-debugging-improvements"></a><span data-ttu-id="5a9db-111">DSC リソースのデバッグの機能強化</span><span class="sxs-lookup"><span data-stu-id="5a9db-111">DSC resource debugging improvements</span></span>

<span data-ttu-id="5a9db-112">WMF 5.0 では、PowerShell デバッガーは、クラス ベースのリソース メソッド (Get/Set/Test) で直接停止しませんでした。</span><span class="sxs-lookup"><span data-stu-id="5a9db-112">In WMF 5.0, the PowerShell debugger did not stop at the class-based resource method (Get/Set/Test) directly.</span></span> <span data-ttu-id="5a9db-113">WMF 5.1 では、このデバッガーは、MOF ベースのリソース メソッドと同様に、クラス ベースのリソース メソッドで停止します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-113">In WMF 5.1, the debugger stops at the class-based resource method in the same way as for MOF-based resources methods.</span></span>

## <a name="dsc-pull-client-supports-tls-11-and-tls-12"></a><span data-ttu-id="5a9db-114">DSC プル クライアントは TLS 1.1 と TLS 1.2 をサポート</span><span class="sxs-lookup"><span data-stu-id="5a9db-114">DSC pull client supports TLS 1.1 and TLS 1.2</span></span>

<span data-ttu-id="5a9db-115">以前、DSC プル クライアントは HTTPS 接続で SSL3.0 と TLS1.0 にのみ対応していました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-115">Previously, the DSC pull client only supported SSL3.0 and TLS1.0 over HTTPS connections.</span></span> <span data-ttu-id="5a9db-116">より安全なプロトコルを使用するように強制されると、このプル クライアントは動作を停止しました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-116">When forced to use more secure protocols, the pull client would stop functioning.</span></span> <span data-ttu-id="5a9db-117">WMF 5.1 では、DSC プル クライアントは SSL 3.0 をサポートせず、より安全な TLS 1.1 プロトコルと TLS 1.2 プロトコルをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5a9db-117">In WMF 5.1, the DSC pull client no longer supports SSL 3.0 and adds support for the more secure TLS 1.1 and TLS 1.2 protocols.</span></span>

## <a name="improved-pull-server-registration"></a><span data-ttu-id="5a9db-118">プル サーバー登録の機能強化</span><span class="sxs-lookup"><span data-stu-id="5a9db-118">Improved pull server registration</span></span>

<span data-ttu-id="5a9db-119">以前のバージョンの WMF では、ESENT データベースを使用しながら同時に DSC プル サーバーに登録/レポートを要求すると、LCM は登録またはレポートに失敗していました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-119">In the earlier versions of WMF, simultaneous registrations/reporting requests to a DSC pull server while using the ESENT database would lead to LCM failing to register and/or report.</span></span> <span data-ttu-id="5a9db-120">そのような場合、プル サーバーのイベント ログに "既に使用されているインスタンス名" というエラーが記録されました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-120">In such cases, the event logs on the pull server has the error "Instance Name already in use."</span></span> <span data-ttu-id="5a9db-121">これは、マルチスレッド シナリオで ESENT データベースにアクセスするとき、間違ったパターンが使用されることに起因していました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-121">This was caused by an incorrect pattern being used to access the ESENT database in a multi-threaded scenario.</span></span> <span data-ttu-id="5a9db-122">WMF 5.1 では、この問題は修正されました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-122">In WMF 5.1, this issue has been fixed.</span></span> <span data-ttu-id="5a9db-123">同時登録または同時レポート (ESENT データベースを含む) が WMF 5.1 では正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-123">Concurrent registrations or reporting (involving ESENT database) works fine in WMF 5.1.</span></span> <span data-ttu-id="5a9db-124">この問題は ESENT データベースにのみ関連し、OLEDB データベースには関連しません。</span><span class="sxs-lookup"><span data-stu-id="5a9db-124">This issue is applicable only to the ESENT database and does not apply to the OLEDB database.</span></span>

## <a name="enable-circular-log-on-esent-database-instance"></a><span data-ttu-id="5a9db-125">ESENT データベース インスタンスでの循環ログの有効化</span><span class="sxs-lookup"><span data-stu-id="5a9db-125">Enable Circular log on ESENT database instance</span></span>

<span data-ttu-id="5a9db-126">以前のバージョンの DSC-PullServer では、データベース インスタンスが循環ログなしで作成されていたため、ESENT データベース ログ ファイルがプル サーバーのディスク領域を占有していました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-126">In eariler version of DSC-PullServer, the ESENT database log files were filling up the disk space of the pullserver because the database instance was being created without circular logging.</span></span> <span data-ttu-id="5a9db-127">このリリースには、プルサーバーの web.config を使用してインスタンスの循環ログ動作を制御するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5a9db-127">In this release, you have the option to control the circular logging behavior of the instance using the web.config of the pullserver.</span></span> <span data-ttu-id="5a9db-128">既定では、CircularLogging が TRUE に設定されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-128">By default CircularLogging is set to TRUE.</span></span>

```xml
<appSettings>
    <add key="dbprovider" value="ESENT" />
    <add key="dbconnectionstr" value="C:\Program Files\WindowsPowerShell\DscService\Devices.edb" />
    <add key="CheckpointDepthMaxKB" value="512" />
    <add key="UseCircularESENTLogs" value="TRUE" />
  </appSettings>
```

## <a name="wow64-support-for-configuration-keyword"></a><span data-ttu-id="5a9db-129">構成キーワードの WOW64 サポート</span><span class="sxs-lookup"><span data-stu-id="5a9db-129">WOW64 support for Configuration Keyword</span></span>

<span data-ttu-id="5a9db-130">64 ビット コンピューターの WOW64 で、`Configuration` キーワードがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-130">The `Configuration` keyword is now supported in WOW64 on a 64-bit computer.</span></span> <span data-ttu-id="5a9db-131">これは、64 ビット コンピューターで実行されている Windows PowerShell ISE (x86) などの 32 ビット プロセス内で DSC 構成を定義してコンパイルできることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-131">This means that a DSC configuration can be defined and compiled within a 32-bit process such as Windows PowerShell ISE (x86) running on a 64-bit computer.</span></span>

## <a name="pull-partial-configuration-naming-convention"></a><span data-ttu-id="5a9db-132">部分構成命名規則のプル</span><span class="sxs-lookup"><span data-stu-id="5a9db-132">Pull partial configuration naming convention</span></span>

<span data-ttu-id="5a9db-133">以前のリリースでは、部分構成の命名規則は、プル サーバー/サービスの MOF ファイル名はローカル構成マネージャー設定に指定されている部分構成名に一致する必要があり、ローカル構成マネージャー設定は MOF ファイルに組み込まれている構成名に一致する必要があるというものでした。</span><span class="sxs-lookup"><span data-stu-id="5a9db-133">In the previous release, the naming convention for a partial configuration was that the MOF file name in the pull server/service should match the partial configuration name specified in the local configuration manager settings that in turn must match the configuration name embedded in the MOF file.</span></span>

<span data-ttu-id="5a9db-134">下のスナップショットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a9db-134">See the snapshots below:</span></span>

- <span data-ttu-id="5a9db-135">ローカル構成設定により、あるノードに受信を許可する部分構成が定義されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-135">Local configuration settings which defines a partial configuration that a node is allowed to receive.</span></span>

  ![サンプルのメタ構成](media/DSC-improvements/MetaConfigPartialOne.png)

- <span data-ttu-id="5a9db-137">サンプルの部分構成定義</span><span class="sxs-lookup"><span data-stu-id="5a9db-137">Sample partial configuration definition</span></span>

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

- <span data-ttu-id="5a9db-138">生成された MOF ファイルに組み込まれている 'ConfigurationName'。</span><span class="sxs-lookup"><span data-stu-id="5a9db-138">'ConfigurationName' embedded in the generated MOF file.</span></span>

  ![生成された MOF ファイルのサンプル](media/DSC-improvements/PartialGeneratedMof.png)

- <span data-ttu-id="5a9db-140">プル構成リポジトリの FileName</span><span class="sxs-lookup"><span data-stu-id="5a9db-140">FileName in the pull configuration repository</span></span>

  ![構成リポジトリの FileName](media/DSC-improvements/PartialInConfigRepository.png)

  <span data-ttu-id="5a9db-142">Azure Automation サービス名により、MOF ファイルが `<ConfigurationName>.<NodeName>.mof` として生成されました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-142">Azure Automation service name generated MOF files as `<ConfigurationName>.<NodeName>.mof`.</span></span> <span data-ttu-id="5a9db-143">そのため、下の構成は PartialOne.localhost.mof にコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-143">So the configuration below compiles to PartialOne.localhost.mof.</span></span>

  <span data-ttu-id="5a9db-144">これで、Azure Automation サービスから部分構成をプルできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-144">This made it impossible to pull one of your partial configuration from Azure Automation service.</span></span>

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

  <span data-ttu-id="5a9db-145">WMF 5.1 では、プル サーバー/サービスの部分構成の名前を `<ConfigurationName>.<NodeName>.mof` にできます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-145">In WMF 5.1, a partial configuration in the pull server/service can be named as `<ConfigurationName>.<NodeName>.mof`.</span></span> <span data-ttu-id="5a9db-146">さらに、コンピューターがプル サーバー/サービスから 1 つの構成をプルする場合、プル サーバー構成リポジトリの構成ファイルに任意のファイル名を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-146">Moreover, if a machine is pulling a single configuration from a pull server/service then the configuration file on the pull server configuration repository can have any file name.</span></span> <span data-ttu-id="5a9db-147">このように命名規則が柔軟なことから、ノードを部分的に Azure Automation サービスで管理し (ノードの一部の構成が Azure Automation DSC から誘導されます)、部分構成をローカル管理できます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-147">This naming flexibility allows you to manage your nodes partially by Azure Automation service, where some configuration for your node is coming from Azure Automation DSC and with a partial configuration that you manage locally.</span></span>

  <span data-ttu-id="5a9db-148">以下のメタ構成では、ローカルと Azure Automation サービスの両方で管理されるようにノードが設定されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-148">The metaconfiguration below sets up a node to be managed both locally as well as by Azure Automation service.</span></span>

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

## <a name="using-psdscrunascredential-with-dsc-composite-resources"></a><span data-ttu-id="5a9db-149">PsDscRunAsCredential と DSC 複合リソースを使用する</span><span class="sxs-lookup"><span data-stu-id="5a9db-149">Using PsDscRunAsCredential with DSC composite resources</span></span>

<span data-ttu-id="5a9db-150">DSC [複合](/powershell/scripting/dsc/resources/authoringresourcecomposite)リソースで [PsDscRunAsCredential](/powershell/scripting/dsc/configurations/runAsUser) を使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-150">We have added support for using [PsDscRunAsCredential](/powershell/scripting/dsc/configurations/runAsUser) with DSC [Composite](/powershell/scripting/dsc/resources/authoringresourcecomposite) resources.</span></span>

<span data-ttu-id="5a9db-151">構成内で複合リソースを使用するとき、**PsDscRunAsCredential** の値を指定できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-151">You can now specify a value for **PsDscRunAsCredential** when using composite resources inside configurations.</span></span> <span data-ttu-id="5a9db-152">指定されると、すべてのリソースが複合リソース内で RunAs ユーザーとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-152">When specified, all resources run inside a composite resource as a RunAs user.</span></span> <span data-ttu-id="5a9db-153">複合リソースが別の複合リソースを呼び出す場合、すべてのそれらのリソースも RunAs ユーザーとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-153">If a composite resource calls another composite resource, all those resources are also executed as RunAs user.</span></span> <span data-ttu-id="5a9db-154">RunAs 資格情報が複合リソース階層のあらゆるレベルに配信されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-154">RunAs credentials are propagated to any level of the composite resource hierarchy.</span></span> <span data-ttu-id="5a9db-155">複合リソース内のいずれかのリソースで **PsDscRunAsCredential** に対して独自の値が指定されている場合、構成コンパイル中に結合エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-155">If any resource inside a composite resource specifies its own value for **PsDscRunAsCredential**, a merge error results during configuration compilation.</span></span>

<span data-ttu-id="5a9db-156">この例では、PSDesiredStateConfiguration モジュールに含まれている [WindowsFeatureSet](/powershell/scripting/dsc/reference/resources/windows/windowsfeaturesetresource) 複合リソースの利用が示されています。</span><span class="sxs-lookup"><span data-stu-id="5a9db-156">This example shows usage with the [WindowsFeatureSet](/powershell/scripting/dsc/reference/resources/windows/windowsfeaturesetresource) composite resource included in PSDesiredStateConfiguration module.</span></span>

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

## <a name="allowing-for-identical-duplicate-resources-in-a-configuration"></a><span data-ttu-id="5a9db-157">構成における同一重複リソースの許容</span><span class="sxs-lookup"><span data-stu-id="5a9db-157">Allowing for Identical Duplicate Resources in a Configuration</span></span>

<span data-ttu-id="5a9db-158">DSC は、構成内で競合するリソース定義を許可せず、処理しません。</span><span class="sxs-lookup"><span data-stu-id="5a9db-158">DSC does not allow or handle conflicting resource definitions within a configuration.</span></span> <span data-ttu-id="5a9db-159">競合を解決するのではなく、ただの失敗となります。</span><span class="sxs-lookup"><span data-stu-id="5a9db-159">Instead of trying to resolve the conflict, it simply fails.</span></span> <span data-ttu-id="5a9db-160">複合リソースなどの間で構成の再利用が多く行われるようになるほど、競合は頻繁に発生します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-160">As configuration reuse becomes more utilized through composite resources, etc. conflicts will occur more often.</span></span> <span data-ttu-id="5a9db-161">競合するリソース定義が一致する場合、DSC は賢くこれを許可します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-161">When conflicting resource definitions are identical, DSC should be smart and allow this.</span></span> <span data-ttu-id="5a9db-162">このリリースにより、同一の定義を持つ複数のリソース インスタンスをサポートするようになりました:</span><span class="sxs-lookup"><span data-stu-id="5a9db-162">With this release, we support having multiple resource instances that have identical definitions:</span></span>

```powershell
Configuration IIS_FrontEnd
{
    WindowsFeature FE_IIS         #Identical resource
    {
        Ensure = 'Present'
        Name = 'Web-Server'
    }

    WindowsFeature FTP
    {
        Ensure = 'Present'
        Name = 'Web-FTP-Server'
    }
}

Configuration IIS_Worker
{
    WindowsFeature Worker_IIS      #Identical resource
    {
        Ensure = 'Present'
        Name = 'Web-Server'
    }

    WindowsFeature ASP
    {
        Ensure = 'Present'
        Name = 'Web-ASP-Net45'
    }
}

Configuration WebApplication
{
    IIS_Frontend Web {}

    IIS_Worker ASP {}
}
```

<span data-ttu-id="5a9db-163">以前のリリースでは、'Web サーバー' ロールが確実にインストールされるようにするために発生する WindowsFeature FE_IIS と WindowsFeature Worker_IIS インスタンス間の競合により、コンパイルの失敗に終わっていました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-163">In previous releases, the result would be a failed compilation due to a conflict between the WindowsFeature FE_IIS and WindowsFeature Worker_IIS instances trying to ensure the 'Web-Server' role is installed.</span></span> <span data-ttu-id="5a9db-164">構成が実行される*すべて*のプロパティは、これら 2 つの構成間で一致していることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="5a9db-164">Notice that *all* of the properties that are being configured are identical in these two configurations.</span></span> <span data-ttu-id="5a9db-165">これらの 2 つのプロパティのリソースは*すべて*一致するため、結果として正常にコンパイルできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5a9db-165">Since *all* of the properties in these two resources are identical, this will result in a successful compilation now.</span></span>

<span data-ttu-id="5a9db-166">2 つのリソース間でいずれかのプロパティが異なる場合、一致していないと見なされ、コンパイルは失敗します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-166">If any of the properties are different between the two resources, they will not be considered identical and compilation will fail.</span></span>

## <a name="dsc-module-and-configuration-signing-validations"></a><span data-ttu-id="5a9db-167">DSC のモジュールと構成の署名検証</span><span class="sxs-lookup"><span data-stu-id="5a9db-167">DSC module and configuration signing validations</span></span>

<span data-ttu-id="5a9db-168">DSC では、プル サーバーからマネージド コンピューターに構成とモジュールが配信されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-168">In DSC, configurations and modules are distributed to managed computers from the pull server.</span></span> <span data-ttu-id="5a9db-169">プル サーバーが侵害された場合、攻撃者はプル サーバーで構成とモジュールを改ざんし、すべてのマネージド ノードに配信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a9db-169">If the pull server is compromised, an attacker can potentially modify the configurations and modules on the pull server and have it distributed to all managed nodes.</span></span>

<span data-ttu-id="5a9db-170">WMF 5.1 では、DSC はカタログ ファイルと構成 (.MOF) ファイルのデジタル署名の検証に対応しています。</span><span class="sxs-lookup"><span data-stu-id="5a9db-170">In WMF 5.1, DSC supports validating the digital signatures on catalog and configuration (.MOF) files.</span></span> <span data-ttu-id="5a9db-171">この機能では、信頼できる署名者が署名していない、あるいは信頼できる署名者が署名した後に改ざんされた構成ファイルまたはモジュール ファイルの実行が防止されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-171">This feature prevents nodes from executing configurations or module files which are not signed by a trusted signer or which have been tampered with after they have been signed by trusted signer.</span></span>

### <a name="how-to-sign-configuration-and-module"></a><span data-ttu-id="5a9db-172">構成とモジュールに署名する方法</span><span class="sxs-lookup"><span data-stu-id="5a9db-172">How to sign configuration and module</span></span>

- <span data-ttu-id="5a9db-173">構成ファイル (.MOF): 既存の PowerShell コマンドレット [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature) が拡張され、MOF ファイルの署名に対応しています。</span><span class="sxs-lookup"><span data-stu-id="5a9db-173">Configuration Files (.MOFs): The existing PowerShell cmdlet [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature) is extended to support signing of MOF files.</span></span>
- <span data-ttu-id="5a9db-174">モジュール: モジュールの署名は、次の手順を利用し、対応するモジュール カタログに署名することで完了します:</span><span class="sxs-lookup"><span data-stu-id="5a9db-174">Modules: Signing of modules is done by signing the corresponding module catalog using the following steps:</span></span>
  1. <span data-ttu-id="5a9db-175">カタログ ファイルの作成: カタログ ファイルには、暗号法のハッシュまたは拇印の集まりが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5a9db-175">Create a catalog file: A catalog file contains a collection of cryptographic hashes or thumbprints.</span></span> <span data-ttu-id="5a9db-176">拇印はそれぞれ、モジュールに含まれるファイルに対応します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-176">Each thumbprint corresponds to a file that is included in the module.</span></span> <span data-ttu-id="5a9db-177">新しいコマンドレット [New-FileCatalog](/powershell/module/microsoft.powershell.security/new-filecatalog) が追加され、ユーザーは自分のモジュールのカタログ ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-177">The new cmdlet [New-FileCatalog](/powershell/module/microsoft.powershell.security/new-filecatalog), has been added to enable users to create a catalog file for their module.</span></span>
  2. <span data-ttu-id="5a9db-178">カタログ ファイルの署名: [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature) を利用し、カタログ ファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-178">Sign the catalog file: Use [Set-AuthenticodeSignature](/powershell/module/Microsoft.PowerShell.Security/Set-AuthenticodeSignature) to sign the catalog file.</span></span>
  3. <span data-ttu-id="5a9db-179">モジュール フォルダー内にカタログ ファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-179">Place the catalog file inside the module folder.</span></span> <span data-ttu-id="5a9db-180">慣例では、モジュール カタログ ファイルは、モジュールと同じ名前のモジュール フォルダーの下に配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a9db-180">By convention, module catalog file should be placed under the module folder with the same name as the module.</span></span>

### <a name="localconfigurationmanager-settings-to-enable-signing-validations"></a><span data-ttu-id="5a9db-181">LocalConfigurationManager 設定で署名検証を有効にする</span><span class="sxs-lookup"><span data-stu-id="5a9db-181">LocalConfigurationManager settings to enable signing validations</span></span>

#### <a name="pull"></a><span data-ttu-id="5a9db-182">プル</span><span class="sxs-lookup"><span data-stu-id="5a9db-182">Pull</span></span>

<span data-ttu-id="5a9db-183">ノードの LocalConfigurationManager は、その現在の設定に基づき、モジュールと構成の署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-183">The LocalConfigurationManager of a node performs signing validation of modules and configurations based on its current settings.</span></span> <span data-ttu-id="5a9db-184">既定では、署名検証は無効です。</span><span class="sxs-lookup"><span data-stu-id="5a9db-184">By default, signature validation is disabled.</span></span> <span data-ttu-id="5a9db-185">署名検証は、"SignatureValidation" ブロックを下の図のようにノードのメタ構成定義に追加することで有効にできます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-185">Signature validation can enabled by adding the 'SignatureValidation' block to the meta-configuration definition of the node as shown below:</span></span>

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
        # If the TrustedStorePath property is provided then LCM will use the custom path. Otherwise, the LCM will use default trusted store path (Cert:\LocalMachine\DSCStore) to find the signing certificate.
        TrustedStorePath = 'Cert:\LocalMachine\DSCStore'
        SignedItemType = 'Configuration','Module'         # This is a list of DSC artifacts, for which LCM need to verify their digital signature before executing them on the node.
    }

}
EnableSignatureValidation
Set-DscLocalConfigurationManager -Path .\EnableSignatureValidation -Verbose
```

<span data-ttu-id="5a9db-186">ノードに上記のメタ構成を設定すると、ダウンロードした構成とモジュールで署名を検証できます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-186">Setting the above metaconfiguration on a node enables signature validation on downloaded configurations and modules.</span></span> <span data-ttu-id="5a9db-187">ローカル構成マネージャーは次の手順でデジタル署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-187">The Local Configuration Manager performs the following steps to verify the digital signatures.</span></span>

1. <span data-ttu-id="5a9db-188">`Get-AuthenticodeSignature` コマンドレットを使って、構成ファイル (.MOF) での署名が有効であることを検証します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-188">Verify the signature on a configuration file (.MOF) is valid using the `Get-AuthenticodeSignature` cmdlet.</span></span>
2. <span data-ttu-id="5a9db-189">署名者が信頼できることを認定した証明機関を検証します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-189">Verify the certificate authority that authorized the signer is trusted.</span></span>
3. <span data-ttu-id="5a9db-190">構成のモジュール/リソース依存性を一時的な場所にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="5a9db-190">Download module/resource dependencies of the configuration to a temp location.</span></span>
4. <span data-ttu-id="5a9db-191">モジュール内に含まれるカタログの署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-191">Verify the signature of the catalog included inside the module.</span></span>
   - <span data-ttu-id="5a9db-192">`<moduleName>.cat` ファイルを見つけ、`Get-AuthenticodeSignature` を使ってその署名を検証します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-192">Find a `<moduleName>.cat` file and verify its signature using `Get-AuthenticodeSignature`.</span></span>
   - <span data-ttu-id="5a9db-193">署名者が信頼できることを認定した証明機関を検証します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-193">Verify the certification authority that authenticated the signer is trusted.</span></span>
   - <span data-ttu-id="5a9db-194">新しいコマンドレット `Test-FileCatalog` を利用し、モジュールのコンテンツが改ざんされていないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-194">Verify the content of the modules has not been tampered using the new cmdlet `Test-FileCatalog`.</span></span>
5. <span data-ttu-id="5a9db-195">`$env:ProgramFiles\WindowsPowerShell\Modules\` に対して `Install-Module` を行います</span><span class="sxs-lookup"><span data-stu-id="5a9db-195">`Install-Module` to `$env:ProgramFiles\WindowsPowerShell\Modules\`</span></span>
6. <span data-ttu-id="5a9db-196">プロセス構成</span><span class="sxs-lookup"><span data-stu-id="5a9db-196">Process configuration</span></span>

> [!NOTE]
> <span data-ttu-id="5a9db-197">モジュール カタログと構成の署名検証は、構成がシステムに最初に適用されるときか、モジュールがダウンロードされ、インストールされるときにのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-197">Signature validation on module-catalog and configuration is only performed when the configuration is applied to the system for the first time or when the module is downloaded and installed.</span></span>
> <span data-ttu-id="5a9db-198">整合性実行では、Current.mof やそのモジュール依存性の署名は検証されません。</span><span class="sxs-lookup"><span data-stu-id="5a9db-198">Consistency runs do not validate the signature of Current.mof or its module dependencies.</span></span> <span data-ttu-id="5a9db-199">何らかの段階で検証に失敗した場合、たとえば、プル サーバーからプルされた構成に署名がされていない場合、構成の処理が中止となり、下にエラーが表示されます。一時ファイルはすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-199">If verification has failed at any stage, for instance, if the configuration pulled from the pull server is unsigned, then processing of the configuration terminates with the error shown below and all temporary files are deleted.</span></span>

![構成のエラー出力のサンプル](media/DSC-improvements/PullUnsignedConfigFail.png)

<span data-ttu-id="5a9db-201">同様に、カタログに署名のないモジュールがプルされると次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-201">Similarly, pulling a module whose catalog is not signed results in the following error:</span></span>

![モジュールのエラー出力のサンプル](media/DSC-improvements/PullUnisgnedCatalog.png)

#### <a name="push"></a><span data-ttu-id="5a9db-203">プッシュ</span><span class="sxs-lookup"><span data-stu-id="5a9db-203">Push</span></span>

<span data-ttu-id="5a9db-204">プッシュで配信された構成は、ノードに届く前にその出所で改ざんされていた可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5a9db-204">A configuration delivered by using push might be tampered with at its source before it delivered to the node.</span></span> <span data-ttu-id="5a9db-205">ローカル構成マネージャーは、プッシュまたは公開された構成に対して同様の署名検証手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-205">The Local Configuration Manager performs similar signature validation steps for pushed or published configuration(s).</span></span> <span data-ttu-id="5a9db-206">以下は、プッシュの署名検証の完全例です。</span><span class="sxs-lookup"><span data-stu-id="5a9db-206">Below is a complete example of signature validation for push.</span></span>

- <span data-ttu-id="5a9db-207">ノードで署名検証を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5a9db-207">Enable signature validation on the node.</span></span>

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

- <span data-ttu-id="5a9db-208">サンプル構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-208">Create a sample configuration file.</span></span>

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

- <span data-ttu-id="5a9db-209">署名のない構成ファイルをノードにプッシュしてみます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-209">Try pushing the unsigned configuration file in to the node.</span></span>

  ```powershell
  Start-DscConfiguration -Path .\Test -Wait -Verbose -Force
  ```

  ![エラー - 署名のない MOF ファイルがプッシュされました](media/DSC-improvements/PushUnsignedMof.png)

- <span data-ttu-id="5a9db-211">コード署名証明書を利用し、構成ファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="5a9db-211">Sign the configuration file using code-signing certificate.</span></span>

  ![MOF ファイルに署名する](media/DSC-improvements/SignMofFile.png)

- <span data-ttu-id="5a9db-213">署名された MOF ファイルをプッシュしてみます。</span><span class="sxs-lookup"><span data-stu-id="5a9db-213">Try pushing the signed MOF file.</span></span>

  ![署名された MOF ファイルをプッシュする](media/DSC-improvements/PushSignedMof.png)
