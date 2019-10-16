---
title: コマンドレットのパラメーターセット |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f902fd4d-8f6e-4ef1-b07f-59983039a0d1
caps.latest.revision: 10
ms.openlocfilehash: d8c00c7ffd369a32af151836785a2c5f47b05a68
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72365901"
---
# <a name="cmdlet-parameter-sets"></a><span data-ttu-id="3994a-102">コマンドレットのパラメーターセット</span><span class="sxs-lookup"><span data-stu-id="3994a-102">Cmdlet parameter sets</span></span>

<span data-ttu-id="3994a-103">PowerShell では、パラメーターセットを使用して、さまざまなシナリオに対して異なるアクションを実行できる単一のコマンドレットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3994a-103">PowerShell uses parameter sets to enable you to write a single cmdlet that can do different actions for different scenarios.</span></span> <span data-ttu-id="3994a-104">パラメーターセットを使用すると、さまざまなパラメーターをユーザーに公開できます。</span><span class="sxs-lookup"><span data-stu-id="3994a-104">Parameter sets enable you to expose different parameters to the user.</span></span> <span data-ttu-id="3994a-105">また、ユーザーが指定したパラメーターに基づいて異なる情報を返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3994a-105">And, to return different information based on the parameters specified by the user.</span></span>

## <a name="examples-of-parameter-sets"></a><span data-ttu-id="3994a-106">パラメーターセットの例</span><span class="sxs-lookup"><span data-stu-id="3994a-106">Examples of parameter sets</span></span>

<span data-ttu-id="3994a-107">たとえば、PowerShell `Get-EventLog` コマンドレットは、ユーザーが**List**パラメーターまたは**LogName**パラメーターを指定したかどうかに応じて異なる情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3994a-107">For example, the PowerShell `Get-EventLog` cmdlet returns different information depending on whether the user specifies the **List** or **LogName** parameter.</span></span> <span data-ttu-id="3994a-108">**List**パラメーターが指定されている場合、コマンドレットはログファイル自体に関する情報を返しますが、含まれているイベント情報は返しません。</span><span class="sxs-lookup"><span data-stu-id="3994a-108">If the **List** parameter is specified, the cmdlet returns information about the log files themselves but not the event information they contain.</span></span> <span data-ttu-id="3994a-109">**LogName**パラメーターを指定すると、コマンドレットは、特定のイベントログ内のイベントに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3994a-109">If the **LogName** parameter is specified, the cmdlet returns information about the events in a specific event log.</span></span> <span data-ttu-id="3994a-110">**List**および**LogName**パラメーターは、2つの異なるパラメーターセットを識別します。</span><span class="sxs-lookup"><span data-stu-id="3994a-110">The **List** and **LogName** parameters identify two separate parameter sets.</span></span>

## <a name="unique-parameter"></a><span data-ttu-id="3994a-111">一意のパラメーター</span><span class="sxs-lookup"><span data-stu-id="3994a-111">Unique parameter</span></span>

<span data-ttu-id="3994a-112">各パラメーターセットには、適切なパラメーターセットを公開するために PowerShell ランタイムが使用する一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="3994a-112">Each parameter set must have a unique parameter that the PowerShell runtime uses to expose the appropriate parameter set.</span></span> <span data-ttu-id="3994a-113">可能であれば、unique パラメーターは必須パラメーターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="3994a-113">If possible, the unique parameter should be a mandatory parameter.</span></span> <span data-ttu-id="3994a-114">パラメーターが必須の場合、ユーザーはパラメーターを指定する必要があり、PowerShell ランタイムはそのパラメーターを使用してパラメーターセットを識別します。</span><span class="sxs-lookup"><span data-stu-id="3994a-114">When a parameter is mandatory, the user must specify the parameter, and the PowerShell runtime uses that parameter to identify the parameter set.</span></span> <span data-ttu-id="3994a-115">コマンドレットがパラメーターを指定せずに実行するように設計されている場合、unique パラメーターを必須にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3994a-115">The unique parameter can't be mandatory if your cmdlet is designed to run without specifying any parameters.</span></span>

## <a name="multiple-parameter-sets"></a><span data-ttu-id="3994a-116">複数のパラメーターセット</span><span class="sxs-lookup"><span data-stu-id="3994a-116">Multiple parameter sets</span></span>

<span data-ttu-id="3994a-117">次の図では、左側の列に3つの有効なパラメーターセットが示されています。</span><span class="sxs-lookup"><span data-stu-id="3994a-117">In the following illustration, the left column shows three valid parameter sets.</span></span> <span data-ttu-id="3994a-118">**パラメーター a**は最初のパラメーターセットに対して一意で、**パラメーター B**は2番目のパラメーターセットに対して一意であり、**パラメーター C**は3番目のパラメーターセットに対して一意です。</span><span class="sxs-lookup"><span data-stu-id="3994a-118">**Parameter A** is unique to the first parameter set, **parameter B** is unique to the second parameter set, and **parameter C** is unique to the third parameter set.</span></span> <span data-ttu-id="3994a-119">右側の列では、パラメーターセットに一意のパラメーターがありません。</span><span class="sxs-lookup"><span data-stu-id="3994a-119">In the right column, the parameter sets don't have a unique parameter.</span></span>

![ps_parametersets](../media/ps-parametersets.gif)

## <a name="parameter-set-requirements"></a><span data-ttu-id="3994a-121">パラメーターセットの要件</span><span class="sxs-lookup"><span data-stu-id="3994a-121">Parameter set requirements</span></span>

<span data-ttu-id="3994a-122">すべてのパラメーターセットには、次の要件が適用されます。</span><span class="sxs-lookup"><span data-stu-id="3994a-122">The following requirements apply to all parameter sets.</span></span>

- <span data-ttu-id="3994a-123">各パラメーターセットには、少なくとも1つの一意のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="3994a-123">Each parameter set must have at least one unique parameter.</span></span> <span data-ttu-id="3994a-124">可能であれば、このパラメーターを必須パラメーターにします。</span><span class="sxs-lookup"><span data-stu-id="3994a-124">If possible, make this parameter a mandatory parameter.</span></span>

- <span data-ttu-id="3994a-125">複数の位置指定パラメーターを含むパラメーターセットでは、パラメーターごとに一意の位置を定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3994a-125">A parameter set that contains multiple positional parameters must define unique positions for each parameter.</span></span> <span data-ttu-id="3994a-126">2つの位置指定パラメーターで同じ位置を指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3994a-126">No two positional parameters can specify the same position.</span></span>

- <span data-ttu-id="3994a-127">値が `true` の @no__t 0 キーワードを宣言できるのは、セット内の1つのパラメーターだけです。</span><span class="sxs-lookup"><span data-stu-id="3994a-127">Only one parameter in a set can declare the `ValueFromPipeline` keyword with a value of `true`.</span></span>
  <span data-ttu-id="3994a-128">複数のパラメーターでは、値が `true` の @no__t 0 キーワードを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3994a-128">Multiple parameters can define the `ValueFromPipelineByPropertyName` keyword with a value of `true`.</span></span>

- <span data-ttu-id="3994a-129">パラメーターにパラメーターセットが指定されていない場合、パラメーターはすべてのパラメーターセットに属します。</span><span class="sxs-lookup"><span data-stu-id="3994a-129">If no parameter set is specified for a parameter, the parameter belongs to all parameter sets.</span></span>

> [!NOTE]
> <span data-ttu-id="3994a-130">コマンドレットまたは関数の場合、32パラメーターセットの制限があります。</span><span class="sxs-lookup"><span data-stu-id="3994a-130">For a cmdlet or function, there is a limit of 32 parameter sets.</span></span>

## <a name="default-parameter-sets"></a><span data-ttu-id="3994a-131">既定のパラメーターセット</span><span class="sxs-lookup"><span data-stu-id="3994a-131">Default parameter sets</span></span>

<span data-ttu-id="3994a-132">複数のパラメーターセットが定義されている場合は、**コマンドレット**属性の @no__t 0 キーワードを使用して、既定のパラメーターセットを指定できます。</span><span class="sxs-lookup"><span data-stu-id="3994a-132">When multiple parameter sets are defined, you can use the `DefaultParameterSetName` keyword of the **Cmdlet** attribute to specify the default parameter set.</span></span> <span data-ttu-id="3994a-133">PowerShell では、コマンドによって提供される情報に基づいて、使用するパラメーターセットを特定できない場合、既定のパラメーターセットが使用されます。</span><span class="sxs-lookup"><span data-stu-id="3994a-133">PowerShell uses the default parameter set if it can't determine the parameter set to use based on the information provided by the command.</span></span> <span data-ttu-id="3994a-134">**コマンドレット**属性の詳細については、「[コマンドレット属性の宣言](./cmdlet-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3994a-134">For more information about the **Cmdlet** attribute, see [Cmdlet Attribute Declaration](./cmdlet-attribute-declaration.md).</span></span>

## <a name="declaring-parameter-sets"></a><span data-ttu-id="3994a-135">パラメーターセットの宣言</span><span class="sxs-lookup"><span data-stu-id="3994a-135">Declaring parameter sets</span></span>

<span data-ttu-id="3994a-136">パラメーターセットを作成するには、パラメーターセット内のすべてのパラメーターの**パラメーター**属性を宣言するときに、`ParameterSetName` キーワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3994a-136">To create a parameter set, you must specify the `ParameterSetName` keyword when you declare the **Parameter** attribute for every parameter in the parameter set.</span></span> <span data-ttu-id="3994a-137">複数のパラメーターセットに属するパラメーターの場合は、パラメーターセットごとに**パラメーター**属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="3994a-137">For parameters that belong to multiple parameter sets, add a **Parameter** attribute for each parameter set.</span></span> <span data-ttu-id="3994a-138">この属性を使用すると、パラメーターセットごとに異なる方法でパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3994a-138">This attribute enables you to define the parameter differently for each parameter set.</span></span> <span data-ttu-id="3994a-139">たとえば、あるセットでは必須として、別のセットでは省略可能なパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3994a-139">For example, you can define a parameter as mandatory in one set and optional in another.</span></span> <span data-ttu-id="3994a-140">ただし、各パラメーターセットには一意のパラメーターを1つ含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="3994a-140">However, each parameter set must contain one unique parameter.</span></span> <span data-ttu-id="3994a-141">詳細については、「[パラメーター属性の宣言](parameter-attribute-declaration.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3994a-141">For more information, see [Parameter Attribute Declaration](parameter-attribute-declaration.md).</span></span>

<span data-ttu-id="3994a-142">次の例では、 **UserName**パラメーターは `Test01` パラメーターセットの一意のパラメーターであり、 **ComputerName**パラメーターは、`Test02` パラメーターセットの一意のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="3994a-142">In the following example, the **UserName** parameter is the unique parameter of the `Test01` parameter set, and the **ComputerName** parameter is the unique parameter of the `Test02` parameter set.</span></span> <span data-ttu-id="3994a-143">**Sharedparam**パラメーターは両方のセットに属しており、`Test01` パラメーターセットでは必須ですが、@no__t パラメーターセットの場合は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3994a-143">The **SharedParam** parameter belongs to both sets and is mandatory for the `Test01` parameter set but optional for the `Test02` parameter set.</span></span>

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
private string sharedParam;
```
