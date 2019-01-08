---
ms.date: 06/20/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagement リソース
ms.openlocfilehash: 18cbbfe0715c82dcfdf4a5fb6ee36ee814e43d3b
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047718"
---
# <a name="dsc-packagemanagement-resource"></a>DSC の PackageManagement リソース

適用先:Windows PowerShell 4.0、Windows PowerShell 5.0、Windows PowerShell 5.1

Windows PowerShell Desired State Configuration (DSC) の **PackageManagement** リソースは、ターゲット ノードで Package Management パッケージをインストールまたはアンインストールするメカニズムを備えています。 このリソースには **PackageManagement** モジュールが必要です。これは、[http://PowerShellGallery.com](http://PowerShellGallery.com) から入手できます。

> [!IMPORTANT]
> **PackageManagement** モジュールは、次のプロパティ情報が適切であるようにバージョン 1.1.7.0 以降である必要があります。

## <a name="syntax"></a>構文

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [AdditionalParameters = [HashTable]]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [MaximumVersion = [string]]
    [MinimumVersion = [string]]
    [ProviderName = [string]]
    [PsDscRunAsCredential = [PSCredential]]
    [RequiredVersion = [string]]
    [Source = [string]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a>プロパティ

| プロパティ | 説明 |
| --- | --- |
| 名前| インストールまたはアンインストールするパッケージの名前を指定します。|
| AdditionalParameters| `Get-Package -AdditionalArguments` に渡されるパラメーターのプロバイダー固有のハッシュ テーブル。 たとえば、NuGet プロバイダーでは DestinationPath のような追加のパラメーターを渡すことができます。|
| Ensure| パッケージをインストールまたはアンインストールするかどうかを決定します。|
| MaximumVersion|検索するパッケージで許容される最大バージョンを指定します。 このパラメーターを追加しない場合、リソースでは利用できるパッケージの最新バージョンが検索されます。|
| MinimumVersion|検索するパッケージで許容される最小バージョンを指定します。 このパラメーターを追加しない場合、_MaximumVersion_ パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがリソースによって検索されます。|
| ProviderName| パッケージの検索先となるパッケージ プロバイダー名を指定します。 `Get-PackageProvider` コマンドレットを実行して、パッケージ プロバイダー名を取得できます。|
| RequiredVersion| インストールするパッケージの正確なバージョンを指定します。 このパラメーターを指定しない場合、_MaximumVersion_ パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがこの DSC リソースによってインストールされます。|
| ソース| パッケージのあるパッケージ ソースの名前を指定します。 これは、URI か、`Register-PackageSource` または PackageManagementSource の DSC リソースに登録されたソースのどちらかになります。|
| SourceCredential | 指定したパッケージ プロバイダーまたはソースのパッケージをインストールする権限を持つユーザー アカウントを指定します。|

## <a name="additional-parameters"></a>追加のパラメーター

次の表は、AdditionalParameters プロパティのオプションを示しています。

| パラメーター | 説明 |
| --- | --- |
| DestinationPath| 組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。 パッケージをインストールするファイルの場所を指定します。|
| InstallationPolicy| 組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。 パッケージのソースを信頼するかどうかを決定します。 `Untrusted` または `Trusted` のどちらかです。|

## <a name="example"></a>例

この例では、**PackageManagement** DSC リソースを使用して、**JQuery** NuGet パッケージおよび **GistProvider** PowerShell モジュールをインストールします。 この例では、最初に必要なパッケージのソースが利用できることを確認し、次に **JQuery** および **GistProvider** のパッケージ (それぞれ NuGet と PowerShell) の予期される状態を定義しています。

```powershell
Configuration PackageTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagementSource PSGallery
    {
        Ensure      = "Present"
        Name        = "psgallery"
        ProviderName= "PowerShellGet"
        SourceLocation   = "https://www.powershellgallery.com/api/v2/"
        InstallationPolicy ="Trusted"
    }

    PackageManagement NugetPackage
    {
        Ensure               = "Present"
        Name                 = "JQuery"
        AdditionalParameters = "$env:HomeDrive\nuget"
        RequiredVersion      = "2.0.1"
        DependsOn            = "[PackageManagementSource]SourceRepository"
    }

    PackageManagement PSModule
    {
        Ensure               = "Present"
        Name                 = "gistprovider"
        Source               = "PSGallery"
        DependsOn            = "[PackageManagementSource]PSGallery"
    }
}
```