---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC の PackageManagement リソース"
ms.openlocfilehash: a984fbf5db561a696d89b60dde8b92096c6e4924
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="dsc-packagemanagement-resource" class="xliff"></a>

# DSC の PackageManagement リソース

> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) の **PackageManagement** リソースは、ターゲット ノードで Package Management パッケージをインストールまたはアンインストールするメカニズムを備えています。 このリソースには **PackageManagement** モジュールが必要です。これは、http://PowerShellGallery.com から入手できます。

<a id="syntax" class="xliff"></a>

## 構文

```
PackageManagement [string] #ResourceName
{
    Name = [string]
    [ Source = [string] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ RequiredVersion = [string] ]
    [ MinimumVersion = [string] ]
    [ MaximumVersion = [string] ]
    [ SourceCredential = [PSCredential] ]
    [ ProviderName = [string] ]
    [ AdditionalParameters = [Microsoft.Management.Infrastructure.CimInstance[]] ]
}
```

<a id="properties" class="xliff"></a>

## プロパティ
|  プロパティ  |  説明   | 
|---|---| 
| 名前| インストールまたはアンインストールするパッケージの名前を指定します。| 
| ソース| パッケージのあるパッケージ ソースの名前を指定します。 これは、URI、または Register-PackageSource または PackageManagementSource の DSC リソースに登録されたソースのどちらかになります。 DSC リソース MSFT_PackageManagementSource にもパッケージ リソースを登録できます。| 
| Ensure| パッケージをインストールまたはアンインストールするかどうかを決定します。| 
| RequiredVersion| インストールするパッケージの正確なバージョンを指定します。 このパラメーターを指定しない場合、MaximumVersion パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがこの DSC リソースによってインストールされます。| 
| MinimumVersion| インストールするパッケージで許容される最小バージョンを指定します。 このパラメーターを追加しない場合、MaximumVersion パラメーターで指定された最大バージョンも満たす、パッケージで利用可能な最新バージョンがこの DSC リソースによってインストールされます。| 
| MaximumVersion| インストールするパッケージで許容される最大バージョンを指定します。 このパラメーターを指定しない場合、この DSC リソースではパッケージで利用可能な最も高い数字のバージョンがインストールされます。| 
| SourceCredential | 指定したパッケージ プロバイダーまたはソースのパッケージをインストールする権限を持つユーザー アカウントを指定します。| 
| ProviderName| パッケージの検索先となるパッケージ プロバイダー名を指定します。 Get-PackageProvider コマンドレットを実行して、パッケージ プロバイダー名を取得できます。| 
| AdditionalParameters| ハッシュテーブルとして渡されるプロバイダー固有のパラメーター。 たとえば、NuGet プロバイダーでは DestinationPath のような追加のパラメーターを渡すことができます。| 

<a id="additional-parameters" class="xliff"></a>

## 追加のパラメーター
次の表は、AdditionalParameters プロパティのオプションを示しています。
|  パラメーター  | 説明   | 
|---|---|
| DestinationPath| 組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。 パッケージをインストールするファイルの場所を指定します。|
| InstallationPolicy| 組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。 パッケージのソースを信頼するかどうかを決定します。 "Untrusted" または "Trusted" のどちらかです。|

<a id="example" class="xliff"></a>

## 例

この例では、**PackageManagement** DSC リソースを使用して、**JQuery** NuGet パッケージおよび **GistProvider** PowerShell モジュールをインストールします。 この例では、最初に必要なパッケージのソースが利用できることを確認し、次に **JQuery** および **GistProvider** のパッケージ (それぞれ NuGet と PowerShell) の予期される状態を定義しています。

```powershell
Configuration PackageTest
{    
    PackageManagementSource SourceRepository 
    { 
        Ensure      = "Present" 
        Name        = "MyNuget" 
        ProviderName= "Nuget" 
        SourceUri   = "http://nuget.org/api/v2/"   
        InstallationPolicy ="Trusted" 
    }    
    
    PackageManagementSource PSGallery 
    { 
        Ensure      = "Present" 
        Name        = "psgallery" 
        ProviderName= "PowerShellGet" 
        SourceUri   = "https://www.powershellgallery.com/api/v2/"   
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

