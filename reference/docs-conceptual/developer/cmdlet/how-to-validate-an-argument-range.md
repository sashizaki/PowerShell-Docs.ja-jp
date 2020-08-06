---
title: 引数の範囲を検証する方法 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateRange attribute, example
ms.openlocfilehash: b48b1b87425add51e855c48ec700c78c3ae296c1
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782074"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="7f897-102">引数範囲を検証する方法</span><span class="sxs-lookup"><span data-stu-id="7f897-102">How to Validate an Argument Range</span></span>

<span data-ttu-id="7f897-103">この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数の最小値と最大値を確認するために使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="7f897-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="7f897-104">この検証規則を設定するには、ValidateRange 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="7f897-104">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="7f897-105">この属性を定義するクラスの詳細については、「system.object[属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f897-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="7f897-106">引数の範囲を検証するには</span><span class="sxs-lookup"><span data-stu-id="7f897-106">To validate an argument range</span></span>

- <span data-ttu-id="7f897-107">次のコードに示すように、ValidateRange 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="7f897-107">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="7f897-108">この例では、パラメーターに 0 ~ 5 の範囲を指定し `InputData` ます。</span><span class="sxs-lookup"><span data-stu-id="7f897-108">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

<span data-ttu-id="7f897-109">この属性を宣言する方法の詳細については、「 [ValidateRange Attribute 宣言](./validaterange-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f897-109">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7f897-110">参照</span><span class="sxs-lookup"><span data-stu-id="7f897-110">See Also</span></span>

[<span data-ttu-id="7f897-111">ValidateRange 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="7f897-111">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="7f897-112">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="7f897-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
