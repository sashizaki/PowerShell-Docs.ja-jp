---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成内での条件付きステートメントとループ
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080137"
---
# <a name="conditional-statements-and-loops-in-configurations"></a><span data-ttu-id="99c17-103">構成内での条件付きステートメントとループ</span><span class="sxs-lookup"><span data-stu-id="99c17-103">Conditional statements and loops in Configurations</span></span>

<span data-ttu-id="99c17-104">PowerShell のフロー制御キーワードを使って、[構成](configurations.md)をより動的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="99c17-104">You can make your [Configurations](configurations.md) more dynamic using PowerShell flow-control keywords.</span></span> <span data-ttu-id="99c17-105">この記事では、条件ステートメントとループを使って構成をより動的にする方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="99c17-105">This article will show you how you can use conditional statements, and loops to make your Configurations more dynamic.</span></span> <span data-ttu-id="99c17-106">条件とループを[パラメーター](add-parameters-to-a-configuration.md)および[構成データ](configData.md)と組み合わせることで、構成をコンパイルするときの柔軟性と制御が増します。</span><span class="sxs-lookup"><span data-stu-id="99c17-106">Combining conditional and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your Configurations.</span></span>

<span data-ttu-id="99c17-107">関数またはスクリプト ブロックと同じように、構成内で任意の PowerShell 言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99c17-107">Just like a Function or a Script Block, you can use any PowerShell language within a Configuration.</span></span> <span data-ttu-id="99c17-108">使用するステートメントは、".mof" ファイルをコンパイルするために構成を呼び出すときにのみ評価されます。</span><span class="sxs-lookup"><span data-stu-id="99c17-108">The statements you use will only be evaluated when you call your Configuration to compile a ".mof" file.</span></span> <span data-ttu-id="99c17-109">次の例では、簡単なシナリオを使って概念を説明します。</span><span class="sxs-lookup"><span data-stu-id="99c17-109">The examples below show simple scenarios to demonstrate concepts.</span></span> <span data-ttu-id="99c17-110">条件とループは、パラメーターや構成データと共に使われることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="99c17-110">Conditionals are loops are more often used with parameters and Configuration Data.</span></span>

<span data-ttu-id="99c17-111">この簡単な例では、**Service** リソース ブロックでコンパイル時にサービスの現在の状態を取得し、現在の状態を保持する ".mof" ファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="99c17-111">In this simple example, the **Service** resource block retrieves the current state of a service at compile time to generate a ".mof" file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="99c17-112">動的な Resource ブロックを使うと、IntelliSense の有効性は失われます。</span><span class="sxs-lookup"><span data-stu-id="99c17-112">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="99c17-113">PowerShell のパーサーでは、構成がコンパイルされるまで、指定された値が許容されるかどうかを判断できません。</span><span class="sxs-lookup"><span data-stu-id="99c17-113">The PowerShell parser cannot determine if the values specified are acceptable until the Configuration is compiled.</span></span>

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

<span data-ttu-id="99c17-114">さらに、`foreach` ループを使って、現在のコンピューター上のすべてのサービスに対して **Service** ブロック リソースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="99c17-114">Additionally, you could create a **Service** block resource for every service on the current machine, using a `foreach` loop.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration
    Node localhost
    {
        Foreach ($service in $(Get-Service))
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

<span data-ttu-id="99c17-115">また、簡単な `if` ステートメントを使うことで、オンラインになっているコンピューターに対してのみ構成を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="99c17-115">You could also only create configurations for machines that are online, by using a simple `if` statement.</span></span>

```powershell
Configuration ServiceState
{
    # It is best practice to explicitly import any resources used in your Configurations.
    Import-DSCResource -Name Service -Module PSDesiredStateConfiguration

    Foreach ($computer in @('Server01', 'Server02', 'Server03'))
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
> <span data-ttu-id="99c17-116">上の例の動的なリソース ブロックでは、現在のコンピューターが参照されています。</span><span class="sxs-lookup"><span data-stu-id="99c17-116">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="99c17-117">このインスタンスでは、それはターゲット ノードではなく、構成を作成しているコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="99c17-117">In this instance, that would be the machine you are authoring the Configuration on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="99c17-118">要約</span><span class="sxs-lookup"><span data-stu-id="99c17-118">Summary</span></span>

<span data-ttu-id="99c17-119">まとめると、構成内では任意の PowerShell 言語を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="99c17-119">In summary, you can use any PowerShell language within a Configuration.</span></span>

<span data-ttu-id="99c17-120">これには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="99c17-120">This includes things like:</span></span>

- <span data-ttu-id="99c17-121">カスタム オブジェクト</span><span class="sxs-lookup"><span data-stu-id="99c17-121">Custom Objects</span></span>
- <span data-ttu-id="99c17-122">ハッシュテーブル</span><span class="sxs-lookup"><span data-stu-id="99c17-122">Hashtables</span></span>
- <span data-ttu-id="99c17-123">文字列操作</span><span class="sxs-lookup"><span data-stu-id="99c17-123">String manipulation</span></span>
- <span data-ttu-id="99c17-124">リモート処理</span><span class="sxs-lookup"><span data-stu-id="99c17-124">Remoting</span></span>
- <span data-ttu-id="99c17-125">WMI と CIM</span><span class="sxs-lookup"><span data-stu-id="99c17-125">WMI and CIM</span></span>
- <span data-ttu-id="99c17-126">ActiveDirectory オブジェクト</span><span class="sxs-lookup"><span data-stu-id="99c17-126">ActiveDirectory objects</span></span>
- <span data-ttu-id="99c17-127">その他...</span><span class="sxs-lookup"><span data-stu-id="99c17-127">and more...</span></span>

<span data-ttu-id="99c17-128">構成で定義されているすべての PowerShell コードはコンパイル時に評価されますが、構成を含むスクリプトにコードを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="99c17-128">Any PowerShell code defined in a Configuration will be evaluated a compile time, but you can also place code in the script containing your Configuration.</span></span> <span data-ttu-id="99c17-129">構成ブロックの外部にあるすべてのコードは、構成をインポートするときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="99c17-129">Any code outside of the Configuration block will be executed when you import your Configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="99c17-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="99c17-130">See also</span></span>

- [<span data-ttu-id="99c17-131">構成にパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="99c17-131">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="99c17-132">構成から構成データを分離する</span><span class="sxs-lookup"><span data-stu-id="99c17-132">Separate Configuration data from Configurations</span></span>](configData.md)
