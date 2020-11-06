---
description: 整数リテラルと実数リテラルは、どちらも型および乗数サフィックスを持つことができます。
Locale: en-US
ms.date: 04/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 数値リテラルについて
ms.openlocfilehash: f9d23a37c06c8285c23328ea8ddcebf8d6caae9e
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354730"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="9a12b-103">数値リテラルについて</span><span class="sxs-lookup"><span data-stu-id="9a12b-103">About numeric literals</span></span>

<span data-ttu-id="9a12b-104">数値リテラルには、整数と実数の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="9a12b-105">どちらも、型と乗数のサフィックスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="9a12b-106">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="9a12b-106">Integer literals</span></span>

<span data-ttu-id="9a12b-107">整数リテラルは、10進数、16進数、またはバイナリ表記で記述できます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-107">Integer literals can be written in decimal, hexadecimal, or binary notation.</span></span>
<span data-ttu-id="9a12b-108">16進数リテラルにはプレフィックスが付き `0x` 、バイナリリテラルには、 `0b` 10 進数と区別するためのプレフィックスが付きます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-108">Hexadecimal literals are prefixed with `0x` and binary literals are prefixed with `0b` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="9a12b-109">整数リテラルには、型サフィックスと乗数サフィックスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="9a12b-110">サフィックス</span><span class="sxs-lookup"><span data-stu-id="9a12b-110">Suffix</span></span> |            <span data-ttu-id="9a12b-111">意味</span><span class="sxs-lookup"><span data-stu-id="9a12b-111">Meaning</span></span>             |          <span data-ttu-id="9a12b-112">メモ</span><span class="sxs-lookup"><span data-stu-id="9a12b-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="9a12b-113">○</span><span class="sxs-lookup"><span data-stu-id="9a12b-113">y</span></span>      | <span data-ttu-id="9a12b-114">符号付きバイトデータ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-114">signed byte data type</span></span>          | <span data-ttu-id="9a12b-115">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="9a12b-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="9a12b-116">uy</span><span class="sxs-lookup"><span data-stu-id="9a12b-116">uy</span></span>     | <span data-ttu-id="9a12b-117">unsigned byte データ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-117">unsigned byte data type</span></span>        | <span data-ttu-id="9a12b-118">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="9a12b-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="9a12b-119">s</span><span class="sxs-lookup"><span data-stu-id="9a12b-119">s</span></span>      | <span data-ttu-id="9a12b-120">short データ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-120">short data type</span></span>                | <span data-ttu-id="9a12b-121">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="9a12b-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="9a12b-122">us</span><span class="sxs-lookup"><span data-stu-id="9a12b-122">us</span></span>     | <span data-ttu-id="9a12b-123">unsigned short データ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-123">unsigned short data type</span></span>       | <span data-ttu-id="9a12b-124">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="9a12b-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="9a12b-125">l</span><span class="sxs-lookup"><span data-stu-id="9a12b-125">l</span></span>      | <span data-ttu-id="9a12b-126">long データ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-126">long data type</span></span>                 |                         |
| <span data-ttu-id="9a12b-127">u</span><span class="sxs-lookup"><span data-stu-id="9a12b-127">u</span></span>      | <span data-ttu-id="9a12b-128">unsigned int または long データ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-128">unsigned int or long data type</span></span> | <span data-ttu-id="9a12b-129">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="9a12b-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="9a12b-130">ul</span><span class="sxs-lookup"><span data-stu-id="9a12b-130">ul</span></span>     | <span data-ttu-id="9a12b-131">unsigned long データ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-131">unsigned long data type</span></span>        | <span data-ttu-id="9a12b-132">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="9a12b-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="9a12b-133">n</span><span class="sxs-lookup"><span data-stu-id="9a12b-133">n</span></span>      | <span data-ttu-id="9a12b-134">BigInteger データ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-134">BigInteger data type</span></span>           | <span data-ttu-id="9a12b-135">PowerShell 7.0 で追加</span><span class="sxs-lookup"><span data-stu-id="9a12b-135">Added in PowerShell 7.0</span></span> |
| <span data-ttu-id="9a12b-136">kb</span><span class="sxs-lookup"><span data-stu-id="9a12b-136">kb</span></span>     | <span data-ttu-id="9a12b-137">キロバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-137">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="9a12b-138">mb</span><span class="sxs-lookup"><span data-stu-id="9a12b-138">mb</span></span>     | <span data-ttu-id="9a12b-139">メガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-139">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="9a12b-140">8gb</span><span class="sxs-lookup"><span data-stu-id="9a12b-140">gb</span></span>     | <span data-ttu-id="9a12b-141">ギガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-141">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="9a12b-142">単位</span><span class="sxs-lookup"><span data-stu-id="9a12b-142">tb</span></span>     | <span data-ttu-id="9a12b-143">テラバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-143">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="9a12b-144">pb</span><span class="sxs-lookup"><span data-stu-id="9a12b-144">pb</span></span>     | <span data-ttu-id="9a12b-145">ペタバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-145">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="9a12b-146">整数リテラルの型は、その値、型のサフィックス、および数値乗数のサフィックスによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-146">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="9a12b-147">型サフィックスのない整数リテラルの場合:</span><span class="sxs-lookup"><span data-stu-id="9a12b-147">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="9a12b-148">値を型で表すことができる場合 `[int]` は。それが型である場合は。</span><span class="sxs-lookup"><span data-stu-id="9a12b-148">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="9a12b-149">それ以外の場合、値を型で表すことができる場合は、それ以外の場合は `[long]` 型です。</span><span class="sxs-lookup"><span data-stu-id="9a12b-149">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="9a12b-150">それ以外の場合、値を型で表すことができる場合は、それ以外の場合は `[decimal]` 型です。</span><span class="sxs-lookup"><span data-stu-id="9a12b-150">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="9a12b-151">それ以外の場合は、型によって表され `[double]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-151">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="9a12b-152">型サフィックスを持つ整数リテラルの場合:</span><span class="sxs-lookup"><span data-stu-id="9a12b-152">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="9a12b-153">型のサフィックスがで、 `u` 値を型で表すことができる場合、 `[uint]` 型はになり `[uint]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-153">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="9a12b-154">型のサフィックスがで、 `u` 値を型で表すことができる場合、 `[ulong]` 型はになり `[ulong]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-154">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="9a12b-155">指定された型で値を表すことができる場合は、その型になります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-155">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="9a12b-156">それ以外の場合は、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9a12b-156">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="9a12b-157">実数リテラル</span><span class="sxs-lookup"><span data-stu-id="9a12b-157">Real literals</span></span>

<span data-ttu-id="9a12b-158">実際のリテラルは、10進表記でのみ記述できます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-158">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="9a12b-159">この表記法では、小数点の後に指数部を使用した小数値と指数表記を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-159">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="9a12b-160">指数部には、"e" の後に省略可能な符号 (+/-) と指数を表す数値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-160">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="9a12b-161">たとえば、リテラル値は `1e2` 数値100と同じです。</span><span class="sxs-lookup"><span data-stu-id="9a12b-161">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="9a12b-162">実際のリテラルは、型サフィックスと乗数サフィックスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-162">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="9a12b-163">サフィックス</span><span class="sxs-lookup"><span data-stu-id="9a12b-163">Suffix</span></span> |       <span data-ttu-id="9a12b-164">意味</span><span class="sxs-lookup"><span data-stu-id="9a12b-164">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="9a12b-165">d</span><span class="sxs-lookup"><span data-stu-id="9a12b-165">d</span></span>      | <span data-ttu-id="9a12b-166">decimal データ型</span><span class="sxs-lookup"><span data-stu-id="9a12b-166">decimal data type</span></span>   |
| <span data-ttu-id="9a12b-167">kb</span><span class="sxs-lookup"><span data-stu-id="9a12b-167">kb</span></span>     | <span data-ttu-id="9a12b-168">キロバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-168">kilobyte multiplier</span></span> |
| <span data-ttu-id="9a12b-169">mb</span><span class="sxs-lookup"><span data-stu-id="9a12b-169">mb</span></span>     | <span data-ttu-id="9a12b-170">メガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-170">megabyte multiplier</span></span> |
| <span data-ttu-id="9a12b-171">8gb</span><span class="sxs-lookup"><span data-stu-id="9a12b-171">gb</span></span>     | <span data-ttu-id="9a12b-172">ギガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-172">gigabyte multiplier</span></span> |
| <span data-ttu-id="9a12b-173">単位</span><span class="sxs-lookup"><span data-stu-id="9a12b-173">tb</span></span>     | <span data-ttu-id="9a12b-174">テラバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-174">terabyte multiplier</span></span> |
| <span data-ttu-id="9a12b-175">pb</span><span class="sxs-lookup"><span data-stu-id="9a12b-175">pb</span></span>     | <span data-ttu-id="9a12b-176">ペタバイト乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-176">petabyte multiplier</span></span> |

<span data-ttu-id="9a12b-177">実数リテラルには、double と decimal の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-177">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="9a12b-178">これらは、それぞれ、decimal 型のサフィックスによって、個別に存在するかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-178">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="9a12b-179">PowerShell では、値のリテラル表現はサポートされていません `[float]` 。</span><span class="sxs-lookup"><span data-stu-id="9a12b-179">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="9a12b-180">Double 実数リテラルには型があり `[double]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-180">A double real literal has type `[double]`.</span></span> <span data-ttu-id="9a12b-181">10進数の実数リテラルには型があり `[decimal]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-181">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="9a12b-182">10進数の実数リテラルの小数部の末尾の0は有意です。</span><span class="sxs-lookup"><span data-stu-id="9a12b-182">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="9a12b-183">実数リテラルの指数部の数字の値が、 `[double]` サポートされる最小値よりも小さい場合、その `[double]` 実数リテラルの値は0になります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-183">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="9a12b-184">実数リテラルの指数部の数字の値が、 `[decimal]` サポートされている最小値よりも小さい場合、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9a12b-184">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="9a12b-185">または実数リテラルの指数部の数字の値 `[double]` `[decimal]` が、サポートされている最大値を超えている場合、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9a12b-185">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="9a12b-186">この構文では、2つの実数リテラルに long 型のサフィックスを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-186">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="9a12b-187">PowerShell では、このケースは、値が型で表される整数リテラルとして扱われ `[long]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-187">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="9a12b-188">この機能は、以前のバージョンの PowerShell との下位互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="9a12b-188">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="9a12b-189">ただし、プログラマはこの形式の整数リテラルを使用しないことをお勧めします。これは、リテラルの実際の値を簡単に隠すことができるためです。</span><span class="sxs-lookup"><span data-stu-id="9a12b-189">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="9a12b-190">たとえば、の値 `1.2L` が1で、値が `1.2345e1L` 12 で、 `1.2345e-5L` 値が0である場合、そのいずれもすぐにはわかりません。</span><span class="sxs-lookup"><span data-stu-id="9a12b-190">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="9a12b-191">数値乗数</span><span class="sxs-lookup"><span data-stu-id="9a12b-191">Numeric multipliers</span></span>

<span data-ttu-id="9a12b-192">便宜上、整数と実数のリテラルには数値乗数を含めることができます。これは、一般的に使用される2の累乗の1つを示します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-192">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="9a12b-193">数値の乗数は、大文字または小文字の任意の組み合わせで記述できます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-193">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="9a12b-194">乗数サフィックスは任意の型サフィックスと組み合わせて使用できますが、型サフィックスの後に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-194">The multiplier suffixes can be used in combination with any type suffixes, but must be present after the type suffix.</span></span> <span data-ttu-id="9a12b-195">たとえば、リテラルの `100gbL` 形式が正しくありませんが、リテラルは `100Lgb` 有効です。</span><span class="sxs-lookup"><span data-stu-id="9a12b-195">For example, the literal `100gbL` is malformed, but the literal `100Lgb` is valid.</span></span>

<span data-ttu-id="9a12b-196">乗数によって指定された数値型の有効な値を超える値が作成されると、リテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="9a12b-196">If a multiplier creates a value that exceeds the possible values for the numeric type that the suffix specifies, the literal is malformed.</span></span> <span data-ttu-id="9a12b-197">たとえば、リテラルは、 `1usgb` `1gb` `[ushort]` サフィックスによって指定された型で許可されている値よりも大きいため、形式が正しくあり `us` ません。</span><span class="sxs-lookup"><span data-stu-id="9a12b-197">For example, the literal `1usgb` is malformed, because the value `1gb` is larger than what is permitted for the `[ushort]` type specified by the `us` suffix.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="9a12b-198">乗数の例</span><span class="sxs-lookup"><span data-stu-id="9a12b-198">Multiplier examples</span></span>

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

## <a name="numeric-type-accelerators"></a><span data-ttu-id="9a12b-199">数値型アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="9a12b-199">Numeric type accelerators</span></span>

<span data-ttu-id="9a12b-200">PowerShell では、次の種類のアクセラレータがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9a12b-200">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="9a12b-201">アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="9a12b-201">Accelerator</span></span> |         <span data-ttu-id="9a12b-202">メモ</span><span class="sxs-lookup"><span data-stu-id="9a12b-202">Note</span></span>         |           <span data-ttu-id="9a12b-203">[説明]</span><span class="sxs-lookup"><span data-stu-id="9a12b-203">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="9a12b-204">バイト (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9a12b-204">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="9a12b-205">バイト (符号付き)</span><span class="sxs-lookup"><span data-stu-id="9a12b-205">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="9a12b-206">16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="9a12b-206">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="9a12b-207">の別名 `[int16]`</span><span class="sxs-lookup"><span data-stu-id="9a12b-207">alias for `[int16]`</span></span>  | <span data-ttu-id="9a12b-208">16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="9a12b-208">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="9a12b-209">16ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9a12b-209">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="9a12b-210">の別名 `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="9a12b-210">alias for `[uint16]`</span></span> | <span data-ttu-id="9a12b-211">16ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9a12b-211">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="9a12b-212">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="9a12b-212">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="9a12b-213">の別名 `[int32]`</span><span class="sxs-lookup"><span data-stu-id="9a12b-213">alias for `[int32]`</span></span>  | <span data-ttu-id="9a12b-214">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="9a12b-214">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="9a12b-215">32ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9a12b-215">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="9a12b-216">の別名 `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="9a12b-216">alias for `[uint32]`</span></span> | <span data-ttu-id="9a12b-217">32ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9a12b-217">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="9a12b-218">64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="9a12b-218">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="9a12b-219">の別名 `[int64]`</span><span class="sxs-lookup"><span data-stu-id="9a12b-219">alias for `[int64]`</span></span>  | <span data-ttu-id="9a12b-220">64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="9a12b-220">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="9a12b-221">64ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9a12b-221">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="9a12b-222">の別名 `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="9a12b-222">alias for `[uint64]`</span></span> | <span data-ttu-id="9a12b-223">64ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="9a12b-223">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="9a12b-224">「 [BigInteger Struct][bigint] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9a12b-224">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="9a12b-225">単精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="9a12b-225">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="9a12b-226">の別名 `[single]`</span><span class="sxs-lookup"><span data-stu-id="9a12b-226">alias for `[single]`</span></span> | <span data-ttu-id="9a12b-227">単精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="9a12b-227">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="9a12b-228">倍精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="9a12b-228">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="9a12b-229">128ビット浮動小数点</span><span class="sxs-lookup"><span data-stu-id="9a12b-229">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="9a12b-230">PowerShell 6.2 では、、、、の各型アクセラレータが追加されました。 `[short]` `[ushort]` `[uint]` `[ulong]`</span><span class="sxs-lookup"><span data-stu-id="9a12b-230">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

## <a name="examples"></a><span data-ttu-id="9a12b-231">例</span><span class="sxs-lookup"><span data-stu-id="9a12b-231">Examples</span></span>

<span data-ttu-id="9a12b-232">次の表は、数値リテラルの例をいくつか示し、その型と値を示しています。</span><span class="sxs-lookup"><span data-stu-id="9a12b-232">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|   <span data-ttu-id="9a12b-233">Number</span><span class="sxs-lookup"><span data-stu-id="9a12b-233">Number</span></span>     |  <span data-ttu-id="9a12b-234">Type</span><span class="sxs-lookup"><span data-stu-id="9a12b-234">Type</span></span>      |    <span data-ttu-id="9a12b-235">値</span><span class="sxs-lookup"><span data-stu-id="9a12b-235">Value</span></span>     |
| -----------: | ---------- | -----------: |
|         <span data-ttu-id="9a12b-236">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-236">100</span></span>  | <span data-ttu-id="9a12b-237">Int32</span><span class="sxs-lookup"><span data-stu-id="9a12b-237">Int32</span></span>      |          <span data-ttu-id="9a12b-238">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-238">100</span></span> |
|        <span data-ttu-id="9a12b-239">100u</span><span class="sxs-lookup"><span data-stu-id="9a12b-239">100u</span></span>  | <span data-ttu-id="9a12b-240">UInt32</span><span class="sxs-lookup"><span data-stu-id="9a12b-240">UInt32</span></span>     |          <span data-ttu-id="9a12b-241">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-241">100</span></span> |
|        <span data-ttu-id="9a12b-242">100D</span><span class="sxs-lookup"><span data-stu-id="9a12b-242">100D</span></span>  | <span data-ttu-id="9a12b-243">Decimal</span><span class="sxs-lookup"><span data-stu-id="9a12b-243">Decimal</span></span>    |          <span data-ttu-id="9a12b-244">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-244">100</span></span> |
|        <span data-ttu-id="9a12b-245">100l</span><span class="sxs-lookup"><span data-stu-id="9a12b-245">100l</span></span>  | <span data-ttu-id="9a12b-246">Int64</span><span class="sxs-lookup"><span data-stu-id="9a12b-246">Int64</span></span>      |          <span data-ttu-id="9a12b-247">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-247">100</span></span> |
|       <span data-ttu-id="9a12b-248">100uL</span><span class="sxs-lookup"><span data-stu-id="9a12b-248">100uL</span></span>  | <span data-ttu-id="9a12b-249">UInt64</span><span class="sxs-lookup"><span data-stu-id="9a12b-249">UInt64</span></span>     |          <span data-ttu-id="9a12b-250">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-250">100</span></span> |
|       <span data-ttu-id="9a12b-251">100us</span><span class="sxs-lookup"><span data-stu-id="9a12b-251">100us</span></span>  | <span data-ttu-id="9a12b-252">UInt16</span><span class="sxs-lookup"><span data-stu-id="9a12b-252">UInt16</span></span>     |          <span data-ttu-id="9a12b-253">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-253">100</span></span> |
|       <span data-ttu-id="9a12b-254">100uy</span><span class="sxs-lookup"><span data-stu-id="9a12b-254">100uy</span></span>  | <span data-ttu-id="9a12b-255">Byte</span><span class="sxs-lookup"><span data-stu-id="9a12b-255">Byte</span></span>       |          <span data-ttu-id="9a12b-256">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-256">100</span></span> |
|        <span data-ttu-id="9a12b-257">100y</span><span class="sxs-lookup"><span data-stu-id="9a12b-257">100y</span></span>  | <span data-ttu-id="9a12b-258">SByte</span><span class="sxs-lookup"><span data-stu-id="9a12b-258">SByte</span></span>      |          <span data-ttu-id="9a12b-259">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-259">100</span></span> |
|         <span data-ttu-id="9a12b-260">1e2</span><span class="sxs-lookup"><span data-stu-id="9a12b-260">1e2</span></span>  | <span data-ttu-id="9a12b-261">Double</span><span class="sxs-lookup"><span data-stu-id="9a12b-261">Double</span></span>     |          <span data-ttu-id="9a12b-262">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-262">100</span></span> |
|        <span data-ttu-id="9a12b-263">e2</span><span class="sxs-lookup"><span data-stu-id="9a12b-263">1.e2</span></span>  | <span data-ttu-id="9a12b-264">Double</span><span class="sxs-lookup"><span data-stu-id="9a12b-264">Double</span></span>     |          <span data-ttu-id="9a12b-265">100</span><span class="sxs-lookup"><span data-stu-id="9a12b-265">100</span></span> |
|       <span data-ttu-id="9a12b-266">0x1e2</span><span class="sxs-lookup"><span data-stu-id="9a12b-266">0x1e2</span></span>  | <span data-ttu-id="9a12b-267">Int32</span><span class="sxs-lookup"><span data-stu-id="9a12b-267">Int32</span></span>      |          <span data-ttu-id="9a12b-268">482</span><span class="sxs-lookup"><span data-stu-id="9a12b-268">482</span></span> |
|      <span data-ttu-id="9a12b-269">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="9a12b-269">0x1e2L</span></span>  | <span data-ttu-id="9a12b-270">Int64</span><span class="sxs-lookup"><span data-stu-id="9a12b-270">Int64</span></span>      |          <span data-ttu-id="9a12b-271">482</span><span class="sxs-lookup"><span data-stu-id="9a12b-271">482</span></span> |
|      <span data-ttu-id="9a12b-272">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="9a12b-272">0x1e2D</span></span>  | <span data-ttu-id="9a12b-273">Int32</span><span class="sxs-lookup"><span data-stu-id="9a12b-273">Int32</span></span>      |         <span data-ttu-id="9a12b-274">7725</span><span class="sxs-lookup"><span data-stu-id="9a12b-274">7725</span></span> |
|        <span data-ttu-id="9a12b-275">482D</span><span class="sxs-lookup"><span data-stu-id="9a12b-275">482D</span></span>  | <span data-ttu-id="9a12b-276">Decimal</span><span class="sxs-lookup"><span data-stu-id="9a12b-276">Decimal</span></span>    |          <span data-ttu-id="9a12b-277">482</span><span class="sxs-lookup"><span data-stu-id="9a12b-277">482</span></span> |
|       <span data-ttu-id="9a12b-278">48 gb</span><span class="sxs-lookup"><span data-stu-id="9a12b-278">482gb</span></span>  | <span data-ttu-id="9a12b-279">Int64</span><span class="sxs-lookup"><span data-stu-id="9a12b-279">Int64</span></span>      | <span data-ttu-id="9a12b-280">517543559168</span><span class="sxs-lookup"><span data-stu-id="9a12b-280">517543559168</span></span> |
|       <span data-ttu-id="9a12b-281">482ngb</span><span class="sxs-lookup"><span data-stu-id="9a12b-281">482ngb</span></span> | <span data-ttu-id="9a12b-282">BigInteger</span><span class="sxs-lookup"><span data-stu-id="9a12b-282">BigInteger</span></span> | <span data-ttu-id="9a12b-283">517543559168</span><span class="sxs-lookup"><span data-stu-id="9a12b-283">517543559168</span></span> |
|    <span data-ttu-id="9a12b-284">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="9a12b-284">0x1e2lgb</span></span>  | <span data-ttu-id="9a12b-285">Int64</span><span class="sxs-lookup"><span data-stu-id="9a12b-285">Int64</span></span>      | <span data-ttu-id="9a12b-286">517543559168</span><span class="sxs-lookup"><span data-stu-id="9a12b-286">517543559168</span></span> |
|   <span data-ttu-id="9a12b-287">0b1011011</span><span class="sxs-lookup"><span data-stu-id="9a12b-287">0b1011011</span></span>  | <span data-ttu-id="9a12b-288">Int32</span><span class="sxs-lookup"><span data-stu-id="9a12b-288">Int32</span></span>      |           <span data-ttu-id="9a12b-289">91</span><span class="sxs-lookup"><span data-stu-id="9a12b-289">91</span></span> |
|  <span data-ttu-id="9a12b-290">~</span><span class="sxs-lookup"><span data-stu-id="9a12b-290">0xFFFFFFFF</span></span>  | <span data-ttu-id="9a12b-291">Int32</span><span class="sxs-lookup"><span data-stu-id="9a12b-291">Int32</span></span>      |           <span data-ttu-id="9a12b-292">-1</span><span class="sxs-lookup"><span data-stu-id="9a12b-292">-1</span></span> |
| <span data-ttu-id="9a12b-293">-0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="9a12b-293">-0xFFFFFFFF</span></span>  | <span data-ttu-id="9a12b-294">Int32</span><span class="sxs-lookup"><span data-stu-id="9a12b-294">Int32</span></span>      |            <span data-ttu-id="9a12b-295">1</span><span class="sxs-lookup"><span data-stu-id="9a12b-295">1</span></span> |
| <span data-ttu-id="9a12b-296">0xFFFFFFFFu</span><span class="sxs-lookup"><span data-stu-id="9a12b-296">0xFFFFFFFFu</span></span>  | <span data-ttu-id="9a12b-297">UInt32</span><span class="sxs-lookup"><span data-stu-id="9a12b-297">UInt32</span></span>     |   <span data-ttu-id="9a12b-298">4294967295</span><span class="sxs-lookup"><span data-stu-id="9a12b-298">4294967295</span></span> |

### <a name="working-with-binary-or-hexadecimal-numbers"></a><span data-ttu-id="9a12b-299">バイナリまたは16進数の使用</span><span class="sxs-lookup"><span data-stu-id="9a12b-299">Working with binary or hexadecimal numbers</span></span>

<span data-ttu-id="9a12b-300">極端に大きいバイナリまたは16進数のリテラルは、 `[bigint]` サフィックスが指定されている場合にのみ、解析が失敗するのではなく、as を返すことができ `n` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-300">Overly large binary or hexadecimal literals can return as `[bigint]` rather than failing the parse, if and only if the `n` suffix is specified.</span></span> <span data-ttu-id="9a12b-301">ただし、符号ビットは引き続き範囲を超えてい `[decimal]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-301">Sign bits are still respected above even `[decimal]` ranges, however:</span></span>

- <span data-ttu-id="9a12b-302">バイナリ文字列が8ビット長の倍数である場合、最大ビットは符号ビットとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-302">If a binary string is some multiple of 8 bits long, the highest bit is treated as the sign bit.</span></span>
- <span data-ttu-id="9a12b-303">8の倍数である16進数の文字列に、8以上の最初の桁が含まれている場合、数字は負の値として扱われます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-303">If a hex string, which has a length that is a multiple of 8, has the first digit with 8 or higher, the numeral is treated as negative.</span></span>

<span data-ttu-id="9a12b-304">バイナリリテラルと16進数リテラルに符号なしサフィックスを指定すると、符号ビットが無視されます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-304">Specifying an unsigned suffix on binary and hex literals ignores sign bits.</span></span> <span data-ttu-id="9a12b-305">たとえば、はを `0xFFFFFFFF` 返し `-1` ますが、は `0xFFFFFFFFu` 4294967295 のを返し `[uint]::MaxValue` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-305">For example, `0xFFFFFFFF` returns `-1`, but `0xFFFFFFFFu` returns the `[uint]::MaxValue` of 4294967295.</span></span>

<span data-ttu-id="9a12b-306">リテラルにプレフィックスとしてを指定する `0` と、これは無視され、符号なしとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-306">Prefixing the literal with a `0` will bypass this and be treated as unsigned.</span></span>
<span data-ttu-id="9a12b-307">例: `0b011111111`。</span><span class="sxs-lookup"><span data-stu-id="9a12b-307">For example: `0b011111111`.</span></span> <span data-ttu-id="9a12b-308">これは、 `[bigint]` `u` とのサフィックスを組み合わせることができないため、範囲内のリテラルを使用する場合に必要になることがあり `n` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-308">This can be necessary when working with literals in the `[bigint]` range, as the `u` and `n` suffixes cannot be combined.</span></span>

<span data-ttu-id="9a12b-309">プレフィックスを使用して、バイナリリテラルと16進リテラルを否定することもでき `-` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-309">You can also negate binary and hex literals using the `-` prefix.</span></span> <span data-ttu-id="9a12b-310">符号ビットが許可されるため、これにより正の数値が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-310">This can result in a positive number since sign bits are permitted.</span></span>

<span data-ttu-id="9a12b-311">符号ビットは、BigInteger の数字で受け入れられます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-311">Sign bits are accepted for BigInteger-suffixed numerals:</span></span>

- <span data-ttu-id="9a12b-312">BigInteger-サフィックス16は、符号ビットとして8文字の倍数であるリテラルの上位ビットを処理します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-312">BigInteger-suffixed hex treats the high bit of any literal with a length multiple of 8 characters as the sign bit.</span></span> <span data-ttu-id="9a12b-313">長さには、 `0x` プレフィックスまたはサフィックスは含まれません。</span><span class="sxs-lookup"><span data-stu-id="9a12b-313">The length does not include the `0x` prefix or any suffixes.</span></span>
- <span data-ttu-id="9a12b-314">BigInteger バイナリでは、96と128文字の符号ビット、およびの後の8文字ごとに16進数を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-314">BigInteger-suffixed binary accepts sign bits at 96 and 128 characters, and at every 8 characters after.</span></span>

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="9a12b-315">数値リテラルのようなコマンド</span><span class="sxs-lookup"><span data-stu-id="9a12b-315">Commands that look like numeric literals</span></span>

<span data-ttu-id="9a12b-316">有効な数値リテラルのようなコマンドは、呼び出し演算子 () を使用して実行する必要があり `&` ます。そうしないと、数値として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-316">Any command that looks like a valid numeric literal must be executed using the call operator (`&`), otherwise it is interpreted as a number.</span></span> <span data-ttu-id="9a12b-317">のような有効な構文を使用した正しくないリテラルで `1usgb` は、次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-317">Malformed literals with valid syntax like `1usgb` will result in the following error:</span></span>

```
PS> 1usgb
At line:1 char:6
+ 1usgb
+      ~
The numeric constant 1usgb is not valid.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : BadNumericConstant
```

<span data-ttu-id="9a12b-318">ただし、のような無効な構文を使用した正しく `1gbus` ないリテラルは、標準のベア文字列として解釈され、コマンドが呼び出されるコンテキストで有効なコマンド名として解釈できます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-318">However, malformed literals with invalid syntax like `1gbus` will be interpreted as a standard bare string, and can be interpreted as a valid command name in contexts where commands may be called.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="9a12b-319">数値オブジェクトのプロパティとメソッドへのアクセス</span><span class="sxs-lookup"><span data-stu-id="9a12b-319">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="9a12b-320">数値リテラルのメンバーにアクセスするには、リテラルをかっこで囲む必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-320">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="9a12b-321">リテラルに小数点がありません</span><span class="sxs-lookup"><span data-stu-id="9a12b-321">The literal does not have a decimal point</span></span>
- <span data-ttu-id="9a12b-322">リテラルの小数点の後に数字がありません。</span><span class="sxs-lookup"><span data-stu-id="9a12b-322">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="9a12b-323">リテラルにサフィックスがありません</span><span class="sxs-lookup"><span data-stu-id="9a12b-323">The literal does not have a suffix</span></span>

<span data-ttu-id="9a12b-324">たとえば、次の例では失敗します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-324">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="9a12b-325">次の例は動作します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-325">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="9a12b-326">最初の2つの例では、リテラル値をかっこで囲まずに使用します。これは、PowerShell パーサーが数値リテラルの終了位置と **GetType** メソッドの開始位置を判別できるためです。</span><span class="sxs-lookup"><span data-stu-id="9a12b-326">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

## <a name="how-powershell-parses-numeric-literals"></a><span data-ttu-id="9a12b-327">PowerShell で数値リテラルを解析する方法</span><span class="sxs-lookup"><span data-stu-id="9a12b-327">How PowerShell parses numeric literals</span></span>

<span data-ttu-id="9a12b-328">PowerShell v1.0 では、新しい機能を有効にするために、数値リテラルの解析方法が変更されました。</span><span class="sxs-lookup"><span data-stu-id="9a12b-328">PowerShell v7.0 changed the way numeric literals are parsed to enable the new features.</span></span>

### <a name="parsing-real-numeric-literals"></a><span data-ttu-id="9a12b-329">実際の数値リテラルの解析</span><span class="sxs-lookup"><span data-stu-id="9a12b-329">Parsing real numeric literals</span></span>

<span data-ttu-id="9a12b-330">リテラルに小数点または e 表記が含まれている場合、リテラル文字列は実数を解析します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-330">If the literal contains a decimal point or the e-notation, the literal string is parsed a real number.</span></span>

- <span data-ttu-id="9a12b-331">小数点サフィックスがある場合は、に直接を指定し `[decimal]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-331">If the decimal-suffix is present then directly into `[decimal]`.</span></span>
- <span data-ttu-id="9a12b-332">それ以外の場合は、として解析 `[Double]` し、値に乗数を適用します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-332">Else, parse as `[Double]` and apply multiplier to the value.</span></span> <span data-ttu-id="9a12b-333">次に、型のサフィックスを確認し、適切な型へのキャストを試みます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-333">Then check the type suffixes and attempt to cast into appropriate type.</span></span>
- <span data-ttu-id="9a12b-334">文字列に型のサフィックスがない場合は、として解析し `[Double]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-334">If the string has no type suffix, then parse as `[Double]`.</span></span>

### <a name="paring-integer-numeric-literals"></a><span data-ttu-id="9a12b-335">ペアリング整数の数値リテラル</span><span class="sxs-lookup"><span data-stu-id="9a12b-335">Paring integer numeric literals</span></span>

<span data-ttu-id="9a12b-336">整数型リテラルは、次の手順を使用して解析されます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-336">Integer type literals are parsed using the following steps:</span></span>

1. <span data-ttu-id="9a12b-337">基数の形式を決定する</span><span class="sxs-lookup"><span data-stu-id="9a12b-337">Determine the radix format</span></span>
   - <span data-ttu-id="9a12b-338">バイナリ形式の場合は、をに解析 `[BigInteger]` します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-338">For binary formats, parse into `[BigInteger]`.</span></span>
   - <span data-ttu-id="9a12b-339">16進数形式の場合 `[BigInteger]` は、値がまたはの範囲内にある場合に、特別なビヘイビアーを使用してを解析し、元のを保持し `[int]` `[long]` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-339">For hexidecimal formats, parse into `[BigInteger]` using special casies to retain original behaviours when the value is in the `[int]` or `[long]` range.</span></span>
   - <span data-ttu-id="9a12b-340">バイナリも16進数でもない場合は、をとして通常どおり解析 `[BigInteger]` します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-340">If neither binary nor hex, parse normally as a `[BigInteger]`.</span></span>
2. <span data-ttu-id="9a12b-341">オーバーフローを発生させずに型の境界を適切にチェックするために、キャストを試行する前に乗数値を適用します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-341">Apply the multiplier value before attempting any casts to ensure type bounds can be appropriately checked without overflows.</span></span>
3. <span data-ttu-id="9a12b-342">型のサフィックスを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-342">Check type suffixes.</span></span>
   - <span data-ttu-id="9a12b-343">型の境界を確認し、その型への解析を試行します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-343">Check type bounds and attempt to parse into that type.</span></span>
   - <span data-ttu-id="9a12b-344">サフィックスが使用されていない場合、値は次の順序で境界チェックされます。その結果、最初に成功したテストで数値の型が決定されます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-344">If no suffix is used, then the value is bounds-checked in the following order, resulting in the first successful test determining the type of the number.</span></span>
     - `[int]`
     - `[long]`
     - <span data-ttu-id="9a12b-345">`[decimal]` (基数10リテラルのみ)</span><span class="sxs-lookup"><span data-stu-id="9a12b-345">`[decimal]` (base-10 literals only)</span></span>
     - <span data-ttu-id="9a12b-346">`[double]` (基数10リテラルのみ)</span><span class="sxs-lookup"><span data-stu-id="9a12b-346">`[double]` (base-10 literals only)</span></span>
   - <span data-ttu-id="9a12b-347">値が `[long]` 16 進数値と2進数の範囲外の場合、解析は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-347">If the value is outside the `[long]` range for hex and binary numbers, the parse fails.</span></span>
   - <span data-ttu-id="9a12b-348">値が `[double]` 底10の数値の範囲外の場合、解析は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-348">If the value is outside the `[double]` range for base 10 number, the parse fails.</span></span>
   - <span data-ttu-id="9a12b-349">リテラルをと `n` して解析するには、サフィックスを使用して、より高い値を明示的に記述する必要があり `BigInteger` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-349">Higher values must be explicitly written using the `n` suffix to parse the literal as a `BigInteger`.</span></span>

### <a name="parsing-large-value-literals"></a><span data-ttu-id="9a12b-350">大きな値のリテラルの解析</span><span class="sxs-lookup"><span data-stu-id="9a12b-350">Parsing large value literals</span></span>

<span data-ttu-id="9a12b-351">以前は、より高い整数値は、他の型にキャストされる前に double として解析されていました。</span><span class="sxs-lookup"><span data-stu-id="9a12b-351">Previously, higher integer values were parsed as double before being cast to any other type.</span></span> <span data-ttu-id="9a12b-352">その結果、より高い範囲で精度が低下します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-352">This results in a loss of precision in the higher ranges.</span></span> <span data-ttu-id="9a12b-353">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="9a12b-353">For example:</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="9a12b-354">この問題を回避するには、値を文字列として書き込み、次のように変換する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="9a12b-354">To avoid this problem you had to write values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

<span data-ttu-id="9a12b-355">PowerShell 7.0 では、サフィックスを使用する必要があり `N` ます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-355">In PowerShell 7.0 you must use the `N` suffix.</span></span>

```
PS> 111111111111111111111111111111111111111111111111111111n
111111111111111111111111111111111111111111111111111111
```

<span data-ttu-id="9a12b-356">また、との間の値は、 `[ulong]::MaxValue` `[decimal]::MaxValue` `D` 精度を維持するために、小数点のサフィックスを使用して指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9a12b-356">Also values between `[ulong]::MaxValue` and `[decimal]::MaxValue` should be denoted using the decimal-suffix `D` to maintain accuracy.</span></span> <span data-ttu-id="9a12b-357">サフィックスがない場合、これらの値は `[Double]` 実際の解析モードを使用して解析されます。</span><span class="sxs-lookup"><span data-stu-id="9a12b-357">Without the suffix, these values are parsed as `[Double]` using the real-parsing mode.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
