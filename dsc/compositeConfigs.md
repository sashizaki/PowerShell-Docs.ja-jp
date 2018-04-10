---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成を入れ子にする
ms.openlocfilehash: 9c6dbce462f7481e5714039a95ae85f85be0072e
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="nesting-dsc-configurations"></a><span data-ttu-id="107a2-103">DSC 構成を入れ子にする</span><span class="sxs-lookup"><span data-stu-id="107a2-103">Nesting DSC configurations</span></span>

<span data-ttu-id="107a2-104">入れ子構成 (複合構成とも呼ぶ) とは、別の構成内でリソースとして呼び出される構成です。</span><span class="sxs-lookup"><span data-stu-id="107a2-104">A nested configuration (also called composite configuration) is a configuration that is called within another configuration as if it were a resource.</span></span>
<span data-ttu-id="107a2-105">両方の構成は、同じファイルで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="107a2-105">Both configurations must be defined in the same file.</span></span>

<span data-ttu-id="107a2-106">簡単な例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="107a2-106">Let's look at a simple example:</span></span>

```powershell
Configuration FileConfig
{
    param (
        [Parameter(Mandatory = $true)]
        [String] $CopyFrom,

        [Parameter(Mandatory = $true)]
        [String] $CopyTo
    )

    Import-DscResource -ModuleName PSDesiredStateConfiguration

    File FileTest
       {
           SourcePath = $CopyFrom
           DestinationPath = $CopyTo
           Ensure = 'Present'
       }

}

Configuration NestedFileConfig
{
    Node localhost
    {
        FileConfig NestedConfig
        {
            CopyFrom = 'C:\Test\TestFile.txt'
            CopyTo = 'C:\Test2'
        }
    }
}
```

<span data-ttu-id="107a2-107">この例では、`FileConfig` は **CopyFrom** および **CopyTo** という 2 つの必須パラメーターを受け取り、それらは `File` リソース ブロック内の **SourcePath** プロパティおよび **DestinationPath** プロパティの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="107a2-107">In this example, `FileConfig` takes two mandatory parameters,  **CopyFrom** and **CopyTo**, which are used as the values for the **SourcePath** and **DestinationPath** properties in the `File` resource block.</span></span>
<span data-ttu-id="107a2-108">`NestedConfig` 構成は `FileConfig` をリソースとして呼び出します。</span><span class="sxs-lookup"><span data-stu-id="107a2-108">The `NestedConfig` configuration calls `FileConfig` as if it were a resource.</span></span>
<span data-ttu-id="107a2-109">`NestedConfig` リソース ブロック内のプロパティ (**CopyFrom** と **CopyTo**) は、`FileConfig` 構成のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="107a2-109">The properties in the `NestedConfig` resource block (**CopyFrom** and **CopyTo**) are the parameters of the `FileConfig` configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="107a2-110">参照</span><span class="sxs-lookup"><span data-stu-id="107a2-110">See Also</span></span>

- [<span data-ttu-id="107a2-111">複合リソース: リソースとしての DSC 構成の使用</span><span class="sxs-lookup"><span data-stu-id="107a2-111">Composite resources--Using a DSC configuration as a resource</span></span>](authoringResourceComposite.md)