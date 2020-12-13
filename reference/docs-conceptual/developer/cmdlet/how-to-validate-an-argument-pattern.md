---
ms.date: 09/13/2016
ms.topic: reference
title: 引数パターンを検証する方法
description: 引数パターンを検証する方法
ms.openlocfilehash: ab5777c918a53c0a3900f87c52e7f14f9cb9b726
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666911"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="d940f-103">引数パターンを検証する方法</span><span class="sxs-lookup"><span data-stu-id="d940f-103">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="d940f-104">この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数の文字パターンを確認するために使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d940f-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="d940f-105">この検証規則を設定するには、ValidatePattern 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="d940f-105">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="d940f-106">この属性を定義するクラスの詳細については、「system.servicemodel [属性](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d940f-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="d940f-107">引数パターンを検証するには</span><span class="sxs-lookup"><span data-stu-id="d940f-107">To validate an argument pattern</span></span>

- <span data-ttu-id="d940f-108">次のコードに示すように Validate 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="d940f-108">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="d940f-109">この例では、4桁のパターンを指定します。各桁の値は 0 ~ 9 です。</span><span class="sxs-lookup"><span data-stu-id="d940f-109">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

    ```csharp
    [ValidatePattern("[0-9][0-9][0-9][0-9]")]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }

    private int inputData;
    ```

<span data-ttu-id="d940f-110">この属性を宣言する方法の詳細については、「 [Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d940f-110">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d940f-111">参照</span><span class="sxs-lookup"><span data-stu-id="d940f-111">See Also</span></span>

[<span data-ttu-id="d940f-112">ValidatePattern 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="d940f-112">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="d940f-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="d940f-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
