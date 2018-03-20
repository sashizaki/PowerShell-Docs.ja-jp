---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "複数のバージョンがあるリソースの使用"
ms.openlocfilehash: 5ca4eadfe23a4675e1b81b86d4274d7f113228fe
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="using-resources-with-multiple-versions"></a><span data-ttu-id="90592-103">複数のバージョンがあるリソースの使用</span><span class="sxs-lookup"><span data-stu-id="90592-103">Using resources with multiple versions</span></span>

> <span data-ttu-id="90592-104">適用先: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="90592-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="90592-105">PowerShell 5.0 では、DSC リソースに複数バージョンを用意することができ、コンピューターにその複数のバージョンをサイド バイ サイドでインストールできます。</span><span class="sxs-lookup"><span data-stu-id="90592-105">In PowerShell 5.0, DSC resources can have multiple versions, and versions can be installed on a computer side-by-side.</span></span> <span data-ttu-id="90592-106">これを実装するには、リソース モジュールの複数のバージョンを同じモジュール フォルダーに格納します。</span><span class="sxs-lookup"><span data-stu-id="90592-106">This is implemented by having multiple versions of a resource module that are contained in the same module folder.</span></span>

## <a name="installing-multiple-resource-versions-side-by-side"></a><span data-ttu-id="90592-107">リソースの複数のバージョンのサイド バイ サイド インストール</span><span class="sxs-lookup"><span data-stu-id="90592-107">Installing multiple resource versions side-by-side</span></span>

<span data-ttu-id="90592-108">[Install-Module](https://technet.microsoft.com/library/dn807162.aspx) コマンドレットの **MinimumVersion**、**MaximumVersion**、**RequiredVersion** の各パラメーターを使用すると、インストールするモジュールのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="90592-108">You can use the **MinimumVersion**, **MaximumVersion**, and **RequiredVersion** parameters of the [Install-Module](https://technet.microsoft.com/library/dn807162.aspx) cmdlet to specify which version of a module to install.</span></span> <span data-ttu-id="90592-109">バージョンを指定せずに **Install-Module** を呼び出すと、最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="90592-109">Calling **Install-Module** without specifying a version installs the most recent version.</span></span>

<span data-ttu-id="90592-110">たとえば、**xFailOverCluster** モジュールの複数のバージョンがあり、それぞれに **xCluster** リソースが含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="90592-110">For example, there are multiple versions of the **xFailOverCluster** module, each of which contains an **xCluster** resouce.</span></span> <span data-ttu-id="90592-111">バージョン番号を指定せずに **Install-Module** を呼び出すと次のようになります。</span><span class="sxs-lookup"><span data-stu-id="90592-111">The result of calling **Install-Module** without specifying the version number is as follows:</span></span>

```powershell
C:\Program Files\WindowsPowerShell\Modules\xFailOverCluster> Install-Module xFailOverCluster
C:\Program Files\WindowsPowerShell\Modules\xFailOverCluster> Get-DscResource xCluster

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, ...
```

<span data-ttu-id="90592-112">ここで、もう一度 **Install-Module** を呼び出し、**RequiredVersion** に 1.1.0.0 を指定すると、結果は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="90592-112">Now, if you call **Install-Module** again, but specify a **RequiredVersion** of 1.1.0.0, it results in the following:</span></span>

```powershell
C:\Program Files\WindowsPowerShell\Modules\xFailOverCluster> Install-Module xFailOverCluster -RequiredVersion 1.1
C:\Program Files\WindowsPowerShell\Modules\xFailOverCluster> Get-DscResource xCluster

ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a><span data-ttu-id="90592-113">構成でのリソース バージョンの指定</span><span class="sxs-lookup"><span data-stu-id="90592-113">Specifying a resource version in a configuration</span></span>

<span data-ttu-id="90592-114">コンピューターに複数のリソースがインストールされている場合は、構成でリソースを使用するときに、そのリソースのバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="90592-114">If you have multiple resources installed on a computer, you must specify the version of that resource when you use it in a configuration.</span></span> <span data-ttu-id="90592-115">これを行うには、**Import-DscResource** キーワードの **ModuleVersion** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="90592-115">You do this by specifying the **ModuleVersion** parameter of the **Import-DscResource** keyword.</span></span> <span data-ttu-id="90592-116">複数のバージョンがインストールされているリソースのリソース モジュールのバージョンを指定しないと、構成によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="90592-116">If you fail to specify the version of a resource module of a resource of which you have more than one version installed, the configuration generates an error.</span></span>

<span data-ttu-id="90592-117">次の構成は、呼び出すリソースのバージョンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="90592-117">The following configuration shows how to specify the version of the resource to call:</span></span>

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

><span data-ttu-id="90592-118">注: Import-DscResource の ModuleVersion パラメーターは PowerShell 4.0 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="90592-118">Note: The ModuleVersion parameter of Import-DscResource is not available in PowerShell 4.0.</span></span> <span data-ttu-id="90592-119">PowerShell 4.0 では、Import-DscResource の ModuleName パラメーターにモジュール指定オブジェクトを渡すことで、モジュールのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="90592-119">In PowerShell 4.0, you can specify a module version by passing a module specification object to the ModuleName parameter of Import-DscResource.</span></span> <span data-ttu-id="90592-120">モジュール指定オブジェクトは、ModuleName キーと RequiredVersion キーを含むハッシュ テーブルです。</span><span class="sxs-lookup"><span data-stu-id="90592-120">A module specification object is a hash table that contains ModuleName and RequiredVersion  keys.</span></span> <span data-ttu-id="90592-121">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="90592-121">For example:</span></span>

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

<span data-ttu-id="90592-122">これは PowerShell 5.0 でも動作しますが、PowerShell 5.0 では、**ModuleVersion** パラメーターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90592-122">This will also work in PowerShell 5.0, but it is recommended that you use the **ModuleVersion** parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="90592-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="90592-123">See also</span></span>
* [<span data-ttu-id="90592-124">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="90592-124">DSC Configurations</span></span>](configurations.md)
* [<span data-ttu-id="90592-125">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="90592-125">DSC Resources</span></span>](resources.md)

