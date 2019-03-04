---
title: 引数の数を検証する方法 |Microsoft Docs
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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859138"
---
# <a name="how-to-validate-an-argument-count"></a>引数カウントを検証する方法

この例は、パラメーターが受け取る引数 (数) の数を確認する、Windows PowerShell ランタイムを使用する検証規則を指定する方法を示します、コマンドレットの実行前にします。 ValidateCount 属性を宣言することで、この検証規則を設定します。

> [!NOTE]
> この属性を定義するクラスの詳細については、次を参照してください。 [System.Management.Automation.Validatecountattribute](/dotnet/api/System.Management.Automation.ValidateCountAttribute)します。

## <a name="to-validate-an-argument-count"></a>引数の数を検証するには

- 次のコードに示すように、検証属性を追加します。 この例では、1 つまたは 3 台の引数のパラメーターが受け入れることを指定します。

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

この属性を宣言する方法の詳細については、次を参照してください。 [ValidateCount 属性宣言](./validatecount-attribute-declaration.md)します。

## <a name="see-also"></a>参照

[ValidateCount 属性の宣言](./validatecount-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
