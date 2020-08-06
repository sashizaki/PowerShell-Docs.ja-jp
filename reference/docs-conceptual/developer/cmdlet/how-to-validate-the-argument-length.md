---
title: 引数の長さを検証する方法 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, example
ms.openlocfilehash: aa0545def6d9628f6b41090a425f0c5af25f6ad7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784080"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="5022b-102">引数の長さを検証する方法</span><span class="sxs-lookup"><span data-stu-id="5022b-102">How to Validate the Argument Length</span></span>

<span data-ttu-id="5022b-103">この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数の文字数 (長さ) を確認するために使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5022b-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="5022b-104">この検証規則を設定するには、ValidateLength 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="5022b-104">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="5022b-105">この属性を定義するクラスの詳細については、「 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5022b-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="5022b-106">引数の長さを検証するには</span><span class="sxs-lookup"><span data-stu-id="5022b-106">To validate the argument length</span></span>

- <span data-ttu-id="5022b-107">次のコードに示すように Validate 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="5022b-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="5022b-108">この例では、引数の長さが 0 ~ 10 文字の長さであることを指定します。</span><span class="sxs-lookup"><span data-stu-id="5022b-108">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

    ```csharp
    [ValidateLength(0, 10)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="5022b-109">この属性を宣言する方法の詳細については、「 [ValidateLength Attribute 宣言](./validatelength-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5022b-109">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5022b-110">参照</span><span class="sxs-lookup"><span data-stu-id="5022b-110">See Also</span></span>

[<span data-ttu-id="5022b-111">ValidateLength 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="5022b-111">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="5022b-112">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="5022b-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
