---
title: コマンドレットのパラメーターの種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6602730d-3892-4656-80c7-7bca2d14337f
caps.latest.revision: 14
ms.openlocfilehash: f5781c0c03aca41d01a44598a9a8c00d6d21d2fd
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067197"
---
# <a name="types-of-cmdlet-parameters"></a><span data-ttu-id="fb15f-102">コマンドレット パラメーターの種類</span><span class="sxs-lookup"><span data-stu-id="fb15f-102">Types of Cmdlet Parameters</span></span>

<span data-ttu-id="fb15f-103">このトピックでは、コマンドレットで宣言するパラメーターのさまざまな種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb15f-103">This topic describes the different types of parameters that you can declare in cmdlets.</span></span> <span data-ttu-id="fb15f-104">コマンドレットのパラメーターは、位置指定、名前付き、必要な省略可能なまたはスイッチ パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fb15f-104">Cmdlet parameters can be positional, named, required, optional, or switch parameters.</span></span>

## <a name="positional-and-named-parameters"></a><span data-ttu-id="fb15f-105">位置指定引数と名前付きパラメーター</span><span class="sxs-lookup"><span data-stu-id="fb15f-105">Positional and Named Parameters</span></span>

<span data-ttu-id="fb15f-106">すべてのコマンドレット パラメーターは、名前付きまたは位置指定パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="fb15f-106">All cmdlet parameters are either named or positional parameters.</span></span> <span data-ttu-id="fb15f-107">名前付きパラメーターは、コマンドレットを呼び出すときに、引数とパラメーターの名前を入力することが必要です。</span><span class="sxs-lookup"><span data-stu-id="fb15f-107">A named parameter requires that you type the parameter name and argument when calling the cmdlet.</span></span> <span data-ttu-id="fb15f-108">位置指定パラメーターは、相対的な順序で引数を入力することにのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="fb15f-108">A positional parameter requires only that you type the arguments in relative order.</span></span> <span data-ttu-id="fb15f-109">システムは、名前のない最初の引数を位置指定の最初のパラメーターにマップします。</span><span class="sxs-lookup"><span data-stu-id="fb15f-109">The system then maps the first unnamed argument to the first positional parameter.</span></span> <span data-ttu-id="fb15f-110">システムでは、名前のない 2 番目の引数を 2 番目のパラメーターの名前のない、という具合です。</span><span class="sxs-lookup"><span data-stu-id="fb15f-110">The system maps the second unnamed argument to the second unnamed parameter, and so on.</span></span> <span data-ttu-id="fb15f-111">既定では、すべてのコマンドレット パラメーターは名前付きパラメーター。</span><span class="sxs-lookup"><span data-stu-id="fb15f-111">By default, all cmdlet parameters are named parameters.</span></span>

<span data-ttu-id="fb15f-112">名前付きパラメーターを定義するには、省略、`Position`キーワード、**パラメーター**属性の宣言では、次のパラメーターの宣言で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="fb15f-112">To define a named parameter, omit the `Position` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="fb15f-113">位置指定パラメーターを定義するには、追加、`Position`パラメーターにキーワード属性宣言と位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="fb15f-113">To define a positional parameter, add the `Position` keyword in the Parameter attribute declaration, and then specify a position.</span></span> <span data-ttu-id="fb15f-114">次の例で、`UserName`位置 0 の位置指定パラメーターとしてパラメーターを宣言します。</span><span class="sxs-lookup"><span data-stu-id="fb15f-114">In the following sample, the `UserName` parameter is declared as a positional parameter with position 0.</span></span> <span data-ttu-id="fb15f-115">つまり、呼び出しの最初の引数を自動的にこのパラメーターにバインドされます。</span><span class="sxs-lookup"><span data-stu-id="fb15f-115">This means that the first argument of the call will be automatically bound to this parameter.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

> [!NOTE]
> <span data-ttu-id="fb15f-116">適切なコマンドレットのデザインは、ユーザーが、コマンドレットを実行すると、パラメーター名を入力する必要があるないように、最も使用頻度のパラメーターを位置指定パラメーターとして宣言することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fb15f-116">Good cmdlet design recommends that the most-used parameters be declared as positional parameters so that the user does not have to enter the parameter name when the cmdlet is run.</span></span>

<span data-ttu-id="fb15f-117">位置指定引数と名前付きパラメーターは、1 つの引数またはコンマで区切られた複数の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fb15f-117">Positional and named parameters accept single arguments or multiple arguments separated by commas.</span></span> <span data-ttu-id="fb15f-118">複数の引数は、パラメーターが文字列の配列などのコレクションを受け取る場合にのみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="fb15f-118">Multiple arguments are allowed only if the parameter accepts a collection such as an array of strings.</span></span> <span data-ttu-id="fb15f-119">同じコマンドレットで位置指定引数と名前付きパラメーターを混在させることがあります。</span><span class="sxs-lookup"><span data-stu-id="fb15f-119">You may mix positional and named parameters in the same cmdlet.</span></span> <span data-ttu-id="fb15f-120">この場合、システムが最初に、名前付き引数を取得し、名前なし引数を位置指定パラメーターのし、残りをマップしよう。</span><span class="sxs-lookup"><span data-stu-id="fb15f-120">In this case, the system retrieves the named arguments first, and then attempts to map the remaining unnamed arguments to the positional parameters.</span></span>

<span data-ttu-id="fb15f-121">次のコマンドは、1 つまたは複数の引数のパラメーターを指定できます、さまざまな方法を示して、`Get-Command`コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="fb15f-121">The following commands show the different ways in which you can specify single and multiple arguments for the parameters of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="fb15f-122">最後の 2 つのサンプルで **-名前**ためにを指定する必要はありません、`Name`パラメーターは位置指定パラメーターとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="fb15f-122">Notice that in the last two samples, **-name** does not need to be specified because the `Name` parameter is defined as a positional parameter.</span></span>

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a><span data-ttu-id="fb15f-123">必須および省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="fb15f-123">Mandatory and Optional Parameters</span></span>

<span data-ttu-id="fb15f-124">必須またはオプションのパラメーターとしてコマンドレットのパラメーターを定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="fb15f-124">You can also define cmdlet parameters as mandatory or optional parameters.</span></span> <span data-ttu-id="fb15f-125">(必須のパラメーター指定してください、Windows PowerShell ランタイムは、コマンドレットを呼び出す前に。)既定では、パラメーターは省略可能として定義されます。</span><span class="sxs-lookup"><span data-stu-id="fb15f-125">(A mandatory parameter must be specified before the Windows PowerShell runtime invokes the cmdlet.)  By default, parameters are defined as optional.</span></span>

<span data-ttu-id="fb15f-126">必須のパラメーターを定義するには、追加、`Mandatory`キーワード パラメーターに属性宣言、およびに設定`true`、次のパラメーターの宣言で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="fb15f-126">To define a mandatory parameter, add the `Mandatory` keyword in the Parameter attribute declaration, and set it to `true`, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="fb15f-127">オプションのパラメーターを定義するには、省略、`Mandatory`キーワード、**パラメーター**属性の宣言では、次のパラメーターの宣言で示すようにします。</span><span class="sxs-lookup"><span data-stu-id="fb15f-127">To define an optional parameter, omit the `Mandatory` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a><span data-ttu-id="fb15f-128">スイッチ パラメーター</span><span class="sxs-lookup"><span data-stu-id="fb15f-128">Switch Parameters</span></span>

<span data-ttu-id="fb15f-129">Windows PowerShell では、 [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)に値を持つパラメーターを定義することができますの種類が自動的に設定`false`コマンドレットはときに、パラメーターが指定されていない場合と呼ばれる。</span><span class="sxs-lookup"><span data-stu-id="fb15f-129">Windows PowerShell provides a [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type that allows you to define a parameter whose value is automatically set to `false` if the parameter is not specified when the cmdlet is called.</span></span> <span data-ttu-id="fb15f-130">可能であれば、ブール型パラメーターの代わりにスイッチ パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb15f-130">Whenever possible, use switch parameters in place of Boolean parameters.</span></span>

<span data-ttu-id="fb15f-131">次の例を検討してください。</span><span class="sxs-lookup"><span data-stu-id="fb15f-131">Consider the following sample.</span></span> <span data-ttu-id="fb15f-132">既定では、いくつかの Windows PowerShell コマンドレットは、パイプラインに出力オブジェクトを渡さないでください。</span><span class="sxs-lookup"><span data-stu-id="fb15f-132">By default, several Windows PowerShell cmdlets do not pass an output object down the pipeline.</span></span> <span data-ttu-id="fb15f-133">ただし、これらのコマンドレットがある、`PassThru`スイッチ パラメーターを既定の動作をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="fb15f-133">However, these cmdlets have a `PassThru` switch parameter that overrides the default behavior.</span></span> <span data-ttu-id="fb15f-134">場合、`PassThru`これらのコマンドレットを呼び出すときに、パラメーターを指定すると、コマンドレットは、パイプラインに出力オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="fb15f-134">If the `PassThru` parameter is specified when these cmdlets are called, the cmdlet returns an output object to the pipeline.</span></span>

<span data-ttu-id="fb15f-135">かどうか、パラメーターの既定値を設定する必要があります。`true`呼び出しでは、パラメーターが指定されていない、ときには、パラメーターの意味を反転することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="fb15f-135">If you need the parameter to have a default value of `true` when the parameter is not specified in the call, consider reversing the sense of the parameter.</span></span> <span data-ttu-id="fb15f-136">サンプルでは、パラメーター属性にブール値を設定するのではなく`true`、プロパティとして宣言、 [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)を入力し、するパラメーターの既定値を設定`false`.</span><span class="sxs-lookup"><span data-stu-id="fb15f-136">For sample, instead of setting the parameter attribute to a Boolean value of `true`, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, and then set the default value of the parameter to `false`.</span></span>

<span data-ttu-id="fb15f-137">スイッチ パラメーターを定義するには、プロパティとしてを宣言、 [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter)の次の例に示すように入力します。</span><span class="sxs-lookup"><span data-stu-id="fb15f-137">To define a switch parameter, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, as shown in the following sample.</span></span>

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

<span data-ttu-id="fb15f-138">指定されているときに、パラメーターを操作するコマンドレットのいずれかの入力処理メソッドは、次の構造を使用します。</span><span class="sxs-lookup"><span data-stu-id="fb15f-138">To make the cmdlet act on the parameter when it is specified, use the following structure within one of the input processing methods.</span></span>

```csharp
protected override void ProcessRecord()
{
  WriteObject("Switch parameter test: " + userName + ".");
  if(goodbye)
  {
    WriteObject(" Goodbye!");
  }
} // End ProcessRecord
```

## <a name="see-also"></a><span data-ttu-id="fb15f-139">参照</span><span class="sxs-lookup"><span data-stu-id="fb15f-139">See Also</span></span>

[<span data-ttu-id="fb15f-140">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="fb15f-140">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
