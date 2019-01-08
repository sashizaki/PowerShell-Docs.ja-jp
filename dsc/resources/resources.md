---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC リソース
ms.openlocfilehash: 1f77b5e6630a2e3de6e1d1a05638f94d2df039ae
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54046693"
---
# <a name="dsc-resources"></a>DSC リソース

>適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。 リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。

リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。  リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。

各リソースには、* スキーマ内のリソースを使用するために必要な構文を決定する、[構成](../configurations/configurations.md)します。 次の方法では、リソースのスキーマを定義できます。

- **'Schema.Mof'** ファイル。ほとんどのリソースを定義、*スキーマ*'schema.mof' でファイルを使用して[マネージ オブジェクト形式](/windows/desktop/wmisdk/managed-object-format--mof-)します。
- **'\<リソース名\>. schema.psm1'** ファイル。[複合リソース](../configurations/compositeConfigs.md)定義、*スキーマ*で、'<ResourceName>. schema.psm1' ファイルを使用して、 [Parameter Block](/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-6#functions-with-parameters)します。
- **'\<リソース名\>.psm1'** ファイル。クラス ベース DSC リソースの定義、*スキーマ*クラス定義にします。 構文項目は、クラスのプロパティとして表されます。 詳細については、次を参照してください。 [about_Classes](/powershell/module/psdesiredstateconfiguration/about/about_classes_and_dsc)します。

DSC リソースの構文を取得する、 [Get-dscresource](/powershell/module/PSDesiredStateConfiguration/Get-DscResource)コマンドレットと、`-Syntax`パラメーター。 この使用法の使用と似ています[Get-command](/powershell/module/microsoft.powershell.core/get-command)で、`-Syntax`パラメーターをコマンドレットの構文を取得します。 表示出力は、指定したリソースのリソース ブロックで使用するテンプレートに表示されます。

```powershell
Get-DscResource -Syntax Service
```

表示出力は、このリソースの構文は、後で変わる可能性がありますが、次のようなことがあります。 などのコマンドレットの構文、*キー*角かっこで囲んで表示は省略可能です。 種類は、各キーはデータの種類を指定します。

> [!NOTE]
> **を確認してください**既定値は"present"にあるために、キーは省略可能です。

```output
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

構成では、内部、**サービス**リソース ブロックするようになります**を確認してください**スプーラ サービスを実行しています。

> [!NOTE]
> 構成では、リソースを使用する前に使用してインポートする必要があります[Import-dscresource](../configurations/import-dscresource.md)します。

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }
    }
}
```

構成は、同じリソースの種類の複数のインスタンスを含めることができます。 各インスタンスを一意に名前にする必要があります。 次の例では、1 秒あたり**サービス**リソース ブロックは、"DHCP"サービスの構成に追加されます。

```powershell
Configuration TestConfig
{
    # It is best practice to always directly import resources, even if the resource is a built-in resource.
    Import-DSCResource -Name Service
    Node localhost
    {
        # The name of this resource block, can be anything you choose, as long as it is of type [String] as indicated by the schema.
        Service "Spooler:Running"
        {
            Name = "Spooler"
            State = "Running"
        }

        # To configure a second service resource block, add another Service resource block and use a unique name.
        Service "DHCP:Running"
        {
            Name = "DHCP"
            State = "Running"
        }
    }
}
```

> [!NOTE]
> DSC の PowerShell 5.0 以降では、intellisense が追加されました。 この新しい機能では、使用できます。\<タブ\>と\<Ctrl + Space\>キー名のオートコンプリートにします。

![リソースの Tab 補完機能](../media/resource-tabcompletion.png)

## <a name="built-in-resources"></a>組み込みリソース

コミュニティ リソース、Windows、linux の場合、リソースおよびノードの相互依存関係のリソース用組み込みリソースがあります。 上記の手順を使用すると、これらのリソースとその使用方法の構文を確認します。 これらのリソースを提供するページがアーカイブされた**参照**します。

Windows 組み込みリソース

* [アーカイブ リソース](../reference/resources/windows/archiveResource.md)
* [環境リソース](../reference/resources/windows/environmentResource.md)
* [ファイル リソース](../reference/resources/windows/fileResource.md)
* [グループ リソース](../reference/resources/windows/groupResource.md)
* [GroupSet リソース](../reference/resources/windows/groupSetResource.md)
* [ログ リソース](../reference/resources/windows/logResource.md)
* [パッケージ リソース](../reference/resources/windows/packageResource.md)
* [ProcessSet リソース](../reference/resources/windows/ProcessSetResource.md)
* [レジストリ リソース](../reference/resources/windows/registryResource.md)
* [スクリプト リソース](../reference/resources/windows/scriptResource.md)
* [サービス リソース](../reference/resources/windows/serviceResource.md)
* [ServiceSet リソース](../reference/resources/windows/serviceSetResource.md)
* [ユーザー リソース](../reference/resources/windows/userResource.md)
* [WindowsFeature リソース](../reference/resources/windows/windowsFeatureResource.md)
* [WindowsFeatureSet リソース](../reference/resources/windows/windowsFeatureSetResource.md)
* [WindowsOptionalFeature リソース](../reference/resources/windows/windowsOptionalFeatureResource.md)
* [WindowsOptionalFeatureSet リソース](../reference/resources/windows/windowsOptionalFeatureSetResource.md)
* [WindowsPackageCabResource リソース](../reference/resources/windows/windowsPackageCabResource.md)
* [WindowsProcess リソース](../reference/resources/windows/windowsProcessResource.md)

[ノードの相互依存関係](../configurations/crossNodeDependencies.md)リソース

* [WaitForAll リソース](../reference/resources/windows/waitForAllResource.md)
* [WaitForSome リソース](../reference/resources/windows/waitForSomeResource.md)
* [WaitForAny リソース](../reference/resources/windows/waitForAnyResource.md)

パッケージの管理リソース

* [PackageManagement リソース](../reference/resources/packagemanagement/PackageManagementDscResource.md)
* [PackageManagementSource リソース](../reference/resources/packagemanagement/PackageManagementSourceDscResource.md)

Linux のリソース

* [Linux の Archive リソース](../reference/resources/linux/lnxArchiveResource.md)
* [Linux 環境のリソース](../reference/resources/linux/lnxEnvironmentResource.md)
* [Linux FileLine リソース](../reference/resources/linux/lnxFileLineResource.md)
* [Linux ファイル リソース](../reference/resources/linux/lnxFileResource.md)
* [Linux グループ リソース](../reference/resources/linux/lnxGroupResource.md)
* [Linux パッケージ リソース](../reference/resources/linux/lnxPackageResource.md)
* [Linux スクリプト リソース](../reference/resources/linux/lnxScriptResource.md)
* [Linux のサービス リソース](../reference/resources/linux/lnxServiceResource.md)
* [Linux SshAuthorizedKeys リソース](../reference/resources/linux/lnxSshAuthorizedKeysResource.md)
* [Linux ユーザーのリソース](../reference/resources/linux/lnxUserResource.md)
