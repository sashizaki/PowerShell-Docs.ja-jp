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
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58059169"
---
# <a name="how-to-declare-cmdlet-parameters"></a>コマンドレット パラメーターを宣言する方法

これらの例では、名前付き、位置指定、必要な省略可能なを宣言し、パラメーターを切り替える方法を示します。 これらの例では、パラメーター エイリアスを定義する方法も示します。

## <a name="how-to-declare-a-named-parameter"></a>名前付きパラメーターを宣言する方法

- 次のコードに示すように、パブリック プロパティを定義します。 パラメーター属性を追加する場合は、省略、`Position`属性からのキーワード。

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

パラメーター属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。

## <a name="how-to-declare-a-positional-parameter"></a>位置指定パラメーターを宣言する方法

- 次のコードに示すように、パブリック プロパティを定義します。 パラメーター属性を追加する場合は、設定、`Position`キーワードを引数の位置。 値 0 は、最初の位置を示します。

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

パラメーター属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。

## <a name="how-to-declare-a-mandatory-parameter"></a>必須のパラメーターを宣言する方法

- 次のコードに示すように、パブリック プロパティを定義します。 パラメーター属性を追加する場合は、設定、`Mandatory`キーワードを`true`します。

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

パラメーター属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。

## <a name="how-to-declare-an-optional-parameter"></a>オプションのパラメーターを宣言する方法

- 次のコードに示すように、パブリック プロパティを定義します。 パラメーター属性を追加する場合は、省略、`Mandatory`キーワード。

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a>スイッチ パラメーターを宣言する方法

- パブリック プロパティを型として定義[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)パラメーターの属性を宣言してから、します。

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

パラメーター属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。

## <a name="how-to-declare-a-parameter-with-aliases"></a>エイリアスを持つパラメーターを宣言する方法

- 次のコードに示すように、パブリック プロパティを定義します。 パラメーターのエイリアス一覧表示する属性をエイリアスを追加します。 この例では、3 つのエイリアスは、同じパラメーターに対して定義されます。 最初のエイリアスは、ショートカットを提供します。 2 番目と 3 番目のエイリアスは、さまざまなシナリオに使用できる名前を提供します。

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

Alias 属性の詳細については、次を参照してください。[エイリアス属性宣言](./alias-attribute-declaration.md)します。

## <a name="see-also"></a>参照

[System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)

[パラメーター属性の宣言](./parameter-attribute-declaration.md)

[エイリアス属性の宣言](./alias-attribute-declaration.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
