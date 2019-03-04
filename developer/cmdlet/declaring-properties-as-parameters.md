---
title: パラメーターとしてプロパティの宣言 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f71ea35d-cff5-4e44-a5c6-3a747ed4c4d9
caps.latest.revision: 9
ms.openlocfilehash: 6f6640afb15b3608669538f9b5f53d7a8a5c380d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56861378"
---
# <a name="declaring-properties-as-parameters"></a><span data-ttu-id="725ca-102">パラメーターとしてプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="725ca-102">Declaring Properties as Parameters</span></span>

<span data-ttu-id="725ca-103">このトピックでは、コマンドレットのパラメーターを宣言する前に理解する必要があります、基本的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="725ca-103">This topic provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="725ca-104">コマンドレット クラス内でのコマンドレットのパラメーターを宣言するには、各パラメーターを表すパブリック プロパティを定義し、各プロパティに 1 つまたは複数のパラメーター属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="725ca-104">To declare the parameters of a cmdlet within your cmdlet class, define the public properties that represent each parameter, and then add one or more Parameter attributes to each property.</span></span> <span data-ttu-id="725ca-105">Windows PowerShell ランタイムでは、パラメーターの属性を使用して、コマンドレット パラメーターとしてプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="725ca-105">The Windows PowerShell runtime uses the Parameter attributes to identify the property as a cmdlet parameter.</span></span> <span data-ttu-id="725ca-106">パラメーター属性を宣言するための基本構文は`[Parameter()]`します。</span><span class="sxs-lookup"><span data-stu-id="725ca-106">The basic syntax for declaring the Parameter attribute is `[Parameter()]`.</span></span>

<span data-ttu-id="725ca-107">必要なパラメーターとして定義されているプロパティの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="725ca-107">Here is an example of a property defined as a required parameter.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="725ca-108">パラメーターに関する注意事項があります。</span><span class="sxs-lookup"><span data-stu-id="725ca-108">Here are some things to remember about parameters.</span></span>

- <span data-ttu-id="725ca-109">パラメーターをする必要があります明示的にパブリックと指定します。</span><span class="sxs-lookup"><span data-stu-id="725ca-109">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="725ca-110">内部にパブリックの既定としてマークされていないと、Windows PowerShell ランタイムでは見つからないされるパラメーター。</span><span class="sxs-lookup"><span data-stu-id="725ca-110">Parameters that are not marked as public default to internal and will not be found by the Windows PowerShell runtime.</span></span>

- <span data-ttu-id="725ca-111">パラメーターより優れたパラメーターの検証を提供する Microsoft .NET Framework 型として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="725ca-111">Parameters should be defined as Microsoft .NET Framework types to provide better parameter validation.</span></span> <span data-ttu-id="725ca-112">たとえば、値の中から 1 つの値に制限されているパラメーターは、列挙型として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="725ca-112">For example, parameters that are restricted to one value out of a set of values should be defined as an enumeration type.</span></span> <span data-ttu-id="725ca-113">型の Uniform Resource Identifier (URI) の値を受け取るパラメーターは必ず[System.Uri](/dotnet/api/System.Uri)します。</span><span class="sxs-lookup"><span data-stu-id="725ca-113">Parameters that take a Uniform Resource Identifier (URI) value should be of type [System.Uri](/dotnet/api/System.Uri).</span></span>

- <span data-ttu-id="725ca-114">以外のすべての自由形式テキストのプロパティの基本的な文字列パラメーターを回避します。</span><span class="sxs-lookup"><span data-stu-id="725ca-114">Avoid basic string parameters for all but free-form text properties.</span></span>

- <span data-ttu-id="725ca-115">パラメーターは、任意の数のパラメーター セットを追加できます。</span><span class="sxs-lookup"><span data-stu-id="725ca-115">You can add a parameter to any number of parameter sets.</span></span> <span data-ttu-id="725ca-116">パラメーター セットの詳細については、次を参照してください。[コマンドレット パラメーター設定](./cmdlet-parameter-sets.md)します。</span><span class="sxs-lookup"><span data-stu-id="725ca-116">For more information about parameter sets, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

<span data-ttu-id="725ca-117">Windows PowerShell には、すべてのコマンドレットを自動的に利用できる共通のパラメーターのセットも提供します。</span><span class="sxs-lookup"><span data-stu-id="725ca-117">Windows PowerShell also provides a set of common parameters that are automatically available to every cmdlet.</span></span> <span data-ttu-id="725ca-118">これらのパラメーターと、エイリアスの詳細については、次を参照してください。[コマンドレットに共通のパラメーター](./common-parameter-names.md)します。</span><span class="sxs-lookup"><span data-stu-id="725ca-118">For more information about these parameters and their aliases, see [Cmdlet Common Parameters](./common-parameter-names.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="725ca-119">参照</span><span class="sxs-lookup"><span data-stu-id="725ca-119">See Also</span></span>

[<span data-ttu-id="725ca-120">コマンドレットの一般的なパラメーター</span><span class="sxs-lookup"><span data-stu-id="725ca-120">Cmdlet Common Parameters</span></span>](./common-parameter-names.md)

[<span data-ttu-id="725ca-121">コマンドレットのパラメーターの型</span><span class="sxs-lookup"><span data-stu-id="725ca-121">Types of Cmdlet Parameter</span></span>](./types-of-cmdlet-parameters.md)

[<span data-ttu-id="725ca-122">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="725ca-122">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
