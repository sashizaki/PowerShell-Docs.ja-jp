---
title: 引数パターンを検証する方法 |Microsoft Docs
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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365561"
---
# <a name="how-to-validate-an-argument-pattern"></a>引数パターンを検証する方法

この例では、コマンドレットを実行する前に、Windows PowerShell ランタイムがパラメーター引数の文字パターンを確認するために使用できる検証規則を指定する方法を示します。 この検証規則を設定するには、ValidatePattern 属性を宣言します。

> [!NOTE]
> この属性を定義するクラスの詳細については、「system.servicemodel[属性](/dotnet/api/System.Management.Automation.ValidatePatternAttribute)」を参照してください。

## <a name="to-validate-an-argument-pattern"></a>引数パターンを検証するには

- 次のコードに示すように Validate 属性を追加します。 この例では、4桁のパターンを指定します。各桁の値は 0 ~ 9 です。

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

この属性を宣言する方法の詳細については、「 [Validatepattern 属性の宣言](./validatepattern-attribute-declaration.md)」を参照してください。

## <a name="see-also"></a>参照

[ValidatePattern 属性の宣言](./validatepattern-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
