---
ms.date: 12/12/2018
keywords: DSC, PowerShell, 構成, セットアップ
title: 構成内での条件付きステートメントとループ
ms.openlocfilehash: 0073d94d28afbb45bb635442129a6cddde4c805a
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53402317"
---
# <a name="conditional-statements-and-loops-in-configurations"></a><span data-ttu-id="757b8-103">構成内での条件付きステートメントとループ</span><span class="sxs-lookup"><span data-stu-id="757b8-103">Conditional statements and loops in Configurations</span></span>

<span data-ttu-id="757b8-104">行うことができます、[構成](configurations.md)より動的な PowerShell のフロー制御キーワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="757b8-104">You can make your [Configurations](configurations.md) more dynamic using PowerShell flow-control keywords.</span></span> <span data-ttu-id="757b8-105">この記事では説明する条件付きのステートメントとループを使用して、動的な構成を作成する方法。</span><span class="sxs-lookup"><span data-stu-id="757b8-105">This article will show you how you can use conditional statements, and loops to make your Configurations more dynamic.</span></span> <span data-ttu-id="757b8-106">結合条件とループの[パラメーター](add-parameters-to-a-configuration.md)と[構成データ](configData.md)できる柔軟性と制御の構成をコンパイルするときにします。</span><span class="sxs-lookup"><span data-stu-id="757b8-106">Combining conditional and loops with [parameters](add-parameters-to-a-configuration.md) and [Configuration Data](configData.md) allows you more flexibility and control when compiling your Configurations.</span></span>

<span data-ttu-id="757b8-107">関数またはスクリプト ブロックと同じようには、構成内の任意の PowerShell 言語を使用できます。</span><span class="sxs-lookup"><span data-stu-id="757b8-107">Just like a Function or a Script Block, you can use any PowerShell language within a Configuration.</span></span> <span data-ttu-id="757b8-108">使用するステートメントは、".mof"ファイルをコンパイルするための構成を呼び出すときにのみ評価されます。</span><span class="sxs-lookup"><span data-stu-id="757b8-108">The statements you use will only be evaluated when you call your Configuration to compile a ".mof" file.</span></span> <span data-ttu-id="757b8-109">次の例では、概念を説明する単純なシナリオを説明します。</span><span class="sxs-lookup"><span data-stu-id="757b8-109">The examples below show simple scenarios to demonstrate concepts.</span></span> <span data-ttu-id="757b8-110">条件は、ループはパラメーターと構成データをよりよく使用されます。</span><span class="sxs-lookup"><span data-stu-id="757b8-110">Conditionals are loops are more often used with parameters and Configuration Data.</span></span>

<span data-ttu-id="757b8-111">この簡単な例で、**サービス**リソース ブロックは、現在の状態を保持する".mof"ファイルを生成するコンパイル時に、サービスの現在の状態を取得します。</span><span class="sxs-lookup"><span data-stu-id="757b8-111">In this simple example, the **Service** resource block retrieves the current state of a service at compile time to generate a ".mof" file that maintains its current state.</span></span>

> [!NOTE]
> <span data-ttu-id="757b8-112">動的リソースのブロックを使用すると、Intellisense の有効性を切断します。</span><span class="sxs-lookup"><span data-stu-id="757b8-112">Using dynamic Resource blocks will preempt the effectiveness of Intellisense.</span></span> <span data-ttu-id="757b8-113">PowerShell のパーサーでは、構成をコンパイルするまで指定された値が許容されるかどうかを判断できません。</span><span class="sxs-lookup"><span data-stu-id="757b8-113">The PowerShell parser cannot determine if the values specified are acceptable until the Configuration is compiled.</span></span>

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

<span data-ttu-id="757b8-114">さらに、作成することが、**サービス**ブロックの現在のコンピューター上のすべてのサービスのリソースを使用して、`foreach`ループします。</span><span class="sxs-lookup"><span data-stu-id="757b8-114">Additionally, you could create a **Service** block resource for every service on the current machine, using a `foreach` loop.</span></span>

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

<span data-ttu-id="757b8-115">単純なを使用してオンラインでマシンの構成を作成することだけでした`if`ステートメント。</span><span class="sxs-lookup"><span data-stu-id="757b8-115">You could also only create configurations for machines that are online, by using a simple `if` statement.</span></span>

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
> <span data-ttu-id="757b8-116">動的なリソースは、上記の例のリファレンスで、現在のコンピューターをブロックします。</span><span class="sxs-lookup"><span data-stu-id="757b8-116">The dynamic resource blocks in the above examples reference the current machine.</span></span> <span data-ttu-id="757b8-117">構成を作成しているコンピューターになる、このインスタンスは、ターゲット ノードではありません。</span><span class="sxs-lookup"><span data-stu-id="757b8-117">In this instance, that would be the machine you are authoring the Configuration on, not the target Node.</span></span>

<!---
Mention Get-DSCConfigurationFromSystem
-->

## <a name="summary"></a><span data-ttu-id="757b8-118">要約</span><span class="sxs-lookup"><span data-stu-id="757b8-118">Summary</span></span>

<span data-ttu-id="757b8-119">要約すると、構成内の任意の PowerShell 言語を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="757b8-119">In summary, you can use any PowerShell language within a Configuration.</span></span>

<span data-ttu-id="757b8-120">これなどが含まれます。</span><span class="sxs-lookup"><span data-stu-id="757b8-120">This includes things like:</span></span>

- <span data-ttu-id="757b8-121">カスタム オブジェクト</span><span class="sxs-lookup"><span data-stu-id="757b8-121">Custom Objects</span></span>
- <span data-ttu-id="757b8-122">ハッシュ テーブル</span><span class="sxs-lookup"><span data-stu-id="757b8-122">Hashtables</span></span>
- <span data-ttu-id="757b8-123">文字列操作</span><span class="sxs-lookup"><span data-stu-id="757b8-123">String manipulation</span></span>
- <span data-ttu-id="757b8-124">リモート処理</span><span class="sxs-lookup"><span data-stu-id="757b8-124">Remoting</span></span>
- <span data-ttu-id="757b8-125">WMI と CIM</span><span class="sxs-lookup"><span data-stu-id="757b8-125">WMI and CIM</span></span>
- <span data-ttu-id="757b8-126">Active Directory オブジェクト</span><span class="sxs-lookup"><span data-stu-id="757b8-126">ActiveDirectory objects</span></span>
- <span data-ttu-id="757b8-127">その他...</span><span class="sxs-lookup"><span data-stu-id="757b8-127">and more...</span></span>

<span data-ttu-id="757b8-128">構成で定義されている任意の PowerShell コードがコンパイル時に評価されますが、構成を含むスクリプトのコードを配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="757b8-128">Any PowerShell code defined in a Configuration will be evaluated a compile time, but you can also place code in the script containing your Configuration.</span></span> <span data-ttu-id="757b8-129">構成ブロック外の任意のコードは、構成をインポートするときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="757b8-129">Any code outside of the Configuration block will be executed when you import your Configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="757b8-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="757b8-130">See also</span></span>

- [<span data-ttu-id="757b8-131">構成にパラメーターを追加する</span><span class="sxs-lookup"><span data-stu-id="757b8-131">Add parameters to a Configuration</span></span>](add-parameters-to-a-configuration.md)
- [<span data-ttu-id="757b8-132">構成から構成データを分離する</span><span class="sxs-lookup"><span data-stu-id="757b8-132">Separate Configuration data from Configurations</span></span>](configData.md)
