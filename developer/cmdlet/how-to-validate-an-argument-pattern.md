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
# <a name="how-to-validate-an-argument-pattern"></a>引数パターンを検証する方法

この例では、Windows PowerShell ランタイムは、コマンドレットを実行する前に、パラメーターの引数の文字パターンを確認に使用できる検証規則を指定する方法を示します。 この検証規則を設定するには、ValidatePattern 属性を宣言します。

> [!NOTE]
> この属性を定義するクラスの詳細については、次を参照してください。 [System.Management.Automation.Validatepatternattribute](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)します。

## <a name="to-validate-an-argument-pattern"></a>引数のパターンを検証するには

- 次のコードに示すように、検証属性を追加します。 この例では、各桁が 0 ~ 9 の値を持つ、4 桁の数字のパターンを指定します。

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

この属性を宣言する方法の詳細については、次を参照してください。 [ValidatePattern 属性宣言](./validatepattern-attribute-declaration.md)します。

## <a name="see-also"></a>参照

[ValidatePattern 属性の宣言](./validatepattern-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
