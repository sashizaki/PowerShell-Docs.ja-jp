---
title: 引数のパターンを検証する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidatePattern attribute, example
ms.assetid: 7ff76d4c-443a-4887-9ff8-241225f0aeec
caps.latest.revision: 9
ms.openlocfilehash: 5efc1210328c76e57a31d93b9eb52de114816c3c
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855068"
---
# <a name="how-to-validate-an-argument-pattern"></a><span data-ttu-id="8a02a-102">引数パターンを検証する方法</span><span class="sxs-lookup"><span data-stu-id="8a02a-102">How to Validate an Argument Pattern</span></span>

<span data-ttu-id="8a02a-103">この例では、Windows PowerShell ランタイムは、コマンドレットを実行する前に、パラメーターの引数の文字パターンを確認に使用できる検証規則を指定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="8a02a-103">This example shows how to specify a validation rule that the Windows PowerShell runtime can use to check the character pattern of the parameter argument before the cmdlet is run.</span></span> <span data-ttu-id="8a02a-104">この検証規則を設定するには、ValidatePattern 属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="8a02a-104">You set this validation rule by declaring the ValidatePattern attribute.</span></span>

> [!NOTE]
> <span data-ttu-id="8a02a-105">この属性を定義するクラスの詳細については、次を参照してください。 [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)します。</span><span class="sxs-lookup"><span data-stu-id="8a02a-105">For more information about the class that defines this attribute, see [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute).</span></span>

## <a name="to-validate-an-argument-pattern"></a><span data-ttu-id="8a02a-106">引数のパターンを検証するには</span><span class="sxs-lookup"><span data-stu-id="8a02a-106">To validate an argument pattern</span></span>

- <span data-ttu-id="8a02a-107">次のコードに示すように、検証属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="8a02a-107">Add the Validate attribute as shown in the following code.</span></span> <span data-ttu-id="8a02a-108">この例では、各桁が 0 ~ 9 の値を持つ、4 桁の数字のパターンを指定します。</span><span class="sxs-lookup"><span data-stu-id="8a02a-108">This example specifies a pattern of four digits, where each digit has a value of 0 through 9.</span></span>

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

<span data-ttu-id="8a02a-109">この属性を宣言する方法の詳細については、次を参照してください。 [ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="8a02a-109">For more information about how to declare this attribute, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8a02a-110">参照</span><span class="sxs-lookup"><span data-stu-id="8a02a-110">See Also</span></span>

[<span data-ttu-id="8a02a-111">ValidatePattern 属性の宣言</span><span class="sxs-lookup"><span data-stu-id="8a02a-111">ValidatePattern Attribute Declaration</span></span>](./validatepattern-attribute-declaration.md)

[<span data-ttu-id="8a02a-112">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="8a02a-112">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
