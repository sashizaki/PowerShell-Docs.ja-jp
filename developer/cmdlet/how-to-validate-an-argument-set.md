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
# <a name="how-to-validate-an-argument-set"></a>引数セットを検証する方法

この例では、コマンドレットを実行する前に、パラメーターの引数を確認、Windows PowerShell ランタイムが使用できる検証規則を指定する方法を示します。 この検証規則は、パラメーターの引数の有効な値のセットを提供します。

> [!NOTE]
> この属性を定義するクラスの詳細については、次を参照してください。 [System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)します。

## <a name="to-validate-an-argument-set"></a>引数を検証するには、次のように設定します。

- 次のコードに示すように、ValidateSet 属性を追加します。 この例の 3 つの値のセットを指定する、`UserName`パラメーター。

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

この属性を宣言する方法の詳細については、次を参照してください。 [ValidateSet 属性宣言](./validateset-attribute-declaration.md)します。

## <a name="see-also"></a>参照

[System.Management.Automation.Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[ValidateSet 属性の宣言](./validateset-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
