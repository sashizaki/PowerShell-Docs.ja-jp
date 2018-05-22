---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 複数のバージョンがあるリソースの使用
ms.openlocfilehash: 6400d6506106657ba28fa1f9c83d9f8ee1c93ba3
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="using-resources-with-multiple-versions"></a>複数のバージョンがあるリソースの使用

> 適用先: Windows PowerShell 5.0

PowerShell 5.0 では、DSC リソースに複数バージョンを用意することができ、コンピューターにその複数のバージョンをサイド バイ サイドでインストールできます。 これを実装するには、リソース モジュールの複数のバージョンを同じモジュール フォルダーに格納します。

## <a name="installing-multiple-resource-versions-side-by-side"></a>リソースの複数のバージョンのサイド バイ サイド インストール

[Install-Module](https://technet.microsoft.com/library/dn807162.aspx) コマンドレットの **MinimumVersion**、**MaximumVersion**、**RequiredVersion** の各パラメーターを使用すると、インストールするモジュールのバージョンを指定できます。 バージョンを指定せずに **Install-Module** を呼び出すと、最新バージョンがインストールされます。

たとえば、**xFailOverCluster** モジュールの複数のバージョンがあり、それぞれに **xCluster** リソースが含まれているとします。 バージョン番号を指定せずに **Install-Module** を呼び出すと次のようになります。

```powershell
C:\Program Files\WindowsPowerShell\Modules\xFailOverCluster> Install-Module xFailOverCluster
C:\Program Files\WindowsPowerShell\Modules\xFailOverCluster> Get-DscResource xCluster

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, ...
```

ここで、もう一度 **Install-Module** を呼び出し、**RequiredVersion** に 1.1.0.0 を指定すると、結果は次のようになります。

```powershell
C:\Program Files\WindowsPowerShell\Modules\xFailOverCluster> Install-Module xFailOverCluster -RequiredVersion 1.1
C:\Program Files\WindowsPowerShell\Modules\xFailOverCluster> Get-DscResource xCluster

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a>構成でのリソース バージョンの指定

コンピューターに複数のリソースがインストールされている場合は、構成でリソースを使用するときに、そのリソースのバージョンを指定する必要があります。 これを行うには、**Import-DscResource** キーワードの **ModuleVersion** パラメーターを指定します。 複数のバージョンがインストールされているリソースのリソース モジュールのバージョンを指定しないと、構成によってエラーが生成されます。

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

>注: Import-DscResource の ModuleVersion パラメーターは PowerShell 4.0 では使用できません。 PowerShell 4.0 では、Import-DscResource の ModuleName パラメーターにモジュール指定オブジェクトを渡すことで、モジュールのバージョンを指定できます。 モジュール指定オブジェクトは、ModuleName キーと RequiredVersion キーを含むハッシュ テーブルです。 たとえば、次のように入力します。

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
* [DSC 構成](configurations.md)
* [DSC リソース](resources.md)