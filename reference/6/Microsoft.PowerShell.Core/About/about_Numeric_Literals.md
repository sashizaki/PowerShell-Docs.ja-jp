---
description: 整数リテラルと実数リテラルは、どちらも型および乗数サフィックスを持つことができます。
Locale: en-US
ms.date: 04/09/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: 数値リテラルについて
ms.openlocfilehash: dc1a55dbec1f0de99e06011645e6884b37480233
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "93354831"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="3f190-103">数値リテラルについて</span><span class="sxs-lookup"><span data-stu-id="3f190-103">About numeric literals</span></span>

<span data-ttu-id="3f190-104">数値リテラルには、整数と実数の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="3f190-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="3f190-105">どちらも、型と乗数のサフィックスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="3f190-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="3f190-106">整数リテラル</span><span class="sxs-lookup"><span data-stu-id="3f190-106">Integer literals</span></span>

<span data-ttu-id="3f190-107">整数リテラルは、10進数または16進表記で記述できます。</span><span class="sxs-lookup"><span data-stu-id="3f190-107">Integer literals can be written in decimal or hexadecimal notation.</span></span> <span data-ttu-id="3f190-108">16進数リテラルには、 `0x` 10 進数と区別するためのプレフィックスが付きます。</span><span class="sxs-lookup"><span data-stu-id="3f190-108">Hexadecimal literals are prefixed with `0x` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="3f190-109">整数リテラルには、型サフィックスと乗数サフィックスを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3f190-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="3f190-110">サフィックス</span><span class="sxs-lookup"><span data-stu-id="3f190-110">Suffix</span></span> |            <span data-ttu-id="3f190-111">意味</span><span class="sxs-lookup"><span data-stu-id="3f190-111">Meaning</span></span>             |          <span data-ttu-id="3f190-112">メモ</span><span class="sxs-lookup"><span data-stu-id="3f190-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="3f190-113">○</span><span class="sxs-lookup"><span data-stu-id="3f190-113">y</span></span>      | <span data-ttu-id="3f190-114">符号付きバイトデータ型</span><span class="sxs-lookup"><span data-stu-id="3f190-114">signed byte data type</span></span>          | <span data-ttu-id="3f190-115">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="3f190-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="3f190-116">uy</span><span class="sxs-lookup"><span data-stu-id="3f190-116">uy</span></span>     | <span data-ttu-id="3f190-117">unsigned byte データ型</span><span class="sxs-lookup"><span data-stu-id="3f190-117">unsigned byte data type</span></span>        | <span data-ttu-id="3f190-118">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="3f190-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="3f190-119">s</span><span class="sxs-lookup"><span data-stu-id="3f190-119">s</span></span>      | <span data-ttu-id="3f190-120">short データ型</span><span class="sxs-lookup"><span data-stu-id="3f190-120">short data type</span></span>                | <span data-ttu-id="3f190-121">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="3f190-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="3f190-122">us</span><span class="sxs-lookup"><span data-stu-id="3f190-122">us</span></span>     | <span data-ttu-id="3f190-123">unsigned short データ型</span><span class="sxs-lookup"><span data-stu-id="3f190-123">unsigned short data type</span></span>       | <span data-ttu-id="3f190-124">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="3f190-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="3f190-125">l</span><span class="sxs-lookup"><span data-stu-id="3f190-125">l</span></span>      | <span data-ttu-id="3f190-126">long データ型</span><span class="sxs-lookup"><span data-stu-id="3f190-126">long data type</span></span>                 |                         |
| <span data-ttu-id="3f190-127">u</span><span class="sxs-lookup"><span data-stu-id="3f190-127">u</span></span>      | <span data-ttu-id="3f190-128">unsigned int または long データ型</span><span class="sxs-lookup"><span data-stu-id="3f190-128">unsigned int or long data type</span></span> | <span data-ttu-id="3f190-129">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="3f190-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="3f190-130">ul</span><span class="sxs-lookup"><span data-stu-id="3f190-130">ul</span></span>     | <span data-ttu-id="3f190-131">unsigned long データ型</span><span class="sxs-lookup"><span data-stu-id="3f190-131">unsigned long data type</span></span>        | <span data-ttu-id="3f190-132">PowerShell 6.2 で追加</span><span class="sxs-lookup"><span data-stu-id="3f190-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="3f190-133">kb</span><span class="sxs-lookup"><span data-stu-id="3f190-133">kb</span></span>     | <span data-ttu-id="3f190-134">キロバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-134">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="3f190-135">mb</span><span class="sxs-lookup"><span data-stu-id="3f190-135">mb</span></span>     | <span data-ttu-id="3f190-136">メガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-136">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="3f190-137">8gb</span><span class="sxs-lookup"><span data-stu-id="3f190-137">gb</span></span>     | <span data-ttu-id="3f190-138">ギガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-138">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="3f190-139">単位</span><span class="sxs-lookup"><span data-stu-id="3f190-139">tb</span></span>     | <span data-ttu-id="3f190-140">テラバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-140">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="3f190-141">pb</span><span class="sxs-lookup"><span data-stu-id="3f190-141">pb</span></span>     | <span data-ttu-id="3f190-142">ペタバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-142">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="3f190-143">整数リテラルの型は、その値、型のサフィックス、および数値乗数のサフィックスによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="3f190-143">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="3f190-144">型サフィックスのない整数リテラルの場合:</span><span class="sxs-lookup"><span data-stu-id="3f190-144">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="3f190-145">値を型で表すことができる場合 `[int]` は。それが型である場合は。</span><span class="sxs-lookup"><span data-stu-id="3f190-145">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="3f190-146">それ以外の場合、値を型で表すことができる場合は、それ以外の場合は `[long]` 型です。</span><span class="sxs-lookup"><span data-stu-id="3f190-146">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="3f190-147">それ以外の場合、値を型で表すことができる場合は、それ以外の場合は `[decimal]` 型です。</span><span class="sxs-lookup"><span data-stu-id="3f190-147">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="3f190-148">それ以外の場合は、型によって表され `[double]` ます。</span><span class="sxs-lookup"><span data-stu-id="3f190-148">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="3f190-149">型サフィックスを持つ整数リテラルの場合:</span><span class="sxs-lookup"><span data-stu-id="3f190-149">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="3f190-150">型のサフィックスがで、 `u` 値を型で表すことができる場合、 `[uint]` 型はになり `[uint]` ます。</span><span class="sxs-lookup"><span data-stu-id="3f190-150">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="3f190-151">型のサフィックスがで、 `u` 値を型で表すことができる場合、 `[ulong]` 型はになり `[ulong]` ます。</span><span class="sxs-lookup"><span data-stu-id="3f190-151">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="3f190-152">指定された型で値を表すことができる場合は、その型になります。</span><span class="sxs-lookup"><span data-stu-id="3f190-152">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="3f190-153">それ以外の場合は、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="3f190-153">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="3f190-154">実数リテラル</span><span class="sxs-lookup"><span data-stu-id="3f190-154">Real literals</span></span>

<span data-ttu-id="3f190-155">実際のリテラルは、10進表記でのみ記述できます。</span><span class="sxs-lookup"><span data-stu-id="3f190-155">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="3f190-156">この表記法では、小数点の後に指数部を使用した小数値と指数表記を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3f190-156">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="3f190-157">指数部には、"e" の後に省略可能な符号 (+/-) と指数を表す数値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3f190-157">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="3f190-158">たとえば、リテラル値は `1e2` 数値100と同じです。</span><span class="sxs-lookup"><span data-stu-id="3f190-158">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="3f190-159">実際のリテラルは、型サフィックスと乗数サフィックスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="3f190-159">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="3f190-160">サフィックス</span><span class="sxs-lookup"><span data-stu-id="3f190-160">Suffix</span></span> |       <span data-ttu-id="3f190-161">意味</span><span class="sxs-lookup"><span data-stu-id="3f190-161">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="3f190-162">d</span><span class="sxs-lookup"><span data-stu-id="3f190-162">d</span></span>      | <span data-ttu-id="3f190-163">decimal データ型</span><span class="sxs-lookup"><span data-stu-id="3f190-163">decimal data type</span></span>   |
| <span data-ttu-id="3f190-164">kb</span><span class="sxs-lookup"><span data-stu-id="3f190-164">kb</span></span>     | <span data-ttu-id="3f190-165">キロバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-165">kilobyte multiplier</span></span> |
| <span data-ttu-id="3f190-166">mb</span><span class="sxs-lookup"><span data-stu-id="3f190-166">mb</span></span>     | <span data-ttu-id="3f190-167">メガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-167">megabyte multiplier</span></span> |
| <span data-ttu-id="3f190-168">8gb</span><span class="sxs-lookup"><span data-stu-id="3f190-168">gb</span></span>     | <span data-ttu-id="3f190-169">ギガバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-169">gigabyte multiplier</span></span> |
| <span data-ttu-id="3f190-170">単位</span><span class="sxs-lookup"><span data-stu-id="3f190-170">tb</span></span>     | <span data-ttu-id="3f190-171">テラバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-171">terabyte multiplier</span></span> |
| <span data-ttu-id="3f190-172">pb</span><span class="sxs-lookup"><span data-stu-id="3f190-172">pb</span></span>     | <span data-ttu-id="3f190-173">ペタバイト乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-173">petabyte multiplier</span></span> |

<span data-ttu-id="3f190-174">実数リテラルには、double と decimal の2種類があります。</span><span class="sxs-lookup"><span data-stu-id="3f190-174">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="3f190-175">これらは、それぞれ、decimal 型のサフィックスによって、個別に存在するかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="3f190-175">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="3f190-176">PowerShell では、値のリテラル表現はサポートされていません `[float]` 。</span><span class="sxs-lookup"><span data-stu-id="3f190-176">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="3f190-177">Double 実数リテラルには型があり `[double]` ます。</span><span class="sxs-lookup"><span data-stu-id="3f190-177">A double real literal has type `[double]`.</span></span> <span data-ttu-id="3f190-178">10進数の実数リテラルには型があり `[decimal]` ます。</span><span class="sxs-lookup"><span data-stu-id="3f190-178">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="3f190-179">10進数の実数リテラルの小数部の末尾の0は有意です。</span><span class="sxs-lookup"><span data-stu-id="3f190-179">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="3f190-180">実数リテラルの指数部の数字の値が、 `[double]` サポートされる最小値よりも小さい場合、その `[double]` 実数リテラルの値は0になります。</span><span class="sxs-lookup"><span data-stu-id="3f190-180">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="3f190-181">実数リテラルの指数部の数字の値が、 `[decimal]` サポートされている最小値よりも小さい場合、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="3f190-181">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="3f190-182">または実数リテラルの指数部の数字の値 `[double]` `[decimal]` が、サポートされている最大値を超えている場合、そのリテラルの形式が正しくありません。</span><span class="sxs-lookup"><span data-stu-id="3f190-182">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="3f190-183">この構文では、2つの実数リテラルに long 型のサフィックスを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="3f190-183">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="3f190-184">PowerShell では、このケースは、値が型で表される整数リテラルとして扱われ `[long]` ます。</span><span class="sxs-lookup"><span data-stu-id="3f190-184">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="3f190-185">この機能は、以前のバージョンの PowerShell との下位互換性のために残されています。</span><span class="sxs-lookup"><span data-stu-id="3f190-185">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="3f190-186">ただし、プログラマはこの形式の整数リテラルを使用しないことをお勧めします。これは、リテラルの実際の値を簡単に隠すことができるためです。</span><span class="sxs-lookup"><span data-stu-id="3f190-186">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="3f190-187">たとえば、の値 `1.2L` が1で、値が `1.2345e1L` 12 で、 `1.2345e-5L` 値が0である場合、そのいずれもすぐにはわかりません。</span><span class="sxs-lookup"><span data-stu-id="3f190-187">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="3f190-188">数値乗数</span><span class="sxs-lookup"><span data-stu-id="3f190-188">Numeric multipliers</span></span>

<span data-ttu-id="3f190-189">便宜上、整数と実数のリテラルには数値乗数を含めることができます。これは、一般的に使用される2の累乗の1つを示します。</span><span class="sxs-lookup"><span data-stu-id="3f190-189">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="3f190-190">数値の乗数は、大文字または小文字の任意の組み合わせで記述できます。</span><span class="sxs-lookup"><span data-stu-id="3f190-190">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="3f190-191">乗数サフィックスは、、、およびの各型サフィックスと組み合わせて使用でき `u` `ul` `l` ます。</span><span class="sxs-lookup"><span data-stu-id="3f190-191">The multiplier suffixes can be used in combination with the `u`, `ul`, and `l` type suffixes.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="3f190-192">乗数の例</span><span class="sxs-lookup"><span data-stu-id="3f190-192">Multiplier examples</span></span>

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

## <a name="numeric-type-accelerators"></a><span data-ttu-id="3f190-193">数値型アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="3f190-193">Numeric type accelerators</span></span>

<span data-ttu-id="3f190-194">PowerShell では、次の種類のアクセラレータがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3f190-194">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="3f190-195">アクセラレータ</span><span class="sxs-lookup"><span data-stu-id="3f190-195">Accelerator</span></span> |         <span data-ttu-id="3f190-196">メモ</span><span class="sxs-lookup"><span data-stu-id="3f190-196">Note</span></span>         |           <span data-ttu-id="3f190-197">[説明]</span><span class="sxs-lookup"><span data-stu-id="3f190-197">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="3f190-198">バイト (符号なし)</span><span class="sxs-lookup"><span data-stu-id="3f190-198">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="3f190-199">バイト (符号付き)</span><span class="sxs-lookup"><span data-stu-id="3f190-199">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="3f190-200">16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="3f190-200">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="3f190-201">の別名 `[int16]`</span><span class="sxs-lookup"><span data-stu-id="3f190-201">alias for `[int16]`</span></span>  | <span data-ttu-id="3f190-202">16 ビット整数</span><span class="sxs-lookup"><span data-stu-id="3f190-202">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="3f190-203">16ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="3f190-203">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="3f190-204">の別名 `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="3f190-204">alias for `[uint16]`</span></span> | <span data-ttu-id="3f190-205">16ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="3f190-205">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="3f190-206">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="3f190-206">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="3f190-207">の別名 `[int32]`</span><span class="sxs-lookup"><span data-stu-id="3f190-207">alias for `[int32]`</span></span>  | <span data-ttu-id="3f190-208">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="3f190-208">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="3f190-209">32ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="3f190-209">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="3f190-210">の別名 `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="3f190-210">alias for `[uint32]`</span></span> | <span data-ttu-id="3f190-211">32ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="3f190-211">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="3f190-212">64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="3f190-212">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="3f190-213">の別名 `[int64]`</span><span class="sxs-lookup"><span data-stu-id="3f190-213">alias for `[int64]`</span></span>  | <span data-ttu-id="3f190-214">64 ビット整数</span><span class="sxs-lookup"><span data-stu-id="3f190-214">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="3f190-215">64ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="3f190-215">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="3f190-216">の別名 `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="3f190-216">alias for `[uint64]`</span></span> | <span data-ttu-id="3f190-217">64ビット整数 (符号なし)</span><span class="sxs-lookup"><span data-stu-id="3f190-217">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="3f190-218">「 [BigInteger Struct][bigint] 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f190-218">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="3f190-219">単精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="3f190-219">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="3f190-220">の別名 `[single]`</span><span class="sxs-lookup"><span data-stu-id="3f190-220">alias for `[single]`</span></span> | <span data-ttu-id="3f190-221">単精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="3f190-221">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="3f190-222">倍精度浮動小数点</span><span class="sxs-lookup"><span data-stu-id="3f190-222">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="3f190-223">128ビット浮動小数点</span><span class="sxs-lookup"><span data-stu-id="3f190-223">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="3f190-224">PowerShell 6.2 では、、、、の各型アクセラレータが追加されました。 `[short]` `[ushort]` `[uint]` `[ulong]`</span><span class="sxs-lookup"><span data-stu-id="3f190-224">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

### <a name="working-with-other-numeric-types"></a><span data-ttu-id="3f190-225">他の数値型の使用</span><span class="sxs-lookup"><span data-stu-id="3f190-225">Working with other numeric types</span></span>

<span data-ttu-id="3f190-226">他の数値型を操作するには、型アクセラレータを使用する必要があります。これは、いくつかの問題がないことを示します。</span><span class="sxs-lookup"><span data-stu-id="3f190-226">To work with any other numeric types you must use type accelerators, which is not without some problems.</span></span> <span data-ttu-id="3f190-227">たとえば、高い整数値は、他の型にキャストされる前に、常に double として解析されます。</span><span class="sxs-lookup"><span data-stu-id="3f190-227">For example, high integer values are always parsed as double before being cast to any other type.</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="3f190-228">値は、最初は double として解析され、上位の範囲の有効桁数が失われます。</span><span class="sxs-lookup"><span data-stu-id="3f190-228">The value is parsed as a double first, losing precision in the higher ranges.</span></span>
<span data-ttu-id="3f190-229">この問題を回避するには、値を文字列として入力し、変換します。</span><span class="sxs-lookup"><span data-stu-id="3f190-229">To avoid this problem, enter values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

## <a name="examples"></a><span data-ttu-id="3f190-230">例</span><span class="sxs-lookup"><span data-stu-id="3f190-230">Examples</span></span>

<span data-ttu-id="3f190-231">次の表は、数値リテラルの例をいくつか示し、その型と値を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f190-231">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|  <span data-ttu-id="3f190-232">Number</span><span class="sxs-lookup"><span data-stu-id="3f190-232">Number</span></span>  |  <span data-ttu-id="3f190-233">Type</span><span class="sxs-lookup"><span data-stu-id="3f190-233">Type</span></span>   |    <span data-ttu-id="3f190-234">値</span><span class="sxs-lookup"><span data-stu-id="3f190-234">Value</span></span>     |
| -------: | ------- | -----------: |
|      <span data-ttu-id="3f190-235">100</span><span class="sxs-lookup"><span data-stu-id="3f190-235">100</span></span> | <span data-ttu-id="3f190-236">Int32</span><span class="sxs-lookup"><span data-stu-id="3f190-236">Int32</span></span>   |          <span data-ttu-id="3f190-237">100</span><span class="sxs-lookup"><span data-stu-id="3f190-237">100</span></span> |
|     <span data-ttu-id="3f190-238">100D</span><span class="sxs-lookup"><span data-stu-id="3f190-238">100D</span></span> | <span data-ttu-id="3f190-239">Decimal</span><span class="sxs-lookup"><span data-stu-id="3f190-239">Decimal</span></span> |          <span data-ttu-id="3f190-240">100</span><span class="sxs-lookup"><span data-stu-id="3f190-240">100</span></span> |
|     <span data-ttu-id="3f190-241">100l</span><span class="sxs-lookup"><span data-stu-id="3f190-241">100l</span></span> | <span data-ttu-id="3f190-242">Int64</span><span class="sxs-lookup"><span data-stu-id="3f190-242">Int64</span></span>   |          <span data-ttu-id="3f190-243">100</span><span class="sxs-lookup"><span data-stu-id="3f190-243">100</span></span> |
|    <span data-ttu-id="3f190-244">100uL</span><span class="sxs-lookup"><span data-stu-id="3f190-244">100uL</span></span> | <span data-ttu-id="3f190-245">UInt64</span><span class="sxs-lookup"><span data-stu-id="3f190-245">UInt64</span></span>  |          <span data-ttu-id="3f190-246">100</span><span class="sxs-lookup"><span data-stu-id="3f190-246">100</span></span> |
|    <span data-ttu-id="3f190-247">100us</span><span class="sxs-lookup"><span data-stu-id="3f190-247">100us</span></span> | <span data-ttu-id="3f190-248">UInt16</span><span class="sxs-lookup"><span data-stu-id="3f190-248">UInt16</span></span>  |          <span data-ttu-id="3f190-249">100</span><span class="sxs-lookup"><span data-stu-id="3f190-249">100</span></span> |
|    <span data-ttu-id="3f190-250">100uy</span><span class="sxs-lookup"><span data-stu-id="3f190-250">100uy</span></span> | <span data-ttu-id="3f190-251">Byte</span><span class="sxs-lookup"><span data-stu-id="3f190-251">Byte</span></span>    |          <span data-ttu-id="3f190-252">100</span><span class="sxs-lookup"><span data-stu-id="3f190-252">100</span></span> |
|     <span data-ttu-id="3f190-253">100y</span><span class="sxs-lookup"><span data-stu-id="3f190-253">100y</span></span> | <span data-ttu-id="3f190-254">SByte</span><span class="sxs-lookup"><span data-stu-id="3f190-254">SByte</span></span>   |          <span data-ttu-id="3f190-255">100</span><span class="sxs-lookup"><span data-stu-id="3f190-255">100</span></span> |
|      <span data-ttu-id="3f190-256">1e2</span><span class="sxs-lookup"><span data-stu-id="3f190-256">1e2</span></span> | <span data-ttu-id="3f190-257">Double</span><span class="sxs-lookup"><span data-stu-id="3f190-257">Double</span></span>  |          <span data-ttu-id="3f190-258">100</span><span class="sxs-lookup"><span data-stu-id="3f190-258">100</span></span> |
|     <span data-ttu-id="3f190-259">e2</span><span class="sxs-lookup"><span data-stu-id="3f190-259">1.e2</span></span> | <span data-ttu-id="3f190-260">Double</span><span class="sxs-lookup"><span data-stu-id="3f190-260">Double</span></span>  |          <span data-ttu-id="3f190-261">100</span><span class="sxs-lookup"><span data-stu-id="3f190-261">100</span></span> |
|    <span data-ttu-id="3f190-262">0x1e2</span><span class="sxs-lookup"><span data-stu-id="3f190-262">0x1e2</span></span> | <span data-ttu-id="3f190-263">Int32</span><span class="sxs-lookup"><span data-stu-id="3f190-263">Int32</span></span>   |          <span data-ttu-id="3f190-264">482</span><span class="sxs-lookup"><span data-stu-id="3f190-264">482</span></span> |
|   <span data-ttu-id="3f190-265">0x1e2L</span><span class="sxs-lookup"><span data-stu-id="3f190-265">0x1e2L</span></span> | <span data-ttu-id="3f190-266">Int64</span><span class="sxs-lookup"><span data-stu-id="3f190-266">Int64</span></span>   |          <span data-ttu-id="3f190-267">482</span><span class="sxs-lookup"><span data-stu-id="3f190-267">482</span></span> |
|   <span data-ttu-id="3f190-268">0x1e2D</span><span class="sxs-lookup"><span data-stu-id="3f190-268">0x1e2D</span></span> | <span data-ttu-id="3f190-269">Int32</span><span class="sxs-lookup"><span data-stu-id="3f190-269">Int32</span></span>   |         <span data-ttu-id="3f190-270">7725</span><span class="sxs-lookup"><span data-stu-id="3f190-270">7725</span></span> |
|     <span data-ttu-id="3f190-271">482D</span><span class="sxs-lookup"><span data-stu-id="3f190-271">482D</span></span> | <span data-ttu-id="3f190-272">Decimal</span><span class="sxs-lookup"><span data-stu-id="3f190-272">Decimal</span></span> |          <span data-ttu-id="3f190-273">482</span><span class="sxs-lookup"><span data-stu-id="3f190-273">482</span></span> |
|    <span data-ttu-id="3f190-274">48 gb</span><span class="sxs-lookup"><span data-stu-id="3f190-274">482gb</span></span> | <span data-ttu-id="3f190-275">Int64</span><span class="sxs-lookup"><span data-stu-id="3f190-275">Int64</span></span>   | <span data-ttu-id="3f190-276">517543559168</span><span class="sxs-lookup"><span data-stu-id="3f190-276">517543559168</span></span> |
| <span data-ttu-id="3f190-277">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="3f190-277">0x1e2lgb</span></span> | <span data-ttu-id="3f190-278">Int64</span><span class="sxs-lookup"><span data-stu-id="3f190-278">Int64</span></span>   | <span data-ttu-id="3f190-279">517543559168</span><span class="sxs-lookup"><span data-stu-id="3f190-279">517543559168</span></span> |

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="3f190-280">数値リテラルのようなコマンド</span><span class="sxs-lookup"><span data-stu-id="3f190-280">Commands that look like numeric literals</span></span>

<span data-ttu-id="3f190-281">数値リテラルのようなコマンドは、呼び出し演算子 () を使用して実行する必要があり `&` ます。それ以外の場合は、関連付けられている型の数値として解釈されます。</span><span class="sxs-lookup"><span data-stu-id="3f190-281">Any command that looks like a numeric literal must be executed using the the call operator (`&`), otherwise it is interpreted as a number of the associated type.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="3f190-282">数値オブジェクトのプロパティとメソッドへのアクセス</span><span class="sxs-lookup"><span data-stu-id="3f190-282">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="3f190-283">数値リテラルのメンバーにアクセスするには、リテラルをかっこで囲む必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f190-283">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="3f190-284">リテラルに小数点がありません</span><span class="sxs-lookup"><span data-stu-id="3f190-284">The literal does not have a decimal point</span></span>
- <span data-ttu-id="3f190-285">リテラルの小数点の後に数字がありません。</span><span class="sxs-lookup"><span data-stu-id="3f190-285">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="3f190-286">リテラルにサフィックスがありません</span><span class="sxs-lookup"><span data-stu-id="3f190-286">The literal does not have a suffix</span></span>

<span data-ttu-id="3f190-287">たとえば、次の例では失敗します。</span><span class="sxs-lookup"><span data-stu-id="3f190-287">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="3f190-288">次の例は動作します。</span><span class="sxs-lookup"><span data-stu-id="3f190-288">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="3f190-289">最初の2つの例では、リテラル値をかっこで囲まずに使用します。これは、PowerShell パーサーが数値リテラルの終了位置と **GetType** メソッドの開始位置を判別できるためです。</span><span class="sxs-lookup"><span data-stu-id="3f190-289">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger
