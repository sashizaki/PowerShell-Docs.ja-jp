---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成内での条件付きステートメントとループ
description: この記事では、条件ステートメントとループを使って Configuration をより動的にする方法を説明します。 条件ステートメントとループをパラメーターおよび構成データと組み合わせることで、Configuration をコンパイルするときの柔軟性と制御が増します。
ms.openlocfilehash: 7af8a360c17a0842fa2b95d1d1fb288323c327ef
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658465"
---
# <a name="conditional-statements-and-loops-in-a-configuration"></a><span data-ttu-id="dafa2-105">Configuration 内での条件付きステートメントとループ</span><span class="sxs-lookup"><span data-stu-id="dafa2-105">Conditional statements and loops in a Configuration</span></span>

<span data-ttu-id="dafa2-106">PowerShell のフロー制御キーワードを使って、[Configuration](configurations.md) をより動的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-106">You can make your [Configuration](configurations.md) more dynamic by using PowerShell flow-control keywords.</span></span> <span data-ttu-id="dafa2-107">この記事では、条件ステートメントとループを使って `Configuration` をより動的にする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="dafa2-107">This article shows you how you can use conditional statements and loops to make your `Configuration` more dynamic.</span></span> <span data-ttu-id="dafa2-108">条件ステートメントとループを[パラメーター](add-parameters-to-a-configuration.md)および[構成データ](configData.md)と組み合わせることで、`Configuration` をコンパイルするときの柔軟性と制御が増します。</span><span class="sxs-lookup"><span data-stu-id="dafa2-108">Combining conditional statements and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your `Configuration`.</span></span>

<span data-ttu-id="dafa2-109">関数またはスクリプト ブロックと同じように、`Configuration` 内で任意の PowerShell 言語の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-109">Just like a function or a script block, you can use any PowerShell language feature within a `Configuration`.</span></span> <span data-ttu-id="dafa2-110">使用するステートメントは、`.mof` ファイルをコンパイルするために `Configuration` を呼び出すときにのみ評価されます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-110">The statements you use will only be evaluated when you call your `Configuration` to compile a `.mof` file.</span></span> <span data-ttu-id="dafa2-111">次の例では、シナリオを使って概念を説明します。</span><span class="sxs-lookup"><span data-stu-id="dafa2-111">The examples below show scenarios to demonstrate concepts.</span></span> <span data-ttu-id="dafa2-112">条件ステートメントとループは、パラメーターや構成データと共に使われることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="dafa2-112">Conditional statements and loops are more often used with parameters and configuration Data.</span></span>

<span data-ttu-id="dafa2-113">この例では、 **Service** リソース ブロックでコンパイル時にサービスの現在の状態を取得し、現在の状態を保持する `.mof` ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="dafa2-113">In this  example, the **Service** resource block retrieves the current state of a service at compile time to generate a `.mof` file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="dafa2-114">動的な Resource ブロックを使うと、IntelliSense の有効性は失われます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-114">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="dafa2-115">PowerShell のパーサーでは、`Configuration` がコンパイルされるまで、指定された値が許容されるかどうかを判断できません。</span><span class="sxs-lookup"><span data-stu-id="dafa2-115">The PowerShell parser cannot determine if the values specified are acceptable until the `Configuration` is compiled.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Service Spooler
        {
            Name = "Spooler"
            State = $(Get-Service -Name 'spooler').Status
            StartType = $(Get-Service -Name 'spooler').StartType
        }
    }
}
```

<span data-ttu-id="dafa2-116">さらに、`foreach` ループを使って、現在のコンピューター上のすべてのサービスに対して **Service** リソース ブロックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-116">Additionally, you could create a **Service** resource block for every service on the current machine using a `foreach` loop.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        foreach ($service in $(Get-Service))
        {
            Service $service.Name
            {
                Name = $service.Name
                State = $service.Status
                StartType = $service.StartType
            }
        }
    }
}
```

<span data-ttu-id="dafa2-117">また、`if` ステートメントを使用してオンラインになっているコンピューターに対してのみ `Configuration` を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-117">You could also create a `Configuration` only for machines that are online by using an `if` statement.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    foreach ($computer in @('Server01', 'Server02', 'Server03'))
    {
        if (Test-Connection -ComputerName $computer)
        {
            Node $computer
            {
                Service "Spooler"
                {
                    Name = "Spooler"
                    State = "Started"
                }
            }
        }
    }
}
```

> [!NOTE]
> <span data-ttu-id="dafa2-118">上の例の動的なリソース ブロックでは、現在のコンピューターが参照されています。</span><span class="sxs-lookup"><span data-stu-id="dafa2-118">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="dafa2-119">このインスタンスでは、それはターゲット ノードではなく、`Configuration` を作成しているコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="dafa2-119">In this instance, that would be the machine you are authoring the `Configuration` on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="dafa2-120">まとめ</span><span class="sxs-lookup"><span data-stu-id="dafa2-120">Summary</span></span>

<span data-ttu-id="dafa2-121">まとめると、`Configuration` 内では任意の PowerShell 言語の機能を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-121">In summary, you can use any PowerShell language feature within a `Configuration`.</span></span>

<span data-ttu-id="dafa2-122">これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-122">This includes things like:</span></span>

- <span data-ttu-id="dafa2-123">カスタム オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dafa2-123">Custom Objects</span></span>
- <span data-ttu-id="dafa2-124">ハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="dafa2-124">Hashtables</span></span>
- <span data-ttu-id="dafa2-125">文字列操作</span><span class="sxs-lookup"><span data-stu-id="dafa2-125">String manipulation</span></span>
- <span data-ttu-id="dafa2-126">リモート処理</span><span class="sxs-lookup"><span data-stu-id="dafa2-126">Remoting</span></span>
- <span data-ttu-id="dafa2-127">WMI と CIM</span><span class="sxs-lookup"><span data-stu-id="dafa2-127">WMI and CIM</span></span>
- <span data-ttu-id="dafa2-128">ActiveDirectory オブジェクト</span><span class="sxs-lookup"><span data-stu-id="dafa2-128">ActiveDirectory objects</span></span>
- <span data-ttu-id="dafa2-129">その他...</span><span class="sxs-lookup"><span data-stu-id="dafa2-129">and more...</span></span>

<span data-ttu-id="dafa2-130">`Configuration` で定義されているすべての PowerShell コードはコンパイル時に評価されますが、`Configuration` を含むスクリプトにコードを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-130">Any PowerShell code defined in a `Configuration` is evaluated at compile time, but you can also place code in the script containing your `Configuration`.</span></span> <span data-ttu-id="dafa2-131">`Configuration` ブロックの外部にあるすべてのコードは、`Configuration` をインポートするときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="dafa2-131">Any code outside of the `Configuration` block is executed when you import your `Configuration`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dafa2-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="dafa2-132">See also</span></span>

- [<span data-ttu-id="dafa2-133">構成にパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="dafa2-133">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="dafa2-134">構成から構成データを分離する</span><span class="sxs-lookup"><span data-stu-id="dafa2-134">Separate Configuration data from Configurations</span></span>](configData.md)
