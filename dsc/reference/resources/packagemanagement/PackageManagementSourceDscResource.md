---
ms.date: 06/20/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC の PackageManagementSource リソース
ms.openlocfilehash: e51b5318288bef458567dd4b58d17caaea3ed69b
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047526"
---
# <a name="dsc-packagemanagementsource-resource"></a>DSC の PackageManagementSource リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.0、Windows PowerShell 5.1

Windows PowerShell Desired State Configuration (DSC) の **PackageManagementSource** リソースは、ターゲット ノードで Package Management ソースを登録または登録解除するメカニズムを備えています。 **この方法で登録された Package Management ソースは System コンテキストで登録されるため、System アカウントまたは DSC エンジンで使用することができます。** このリソースには **PackageManagement** モジュールが必要です。これは、 http://PowerShellGallery.com から入手できます。

> [!IMPORTANT]
> **PackageManagement** モジュールは、次のプロパティ情報が適切であるようにバージョン 1.1.7.0 以降である必要があります。

## <a name="syntax"></a>構文

```
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [DependsOn = [string[]]]
    [Ensure = [string]{ Absent | Present }]
    [InstallationPolicy = [string]{ Trusted | Untrusted }]
    [PsDscRunAsCredential = [PSCredential]]
    [SourceCredential = [PSCredential]]
}
```

## <a name="properties"></a>プロパティ

|  プロパティ  |  説明   |
|---|---|
| 名前| システムで登録または登録解除するパッケージ ソースの名前を指定します。|
| ProviderName| パッケージ ソースとの相互運用に使用できる OneGet プロバイダーの名前を指定します。|
| SourceLocation| パッケージ ソースの URI を指定します。|
| Ensure| パッケージ ソースを登録または登録解除するかどうかを決定します。|
| InstallationPolicy| 組み込みの Nuget プロバイダーなどのプロバイダーによって使用されます。 パッケージのソースを信頼するかどうかを決定します。  または  のどちらかです。「信頼されていない」、「信頼済み」です。|
| SourceCredential| リモート ソースのパッケージへのアクセスを提供します。|

## <a name="example"></a>例

この例では、**PackageManagementSource** DSC リソースを使用して http://nuget.org パッケージ ソースを登録しています。

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "http://nuget.org/api/v2/"
        InstallationPolicy ="Trusted"
    }
}
```