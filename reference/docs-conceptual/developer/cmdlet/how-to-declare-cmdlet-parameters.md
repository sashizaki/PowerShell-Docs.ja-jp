---
ms.date: 09/13/2016
ms.topic: reference
title: コマンドレット パラメーターを宣言する方法
description: コマンドレット パラメーターを宣言する方法
ms.openlocfilehash: ed53f9788c9afb142b137e08966dff33551b9d0f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667098"
---
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="986d4-103">コマンドレット パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="986d4-103">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="986d4-104">これらの例では、名前付き、位置指定、必須、省略可能、およびスイッチのパラメーターを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="986d4-104">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="986d4-105">これらの例では、パラメーターの別名を定義する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="986d4-105">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="986d4-106">名前付きパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="986d4-106">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="986d4-107">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="986d4-107">Define a public property as shown in the following code.</span></span> <span data-ttu-id="986d4-108">パラメーター属性を追加するときは、 `Position` 属性からキーワードを省略します。</span><span class="sxs-lookup"><span data-stu-id="986d4-108">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="986d4-109">Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="986d4-109">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="986d4-110">位置指定パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="986d4-110">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="986d4-111">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="986d4-111">Define a public property as shown in the following code.</span></span> <span data-ttu-id="986d4-112">パラメーター属性を追加するときに、 `Position` キーワードを引数の位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="986d4-112">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="986d4-113">値が0の場合は、最初の位置を示します。</span><span class="sxs-lookup"><span data-stu-id="986d4-113">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="986d4-114">Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="986d4-114">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="986d4-115">必須パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="986d4-115">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="986d4-116">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="986d4-116">Define a public property as shown in the following code.</span></span> <span data-ttu-id="986d4-117">パラメーター属性を追加するときに、 `Mandatory` キーワードをに設定 `true` します。</span><span class="sxs-lookup"><span data-stu-id="986d4-117">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="986d4-118">Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="986d4-118">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="986d4-119">省略可能なパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="986d4-119">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="986d4-120">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="986d4-120">Define a public property as shown in the following code.</span></span> <span data-ttu-id="986d4-121">パラメーター属性を追加する場合は、キーワードを省略し `Mandatory` ます。</span><span class="sxs-lookup"><span data-stu-id="986d4-121">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="986d4-122">スイッチパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="986d4-122">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="986d4-123">パブリックプロパティを型 system.string として定義 [し、パラメーター](/dotnet/api/System.Management.Automation.SwitchParameter)属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="986d4-123">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="986d4-124">Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="986d4-124">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="986d4-125">エイリアスを使用してパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="986d4-125">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="986d4-126">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="986d4-126">Define a public property as shown in the following code.</span></span> <span data-ttu-id="986d4-127">パラメーターのエイリアスを一覧表示するエイリアス属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="986d4-127">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="986d4-128">この例では、同じパラメーターに対して3つのエイリアスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="986d4-128">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="986d4-129">最初のエイリアスは、ショートカットを提供します。</span><span class="sxs-lookup"><span data-stu-id="986d4-129">The first alias provides a shortcut.</span></span> <span data-ttu-id="986d4-130">2番目と3番目のエイリアスには、さまざまなシナリオで使用できる名前が用意されています。</span><span class="sxs-lookup"><span data-stu-id="986d4-130">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="986d4-131">Alias 属性の詳細については、「 [Alias 属性の宣言](./alias-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="986d4-131">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="986d4-132">参照</span><span class="sxs-lookup"><span data-stu-id="986d4-132">See Also</span></span>

[<span data-ttu-id="986d4-133">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="986d4-133">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="986d4-134">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="986d4-134">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="986d4-135">エイリアス属性の宣言</span><span class="sxs-lookup"><span data-stu-id="986d4-135">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="986d4-136">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="986d4-136">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
