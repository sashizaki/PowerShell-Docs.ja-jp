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
# <a name="how-to-declare-cmdlet-parameters"></a><span data-ttu-id="e4fe2-102">コマンドレット パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="e4fe2-102">How to Declare Cmdlet Parameters</span></span>

<span data-ttu-id="e4fe2-103">これらの例では、名前付き、位置指定、必須、省略可能、およびスイッチのパラメーターを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-103">These examples show how to declare named, positional, required, optional, and switch parameters.</span></span> <span data-ttu-id="e4fe2-104">これらの例では、パラメーターの別名を定義する方法も示しています。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-104">These examples also show how to define a parameter alias.</span></span>

## <a name="how-to-declare-a-named-parameter"></a><span data-ttu-id="e4fe2-105">名前付きパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="e4fe2-105">How to Declare a Named Parameter</span></span>

- <span data-ttu-id="e4fe2-106">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-106">Define a public property as shown in the following code.</span></span> <span data-ttu-id="e4fe2-107">パラメーター属性を追加するときは、属性から @no__t 0 キーワードを省略します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-107">When you add the Parameter attribute, omit the `Position` keyword from the attribute.</span></span>

    ```csharp
    [Parameter()]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="e4fe2-108">Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-108">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-positional-parameter"></a><span data-ttu-id="e4fe2-109">位置指定パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="e4fe2-109">How to Declare a Positional Parameter</span></span>

- <span data-ttu-id="e4fe2-110">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-110">Define a public property as shown in the following code.</span></span> <span data-ttu-id="e4fe2-111">パラメーター属性を追加するときは、`Position` キーワードを引数の位置に設定します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-111">When you add the Parameter attribute, set the `Position` keyword to the argument position.</span></span> <span data-ttu-id="e4fe2-112">値が0の場合は、最初の位置を示します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-112">A value of 0 indicates the first position.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="e4fe2-113">Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-113">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-mandatory-parameter"></a><span data-ttu-id="e4fe2-114">必須パラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="e4fe2-114">How to Declare a Mandatory Parameter</span></span>

- <span data-ttu-id="e4fe2-115">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-115">Define a public property as shown in the following code.</span></span> <span data-ttu-id="e4fe2-116">パラメーター属性を追加するときは、`Mandatory` キーワードを `true` に設定します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-116">When you add the Parameter attribute, set the `Mandatory` keyword to `true`.</span></span>

    ```csharp
    [Parameter(Position = 0, Mandatory = true)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

<span data-ttu-id="e4fe2-117">Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-117">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-an-optional-parameter"></a><span data-ttu-id="e4fe2-118">省略可能なパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="e4fe2-118">How to Declare an Optional Parameter</span></span>

- <span data-ttu-id="e4fe2-119">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-119">Define a public property as shown in the following code.</span></span> <span data-ttu-id="e4fe2-120">パラメーター属性を追加する場合は、`Mandatory` キーワードを省略します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-120">When you add the Parameter attribute, omit the `Mandatory` keyword.</span></span>

    ```csharp
    [Parameter(Position = 0)]
    public string UserName
    {
      get { return userName; }
      set { userName = value; }
    }
    private string userName;
    ```

## <a name="how-to-declare-a-switch-parameter"></a><span data-ttu-id="e4fe2-121">スイッチパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="e4fe2-121">How to Declare a Switch Parameter</span></span>

- <span data-ttu-id="e4fe2-122">パブリックプロパティを型 system.string として定義[し、パラメーター](/dotnet/api/System.Management.Automation.SwitchParameter)属性を宣言します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-122">Define a public property as type [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter), and then declare the Parameter attribute.</span></span>

    ```csharp
    [Parameter(Position = 1)]
    public SwitchParameter GoodBye
    {
      get { return goodbye; }
      set { goodbye = value; }
    }
    private bool goodbye;
    ```

<span data-ttu-id="e4fe2-123">Parameter 属性の詳細については、「 [Parameter 属性の宣言](./parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-123">For more information about the Parameter attribute, see [Parameter Attribute Declaration](./parameter-attribute-declaration.md).</span></span>

## <a name="how-to-declare-a-parameter-with-aliases"></a><span data-ttu-id="e4fe2-124">エイリアスを使用してパラメーターを宣言する方法</span><span class="sxs-lookup"><span data-stu-id="e4fe2-124">How to Declare a Parameter with Aliases</span></span>

- <span data-ttu-id="e4fe2-125">次のコードに示すように、パブリックプロパティを定義します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-125">Define a public property as shown in the following code.</span></span> <span data-ttu-id="e4fe2-126">パラメーターのエイリアスを一覧表示するエイリアス属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-126">Add an Alias attribute that lists the aliases for the parameter.</span></span> <span data-ttu-id="e4fe2-127">この例では、同じパラメーターに対して3つのエイリアスが定義されています。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-127">In this example, three aliases are defined for the same parameter.</span></span> <span data-ttu-id="e4fe2-128">最初のエイリアスは、ショートカットを提供します。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-128">The first alias provides a shortcut.</span></span> <span data-ttu-id="e4fe2-129">2番目と3番目のエイリアスには、さまざまなシナリオで使用できる名前が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-129">The second and third aliases provide names you can use for different scenarios.</span></span>

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

<span data-ttu-id="e4fe2-130">Alias 属性の詳細については、「 [Alias 属性の宣言](./alias-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4fe2-130">For more information about the Alias attribute, see [Alias Attribute Declaration](./alias-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e4fe2-131">参照</span><span class="sxs-lookup"><span data-stu-id="e4fe2-131">See Also</span></span>

[<span data-ttu-id="e4fe2-132">.... SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="e4fe2-132">System.Management.Automation.SwitchParameter</span></span>](/dotnet/api/System.Management.Automation.SwitchParameter)

[<span data-ttu-id="e4fe2-133">パラメーター属性の宣言</span><span class="sxs-lookup"><span data-stu-id="e4fe2-133">Parameter Attribute Declaration</span></span>](./parameter-attribute-declaration.md)

[<span data-ttu-id="e4fe2-134">エイリアス属性の宣言</span><span class="sxs-lookup"><span data-stu-id="e4fe2-134">Alias Attribute Declaration</span></span>](./alias-attribute-declaration.md)

[<span data-ttu-id="e4fe2-135">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="e4fe2-135">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
