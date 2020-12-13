---
ms.date: 09/13/2016
ms.topic: reference
title: パラメーターとしてプロパティを宣言する
description: パラメーターとしてプロパティを宣言する
ms.openlocfilehash: ade7928e2ca277da8bbd1a5e04997bd1d05f1e5d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653151"
---
# <a name="declaring-properties-as-parameters"></a><span data-ttu-id="81cf4-103">パラメーターとしてプロパティを宣言する</span><span class="sxs-lookup"><span data-stu-id="81cf4-103">Declaring Properties as Parameters</span></span>

<span data-ttu-id="81cf4-104">このトピックでは、コマンドレットのパラメーターを宣言する前に理解しておく必要がある基本的な情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="81cf4-104">This topic provides basic information you must understand before you declare the parameters of a cmdlet.</span></span>

<span data-ttu-id="81cf4-105">コマンドレットクラス内のコマンドレットのパラメーターを宣言するには、各パラメーターを表すパブリックプロパティを定義し、1つまたは複数のパラメーター属性を各プロパティに追加します。</span><span class="sxs-lookup"><span data-stu-id="81cf4-105">To declare the parameters of a cmdlet within your cmdlet class, define the public properties that represent each parameter, and then add one or more Parameter attributes to each property.</span></span> <span data-ttu-id="81cf4-106">Windows PowerShell ランタイムは、パラメーター属性を使用して、コマンドレットパラメーターとしてプロパティを識別します。</span><span class="sxs-lookup"><span data-stu-id="81cf4-106">The Windows PowerShell runtime uses the Parameter attributes to identify the property as a cmdlet parameter.</span></span> <span data-ttu-id="81cf4-107">パラメーター属性を宣言するための基本構文は `[Parameter()]` です。</span><span class="sxs-lookup"><span data-stu-id="81cf4-107">The basic syntax for declaring the Parameter attribute is `[Parameter()]`.</span></span>

<span data-ttu-id="81cf4-108">必須パラメーターとして定義されたプロパティの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="81cf4-108">Here is an example of a property defined as a required parameter.</span></span>

```csharp
[Parameter(Position = 0, Mandatory = true)]
public string UserName
{
  get { return userName; }
  set { userName = value; }
}
private string userName;
```

<span data-ttu-id="81cf4-109">ここでは、パラメーターについて覚えておくべきことをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="81cf4-109">Here are some things to remember about parameters.</span></span>

- <span data-ttu-id="81cf4-110">パラメーターは、明示的にパブリックとしてマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="81cf4-110">A parameter must be explicitly marked as public.</span></span> <span data-ttu-id="81cf4-111">既定でパブリックに設定されていないパラメーターは、Windows PowerShell ランタイムによって検出されません。</span><span class="sxs-lookup"><span data-stu-id="81cf4-111">Parameters that are not marked as public default to internal and will not be found by the Windows PowerShell runtime.</span></span>

- <span data-ttu-id="81cf4-112">パラメーターの検証を強化するには、パラメーターを Microsoft .NET Framework 型として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81cf4-112">Parameters should be defined as Microsoft .NET Framework types to provide better parameter validation.</span></span> <span data-ttu-id="81cf4-113">たとえば、値のセットから1つの値に制限されているパラメーターは、列挙型として定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="81cf4-113">For example, parameters that are restricted to one value out of a set of values should be defined as an enumeration type.</span></span> <span data-ttu-id="81cf4-114">Uniform Resource Identifier (URI) 値を受け取るパラメーターは、system.string 型にする必要が[あります。](/dotnet/api/System.Uri)</span><span class="sxs-lookup"><span data-stu-id="81cf4-114">Parameters that take a Uniform Resource Identifier (URI) value should be of type [System.Uri](/dotnet/api/System.Uri).</span></span>

- <span data-ttu-id="81cf4-115">自由形式のテキストプロパティ以外のすべてに対して、基本的な文字列パラメーターを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="81cf4-115">Avoid basic string parameters for all but free-form text properties.</span></span>

- <span data-ttu-id="81cf4-116">任意の数のパラメーターセットにパラメーターを追加できます。</span><span class="sxs-lookup"><span data-stu-id="81cf4-116">You can add a parameter to any number of parameter sets.</span></span> <span data-ttu-id="81cf4-117">パラメーターセットの詳細については、「 [コマンドレットパラメーターセット](./cmdlet-parameter-sets.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81cf4-117">For more information about parameter sets, see [Cmdlet Parameter Sets](./cmdlet-parameter-sets.md).</span></span>

<span data-ttu-id="81cf4-118">Windows PowerShell には、すべてのコマンドレットで自動的に使用できる一連の共通パラメーターも用意されています。</span><span class="sxs-lookup"><span data-stu-id="81cf4-118">Windows PowerShell also provides a set of common parameters that are automatically available to every cmdlet.</span></span> <span data-ttu-id="81cf4-119">これらのパラメーターとそのエイリアスの詳細については、「 [コマンドレットの共通パラメーター](./common-parameter-names.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81cf4-119">For more information about these parameters and their aliases, see [Cmdlet Common Parameters](./common-parameter-names.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="81cf4-120">参照</span><span class="sxs-lookup"><span data-stu-id="81cf4-120">See Also</span></span>

[<span data-ttu-id="81cf4-121">コマンドレットの共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="81cf4-121">Cmdlet Common Parameters</span></span>](./common-parameter-names.md)

[<span data-ttu-id="81cf4-122">コマンドレットパラメーターの型</span><span class="sxs-lookup"><span data-stu-id="81cf4-122">Types of Cmdlet Parameter</span></span>](./types-of-cmdlet-parameters.md)

[<span data-ttu-id="81cf4-123">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="81cf4-123">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
