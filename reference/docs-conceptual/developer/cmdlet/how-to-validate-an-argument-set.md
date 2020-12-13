---
ms.date: 09/13/2016
ms.topic: reference
title: 引数セットを検証する方法
description: 引数セットを検証する方法
ms.openlocfilehash: 50ec0a48277893584d896e14ad6aa843682a28cc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92650370"
---
# <a name="how-to-validate-an-argument-set"></a><span data-ttu-id="f20ea-103">引数セットを検証する方法</span><span class="sxs-lookup"><span data-stu-id="f20ea-103">How to Validate an Argument Set</span></span>

<span data-ttu-id="f20ea-104">この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数を確認するために使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f20ea-104">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="f20ea-105">この検証規則は、パラメーター引数に有効な値のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="f20ea-105">This validation rule provides a set of the valid values for the parameter argument.</span></span>

> [!NOTE]
> <span data-ttu-id="f20ea-106">この属性を定義するクラスの詳細については、「 [Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f20ea-106">For more information about the class that defines this attribute, see [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute).</span></span>

## <a name="to-validate-an-argument-set"></a><span data-ttu-id="f20ea-107">引数セットを検証するには</span><span class="sxs-lookup"><span data-stu-id="f20ea-107">To validate an argument set</span></span>

- <span data-ttu-id="f20ea-108">次のコードに示すように、ValidateSet 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="f20ea-108">Add the ValidateSet attribute as shown in the following code.</span></span> <span data-ttu-id="f20ea-109">この例では、パラメーターに使用可能な3つの値のセットを指定し `UserName` ます。</span><span class="sxs-lookup"><span data-stu-id="f20ea-109">This example specifies a set of three possible values for the `UserName` parameter.</span></span>

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

<span data-ttu-id="f20ea-110">この属性を宣言する方法の詳細については、「 [Validateset 属性宣言](./validateset-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f20ea-110">For more information about how to declare this attribute, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f20ea-111">参照</span><span class="sxs-lookup"><span data-stu-id="f20ea-111">See Also</span></span>

[<span data-ttu-id="f20ea-112">Validatesetattribute (システム管理)</span><span class="sxs-lookup"><span data-stu-id="f20ea-112">System.Management.Automation.Validatesetattribute</span></span>](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[<span data-ttu-id="f20ea-113">ValidateSet 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="f20ea-113">ValidateSet Attribute Declaration</span></span>](./validateset-attribute-declaration.md)

[<span data-ttu-id="f20ea-114">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="f20ea-114">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
