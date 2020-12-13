---
ms.date: 09/13/2016
ms.topic: reference
title: 引数範囲を検証する方法
description: 引数範囲を検証する方法
ms.openlocfilehash: 1c1c53d43350a38beb2193200de3bd6b689366a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666928"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="8c9de-103">引数範囲を検証する方法</span><span class="sxs-lookup"><span data-stu-id="8c9de-103">How to Validate an Argument Range</span></span>

<span data-ttu-id="8c9de-104">この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数の最小値と最大値を確認するために使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8c9de-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="8c9de-105">この検証規則を設定するには、ValidateRange 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="8c9de-105">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="8c9de-106">この属性を定義するクラスの詳細については、「system.object [属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c9de-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="8c9de-107">引数の範囲を検証するには</span><span class="sxs-lookup"><span data-stu-id="8c9de-107">To validate an argument range</span></span>

- <span data-ttu-id="8c9de-108">次のコードに示すように、ValidateRange 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="8c9de-108">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="8c9de-109">この例では、パラメーターに 0 ~ 5 の範囲を指定し `InputData` ます。</span><span class="sxs-lookup"><span data-stu-id="8c9de-109">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

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

<span data-ttu-id="8c9de-110">この属性を宣言する方法の詳細については、「 [ValidateRange Attribute 宣言](./validaterange-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8c9de-110">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c9de-111">参照</span><span class="sxs-lookup"><span data-stu-id="8c9de-111">See Also</span></span>

[<span data-ttu-id="8c9de-112">ValidateRange 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="8c9de-112">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="8c9de-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="8c9de-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
