---
title: 引数のカウントを検証する方法 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateCount attribute, example
ms.openlocfilehash: e7c0eb364a6975cec089b984c2100d476631a12d
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782125"
---
# <a name="how-to-validate-an-argument-count"></a>引数カウントを検証する方法

この例では、コマンドレットを実行する前に、パラメーターが受け取る引数の数 (カウント) を確認するために Windows PowerShell ランタイムで使用できる検証規則を指定する方法を示します。 この検証規則を設定するには、ValidateCount 属性を宣言します。

> [!NOTE]
> この属性を定義するクラスの詳細については、「system.string」[を参照してください。](/dotnet/api/System.Management.Automation.ValidateCountAttribute)

## <a name="to-validate-an-argument-count"></a>引数の数を検証するには

- 次のコードに示すように Validate 属性を追加します。 この例では、パラメーターが1つの引数を受け取るか、または最大3つの引数を受け取ることを指定します。

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

この属性を宣言する方法の詳細については、「 [Validatecount 属性の宣言](./validatecount-attribute-declaration.md)」を参照してください。

## <a name="see-also"></a>参照

[ValidateCount 属性の宣言](./validatecount-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
