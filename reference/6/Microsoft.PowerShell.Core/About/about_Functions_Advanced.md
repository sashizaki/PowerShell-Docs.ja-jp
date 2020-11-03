---
description: には、スクリプトを使用してコマンドレットを作成するための高度な関数が導入されています。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_advanced?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_Advanced
ms.openlocfilehash: f7e100122169b3ecb25be4d32fc72a67fea7b7cf
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93221608"
---
# <a name="about-functions-advanced"></a><span data-ttu-id="62084-104">関数の詳細</span><span class="sxs-lookup"><span data-stu-id="62084-104">About Functions Advanced</span></span>

## <a name="short-description"></a><span data-ttu-id="62084-105">概要</span><span class="sxs-lookup"><span data-stu-id="62084-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="62084-106">には、スクリプトを使用してコマンドレットを作成するための高度な関数が導入されています。</span><span class="sxs-lookup"><span data-stu-id="62084-106">Introduces advanced functions that are a way to create cmdlets using scripts.</span></span>

## <a name="long-description"></a><span data-ttu-id="62084-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="62084-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="62084-108">コマンドレットは、PowerShell のパイプラインセマンティクスに関与する単一のコマンドです。</span><span class="sxs-lookup"><span data-stu-id="62084-108">A cmdlet is a single command that participates in the pipeline semantics of PowerShell.</span></span> <span data-ttu-id="62084-109">これには、バイナリコマンドレット、高度なスクリプト関数、CDXML、ワークフローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="62084-109">This includes binary cmdlets, advanced script functions, CDXML, and Workflows.</span></span>

<span data-ttu-id="62084-110">高度な関数を使用すると、PowerShell 関数として記述されたコマンドレットを作成できます。</span><span class="sxs-lookup"><span data-stu-id="62084-110">Advanced functions allow you create cmdlets that are written as a PowerShell function.</span></span> <span data-ttu-id="62084-111">高度な関数を使用すると、バイナリコマンドレットを記述してコンパイルしなくても、コマンドレットを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="62084-111">Advanced functions make it easier to create cmdlets without having to write and compile a binary cmdlet.</span></span> <span data-ttu-id="62084-112">バイナリコマンドレットは、C# などの .NET 言語で記述された .NET クラスです。</span><span class="sxs-lookup"><span data-stu-id="62084-112">Binary cmdlets are .NET classes that are written in a .NET language such as C#.</span></span>

<span data-ttu-id="62084-113">高度な関数は、属性を使用し `CmdletBinding` て、コマンドレットのように機能する関数として識別します。</span><span class="sxs-lookup"><span data-stu-id="62084-113">Advanced functions use the `CmdletBinding` attribute to identify them as functions that act like cmdlets.</span></span> <span data-ttu-id="62084-114">属性は、コマンドレット `CmdletBinding` としてクラスを識別するためにコンパイル済みのコマンドレットクラスで使用されるコマンドレット属性に似ています。</span><span class="sxs-lookup"><span data-stu-id="62084-114">The `CmdletBinding` attribute is similar to the Cmdlet attribute that is used in compiled cmdlet classes to identify the class as a cmdlet.</span></span> <span data-ttu-id="62084-115">この属性の詳細については、「 [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62084-115">For more information about this attribute, see [about_Functions_CmdletBindingAttribute](about_Functions_CmdletBindingAttribute.md).</span></span>

<span data-ttu-id="62084-116">次の例は、名前を受け取り、指定された名前を使用してあいさつを出力する関数を示しています。</span><span class="sxs-lookup"><span data-stu-id="62084-116">The following example shows a function that accepts a name and then prints a greeting using the supplied name.</span></span> <span data-ttu-id="62084-117">また、この関数は、コンパイルされたコマンドレットの動詞と名詞のペアのような動詞 (送信) と名詞 (あいさつ) のペアを含む名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="62084-117">Also notice that this function defines a name that includes a verb (Send) and noun (Greeting) pair like the verb-noun pair of a compiled cmdlet.</span></span> <span data-ttu-id="62084-118">ただし、関数には動詞と名詞の名前を付ける必要はありません。</span><span class="sxs-lookup"><span data-stu-id="62084-118">However, functions are not required to have a verb-noun name.</span></span>

```powershell
function Send-Greeting
{
    [CmdletBinding()]
    Param(
        [Parameter(Mandatory=$true)]
        [string] $Name
    )

    Process
    {
        Write-Host ("Hello " + $Name + "!")
    }
}
```

<span data-ttu-id="62084-119">関数のパラメーターは、パラメーター属性を使用して宣言されます。</span><span class="sxs-lookup"><span data-stu-id="62084-119">The parameters of the function are declared by using the Parameter attribute.</span></span>
<span data-ttu-id="62084-120">この属性は単独で使用することも、別名属性またはその他のいくつかのパラメーター検証属性と組み合わせることもできます。</span><span class="sxs-lookup"><span data-stu-id="62084-120">This attribute can be used alone, or it can be combined with the Alias attribute or with several other parameter validation attributes.</span></span> <span data-ttu-id="62084-121">パラメーターを宣言する方法 (実行時に追加される動的パラメーターを含む) の詳細については、「 [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62084-121">For more information about how to declare parameters (including dynamic parameters that are added at runtime), see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

<span data-ttu-id="62084-122">前の関数の実際の処理は、プロセスブロック内で実行されます。これは、コマンドレットに渡されるデータを処理するためにコンパイルされたコマンドレットによって使用される ProcessingRecord メソッドに相当します。</span><span class="sxs-lookup"><span data-stu-id="62084-122">The actual work of the previous function is performed in the Process block, which is equivalent to the ProcessingRecord method that is used by compiled cmdlets to process the data that is passed to the cmdlet.</span></span> <span data-ttu-id="62084-123">このブロックは Begin および End ブロックと共に、 [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) のトピックで説明されています。</span><span class="sxs-lookup"><span data-stu-id="62084-123">This block, along with the Begin and End blocks, is described in the [about_Functions_Advanced_Methods](about_Functions_Advanced_Methods.md) topic.</span></span>

<span data-ttu-id="62084-124">高度な関数は、コンパイルされたコマンドレットとは次の点で異なります。</span><span class="sxs-lookup"><span data-stu-id="62084-124">Advanced functions differ from compiled cmdlets in the following ways:</span></span>

- <span data-ttu-id="62084-125">高度な関数パラメーターのバインドでは、文字列の配列がブール型パラメーターにバインドされている場合、例外はスローされません。</span><span class="sxs-lookup"><span data-stu-id="62084-125">Advanced function parameter binding does not throw an exception when an array of strings is bound to a Boolean parameter.</span></span>
- <span data-ttu-id="62084-126">ValidateSet 属性と Validateset 属性は、名前付きパラメーターを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="62084-126">The ValidateSet attribute and the ValidatePattern attribute cannot pass named parameters.</span></span>
- <span data-ttu-id="62084-127">高度な関数をトランザクションで使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="62084-127">Advanced functions cannot be used in transactions.</span></span>

## <a name="see-also"></a><span data-ttu-id="62084-128">関連項目</span><span class="sxs-lookup"><span data-stu-id="62084-128">SEE ALSO</span></span>

[<span data-ttu-id="62084-129">about_Functions</span><span class="sxs-lookup"><span data-stu-id="62084-129">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="62084-130">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="62084-130">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="62084-131">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="62084-131">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="62084-132">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="62084-132">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="62084-133">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="62084-133">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)
