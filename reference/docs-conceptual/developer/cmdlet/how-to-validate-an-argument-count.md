---
ms.date: 09/13/2016
ms.topic: reference
title: 引数カウントを検証する方法
description: 引数カウントを検証する方法
ms.openlocfilehash: 46a32d61138fb50bceea98171f76749c9d96734d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666945"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="ac075-103">引数カウントを検証する方法</span><span class="sxs-lookup"><span data-stu-id="ac075-103">How to Validate an Argument Count</span></span>

<span data-ttu-id="ac075-104">この例では、コマンドレットを実行する前に、パラメーターが受け取る引数の数 (カウント) を確認するために Windows PowerShell ランタイムで使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ac075-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="ac075-105">この検証規則を設定するには、ValidateCount 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="ac075-105">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="ac075-106">この属性を定義するクラスの詳細については、「system.string」[を参照してください。](/dotnet/api/System.Management.Automation.ValidateCountAttribute)</span><span class="sxs-lookup"><span data-stu-id="ac075-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="ac075-107">引数の数を検証するには</span><span class="sxs-lookup"><span data-stu-id="ac075-107">To validate an argument count</span></span>

- <span data-ttu-id="ac075-108">次のコードに示すように Validate 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="ac075-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="ac075-109">この例では、パラメーターが1つの引数を受け取るか、または最大3つの引数を受け取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac075-109">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

    ```csharp
    [ValidateCount(1, 3)]
    [Parameter(Position = 0, Mandatory = true)]
    public string[] UserNames
    {
      get { return userNames; }
      set { userNames = value; }
    }

    private string[] userNames;
    ```

<span data-ttu-id="ac075-110">この属性を宣言する方法の詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac075-110">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ac075-111">参照</span><span class="sxs-lookup"><span data-stu-id="ac075-111">See Also</span></span>

[<span data-ttu-id="ac075-112">ValidateCount 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="ac075-112">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="ac075-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="ac075-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
