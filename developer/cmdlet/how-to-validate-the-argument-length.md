---
title: 引数の長さを検証する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateLength attribute, example
ms.assetid: d5ddaa6e-4904-46da-beb0-0295a8f38332
caps.latest.revision: 12
ms.openlocfilehash: 8a21675acd087df93f93c25952c78931255d60b3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067715"
---
# <a name="how-to-validate-the-argument-length"></a><span data-ttu-id="b8c83-102">引数の長さを検証する方法</span><span class="sxs-lookup"><span data-stu-id="b8c83-102">How to Validate the Argument Length</span></span>

<span data-ttu-id="b8c83-103">この例では、コマンドレットを実行する前に、パラメーターの引数の文字 (長さ) の数を確認、Windows PowerShell ランタイムが使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="b8c83-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the number of characters (the length) of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="b8c83-104">ValidateLength 属性を宣言することで、この検証規則を設定します。</span><span class="sxs-lookup"><span data-stu-id="b8c83-104">You set this validation rule by declaring the ValidateLength attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c83-105">この属性を定義するクラスの詳細については、次を参照してください。 [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)します。</span><span class="sxs-lookup"><span data-stu-id="b8c83-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute).</span></span>

## <a name="to-validate-the-argument-length"></a><span data-ttu-id="b8c83-106">引数の長さを検証するには</span><span class="sxs-lookup"><span data-stu-id="b8c83-106">To validate the argument length</span></span>

- <span data-ttu-id="b8c83-107">次のコードに示すように、検証属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="b8c83-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="b8c83-108">この例では、引数の長さは 0 ~ 10 文字の長さである必要がありますを指定します。</span><span class="sxs-lookup"><span data-stu-id="b8c83-108">This example specifies that the length of the argument should have a length of 0 to 10 characters.</span></span>

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

<span data-ttu-id="b8c83-109">この属性を宣言する方法の詳細については、次を参照してください。 [ValidateLength 属性宣言](./validatelength-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="b8c83-109">For more information about how to declare this attribute, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8c83-110">参照</span><span class="sxs-lookup"><span data-stu-id="b8c83-110">See Also</span></span>

[<span data-ttu-id="b8c83-111">ValidateLength 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="b8c83-111">ValidateLength Attribute Declaration</span></span>](./validatelength-attribute-declaration.md)

[<span data-ttu-id="b8c83-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="b8c83-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
