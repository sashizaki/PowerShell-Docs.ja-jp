---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: d3a625d05eaf4e7448b4abf90499f6a94e2f7718
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="allowing-for-identical-duplicate-resources-in-a-configuration"></a><span data-ttu-id="d08a3-102">構成における同一重複リソースの許容</span><span class="sxs-lookup"><span data-stu-id="d08a3-102">Allowing for Identical Duplicate Resources in a Configuration</span></span>

<span data-ttu-id="d08a3-103">DSC は、構成内で競合するリソース定義を許可せず、処理しません。</span><span class="sxs-lookup"><span data-stu-id="d08a3-103">DSC does not allow or handle conflicting resource definitions within a configuration.</span></span> <span data-ttu-id="d08a3-104">競合を解決するのではなく、ただの失敗となります。</span><span class="sxs-lookup"><span data-stu-id="d08a3-104">Instead of trying to resolve the conflict, it simply fails.</span></span> <span data-ttu-id="d08a3-105">複合リソースなどの間で構成の再利用が多く行われるようになるほど、競合は頻繁に発生します。</span><span class="sxs-lookup"><span data-stu-id="d08a3-105">As configuration reuse becomes more utilized through composite resources, etc. conflicts will occur more often.</span></span> <span data-ttu-id="d08a3-106">競合するリソース定義が一致する場合、DSC は賢くこれを許可します。</span><span class="sxs-lookup"><span data-stu-id="d08a3-106">When conflicting resource definitions are identical, DSC should be smart and allow this.</span></span> <span data-ttu-id="d08a3-107">このリリースにより、同一の定義を持つ複数のリソース インスタンスをサポートするようになりました:</span><span class="sxs-lookup"><span data-stu-id="d08a3-107">With this release, we support having multiple resource instances that have identical definitions:</span></span>

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

<span data-ttu-id="d08a3-108">以前のリリースでは、'Web サーバー' ロールが確実にインストールされるようにするために発生する WindowsFeature FE_IIS と WindowsFeature Worker_IIS インスタンス間の競合により、コンパイルの失敗に終わっていました。</span><span class="sxs-lookup"><span data-stu-id="d08a3-108">In previous releases, the result would be a failed compilation due to a conflict between the WindowsFeature FE_IIS and WindowsFeature Worker_IIS instances trying to ensure the 'Web-Server' role is installed.</span></span> <span data-ttu-id="d08a3-109">構成が実行される*すべて*のプロパティは、これら 2 つの構成間で一致していることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="d08a3-109">Notice that *all* of the properties that are being configured are identical in these two configurations.</span></span> <span data-ttu-id="d08a3-110">これらの 2 つのプロパティのリソースは*すべて*一致するため、結果として正常にコンパイルできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d08a3-110">Since *all* of the properties in these two resources are identical, this will result in a successful compilation now.</span></span> 

<span data-ttu-id="d08a3-111">2 つのリソース間でいずれかのプロパティが異なる場合、一致していないと見なされ、コンパイルは失敗します:</span><span class="sxs-lookup"><span data-stu-id="d08a3-111">If any of the properties are different between the two resources, they will not be considered identical and compilation will fail:</span></span>

```powershell
Configuration IIS_FrontEnd
{
    WindowsFeature FE_IIS
    {
        Ensure = 'Present'     # Ensure is Present here
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
    WindowsFeature Worker_IIS
    {
        Ensure = 'Absent'      # Ensure property is Absent instead of Present
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

<span data-ttu-id="d08a3-112">この非常に類似した構成は、WindowsFeature FE_IIS と WindowsFeature Worker_IIS リソースが一致せず、競合が発生するようになったため、失敗します。</span><span class="sxs-lookup"><span data-stu-id="d08a3-112">This very similar configuration will fail because the WindowsFeature FE_IIS and the WindowsFeature Worker_IIS resources are no longer identical and therefore conflict.</span></span>

