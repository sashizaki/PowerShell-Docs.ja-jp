---
title: 引数セットを検証する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateSet attribute, example
ms.assetid: 55f0f664-d2ad-4501-a3dc-9f7a27c8ab11
caps.latest.revision: 8
ms.openlocfilehash: 6d8b189ed6311efd5a7348ab1e58934e9bff12a3
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365511"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="a001a-102">引数セットを検証する方法</span><span class="sxs-lookup"><span data-stu-id="a001a-102">How to Validate an Argument Set</span></span>

<span data-ttu-id="a001a-103">この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数を確認するために使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="a001a-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="a001a-104">この検証規則は、パラメーター引数に有効な値のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="a001a-104">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="a001a-105">この属性を定義するクラスの詳細については、「 [Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a001a-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="a001a-106">引数セットを検証するには</span><span class="sxs-lookup"><span data-stu-id="a001a-106">To validate an argument set</span></span>

- <span data-ttu-id="a001a-107">次のコードに示すように、ValidateSet 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="a001a-107">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="a001a-108">この例では、`UserName` パラメーターに使用可能な3つの値のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="a001a-108">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

    ```csharp
    [ValidateSet("Steve", "Mary", "Carl", IgnoreCase = true)]
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }

    private string userName;
    ```

<span data-ttu-id="a001a-109">この属性を宣言する方法の詳細については、「 [Validateset 属性宣言](./validateset-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a001a-109">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a001a-110">参照</span><span class="sxs-lookup"><span data-stu-id="a001a-110">See Also</span></span>

[<span data-ttu-id="a001a-111">Validatesetattribute (システム管理)</span><span class="sxs-lookup"><span data-stu-id="a001a-111">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="a001a-112">ValidateSet 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="a001a-112">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="a001a-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="a001a-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)