---
title: コマンドレットパラメーターの種類 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6602730d-3892-4656-80c7-7bca2d14337f
caps.latest.revision: 14
ms.openlocfilehash: f5781c0c03aca41d01a44598a9a8c00d6d21d2fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369311"
---
# <a name="types-of-cmdlet-parameters"></a><span data-ttu-id="4a2e6-102">コマンドレット パラメーターの種類</span><span class="sxs-lookup"><span data-stu-id="4a2e6-102">Types of Cmdlet Parameters</span></span>

<span data-ttu-id="4a2e6-103">このトピックでは、コマンドレットで宣言できるさまざまな種類のパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-103">This topic describes the different types of parameters that you can declare in cmdlets.</span></span> <span data-ttu-id="4a2e6-104">コマンドレットのパラメーターには、位置指定、名前付き、必須、オプション、またはスイッチのパラメーターを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-104">Cmdlet parameters can be positional, named, required, optional, or switch parameters.</span></span>

## <a name="positional-and-named-parameters"></a><span data-ttu-id="4a2e6-105">位置指定パラメーターと名前付きパラメーター</span><span class="sxs-lookup"><span data-stu-id="4a2e6-105">Positional and Named Parameters</span></span>

<span data-ttu-id="4a2e6-106">すべてのコマンドレットパラメーターには、名前付きパラメーターまたは位置指定パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-106">All cmdlet parameters are either named or positional parameters.</span></span> <span data-ttu-id="4a2e6-107">名前付きパラメーターを使用するには、コマンドレットを呼び出すときに、パラメーターの名前と引数を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-107">A named parameter requires that you type the parameter name and argument when calling the cmdlet.</span></span> <span data-ttu-id="4a2e6-108">位置指定パラメーターでは、引数を相対順序で入力するだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-108">A positional parameter requires only that you type the arguments in relative order.</span></span> <span data-ttu-id="4a2e6-109">次に、最初の名前のない引数が最初の位置指定パラメーターにマップされます。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-109">The system then maps the first unnamed argument to the first positional parameter.</span></span> <span data-ttu-id="4a2e6-110">2番目の無名の引数が、2番目の無名のパラメーターにマップされます。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-110">The system maps the second unnamed argument to the second unnamed parameter, and so on.</span></span> <span data-ttu-id="4a2e6-111">既定では、すべてのコマンドレットパラメーターは名前付きパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-111">By default, all cmdlet parameters are named parameters.</span></span>

<span data-ttu-id="4a2e6-112">名前付きパラメーターを定義するには、次のパラメーター宣言に示すように、 **parameter**属性の宣言で `Position` キーワードを省略します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-112">To define a named parameter, omit the `Position` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(ValueFromPipeline=true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="4a2e6-113">位置指定パラメーターを定義するには、パラメーター属性の宣言に `Position` キーワードを追加し、位置を指定します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-113">To define a positional parameter, add the `Position` keyword in the Parameter attribute declaration, and then specify a position.</span></span> <span data-ttu-id="4a2e6-114">次の例では、`UserName` パラメーターが位置0の位置指定パラメーターとして宣言されています。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-114">In the following sample, the `UserName` parameter is declared as a positional parameter with position 0.</span></span> <span data-ttu-id="4a2e6-115">これは、呼び出しの最初の引数がこのパラメーターに自動的にバインドされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-115">This means that the first argument of the call will be automatically bound to this parameter.</span></span>

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
> <span data-ttu-id="4a2e6-116">適切なコマンドレットの設計では、コマンドレットの実行時にユーザーがパラメーター名を入力する必要がないように、最も使用されるパラメーターを位置指定パラメーターとして宣言することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-116">Good cmdlet design recommends that the most-used parameters be declared as positional parameters so that the user does not have to enter the parameter name when the cmdlet is run.</span></span>

<span data-ttu-id="4a2e6-117">位置指定パラメーターと名前付きパラメーターは、単一の引数またはコンマで区切られた複数の引数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-117">Positional and named parameters accept single arguments or multiple arguments separated by commas.</span></span> <span data-ttu-id="4a2e6-118">パラメーターが文字列の配列などのコレクションを受け入れる場合にのみ、複数の引数を指定できます。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-118">Multiple arguments are allowed only if the parameter accepts a collection such as an array of strings.</span></span> <span data-ttu-id="4a2e6-119">同じコマンドレットで、位置指定パラメーターと名前付きパラメーターを混在させることができます。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-119">You may mix positional and named parameters in the same cmdlet.</span></span> <span data-ttu-id="4a2e6-120">この場合、システムはまず名前付き引数を取得してから、残りの名前なし引数を位置指定パラメーターにマップしようとします。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-120">In this case, the system retrieves the named arguments first, and then attempts to map the remaining unnamed arguments to the positional parameters.</span></span>

<span data-ttu-id="4a2e6-121">次のコマンドは、`Get-Command` コマンドレットのパラメーターに1つ以上の引数を指定するさまざまな方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-121">The following commands show the different ways in which you can specify single and multiple arguments for the parameters of the `Get-Command` cmdlet.</span></span> <span data-ttu-id="4a2e6-122">最後の2つのサンプルでは、`Name` パラメーターが位置パラメーターとして定義されているため、 **-name**を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-122">Notice that in the last two samples, **-name** does not need to be specified because the `Name` parameter is defined as a positional parameter.</span></span>

```powershell
Get-Command -Name get-service
Get-Command -Name get-service,set-service
Get-Command get-service
Get-Command get-service,set-service
```

## <a name="mandatory-and-optional-parameters"></a><span data-ttu-id="4a2e6-123">必須のパラメーターと省略可能なパラメーター</span><span class="sxs-lookup"><span data-stu-id="4a2e6-123">Mandatory and Optional Parameters</span></span>

<span data-ttu-id="4a2e6-124">コマンドレットのパラメーターは、必須パラメーターまたは省略可能なパラメーターとして定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-124">You can also define cmdlet parameters as mandatory or optional parameters.</span></span> <span data-ttu-id="4a2e6-125">(Windows PowerShell ランタイムがコマンドレットを呼び出す前に、必須パラメーターを指定する必要があります)。 既定では、パラメーターはオプションとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-125">(A mandatory parameter must be specified before the Windows PowerShell runtime invokes the cmdlet.)  By default, parameters are defined as optional.</span></span>

<span data-ttu-id="4a2e6-126">必須パラメーターを定義するには、次のパラメーター宣言に示すように、Parameter 属性宣言に `Mandatory` キーワードを追加し、それを `true`に設定します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-126">To define a mandatory parameter, add the `Mandatory` keyword in the Parameter attribute declaration, and set it to `true`, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="4a2e6-127">省略可能なパラメーターを定義するには、次のパラメーター宣言に示すように、 **parameter**属性の宣言で `Mandatory` キーワードを省略します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-127">To define an optional parameter, omit the `Mandatory` keyword in the **Parameter** attribute declaration, as shown in the following parameter declaration.</span></span>

```csharp
[Parameter(Position = 0)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

## <a name="switch-parameters"></a><span data-ttu-id="4a2e6-128">スイッチパラメーター</span><span class="sxs-lookup"><span data-stu-id="4a2e6-128">Switch Parameters</span></span>

<span data-ttu-id="4a2e6-129">Windows PowerShell には、コマンドレットの呼び出し時にパラメーターが指定されていない場合に、値が自動的に `false` に設定されるパラメーターを定義できるようにする、 [switchparameter](/dotnet/api/System.Management.Automation.SwitchParameter)型が用意されています。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-129">Windows PowerShell provides a [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type that allows you to define a parameter whose value is automatically set to `false` if the parameter is not specified when the cmdlet is called.</span></span> <span data-ttu-id="4a2e6-130">可能な限り、ブール型パラメーターの代わりにスイッチパラメーターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-130">Whenever possible, use switch parameters in place of Boolean parameters.</span></span>

<span data-ttu-id="4a2e6-131">次の例について考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-131">Consider the following sample.</span></span> <span data-ttu-id="4a2e6-132">既定では、いくつかの Windows PowerShell コマンドレットは、出力オブジェクトをパイプラインの下位に渡しません。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-132">By default, several Windows PowerShell cmdlets do not pass an output object down the pipeline.</span></span> <span data-ttu-id="4a2e6-133">ただし、これらのコマンドレットには、既定の動作をオーバーライドする `PassThru` スイッチパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-133">However, these cmdlets have a `PassThru` switch parameter that overrides the default behavior.</span></span> <span data-ttu-id="4a2e6-134">これらのコマンドレットを呼び出すときに `PassThru` パラメーターを指定した場合、コマンドレットは出力オブジェクトをパイプラインに返します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-134">If the `PassThru` parameter is specified when these cmdlets are called, the cmdlet returns an output object to the pipeline.</span></span>

<span data-ttu-id="4a2e6-135">パラメーターが呼び出しで指定されていない場合に、パラメーターの既定値 `true` を持つ必要がある場合は、パラメーターの意味を逆にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-135">If you need the parameter to have a default value of `true` when the parameter is not specified in the call, consider reversing the sense of the parameter.</span></span> <span data-ttu-id="4a2e6-136">サンプルの場合は、parameter 属性を `true`のブール値に設定するのではなく、プロパティを system.string[パラメーター](/dotnet/api/System.Management.Automation.SwitchParameter)の型として宣言し、パラメーターの既定値を `false`に設定します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-136">For sample, instead of setting the parameter attribute to a Boolean value of `true`, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, and then set the default value of the parameter to `false`.</span></span>

<span data-ttu-id="4a2e6-137">スイッチパラメーターを定義するには、次の例に示すように、プロパティを system.string[パラメーター](/dotnet/api/System.Management.Automation.SwitchParameter)の型として宣言します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-137">To define a switch parameter, declare the property as the [System.Management.Automation.SwitchParameter](/dotnet/api/System.Management.Automation.SwitchParameter) type, as shown in the following sample.</span></span>

```csharp
[Parameter(Position = 1)]
public SwitchParameter GoodBye
{
  get { return goodbye; }
  set { goodbye = value; }
}
private bool goodbye;
```

<span data-ttu-id="4a2e6-138">パラメーターを指定したときにコマンドレットを実行するには、入力処理メソッドのいずれかで次の構造体を使用します。</span><span class="sxs-lookup"><span data-stu-id="4a2e6-138">To make the cmdlet act on the parameter when it is specified, use the following structure within one of the input processing methods.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="4a2e6-139">参照</span><span class="sxs-lookup"><span data-stu-id="4a2e6-139">See Also</span></span>

[<span data-ttu-id="4a2e6-140">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="4a2e6-140">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
