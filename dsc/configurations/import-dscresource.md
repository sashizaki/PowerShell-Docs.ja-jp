---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: Import-DSCResource の使用
ms.openlocfilehash: ee0b2f0469c6507c8f0148138198597a9e57cdd7
ms.sourcegitcommit: c581c4c8036edf55147e7bce4b00c860da6c5a8b
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2019
ms.locfileid: "56803414"
---
# <a name="using-import-dscresource"></a>Import-DSCResource の使用

`Import-DScResource` 動的なキーワードは、構成スクリプト ブロック内でのみ使用できますです。 `Import-DSCResource`構成に必要なすべてのリソースをインポートするキーワード。 下にあるリソース`$pshome`は自動的に、インポートで使用されるすべてのリソースを明示的にインポートするベスト プラクティスをまだと見なされますが、[構成](Configurations.md)します。

構文は、`Import-DSCResource`を次に示します。  モジュール名を指定するときに新しい行にそれぞれの一覧を表示するための要件になります。

```syntax
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName>]
```

|パラメーター  |説明  |
|---------|---------|
|`-Name`|DSC リソースの名前をインポートする必要があります。 コマンドで検索します。 このモジュール内でこれらの DSC リソース モジュール名が指定されている場合それ以外の場合、コマンドは、すべての DSC リソースのパスでの DSC リソースを検索します。 ワイルド カードがサポートされます。|
|`-ModuleName`|モジュール名、またはモジュールの仕様。  モジュールからインポートするリソースを指定すると、コマンドはリソースのみをインポートしようとします。 モジュールのみを指定する場合、コマンドは、モジュール内のすべての DSC リソースをインポートします。|

```powershell
Import-DscResource -ModuleName xActiveDirectory;
```

## <a name="example-use-import-dscresource-within-a-configuration"></a>例: 使用 Import-dscresource、構成内で

```powershell
Configuration MSDSCConfiguration
{
    # Search for and imports Service, File, and Registry from the module PSDesiredStateConfiguration.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration -Name Service, File, Registry
    
    # Search for and import Resource1 from the module that defines it.
    # If only –Name parameter is used then resources can belong to different PowerShell modules as well.
    # TimeZone resource is from the ComputerManagementDSC module which is not installed by default.
    # As a best practice, list each requirement on a different line if possible.  This makes reviewing
    # multiple changes in source control a bit easier.
    Import-DSCResource -Name File
    Import-DSCResource -Name TimeZone

    # Search for and import all DSC resources inside the module PSDesiredStateConfiguration.
    # When specifying the modulename parameter, it is a requirement to list each on a new line.
    Import-DSCResource -ModuleName PSDesiredStateConfiguration
    Import-DSCResource -ModuleName ComputerManagementDsc
...
```

> [!NOTE]
> 同じコマンドでリソース名とモジュール名の複数の値を指定することはサポートされていません。 非確定的な動作を複数のモジュールで同じリソースが存在する場合は、どのモジュールから読み込むには、どのリソースに関することができます。 次のコマンドは、コンパイル中にエラーに発生します。
>
> ```powershell
> Import-DscResource -Name UserConfigProvider*,TestLogger1 -ModuleName UserConfigProv,PsModuleForTestLogger
> ```

名前のパラメーターのみを使用するときに考慮すべき事項:

- コンピューターにインストールされているモジュールの数に応じてリソースを消費する操作です。
- 指定した名前で見つかった最初のリソースが読み込まれます。 場合は、間違ったリソースを読み込むことがインストールされている同じ名前の 1 つ以上のリソースがある場合。

推奨される使用法は指定`–ModuleName`で、`-Name`パラメーターは、次のようです。

この使用法には、次の利点があります。

- 指定したリソースの検索範囲を制限することによってパフォーマンスに与える影響が減少します。
- 適切なリソースが読み込まれることを確認、リソースを定義するモジュールを明示的に定義します。

> [!NOTE]
> PowerShell 5.0 では、DSC リソースに複数バージョンを用意することができ、コンピューターにその複数のバージョンをサイド バイ サイドでインストールできます。 これを実装するには、リソース モジュールの複数のバージョンを同じモジュール フォルダーに格納します。
> 詳細については、「[複数のバージョンがあるリソースの使用](sxsresource.md)」を参照してください。

## <a name="intellisense-with-import-dscresource"></a>Import-dscresource の Intellisense

ISE で DSC 構成を作成するときに、PowerShell は、リソースとリソースのプロパティの IntelliSence を提供します。 リソースの定義、`$pshome`モジュールのパスが自動的に読み込まれます。 使用してリソースをインポートするときに、`Import-DSCResource`キーワード、指定したリソース定義を追加および Intellisense を拡張して、インポートされたリソースのスキーマが含まれます。

![リソースの Intellisense](/media/resource-intellisense.png)

> [!NOTE]
> PowerShell 5.0 以降では、タブ補完は、DSC リソースとそのプロパティの ISE に追加されました。 詳細については、次を参照してください。[リソース](../resources/resources.md)します。

構成をコンパイルするときに、PowerShell は、構成内のすべてのリソース ブロックを検証するのにインポートされたリソース定義を使用します。
各リソース ブロックは、次の規則のリソースのスキーマ定義を使用して検証されます。

- スキーマで定義されたプロパティのみが使用されます。
- 各プロパティのデータ型が正しいです。
- キー プロパティが指定されます。
- 読み取り専用プロパティは使用されません。
- 値の検証は、型をマップします。

次の構成を検討してください。

```powershell
Configuration SchemaValidationInCorrectEnumValue
{
    # It is best practice to explicitly import all resources used in your Configuration.
    # This includes resources that are imported automatically, like WindowsFeature.
    Import-DSCResource -Name WindowsFeature
    Node localhost
    {
        WindowsFeature ROLE1
        {
            Name = “Telnet-Client”
            Ensure = “Invalid”
        }
    }
}
```

この構成の結果、エラーをコンパイルします。

```output
PSDesiredStateConfiguration\WindowsFeature: At least one of the values ‘Invalid’ is not supported or valid for property ‘Ensure’ on class ‘WindowsFeature’. Please specify only supported values: Present, Absent.
```

Intellisense およびスキーマ検証を使用すると、実行時に複雑な問題を回避する解析とコンパイル時に多くのエラーをキャッチできます。

> [!NOTE]
> 各 DSC リソースの名前を付けることができます、 **FriendlyName**リソースのスキーマで定義します。 "MSFT_ServiceResource.shema.mof"の最初の 2 つの行を次に示します。
> ```syntax
> [ClassVersion("1.0.0"),FriendlyName("Service")]
> class MSFT_ServiceResource : OMI_BaseResource
> ```
> このリソースを使用して、構成では場合、は、指定**MSFT_ServiceResource**または**サービス**します。

## <a name="powershell-v4-and-v5-differences"></a>PowerShell v4 および v5 の違い

PowerShell 4.0 の vs での構成を作成するときに「する複数違いがあります。PowerShell 5.0 以降。 このセクションでは、相違点を強調表示されますこの記事に関連する表示します。

### <a name="multiple-resource-versions"></a>複数のリソース バージョン

インストールとサイド バイ サイドのリソースの複数のバージョンを使用した、PowerShell 4.0 ではサポートされていません。 問題のリソースの構成をインポートする場合は、インストールされているリソースの 1 つのバージョンのみがあることを確認します。

2 つのバージョンの次の図で、 **xPSDesiredStateConfiguration**モジュールがインストールされています。

![複数のリソース バージョンを修正しました](/media/multiple-resource-versions-broken.md)

モジュール ディレクトリの最上位レベルに、必要なモジュールのバージョンの内容をコピーします。

![複数のリソース バージョンを修正しました](/media/multiple-resource-versions-fixed.md)

### <a name="resource-location"></a>リソースの場所

指定された任意のディレクトリに、リソースを格納できる作成と構成のコンパイル、 [PSModulePath](/powershell/developer/module/modifying-the-psmodulepath-installation-path)します。 PowerShell 4.0 のでは、LCM は、"プログラム \windowspowershell\modules"を格納するすべての DSC リソース モジュールを必要があります。 または`$pshome\Modules`します。 PowerShell 5.0 以降では、この要件が削除され、リソース モジュールで指定された任意のディレクトリに格納できる`PSModulePath`します。

## <a name="see-also"></a>関連項目

- [リソース](../resources/resources.md)
