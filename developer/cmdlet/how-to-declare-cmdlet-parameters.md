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
ms.openlocfilehash: d6613889ebd2ba139ce0b3de1b8d24e4aec37d2a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861398"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="c6e7e-102">コマンドレット パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="c6e7e-102">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="c6e7e-103">これらの例では、名前付き、位置指定、必要な省略可能なを宣言し、パラメーターを切り替える方法を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-103">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="c6e7e-104">これらの例では、パラメーター エイリアスを定義する方法も示します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-104">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="c6e7e-105">名前付きパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="c6e7e-105">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="c6e7e-106">次のコードに示すように、パブリック プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-106">Define a public property as shown in the following code.</span></span> <span data-ttu-id="c6e7e-107">パラメーター属性を追加する場合は、省略、`Position`属性からのキーワード。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-107">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="c6e7e-108">パラメーター属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-108">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="c6e7e-109">位置指定パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="c6e7e-109">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="c6e7e-110">次のコードに示すように、パブリック プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-110">Define a public property as shown in the following code.</span></span> <span data-ttu-id="c6e7e-111">パラメーター属性を追加する場合は、設定、`Position`キーワードを引数の位置。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-111">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="c6e7e-112">値 0 は、最初の位置を示します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-112">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="c6e7e-113">パラメーター属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-113">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="c6e7e-114">必須のパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="c6e7e-114">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="c6e7e-115">次のコードに示すように、パブリック プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-115">Define a public property as shown in the following code.</span></span> <span data-ttu-id="c6e7e-116">パラメーター属性を追加する場合は、設定、`Mandatory`キーワードを`true`します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-116">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="c6e7e-117">パラメーター属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-117">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="c6e7e-118">オプションのパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="c6e7e-118">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="c6e7e-119">次のコードに示すように、パブリック プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-119">Define a public property as shown in the following code.</span></span> <span data-ttu-id="c6e7e-120">パラメーター属性を追加する場合は、省略、`Mandatory`キーワード。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-120">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="c6e7e-121">スイッチ パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="c6e7e-121">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="c6e7e-122">パブリック プロパティを型として定義[System.Management.Automation.Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter)パラメーターの属性を宣言してから、します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-122">Define a public property as type [System.Management.Automation.Switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="c6e7e-123">パラメーター属性の詳細については、次を参照してください。[パラメーター属性宣言](./parameter-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-123">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="c6e7e-124">エイリアスを持つパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="c6e7e-124">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="c6e7e-125">次のコードに示すように、パブリック プロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-125">Define a public property as shown in the following code.</span></span> <span data-ttu-id="c6e7e-126">パラメーターのエイリアス一覧表示する属性をエイリアスを追加します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-126">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="c6e7e-127">この例では、3 つのエイリアスは、同じパラメーターに対して定義されます。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-127">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="c6e7e-128">最初のエイリアスは、ショートカットを提供します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-128">The first alias provides a shortcut.</span></span> <span data-ttu-id="c6e7e-129">2 番目と 3 番目のエイリアスは、さまざまなシナリオに使用できる名前を提供します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-129">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="c6e7e-130">Alias 属性の詳細については、次を参照してください。[エイリアス属性宣言](./alias-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="c6e7e-130">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c6e7e-131">参照</span><span class="sxs-lookup"><span data-stu-id="c6e7e-131">See Also</span></span>

[<span data-ttu-id="c6e7e-132">System.Management.Automation.Switchparameter</span><span class="sxs-lookup"><span data-stu-id="c6e7e-132">System.Management.Automation.Switchparameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="c6e7e-133">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="c6e7e-133">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="c6e7e-134">エイリアス属性の宣言</span><span class="sxs-lookup"><span data-stu-id="c6e7e-134">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="c6e7e-135">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c6e7e-135">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
