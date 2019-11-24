---
title: コマンドレットのパラメーターを宣言する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c0509cc-5a50-49ad-a74f-5527023d0270
caps.latest.revision: 10
ms.openlocfilehash: 80e3e27bcf72b078c192525a843a3b3afb306529
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365681"
---
# <a name="how-to-declare-cmdlet-parameters"></a>コマンドレット パラメーターを宣言する方法

これらの例では、名前付き、位置指定、必須、省略可能、およびスイッチのパラメーターを宣言する方法を示します。 これらの例では、パラメーターの別名を定義する方法も示しています。

## <a name="how-to-declare-a-named-parameter"></a>名前付きパラメーターを宣言する方法

- 次のコードに示すように、パブリックプロパティを定義します。 パラメーター属性を追加するときは、属性から `Position` キーワードを省略します。

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。

## <a name="how-to-declare-a-positional-parameter"></a>位置指定パラメーターを宣言する方法

- 次のコードに示すように、パブリックプロパティを定義します。 パラメーター属性を追加するときは、`Position` キーワードを引数の位置に設定します。 値が0の場合は、最初の位置を示します。

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。

## <a name="how-to-declare-a-mandatory-parameter"></a>必須パラメーターを宣言する方法

- 次のコードに示すように、パブリックプロパティを定義します。 パラメーター属性を追加するときは、`Mandatory` キーワードを `true`に設定します。

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。

## <a name="how-to-declare-an-optional-parameter"></a>省略可能なパラメーターを宣言する方法

- 次のコードに示すように、パブリックプロパティを定義します。 パラメーター属性を追加する場合は、`Mandatory` キーワードを省略します。

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a>スイッチパラメーターを宣言する方法

- パブリックプロパティを型 system.string として定義[し、パラメーター](/dotnet/api/System.Management.Automation.SwitchParameter)属性を宣言します。

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。

## <a name="how-to-declare-a-parameter-with-aliases"></a>エイリアスを使用してパラメーターを宣言する方法

- 次のコードに示すように、パブリックプロパティを定義します。 パラメーターのエイリアスを一覧表示するエイリアス属性を追加します。 この例では、同じパラメーターに対して3つのエイリアスが定義されています。 最初のエイリアスは、ショートカットを提供します。 2番目と3番目のエイリアスには、さまざまなシナリオで使用できる名前が用意されています。

    ```csharp
    [Alias("UN","Writer","Editor")]
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

Alias 属性の詳細については、「 [Alias 属性の宣言](./alias-attribute-declaration.md)」を参照してください。

## <a name="see-also"></a>関連項目

[.... SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)

[パラメーター属性の宣言](./parameter-attribute-declaration.md)

[エイリアス属性の宣言](./alias-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
