---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: インストールされているリソースの特定のバージョンをインポートする
ms.openlocfilehash: 5ed81e11aa67eb6590d958647f48a33b1b5f1c0e
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402206"
---
# <a name="import-a-specific-version-of-an-installed-resource"></a>インストールされているリソースの特定のバージョンをインポートする

> 適用先:Windows PowerShell 5.0

PowerShell 5.0 以降、DSC リソースの個別のバージョンは、コンピューターのサイド バイ サイドでインストールできます。 リソース モジュールは、という名前のフォルダーのバージョンで別のバージョンのリソースを格納できます。

## <a name="installing-separate-resource-versions-side-by-side"></a>別のリソース バージョンのサイド バイ サイドのインストール

[Install-Module](/powershell/module/PowershellGet/Install-Module) コマンドレットの **MinimumVersion**、**MaximumVersion**、**RequiredVersion** の各パラメーターを使用すると、インストールするモジュールのバージョンを指定できます。 バージョンを指定せずに **Install-Module** を呼び出すと、最新バージョンがインストールされます。

たとえば、**xFailOverCluster** モジュールのバージョンが複数あり、それぞれに **xCluster** リソースが含まれているとします。 呼び出す**Install-module**数バージョンを指定することがなく、モジュールの最新バージョンがインストールされます。

```powershell
PS> Install-Module xFailOverCluster
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, ...
```

特定のバージョンのモジュールをインストールするには、指定、 **RequiredVersion** 1.1.0.0 の。 これには、インストールされているバージョンと並行指定されたバージョンがインストールされます。

```powershell
PS> Install-Module xFailOverCluster -RequiredVersion 1.1
```

これで、両方を表示します。 モジュールのバージョンを使用する場合にも表示`Get-DSCResource`します。

```powershell
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a>構成でのリソース バージョンの指定

別のリソースのバージョンがコンピューターにインストールした場合は、構成で使用すると、そのリソースのバージョンを指定する必要があります。 これを行うには、**Import-DscResource** キーワードの **ModuleVersion** パラメーターを指定します。 複数のバージョンがインストールされているリソースのリソース モジュールのバージョンを指定しないと、構成によってエラーが生成されます。

次の構成は、呼び出すリソースのバージョンを指定する方法を示しています。

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName xFailOverCluster -ModuleVersion 1.1

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

>注: Import-dscresource の ModuleVersion パラメーターは、PowerShell 4.0 でご利用いただけません。 PowerShell 4.0 では、Import-DscResource の ModuleName パラメーターにモジュール指定オブジェクトを渡すことで、モジュールのバージョンを指定できます。 モジュール指定オブジェクトは、ModuleName キーと RequiredVersion キーを含むハッシュ テーブルです。 たとえば、次のように入力します。

```powershell
configuration VersionTest
{
    Import-DscResource -ModuleName (@{ModuleName='xFailOverCluster'; RequiredVersion='1.1'} )

    Node 'localhost'
    {
       xCluster ClusterTest
       {
            Name                          = 'TestCluster'
            StaticIPAddress               = '10.0.0.3'
            DomainAdministratorCredential = Get-Credential
        }
     }
}
```

これは PowerShell 5.0 でも動作しますが、PowerShell 5.0 では、**ModuleVersion** パラメーターを使用することをお勧めします。

## <a name="see-also"></a>関連項目

- [DSC 構成](configurations.md)
- [DSC リソース](../resources/resources.md)
