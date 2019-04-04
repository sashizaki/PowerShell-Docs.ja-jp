---
title: 引数のセットを検証する方法 |Microsoft Docs
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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861368"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="8be1c-102">引数セットを検証する方法</span><span class="sxs-lookup"><span data-stu-id="8be1c-102">How to Validate an Argument Set</span></span>

<span data-ttu-id="8be1c-103">この例では、コマンドレットを実行する前に、パラメーターの引数を確認、Windows PowerShell ランタイムが使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8be1c-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="8be1c-104">この検証規則は、パラメーターの引数の有効な値のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="8be1c-104">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="8be1c-105">この属性を定義するクラスの詳細については、[System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8be1c-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="8be1c-106">引数を検証するには、次のように設定します。</span><span class="sxs-lookup"><span data-stu-id="8be1c-106">To validate an argument set</span></span>

- <span data-ttu-id="8be1c-107">次のコードに示すように、ValidateSet 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="8be1c-107">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="8be1c-108">この例の 3 つの値のセットを指定する、`UserName`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="8be1c-108">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

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

<span data-ttu-id="8be1c-109">この属性を宣言する方法の詳細については、[ValidateSet 属性宣言](./validateset-attribute-declaration.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8be1c-109">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8be1c-110">参照</span><span class="sxs-lookup"><span data-stu-id="8be1c-110">See Also</span></span>

[<span data-ttu-id="8be1c-111">System.Management.Automation.Validatesetattribute</span><span class="sxs-lookup"><span data-stu-id="8be1c-111">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="8be1c-112">ValidateSet 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="8be1c-112">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="8be1c-113">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="8be1c-113">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
