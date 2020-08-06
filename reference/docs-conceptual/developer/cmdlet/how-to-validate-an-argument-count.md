---
title: 引数のカウントを検証する方法 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateCount attribute, example
ms.openlocfilehash: e7c0eb364a6975cec089b984c2100d476631a12d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782125"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="c246f-102">引数カウントを検証する方法</span><span class="sxs-lookup"><span data-stu-id="c246f-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="c246f-103">この例では、コマンドレットを実行する前に、パラメーターが受け取る引数の数 (カウント) を確認するために Windows PowerShell ランタイムで使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c246f-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="c246f-104">この検証規則を設定するには、ValidateCount 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="c246f-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="c246f-105">この属性を定義するクラスの詳細については、「system.string」[を参照してください。](/dotnet/api/System.Management.Automation.ValidateCountAttribute)</span><span class="sxs-lookup"><span data-stu-id="c246f-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="c246f-106">引数の数を検証するには</span><span class="sxs-lookup"><span data-stu-id="c246f-106">To validate an argument count</span></span>

- <span data-ttu-id="c246f-107">次のコードに示すように Validate 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="c246f-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="c246f-108">この例では、パラメーターが1つの引数を受け取るか、または最大3つの引数を受け取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="c246f-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="c246f-109">この属性を宣言する方法の詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c246f-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c246f-110">参照</span><span class="sxs-lookup"><span data-stu-id="c246f-110">See Also</span></span>

[<span data-ttu-id="c246f-111">ValidateCount 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="c246f-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="c246f-112">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="c246f-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
