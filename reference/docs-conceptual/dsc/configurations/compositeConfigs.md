---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成を入れ子にする
description: DSC を使用すると、構成を別の構成の中に入れ子にすることで複合構成を作成できます。
ms.openlocfilehash: d7a81cb9673126e92e9185aacf19c5c7c17da8ca
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92667421"
---
# <a name="nesting-dsc-configurations"></a><span data-ttu-id="e7293-104">DSC 構成を入れ子にする</span><span class="sxs-lookup"><span data-stu-id="e7293-104">Nesting DSC configurations</span></span>

<span data-ttu-id="e7293-105">入れ子構成 (複合構成とも呼ぶ) とは、別の構成内でリソースとして呼び出される構成です。</span><span class="sxs-lookup"><span data-stu-id="e7293-105">A nested configuration (also called composite configuration) is a configuration that's called within another configuration as if it were a resource.</span></span> <span data-ttu-id="e7293-106">両方の構成は、同じファイルで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7293-106">Both configurations must be defined in the same file.</span></span>

<span data-ttu-id="e7293-107">簡単な例を見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="e7293-107">Let's look at a simple example:</span></span>

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

<span data-ttu-id="e7293-108">この例では、`FileConfig` は **CopyFrom** および **CopyTo** という 2 つの必須パラメーターを受け取り、それらは `File` リソース ブロック内の **SourcePath** プロパティおよび **DestinationPath** プロパティの値として使用されます。</span><span class="sxs-lookup"><span data-stu-id="e7293-108">In this example, `FileConfig` takes two mandatory parameters, **CopyFrom** and **CopyTo** , which are used as the values for the **SourcePath** and **DestinationPath** properties in the `File` resource block.</span></span> <span data-ttu-id="e7293-109">`NestedConfig` 構成は `FileConfig` をリソースとして呼び出します。</span><span class="sxs-lookup"><span data-stu-id="e7293-109">The `NestedConfig` configuration calls `FileConfig` as if it were a resource.</span></span> <span data-ttu-id="e7293-110">`NestedConfig` リソース ブロック内のプロパティ ( **CopyFrom** と **CopyTo** ) は、`FileConfig` 構成のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="e7293-110">The properties in the `NestedConfig` resource block ( **CopyFrom** and **CopyTo** ) are the parameters of the `FileConfig` configuration.</span></span>

<span data-ttu-id="e7293-111">現在、DSC では、入れ子になった構成内に構成を入れ子にすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e7293-111">DSC doesn't currently support nesting configurations within nested configurations.</span></span> <span data-ttu-id="e7293-112">構成を入れ子にできるレイヤーの深さは 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="e7293-112">You can only nest a configuration one layer deep.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7293-113">参照</span><span class="sxs-lookup"><span data-stu-id="e7293-113">See Also</span></span>

- [<span data-ttu-id="e7293-114">複合リソース: リソースとしての DSC 構成の使用</span><span class="sxs-lookup"><span data-stu-id="e7293-114">Composite resources--Using a DSC configuration as a resource</span></span>](../resources/authoringResourceComposite.md)
