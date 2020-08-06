---
title: 引数セットを検証する方法 |Microsoft Docs
ms.date: 09/13/2016
helpviewer_keywords:
- ValidateSet attribute, example
ms.openlocfilehash: 6173f1380583f5b27e2b188990a5ea041f447c57
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87782006"
---
# <a name="how-to-validate-an-argument-set"></a>引数セットを検証する方法

この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数を確認するために使用できる検証規則を指定する方法を示します。 この検証規則は、パラメーター引数に有効な値のセットを提供します。

> [!NOTE]
> この属性を定義するクラスの詳細については、「 [Validatesetattribute](/dotnet/api/System.Management.Automation.ValidateSetAttribute)」を参照してください。

## <a name="to-validate-an-argument-set"></a>引数セットを検証するには

- 次のコードに示すように、ValidateSet 属性を追加します。 この例では、パラメーターに使用可能な3つの値のセットを指定し `UserName` ます。

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

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](./writing-a-windows-powershell-cmdlet.md)
