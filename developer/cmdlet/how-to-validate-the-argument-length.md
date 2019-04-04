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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857128"
---
# <a name="how-to-validate-the-argument-length"></a>引数の長さを検証する方法

この例では、コマンドレットを実行する前に、パラメーターの引数の文字 (長さ) の数を確認、Windows PowerShell ランタイムが使用できる検証規則を指定する方法を示します。 ValidateLength 属性を宣言することで、この検証規則を設定します。

> [!NOTE]
> この属性を定義するクラスの詳細については、[System.Management.Automation.Validatelengthattribute](/dotnet/api/System.Management.Automation.ValidateLengthAttribute)を参照してください。

## <a name="to-validate-the-argument-length"></a>引数の長さを検証するには

- 次のコードに示すように、検証属性を追加します。 この例では、引数の長さは 0 ~ 10 文字の長さである必要がありますを指定します。

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

この属性を宣言する方法の詳細については、[ValidateLength 属性宣言](./validatelength-attribute-declaration.md)を参照してください。

## <a name="see-also"></a>参照

[ValidateLength 属性の宣言](./validatelength-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
