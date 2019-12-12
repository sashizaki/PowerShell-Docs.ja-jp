---
title: 引数のカウントを検証する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateCount attribute, example
ms.assetid: 4e6b6ac4-1003-4e7e-9d4a-9f1cf74fc4af
caps.latest.revision: 8
ms.openlocfilehash: b6ddb8185f21a65b2e3142ebb640962047e11763
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365531"
---
# <a name="how-to-validate-an-argument-count"></a><span data-ttu-id="dcbc0-102">引数カウントを検証する方法</span><span class="sxs-lookup"><span data-stu-id="dcbc0-102">How to Validate an Argument Count</span></span>

<span data-ttu-id="dcbc0-103">この例では、コマンドレットを実行する前に、パラメーターが受け取る引数の数 (カウント) を確認するために Windows PowerShell ランタイムで使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="dcbc0-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of arguments (the count) that a parameter accepts before the cmdlet is run.</span></span> <span data-ttu-id="dcbc0-104">この検証規則を設定するには、ValidateCount 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="dcbc0-104">You set this validation rule by declaring the ValidateCount attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="dcbc0-105">この属性を定義するクラスの詳細については、「system.string」[を参照してください。](/dotnet/api/System.Management.Automation.ValidateCountAttribute)</span><span class="sxs-lookup"><span data-stu-id="dcbc0-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute).</span></span>

## <a name="to-validate-an-argument-count"></a><span data-ttu-id="dcbc0-106">引数の数を検証するには</span><span class="sxs-lookup"><span data-stu-id="dcbc0-106">To validate an argument count</span></span>

- <span data-ttu-id="dcbc0-107">次のコードに示すように Validate 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="dcbc0-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="dcbc0-108">この例では、パラメーターが1つの引数を受け取るか、または最大3つの引数を受け取ることを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcbc0-108">This example specifies that the parameter will accept one argument or as many as three arguments.</span></span>

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

<span data-ttu-id="dcbc0-109">この属性を宣言する方法の詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dcbc0-109">For more information about how to declare this attribute, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dcbc0-110">参照</span><span class="sxs-lookup"><span data-stu-id="dcbc0-110">See Also</span></span>

[<span data-ttu-id="dcbc0-111">ValidateCount 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="dcbc0-111">ValidateCount Attribute Declaration</span></span>](./validatecount-attribute-declaration.md)

[<span data-ttu-id="dcbc0-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="dcbc0-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
