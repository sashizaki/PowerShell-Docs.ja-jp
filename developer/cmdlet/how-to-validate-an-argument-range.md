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
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859738"
---
# <a name="how-to-validate-an-argument-range"></a>引数範囲を検証する方法

この例では、コマンドレットを実行する前に、パラメーターの引数の最小値と最大値を確認、Windows PowerShell ランタイムが使用できる検証規則を指定する方法を示します。 ValidateRange 属性を宣言することで、この検証規則を設定します。

> [!NOTE]
> この属性を定義するクラスの詳細については、次を参照してください。 [System.Management.Automation.Validaterangeattribute](/dotnet/api/System.Management.Automation.ValidateRangeAttribute)します。

### <a name="to-validate-an-argument-range"></a>引数の範囲を検証するには

- 次のコードに示すように、ValidateRange 属性を追加します。 この例には、0 ~ 5 の範囲を指定する、`InputData`パラメーター。

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

この属性を宣言する方法の詳細については、次を参照してください。 [ValidateRange 属性宣言](./validaterange-attribute-declaration.md)します。

## <a name="see-also"></a>参照

[ValidateRange 属性の宣言](./validaterange-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
