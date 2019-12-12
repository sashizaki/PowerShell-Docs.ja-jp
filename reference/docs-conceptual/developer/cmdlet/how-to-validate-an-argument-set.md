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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365511"
---
# <a name="how-to-validate-an-argument-set"></a>引数セットを検証する方法

この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数を確認するために使用できる検証規則を指定する方法を示します。 この検証規則は、パラメーター引数に有効な値のセットを提供します。

> [!NOTE]
> この属性を定義するクラスの詳細については、「 [Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)」を参照してください。

## <a name="to-validate-an-argument-set"></a>引数セットを検証するには

- 次のコードに示すように、ValidateSet 属性を追加します。 この例では、`UserName` パラメーターに使用可能な3つの値のセットを指定します。

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

この属性を宣言する方法の詳細については、「 [Validateset 属性宣言](./validateset-attribute-declaration.md)」を参照してください。

## <a name="see-also"></a>参照

[Validatesetattribute (システム管理)](/dotnet/api/System.Management.Automation.ValidateSetAttribute)

[ValidateSet 属性の宣言](./validateset-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
