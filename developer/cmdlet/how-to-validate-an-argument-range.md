---
title: 引数の範囲を検証する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange attribute, example
ms.assetid: 3cba3ab7-c3b6-4d17-aa17-88377496551b
caps.latest.revision: 9
ms.openlocfilehash: a39e34d1f1c333185f09b4a934819e1368d29a48
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859738"
---
# <a name="how-to-validate-an-argument-range"></a><span data-ttu-id="84d92-102">引数範囲を検証する方法</span><span class="sxs-lookup"><span data-stu-id="84d92-102">How to Validate an Argument Range</span></span>

<span data-ttu-id="84d92-103">この例では、コマンドレットを実行する前に、パラメーターの引数の最小値と最大値を確認、Windows PowerShell ランタイムが使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="84d92-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the minimum and maximum values of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="84d92-104">ValidateRange 属性を宣言することで、この検証規則を設定します。</span><span class="sxs-lookup"><span data-stu-id="84d92-104">You set this validation rule by declaring the ValidateRange attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="84d92-105">この属性を定義するクラスの詳細については、[System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84d92-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute).</span></span>

### <a name="to-validate-an-argument-range"></a><span data-ttu-id="84d92-106">引数の範囲を検証するには</span><span class="sxs-lookup"><span data-stu-id="84d92-106">To validate an argument range</span></span>

- <span data-ttu-id="84d92-107">次のコードに示すように、ValidateRange 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="84d92-107">Add the ValidateRange attribute as shown in the following code.</span></span> <span data-ttu-id="84d92-108">この例には、0 ~ 5 の範囲を指定する、`InputData`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="84d92-108">This example specifies a range of 0 to 5 for the `InputData` parameter.</span></span>

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

<span data-ttu-id="84d92-109">この属性を宣言する方法の詳細については、[ValidateRange 属性宣言](./validaterange-attribute-declaration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84d92-109">For more information about how to declare this attribute, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84d92-110">参照</span><span class="sxs-lookup"><span data-stu-id="84d92-110">See Also</span></span>

[<span data-ttu-id="84d92-111">ValidateRange 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="84d92-111">ValidateRange Attribute Declaration</span></span>](./validaterange-attribute-declaration.md)

[<span data-ttu-id="84d92-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="84d92-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
