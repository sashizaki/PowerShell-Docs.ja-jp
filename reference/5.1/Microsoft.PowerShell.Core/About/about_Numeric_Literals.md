---
description: 整数リテラルと実数リテラルは、どちらも型および乗数サフィックスを持つことができます。
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 数値リテラルについて
ms.openlocfilehash: 99fa8c1a751551d028fe6df0b0cec94e07f19c59
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93224960"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="9f089-103">数値リテラルについて</span><span class="sxs-lookup"><span data-stu-id="9f089-103">About numeric literals</span></span>

<span data-ttu-id="9f089-104">数値リテラルには、整数と実数の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="9f089-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="9f089-105">どちらも、型と乗数のサフィックスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="9f089-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="9f089-106">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="9f089-106">Integer literals</span></span>

<span data-ttu-id="9f089-107">整数リテラルは、10進数または16進表記で記述できます。</span><span class="sxs-lookup"><span data-stu-id="9f089-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="9f089-108">16進数リテラルには、 `0x` 10 進数と区別するためのプレフィックスが付きます。</span><span class="sxs-lookup"><span data-stu-id="9f089-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="9f089-109">整数リテラルには、型サフィックスと乗数サフィックスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f089-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="9f089-110">サフィックス</span><span class="sxs-lookup"><span data-stu-id="9f089-110">Suffix</span></span> |       <span data-ttu-id="9f089-111">説明</span><span class="sxs-lookup"><span data-stu-id="9f089-111">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="9f089-112">l</span><span class="sxs-lookup"><span data-stu-id="9f089-112">l</span></span>      | <span data-ttu-id="9f089-113">long データ型</span><span class="sxs-lookup"><span data-stu-id="9f089-113">long data type</span></span>      |
| <span data-ttu-id="9f089-114">kb</span><span class="sxs-lookup"><span data-stu-id="9f089-114">kb</span></span>     | <span data-ttu-id="9f089-115">キロバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-115">kilobyte multiplier</span></span> |
| <span data-ttu-id="9f089-116">mb</span><span class="sxs-lookup"><span data-stu-id="9f089-116">mb</span></span>     | <span data-ttu-id="9f089-117">メガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-117">megabyte multiplier</span></span> |
| <span data-ttu-id="9f089-118">8gb</span><span class="sxs-lookup"><span data-stu-id="9f089-118">gb</span></span>     | <span data-ttu-id="9f089-119">ギガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-119">gigabyte multiplier</span></span> |
| <span data-ttu-id="9f089-120">単位</span><span class="sxs-lookup"><span data-stu-id="9f089-120">tb</span></span>     | <span data-ttu-id="9f089-121">テラバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-121">terabyte multiplier</span></span> |
| <span data-ttu-id="9f089-122">pb</span><span class="sxs-lookup"><span data-stu-id="9f089-122">pb</span></span>     | <span data-ttu-id="9f089-123">ペタバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-123">petabyte multiplier</span></span> |

<span data-ttu-id="9f089-124">整数リテラルの型は、その値、型のサフィックス、および数値乗数のサフィックスによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="9f089-124">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="9f089-125">型サフィックスのない整数リテラルの場合:</span><span class="sxs-lookup"><span data-stu-id="9f089-125">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="9f089-126">値を型で表すことができる場合 `[int]` は。それが型である場合は。</span><span class="sxs-lookup"><span data-stu-id="9f089-126">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="9f089-127">それ以外の場合、値を型で表すことができる場合は、それ以外の場合は `[long]` 型です。</span><span class="sxs-lookup"><span data-stu-id="9f089-127">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="9f089-128">それ以外の場合、値を型で表すことができる場合は、それ以外の場合は `[decimal]` 型です。</span><span class="sxs-lookup"><span data-stu-id="9f089-128">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="9f089-129">それ以外の場合は、型によって表され `[double]` ます。</span><span class="sxs-lookup"><span data-stu-id="9f089-129">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="9f089-130">型サフィックスを持つ整数リテラルの場合:</span><span class="sxs-lookup"><span data-stu-id="9f089-130">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="9f089-131">型のサフィックスがで、 `u` 値を型で表すことができる場合、 `[int]` 型はになり `[int]` ます。</span><span class="sxs-lookup"><span data-stu-id="9f089-131">If the type suffix is `u` and the value can be represented by type `[int]` then its type is `[int]`.</span></span>
- <span data-ttu-id="9f089-132">型のサフィックスがで、 `u` 値を型で表すことができる場合、 `[long]` 型はになり `[long]` ます。</span><span class="sxs-lookup"><span data-stu-id="9f089-132">If the type suffix is `u` and the value can be represented by type `[long]` then its type is `[long]`.</span></span>
- <span data-ttu-id="9f089-133">指定された型で値を表すことができる場合は、その型になります。</span><span class="sxs-lookup"><span data-stu-id="9f089-133">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="9f089-134">それ以外の場合は、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9f089-134">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="9f089-135">実数リテラル</span><span class="sxs-lookup"><span data-stu-id="9f089-135">Real literals</span></span>

<span data-ttu-id="9f089-136">実際のリテラルは、10進表記でのみ記述できます。</span><span class="sxs-lookup"><span data-stu-id="9f089-136">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="9f089-137">この表記法では、小数点の後に指数部を使用した小数値と指数表記を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9f089-137">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="9f089-138">指数部には、"e" の後に省略可能な符号 (+/-) と指数を表す数値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9f089-138">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="9f089-139">たとえば、リテラル値は `1e2` 数値100と同じです。</span><span class="sxs-lookup"><span data-stu-id="9f089-139">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="9f089-140">実際のリテラルは、型サフィックスと乗数サフィックスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="9f089-140">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="9f089-141">サフィックス</span><span class="sxs-lookup"><span data-stu-id="9f089-141">Suffix</span></span> |       <span data-ttu-id="9f089-142">説明</span><span class="sxs-lookup"><span data-stu-id="9f089-142">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="9f089-143">d</span><span class="sxs-lookup"><span data-stu-id="9f089-143">d</span></span>      | <span data-ttu-id="9f089-144">decimal データ型</span><span class="sxs-lookup"><span data-stu-id="9f089-144">decimal data type</span></span>   |
| <span data-ttu-id="9f089-145">kb</span><span class="sxs-lookup"><span data-stu-id="9f089-145">kb</span></span>     | <span data-ttu-id="9f089-146">キロバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-146">kilobyte multiplier</span></span> |
| <span data-ttu-id="9f089-147">mb</span><span class="sxs-lookup"><span data-stu-id="9f089-147">mb</span></span>     | <span data-ttu-id="9f089-148">メガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-148">megabyte multiplier</span></span> |
| <span data-ttu-id="9f089-149">8gb</span><span class="sxs-lookup"><span data-stu-id="9f089-149">gb</span></span>     | <span data-ttu-id="9f089-150">ギガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-150">gigabyte multiplier</span></span> |
| <span data-ttu-id="9f089-151">単位</span><span class="sxs-lookup"><span data-stu-id="9f089-151">tb</span></span>     | <span data-ttu-id="9f089-152">テラバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-152">terabyte multiplier</span></span> |
| <span data-ttu-id="9f089-153">pb</span><span class="sxs-lookup"><span data-stu-id="9f089-153">pb</span></span>     | <span data-ttu-id="9f089-154">ペタバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-154">petabyte multiplier</span></span> |

<span data-ttu-id="9f089-155">実数リテラルには、double と decimal の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="9f089-155">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="9f089-156">これらは、それぞれ、decimal 型のサフィックスによって、個別に存在するかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="9f089-156">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="9f089-157">PowerShell では、値のリテラル表現はサポートされていません `[float]` 。</span><span class="sxs-lookup"><span data-stu-id="9f089-157">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="9f089-158">Double 実数リテラルには型があり `[double]` ます。</span><span class="sxs-lookup"><span data-stu-id="9f089-158">A double real literal has type `[double]`.</span></span> <span data-ttu-id="9f089-159">10進数の実数リテラルには型があり `[decimal]` ます。</span><span class="sxs-lookup"><span data-stu-id="9f089-159">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="9f089-160">10進数の実数リテラルの小数部の末尾の0は有意です。</span><span class="sxs-lookup"><span data-stu-id="9f089-160">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="9f089-161">実数リテラルの指数部の数字の値が、 `[double]` サポートされる最小値よりも小さい場合、その `[double]` 実数リテラルの値は0になります。</span><span class="sxs-lookup"><span data-stu-id="9f089-161">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="9f089-162">実数リテラルの指数部の数字の値が、 `[decimal]` サポートされている最小値よりも小さい場合、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9f089-162">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="9f089-163">または実数リテラルの指数部の数字の値 `[double]` `[decimal]` が、サポートされている最大値を超えている場合、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9f089-163">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="9f089-164">この構文では、2つの実数リテラルに long 型のサフィックスを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9f089-164">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="9f089-165">PowerShell では、このケースは、値が型で表される整数リテラルとして扱われ `[long]` ます。</span><span class="sxs-lookup"><span data-stu-id="9f089-165">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="9f089-166">この機能は、以前のバージョンの PowerShell との下位互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="9f089-166">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="9f089-167">ただし、プログラマはこの形式の整数リテラルを使用しないことをお勧めします。これは、リテラルの実際の値を簡単に隠すことができるためです。</span><span class="sxs-lookup"><span data-stu-id="9f089-167">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="9f089-168">たとえば、の値 `1.2L` が1で、値が `1.2345e1L` 12 で、 `1.2345e-5L` 値が0である場合、そのいずれもすぐにはわかりません。</span><span class="sxs-lookup"><span data-stu-id="9f089-168">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="9f089-169">数値乗数</span><span class="sxs-lookup"><span data-stu-id="9f089-169">Numeric multipliers</span></span>

<span data-ttu-id="9f089-170">便宜上、整数と実数のリテラルには数値乗数を含めることができます。これは、一般的に使用される2の累乗の1つを示します。</span><span class="sxs-lookup"><span data-stu-id="9f089-170">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="9f089-171">数値の乗数は、大文字または小文字の任意の組み合わせで記述できます。</span><span class="sxs-lookup"><span data-stu-id="9f089-171">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="9f089-172">乗数サフィックスは、、、およびの各型サフィックスと組み合わせて使用でき `u` `ul` `l` ます。</span><span class="sxs-lookup"><span data-stu-id="9f089-172">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="9f089-173">乗数の例</span><span class="sxs-lookup"><span data-stu-id="9f089-173">Multiplier examples</span></span>

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a><span data-ttu-id="9f089-174">数値型アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="9f089-174">Numeric type accelerators</span></span>

<span data-ttu-id="9f089-175">PowerShell では、次の種類のアクセラレータがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9f089-175">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="9f089-176">アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="9f089-176">Accelerator</span></span> |         <span data-ttu-id="9f089-177">注意</span><span class="sxs-lookup"><span data-stu-id="9f089-177">Note</span></span>         |           <span data-ttu-id="9f089-178">説明</span><span class="sxs-lookup"><span data-stu-id="9f089-178">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="9f089-179">バイト (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9f089-179">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="9f089-180">バイト (符号付き)</span><span class="sxs-lookup"><span data-stu-id="9f089-180">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="9f089-181">16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="9f089-181">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="9f089-182">16ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9f089-182">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="9f089-183">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="9f089-183">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="9f089-184">の別名 `[int32]`</span><span class="sxs-lookup"><span data-stu-id="9f089-184">alias for `[int32]`</span></span>  | <span data-ttu-id="9f089-185">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="9f089-185">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="9f089-186">32ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9f089-186">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="9f089-187">64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="9f089-187">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="9f089-188">の別名 `[int64]`</span><span class="sxs-lookup"><span data-stu-id="9f089-188">alias for `[int64]`</span></span>  | <span data-ttu-id="9f089-189">64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="9f089-189">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="9f089-190">64ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9f089-190">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="9f089-191">「 [BigInteger Struct][bigint] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f089-191">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="9f089-192">単精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="9f089-192">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="9f089-193">の別名 `[single]`</span><span class="sxs-lookup"><span data-stu-id="9f089-193">alias for `[single]`</span></span> | <span data-ttu-id="9f089-194">単精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="9f089-194">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="9f089-195">倍精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="9f089-195">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="9f089-196">128ビット浮動小数点</span><span class="sxs-lookup"><span data-stu-id="9f089-196">128-bit floating point</span></span>           |

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="9f089-197">他の数値型の使用</span><span class="sxs-lookup"><span data-stu-id="9f089-197">Working with other numeric types</span></span>

<span data-ttu-id="9f089-198">他の数値型を操作するには、型アクセラレータを使用する必要があります。これは、いくつかの問題がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="9f089-198">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="9f089-199">たとえば、高い整数値は、他の型にキャストされる前に、常に double として解析されます。</span><span class="sxs-lookup"><span data-stu-id="9f089-199">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="9f089-200">値は、最初は double として解析され、上位の範囲の有効桁数が失われます。</span><span class="sxs-lookup"><span data-stu-id="9f089-200">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="9f089-201">この問題を回避するには、値を文字列として入力し、変換します。</span><span class="sxs-lookup"><span data-stu-id="9f089-201">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="9f089-202">例</span><span class="sxs-lookup"><span data-stu-id="9f089-202">Examples</span></span>

<span data-ttu-id="9f089-203">次の表は、数値リテラルの例をいくつか示し、その型と値を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f089-203">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="9f089-204">Number</span><span class="sxs-lookup"><span data-stu-id="9f089-204">Number</span></span>  |  <span data-ttu-id="9f089-205">Type</span><span class="sxs-lookup"><span data-stu-id="9f089-205">Type</span></span>   |    <span data-ttu-id="9f089-206">値</span><span class="sxs-lookup"><span data-stu-id="9f089-206">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="9f089-207">100</span><span class="sxs-lookup"><span data-stu-id="9f089-207">100</span></span> | <span data-ttu-id="9f089-208">Int32</span><span class="sxs-lookup"><span data-stu-id="9f089-208">Int32</span></span>   |          <span data-ttu-id="9f089-209">100</span><span class="sxs-lookup"><span data-stu-id="9f089-209">100</span></span> |
|     <span data-ttu-id="9f089-210">100D</span><span class="sxs-lookup"><span data-stu-id="9f089-210">100D</span></span> | <span data-ttu-id="9f089-211">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="9f089-211">Decimal</span></span> |          <span data-ttu-id="9f089-212">100</span><span class="sxs-lookup"><span data-stu-id="9f089-212">100</span></span> |
|     <span data-ttu-id="9f089-213">100l</span><span class="sxs-lookup"><span data-stu-id="9f089-213">100l</span></span> | <span data-ttu-id="9f089-214">Int64</span><span class="sxs-lookup"><span data-stu-id="9f089-214">Int64</span></span>   |          <span data-ttu-id="9f089-215">100</span><span class="sxs-lookup"><span data-stu-id="9f089-215">100</span></span> |
|      <span data-ttu-id="9f089-216">1e2</span><span class="sxs-lookup"><span data-stu-id="9f089-216">1e2</span></span> | <span data-ttu-id="9f089-217">Double</span><span class="sxs-lookup"><span data-stu-id="9f089-217">Double</span></span>  |          <span data-ttu-id="9f089-218">100</span><span class="sxs-lookup"><span data-stu-id="9f089-218">100</span></span> |
|     <span data-ttu-id="9f089-219">e2</span><span class="sxs-lookup"><span data-stu-id="9f089-219">1.e2</span></span> | <span data-ttu-id="9f089-220">Double</span><span class="sxs-lookup"><span data-stu-id="9f089-220">Double</span></span>  |          <span data-ttu-id="9f089-221">100</span><span class="sxs-lookup"><span data-stu-id="9f089-221">100</span></span> |
|    <span data-ttu-id="9f089-222">0x1e2</span><span class="sxs-lookup"><span data-stu-id="9f089-222">0x1e2</span></span> | <span data-ttu-id="9f089-223">Int32</span><span class="sxs-lookup"><span data-stu-id="9f089-223">Int32</span></span>   |          <span data-ttu-id="9f089-224">482</span><span class="sxs-lookup"><span data-stu-id="9f089-224">482</span></span> |
|   <span data-ttu-id="9f089-225">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="9f089-225">0x1e2L</span></span> | <span data-ttu-id="9f089-226">Int64</span><span class="sxs-lookup"><span data-stu-id="9f089-226">Int64</span></span>   |          <span data-ttu-id="9f089-227">482</span><span class="sxs-lookup"><span data-stu-id="9f089-227">482</span></span> |
|   <span data-ttu-id="9f089-228">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="9f089-228">0x1e2D</span></span> | <span data-ttu-id="9f089-229">Int32</span><span class="sxs-lookup"><span data-stu-id="9f089-229">Int32</span></span>   |         <span data-ttu-id="9f089-230">7725</span><span class="sxs-lookup"><span data-stu-id="9f089-230">7725</span></span> |
|     <span data-ttu-id="9f089-231">482D</span><span class="sxs-lookup"><span data-stu-id="9f089-231">482D</span></span> | <span data-ttu-id="9f089-232">Decimal (10 進数型)</span><span class="sxs-lookup"><span data-stu-id="9f089-232">Decimal</span></span> |          <span data-ttu-id="9f089-233">482</span><span class="sxs-lookup"><span data-stu-id="9f089-233">482</span></span> |
|    <span data-ttu-id="9f089-234">48 gb</span><span class="sxs-lookup"><span data-stu-id="9f089-234">482gb</span></span> | <span data-ttu-id="9f089-235">Int64</span><span class="sxs-lookup"><span data-stu-id="9f089-235">Int64</span></span>   | <span data-ttu-id="9f089-236">517543559168</span><span class="sxs-lookup"><span data-stu-id="9f089-236">517543559168</span></span> |
| <span data-ttu-id="9f089-237">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="9f089-237">0x1e2lgb</span></span> | <span data-ttu-id="9f089-238">Int64</span><span class="sxs-lookup"><span data-stu-id="9f089-238">Int64</span></span>   | <span data-ttu-id="9f089-239">517543559168</span><span class="sxs-lookup"><span data-stu-id="9f089-239">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="9f089-240">数値リテラルのようなコマンド</span><span class="sxs-lookup"><span data-stu-id="9f089-240">Commands that look like numeric literals</span></span>

<span data-ttu-id="9f089-241">数値リテラルのようなコマンドは、呼び出し演算子 () を使用して実行する必要があり `&` ます。それ以外の場合は、関連付けられている型の数値として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="9f089-241">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="9f089-242">数値オブジェクトのプロパティとメソッドへのアクセス</span><span class="sxs-lookup"><span data-stu-id="9f089-242">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="9f089-243">数値リテラルのメンバーにアクセスするには、リテラルをかっこで囲む必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f089-243">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="9f089-244">リテラルに小数点がありません</span><span class="sxs-lookup"><span data-stu-id="9f089-244">The literal does not have a decimal point</span></span>
- <span data-ttu-id="9f089-245">リテラルの小数点の後に数字がありません。</span><span class="sxs-lookup"><span data-stu-id="9f089-245">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="9f089-246">リテラルにサフィックスがありません</span><span class="sxs-lookup"><span data-stu-id="9f089-246">The literal does not have a suffix</span></span>

<span data-ttu-id="9f089-247">たとえば、次の例では失敗します。</span><span class="sxs-lookup"><span data-stu-id="9f089-247">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="9f089-248">次の例は動作します。</span><span class="sxs-lookup"><span data-stu-id="9f089-248">The following examples work:</span></span>

```
PS> 2L.GetType().Name
Int64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="9f089-249">最初の2つの例では、リテラル値をかっこで囲まずに使用します。これは、PowerShell パーサーが数値リテラルの終了位置と **GetType** メソッドの開始位置を判別できるためです。</span><span class="sxs-lookup"><span data-stu-id="9f089-249">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
