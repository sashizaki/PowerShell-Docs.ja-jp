---
title: コマンドレットのパラメーターの設定 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f902fd4d-8f6e-4ef1-b07f-59983039a0d1
caps.latest.revision: 10
ms.openlocfilehash: a5822ef1ed3c9efb5957c20255783d515de8957a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56857268"
---
# <a name="cmdlet-parameter-sets"></a><span data-ttu-id="ac55c-102">コマンドレット パラメーター セット</span><span class="sxs-lookup"><span data-stu-id="ac55c-102">Cmdlet Parameter Sets</span></span>

<span data-ttu-id="ac55c-103">Windows PowerShell では、パラメーター セットを使用して、さまざまなシナリオのさまざまなアクションを実行できる 1 つのコマンドレットを記述できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac55c-103">Windows PowerShell uses parameter sets to enable you to write a single cmdlet that can perform different actions for different scenarios.</span></span> <span data-ttu-id="ac55c-104">パラメーター セットを使用すると、ユーザーに異なるパラメーターを公開して、ユーザーによって指定されたパラメーターに基づいて異なる情報を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="ac55c-104">Parameter sets enable you to expose different parameters to the user and to return different information based on the parameters specified by the user.</span></span>

## <a name="examples-of-parameter-sets"></a><span data-ttu-id="ac55c-105">パラメーター セットの例</span><span class="sxs-lookup"><span data-stu-id="ac55c-105">Examples of Parameter Sets</span></span>

<span data-ttu-id="ac55c-106">たとえば、`Get-EventLog`コマンドレット (Windows PowerShell によって提供される) は、ユーザーを指定するかどうかに応じて、異なる情報を返します、`List`または`LogName`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="ac55c-106">For example, the `Get-EventLog` cmdlet (provided by Windows PowerShell) returns different information depending on whether the user specifies the `List` or `LogName` parameter.</span></span> <span data-ttu-id="ac55c-107">場合、`List`パラメーターを指定すると、自体が含まれているイベント情報ではなく、コマンドレットは、ログ ファイルに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-107">If the `List` parameter is specified, the cmdlet returns information about the log files themselves but not the event information they contain.</span></span> <span data-ttu-id="ac55c-108">場合、`LogName`パラメーターを指定すると、cmdlet は、特定のイベント ログでイベントについての情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-108">If the `LogName` parameter is specified, the cmdlet returns information about the events in a specific event log.</span></span> <span data-ttu-id="ac55c-109">`List`と`LogName`パラメーターが 2 つの個別のパラメーター セットを識別します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-109">The `List` and `LogName` parameters identify two separate parameter sets.</span></span>

## <a name="unique-parameter"></a><span data-ttu-id="ac55c-110">一意のパラメーター</span><span class="sxs-lookup"><span data-stu-id="ac55c-110">Unique Parameter</span></span>

<span data-ttu-id="ac55c-111">各パラメーターのセットには、適切なパラメーター セットを公開する、Windows PowerShell ランタイムが使用できる一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="ac55c-111">Each parameter set must have a unique parameter that the Windows PowerShell runtime can use to expose the appropriate parameter set.</span></span> <span data-ttu-id="ac55c-112">可能であれば、一意のパラメーターには、必須のパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="ac55c-112">If possible, the unique parameter should be a mandatory parameter.</span></span> <span data-ttu-id="ac55c-113">パラメーターが必須の場合は、パラメーターを指定するユーザーが強制実行され、Windows PowerShell ランタイムは、パラメーターを使用する設定を識別するためにそのパラメーターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="ac55c-113">When a parameter is mandatory, the user is forced to specify the parameter, and the Windows PowerShell runtime can use that parameter to identify the parameter set to use.</span></span> <span data-ttu-id="ac55c-114">一意のパラメーターは、パラメーターを指定せずに実行するコマンドレットが設計されている場合に必須にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ac55c-114">The unique parameter cannot be mandatory if your cmdlet is designed to be run without specifying any parameters.</span></span>

## <a name="multiple-parameter-sets"></a><span data-ttu-id="ac55c-115">複数のパラメーター セット</span><span class="sxs-lookup"><span data-stu-id="ac55c-115">Multiple Parameter Sets</span></span>

<span data-ttu-id="ac55c-116">次の図では、左側の列は、次の 3 つの有効なパラメーター セットを表示します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-116">In the following illustration, the left column shows three valid parameter sets.</span></span> <span data-ttu-id="ac55c-117">パラメーター A が最初のパラメーターのセットに一意、B のパラメーターが 2 番目のパラメーターのセットに一意およびパラメーター C は 3 番目のパラメーターのセットに一意です。</span><span class="sxs-lookup"><span data-stu-id="ac55c-117">Parameter A is unique to the first parameter set, parameter B is unique to the second parameter set, and parameter C is unique to the third parameter set.</span></span> <span data-ttu-id="ac55c-118">ただし、右側の列にパラメーター セットはありません、一意のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="ac55c-118">However, in the right column, the parameter sets do not have a unique parameter.</span></span>

![ps_parametersets](../media/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a><span data-ttu-id="ac55c-120">パラメーター セットの要件</span><span class="sxs-lookup"><span data-stu-id="ac55c-120">Parameter Set Requirements</span></span>

<span data-ttu-id="ac55c-121">次の要件は、すべてのパラメーター セットに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ac55c-121">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="ac55c-122">各パラメーターのセットには、少なくとも 1 つの一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="ac55c-122">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="ac55c-123">可能であれば、このパラメーターは必須のパラメーターを確認します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-123">If possible, make this parameter a mandatory parameter.</span></span>

- <span data-ttu-id="ac55c-124">複数の位置指定パラメーターを含むパラメーター セットでは、パラメーターごとに一意の位置を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac55c-124">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="ac55c-125">2 つの位置指定パラメーターなしでは、同じ位置を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ac55c-125">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="ac55c-126">セット内の 1 つだけのパラメーターを宣言できます、`ValueFromPipeline`キーワードの値を持つ`true`します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-126">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span> <span data-ttu-id="ac55c-127">複数のパラメーターを定義できます、`ValueFromPipelineByPropertyName`キーワードの値を持つ`true`します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-127">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="ac55c-128">パラメーターのパラメーター セットが指定されていない場合、パラメーターは、すべてのパラメーター セットに属しています。</span><span class="sxs-lookup"><span data-stu-id="ac55c-128">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="ac55c-129">既定のパラメーター セット</span><span class="sxs-lookup"><span data-stu-id="ac55c-129">Default Parameter Sets</span></span>

<span data-ttu-id="ac55c-130">複数のパラメーター セットが定義されているときに使用できます、`DefaultParameterSetName`コマンドレットの既定のパラメーター セットを指定する属性のキーワード。</span><span class="sxs-lookup"><span data-stu-id="ac55c-130">When multiple parameter sets are defined, you can use the `DefaultParameterSetName` keyword of the Cmdlet attribute to specify the default parameter set.</span></span> <span data-ttu-id="ac55c-131">Windows PowerShell では、コマンドによって提供される情報に基づいて、パラメーターを使用する設定を判断できない場合は、設定、既定のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-131">Windows PowerShell uses the default parameter set if it cannot determine the parameter set to use based on the information provided by the command.</span></span> <span data-ttu-id="ac55c-132">コマンドレットの属性の詳細については、次を参照してください。[コマンドレット属性宣言](./cmdlet-attribute-declaration.md)します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-132">For more information about the Cmdlet attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="ac55c-133">パラメーター セットを宣言します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-133">Declaring Parameter Sets</span></span>

<span data-ttu-id="ac55c-134">パラメーター セットを作成することを指定する必要があります、`ParameterSetName`パラメーター セットのすべてのパラメーターのパラメーターの属性を宣言するときに、キーワード。</span><span class="sxs-lookup"><span data-stu-id="ac55c-134">To create a parameter set, you must specify the `ParameterSetName` keyword when you declare the Parameter attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="ac55c-135">パラメーターの複数のパラメーター セットに属している場合に、各パラメーター セットのパラメーターの属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="ac55c-135">For parameters that belong to multiple parameter sets, add a Parameter attribute for each parameter set.</span></span> <span data-ttu-id="ac55c-136">これにより、パラメーターのセットごとに異なるパラメーターを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="ac55c-136">This enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="ac55c-137">たとえば、1 つのセットで必須で、別のオプションとして、パラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="ac55c-137">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="ac55c-138">ただし、各パラメーター セットは、1 つの一意のパラメーターを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac55c-138">However, each parameter set must contain one unique parameter.</span></span>

<span data-ttu-id="ac55c-139">次の例では、`UserName`パラメーター Test01 パラメーター セットの一意のパラメーターでは、`ComputerName`は Test02 パラメーター セットの一意のパラメーター。</span><span class="sxs-lookup"><span data-stu-id="ac55c-139">In the following example, the `UserName` parameter is the unique parameter of the Test01 parameter set, and the `ComputerName` parameter is the unique parameter of the Test02 parameter set.</span></span> <span data-ttu-id="ac55c-140">`SharedParam`パラメーターは、両方のセットに属しているし、ただし Test02 パラメーター セットの省略可能な設定 Test01 パラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="ac55c-140">The `SharedParam` parameter belongs to both sets and is mandatory for the Test01 parameter set but optional for the Test02 parameter set.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;

[Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test02")]
public string ComputerName
{
  get { return computerName; }
  set { computerName = value; }
}
private string computerName;

[Parameter(Mandatory= true, ParameterSetName = "Test01")]
[Parameter(ParameterSetName = "Test02")]
public string SharedParam
{
    get { return sharedParam; }
    set { sharedParam = value; }
}
private string sharedParam;    [Parameter(Position = 0, Mandatory = true,
           ParameterSetName = "Test01")]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```