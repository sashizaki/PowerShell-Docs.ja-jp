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
# <a name="import-a-specific-version-of-an-installed-resource"></a><span data-ttu-id="b832a-103">インストールされているリソースの特定のバージョンをインポートする</span><span class="sxs-lookup"><span data-stu-id="b832a-103">Import a specific version of an installed resource</span></span>

> <span data-ttu-id="b832a-104">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="b832a-104">Applies To: Windows PowerShell 5.0</span></span>

<span data-ttu-id="b832a-105">PowerShell 5.0 以降、DSC リソースの個別のバージョンは、コンピューターのサイド バイ サイドでインストールできます。</span><span class="sxs-lookup"><span data-stu-id="b832a-105">In PowerShell 5.0, separate versions of DSC resources can be installed on a computer side by side.</span></span> <span data-ttu-id="b832a-106">リソース モジュールは、という名前のフォルダーのバージョンで別のバージョンのリソースを格納できます。</span><span class="sxs-lookup"><span data-stu-id="b832a-106">A resource module can store separate versions of a resource in version named folders.</span></span>

## <a name="installing-separate-resource-versions-side-by-side"></a><span data-ttu-id="b832a-107">別のリソース バージョンのサイド バイ サイドのインストール</span><span class="sxs-lookup"><span data-stu-id="b832a-107">Installing separate resource versions side by side</span></span>

<span data-ttu-id="b832a-108">[Install-Module](/powershell/module/PowershellGet/Install-Module) コマンドレットの **MinimumVersion**、**MaximumVersion**、**RequiredVersion** の各パラメーターを使用すると、インストールするモジュールのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b832a-108">You can use the **MinimumVersion**, **MaximumVersion**, and **RequiredVersion** parameters of the [Install-Module](/powershell/module/PowershellGet/Install-Module) cmdlet to specify which version of a module to install.</span></span> <span data-ttu-id="b832a-109">バージョンを指定せずに **Install-Module** を呼び出すと、最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b832a-109">Calling **Install-Module** without specifying a version installs the most recent version.</span></span>

<span data-ttu-id="b832a-110">たとえば、**xFailOverCluster** モジュールのバージョンが複数あり、それぞれに **xCluster** リソースが含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="b832a-110">For example, there are multiple versions of the **xFailOverCluster** module, each of which contains an **xCluster** resource.</span></span> <span data-ttu-id="b832a-111">呼び出す**Install-module**数バージョンを指定することがなく、モジュールの最新バージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b832a-111">Calling **Install-Module** without specifying the version number installs the most recent version of the module.</span></span>

```powershell
PS> Install-Module xFailOverCluster
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, ...
```

<span data-ttu-id="b832a-112">特定のバージョンのモジュールをインストールするには、指定、 **RequiredVersion** 1.1.0.0 の。</span><span class="sxs-lookup"><span data-stu-id="b832a-112">To install a specific version of a module, specify a **RequiredVersion** of 1.1.0.0.</span></span> <span data-ttu-id="b832a-113">これには、インストールされているバージョンと並行指定されたバージョンがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b832a-113">This installs the specified version side by side with the installed version.</span></span>

```powershell
PS> Install-Module xFailOverCluster -RequiredVersion 1.1
```

<span data-ttu-id="b832a-114">これで、両方を表示します。 モジュールのバージョンを使用する場合にも表示`Get-DSCResource`します。</span><span class="sxs-lookup"><span data-stu-id="b832a-114">Now, you see both version of the module listed when you use `Get-DSCResource`.</span></span>

```powershell
PS> Get-DscResource xCluster
```

```output
ImplementedAs   Name                      ModuleName                     Version    Properties
-------------   ----                      ----------                     -------    ----------
PowerShell      xCluster                  xFailOverCluster               1.1        {DomainAdministratorCredential, Name, ...
PowerShell      xCluster                  xFailOverCluster               1.2.0.0    {DomainAdministratorCredential, Name, ...
```

## <a name="specifying-a-resource-version-in-a-configuration"></a><span data-ttu-id="b832a-115">構成でのリソース バージョンの指定</span><span class="sxs-lookup"><span data-stu-id="b832a-115">Specifying a resource version in a configuration</span></span>

<span data-ttu-id="b832a-116">別のリソースのバージョンがコンピューターにインストールした場合は、構成で使用すると、そのリソースのバージョンを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b832a-116">If you have separate resource versions installed on a computer, you must specify the version of that resource when you use it in a configuration.</span></span> <span data-ttu-id="b832a-117">これを行うには、**Import-DscResource** キーワードの **ModuleVersion** パラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="b832a-117">You do this by specifying the **ModuleVersion** parameter of the **Import-DscResource** keyword.</span></span> <span data-ttu-id="b832a-118">複数のバージョンがインストールされているリソースのリソース モジュールのバージョンを指定しないと、構成によってエラーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="b832a-118">If you fail to specify the version of a resource module of a resource of which you have more than one version installed, the configuration generates an error.</span></span>

<span data-ttu-id="b832a-119">次の構成は、呼び出すリソースのバージョンを指定する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="b832a-119">The following configuration shows how to specify the version of the resource to call:</span></span>

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

><span data-ttu-id="b832a-120">注: Import-dscresource の ModuleVersion パラメーターは、PowerShell 4.0 でご利用いただけません。</span><span class="sxs-lookup"><span data-stu-id="b832a-120">Note: The ModuleVersion parameter of Import-DscResource is not available in PowerShell 4.0.</span></span> <span data-ttu-id="b832a-121">PowerShell 4.0 では、Import-DscResource の ModuleName パラメーターにモジュール指定オブジェクトを渡すことで、モジュールのバージョンを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b832a-121">In PowerShell 4.0, you can specify a module version by passing a module specification object to the ModuleName parameter of Import-DscResource.</span></span> <span data-ttu-id="b832a-122">モジュール指定オブジェクトは、ModuleName キーと RequiredVersion キーを含むハッシュ テーブルです。</span><span class="sxs-lookup"><span data-stu-id="b832a-122">A module specification object is a hash table that contains ModuleName and RequiredVersion  keys.</span></span> <span data-ttu-id="b832a-123">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="b832a-123">For example:</span></span>

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

<span data-ttu-id="b832a-124">これは PowerShell 5.0 でも動作しますが、PowerShell 5.0 では、**ModuleVersion** パラメーターを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b832a-124">This will also work in PowerShell 5.0, but it is recommended that you use the **ModuleVersion** parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="b832a-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="b832a-125">See also</span></span>

- [<span data-ttu-id="b832a-126">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="b832a-126">DSC Configurations</span></span>](configurations.md)
- [<span data-ttu-id="b832a-127">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="b832a-127">DSC Resources</span></span>](../resources/resources.md)
