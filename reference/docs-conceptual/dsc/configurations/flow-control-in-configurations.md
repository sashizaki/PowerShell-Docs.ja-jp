---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成内での条件付きステートメントとループ
ms.openlocfilehash: 86f75be4a3d1c1760dd6269335431e8ab9fd8d09
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736898"
---
# <a name="conditional-statements-and-loops-in-a-configuration"></a><span data-ttu-id="4d32a-103">Configuration 内での条件付きステートメントとループ</span><span class="sxs-lookup"><span data-stu-id="4d32a-103">Conditional statements and loops in a Configuration</span></span>

<span data-ttu-id="4d32a-104">PowerShell のフロー制御キーワードを使って、[Configuration](configurations.md) をより動的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-104">You can make your [Configuration](configurations.md) more dynamic by using PowerShell flow-control keywords.</span></span> <span data-ttu-id="4d32a-105">この記事では、条件ステートメントとループを使って `Configuration` をより動的にする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="4d32a-105">This article shows you how you can use conditional statements and loops to make your `Configuration` more dynamic.</span></span> <span data-ttu-id="4d32a-106">条件ステートメントとループを[パラメーター](add-parameters-to-a-configuration.md)および[構成データ](configData.md)と組み合わせることで、`Configuration` をコンパイルするときの柔軟性と制御が増します。</span><span class="sxs-lookup"><span data-stu-id="4d32a-106">Combining conditional statements and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your `Configuration`.</span></span>

<span data-ttu-id="4d32a-107">関数またはスクリプト ブロックと同じように、`Configuration` 内で任意の PowerShell 言語の機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-107">Just like a function or a script block, you can use any PowerShell language feature within a `Configuration`.</span></span>
<span data-ttu-id="4d32a-108">使用するステートメントは、`.mof` ファイルをコンパイルするために `Configuration` を呼び出すときにのみ評価されます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-108">The statements you use will only be evaluated when you call your `Configuration` to compile a `.mof` file.</span></span> <span data-ttu-id="4d32a-109">次の例では、シナリオを使って概念を説明します。</span><span class="sxs-lookup"><span data-stu-id="4d32a-109">The examples below show scenarios to demonstrate concepts.</span></span> <span data-ttu-id="4d32a-110">条件ステートメントとループは、パラメーターや構成データと共に使われることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="4d32a-110">Conditional statements and loops are more often used with parameters and configuration Data.</span></span>

<span data-ttu-id="4d32a-111">この例では、**Service** リソース ブロックでコンパイル時にサービスの現在の状態を取得し、現在の状態を保持する `.mof` ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="4d32a-111">In this  example, the **Service** resource block retrieves the current state of a service at compile time to generate a `.mof` file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="4d32a-112">動的な Resource ブロックを使うと、IntelliSense の有効性は失われます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-112">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="4d32a-113">PowerShell のパーサーでは、`Configuration` がコンパイルされるまで、指定された値が許容されるかどうかを判断できません。</span><span class="sxs-lookup"><span data-stu-id="4d32a-113">The PowerShell parser cannot determine if the values specified are acceptable until the `Configuration` is compiled.</span></span>

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

<span data-ttu-id="4d32a-114">さらに、`foreach` ループを使って、現在のコンピューター上のすべてのサービスに対して **Service** リソース ブロックを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-114">Additionally, you could create a **Service** resource block for every service on the current machine using a `foreach` loop.</span></span>

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

<span data-ttu-id="4d32a-115">また、`if` ステートメントを使用してオンラインになっているコンピューターに対してのみ `Configuration` を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-115">You could also create a `Configuration` only for machines that are online by using an `if` statement.</span></span>

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
> <span data-ttu-id="4d32a-116">上の例の動的なリソース ブロックでは、現在のコンピューターが参照されています。</span><span class="sxs-lookup"><span data-stu-id="4d32a-116">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="4d32a-117">このインスタンスでは、それはターゲット ノードではなく、`Configuration` を作成しているコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="4d32a-117">In this instance, that would be the machine you are authoring the `Configuration` on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="4d32a-118">まとめ</span><span class="sxs-lookup"><span data-stu-id="4d32a-118">Summary</span></span>

<span data-ttu-id="4d32a-119">まとめると、`Configuration` 内では任意の PowerShell 言語の機能を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-119">In summary, you can use any PowerShell language feature within a `Configuration`.</span></span>

<span data-ttu-id="4d32a-120">これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-120">This includes things like:</span></span>

- <span data-ttu-id="4d32a-121">カスタム オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4d32a-121">Custom Objects</span></span>
- <span data-ttu-id="4d32a-122">ハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="4d32a-122">Hashtables</span></span>
- <span data-ttu-id="4d32a-123">文字列操作</span><span class="sxs-lookup"><span data-stu-id="4d32a-123">String manipulation</span></span>
- <span data-ttu-id="4d32a-124">リモート処理</span><span class="sxs-lookup"><span data-stu-id="4d32a-124">Remoting</span></span>
- <span data-ttu-id="4d32a-125">WMI と CIM</span><span class="sxs-lookup"><span data-stu-id="4d32a-125">WMI and CIM</span></span>
- <span data-ttu-id="4d32a-126">ActiveDirectory オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4d32a-126">ActiveDirectory objects</span></span>
- <span data-ttu-id="4d32a-127">その他...</span><span class="sxs-lookup"><span data-stu-id="4d32a-127">and more...</span></span>

<span data-ttu-id="4d32a-128">`Configuration` で定義されているすべての PowerShell コードはコンパイル時に評価されますが、`Configuration` を含むスクリプトにコードを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-128">Any PowerShell code defined in a `Configuration` is evaluated at compile time, but you can also place code in the script containing your `Configuration`.</span></span> <span data-ttu-id="4d32a-129">`Configuration` ブロックの外部にあるすべてのコードは、`Configuration` をインポートするときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="4d32a-129">Any code outside of the `Configuration` block is executed when you import your `Configuration`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d32a-130">参照</span><span class="sxs-lookup"><span data-stu-id="4d32a-130">See also</span></span>

- [<span data-ttu-id="4d32a-131">構成にパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="4d32a-131">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="4d32a-132">構成から構成データを分離する</span><span class="sxs-lookup"><span data-stu-id="4d32a-132">Separate Configuration data from Configurations</span></span>](configData.md)
