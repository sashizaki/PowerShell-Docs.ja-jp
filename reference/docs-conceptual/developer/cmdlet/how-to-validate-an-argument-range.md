---
title: 引数の範囲を検証する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ValidateRange attribute, example
ms.assetid: 3cba3ab7-c3b6-4d17-aa17-88377496551b
caps.latest.revision: 9
ms.openlocfilehash: a39e34d1f1c333185f09b4a934819e1368d29a48
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72365521"
---
# <a name="how-to-validate-an-argument-range"></a>引数範囲を検証する方法

この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数の最小値と最大値を確認するために使用できる検証規則を指定する方法を示します。 この検証規則を設定するには、ValidateRange 属性を宣言します。

> [!NOTE]
> この属性を定義するクラスの詳細については、「system.object[属性](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)」を参照してください。

### <a name="to-validate-an-argument-range"></a>引数の範囲を検証するには

- 次のコードに示すように、ValidateRange 属性を追加します。 この例では、`InputData` パラメーターに 0 ~ 5 の範囲を指定します。

    ```csharp
    [ValidateRange(0, 5)]
    [Parameter(Position = 0, Mandatory = true)]
    public int InputData
    {
      get { return inputData; }
      set { inputData = value; }
    }
    private int inputData;
    ```

この属性を宣言する方法の詳細については、「 [ValidateRange Attribute 宣言](./validaterange-attribute-declaration.md)」を参照してください。

## <a name="see-also"></a>参照

[ValidateRange 属性の宣言](./validaterange-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
