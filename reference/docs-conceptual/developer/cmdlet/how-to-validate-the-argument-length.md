---
title: 引数の長さを検証する方法 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateLength attribute, example
ms.openlocfilehash: aa0545def6d9628f6b41090a425f0c5af25f6ad7
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784080"
---
# <a name="how-to-validate-the-argument-length"></a>引数の長さを検証する方法

この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数の文字数 (長さ) を確認するために使用できる検証規則を指定する方法を示します。 この検証規則を設定するには、ValidateLength 属性を宣言します。

> [!NOTE]
> この属性を定義するクラスの詳細については、「 [Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)」を参照してください。

## <a name="to-validate-the-argument-length"></a>引数の長さを検証するには

- 次のコードに示すように Validate 属性を追加します。 この例では、引数の長さが 0 ~ 10 文字の長さであることを指定します。

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

この属性を宣言する方法の詳細については、「 [ValidateLength Attribute 宣言](./validatelength-attribute-declaration.md)」を参照してください。

## <a name="see-also"></a>参照

[ValidateLength 属性の宣言](./validatelength-attribute-declaration.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
