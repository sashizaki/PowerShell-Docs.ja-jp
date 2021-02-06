---
description: オブジェクトのコレクションに対するスクリプトフィルターの、より簡単で自然言語の方法について説明します。
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: dbd30d566414f784e7d5eca04af716c2bf1642b9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602219"
---
# <a name="about_simplified_syntax"></a><span data-ttu-id="f9577-103">about_Simplified_Syntax</span><span class="sxs-lookup"><span data-stu-id="f9577-103">about_Simplified_Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="f9577-104">概要</span><span class="sxs-lookup"><span data-stu-id="f9577-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="f9577-105">オブジェクトのコレクションに対するスクリプトフィルターの、より簡単で自然言語の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f9577-105">Describes easier, more natural-language ways of scripting filters for collections of objects.</span></span>

## <a name="long-description"></a><span data-ttu-id="f9577-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="f9577-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="f9577-107">Windows PowerShell 3.0 で導入された簡略化された構文を使用すると、スクリプトブロックを使用せずにいくつかのフィルターコマンドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f9577-107">Simplified syntax, introduced in Windows PowerShell 3.0, lets you build some filter commands without using script blocks.</span></span> <span data-ttu-id="f9577-108">簡略化された構文は自然言語に似ています。これは主に、コマンドと、 `Where-Object` `ForEach-Object` それに対応するエイリアスおよびにパイプされるオブジェクトのコレクションに役立ち `where` `foreach` ます。</span><span class="sxs-lookup"><span data-stu-id="f9577-108">The simplified syntax more closely resembles natural language, and is primarily useful with collections of objects that get piped into commands `Where-Object` and `ForEach-Object` and their corresponding aliases `where` and `foreach`.</span></span>

<span data-ttu-id="f9577-109">スクリプトブロック内の自動変数を参照せずに、コレクションのメンバー (通常は配列) に対してメソッドを使用でき `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="f9577-109">You can use a method on the members of a collection (most commonly, an array) without referring to the automatic variable `$_` inside a script block.</span></span>

<span data-ttu-id="f9577-110">次の2つの呼び出しについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="f9577-110">Consider the following two invocations:</span></span>

### <a name="standard-syntax"></a><span data-ttu-id="f9577-111">標準構文</span><span class="sxs-lookup"><span data-stu-id="f9577-111">Standard Syntax</span></span>

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a><span data-ttu-id="f9577-112">簡略化された構文</span><span class="sxs-lookup"><span data-stu-id="f9577-112">Simplified syntax</span></span>

<span data-ttu-id="f9577-113">簡略化された構文では、コレクション内のオブジェクトのメンバーに対して機能する比較演算子は、パラメーターとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="f9577-113">Under the simplified syntax, comparison operators that work on members of objects in a collection are treated as parameters.</span></span> <span data-ttu-id="f9577-114">スクリプトブロック内の自動変数を参照せずに、コレクション内のオブジェクトに対してメソッドを呼び出すことができ `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="f9577-114">You can invoke a method on objects in a collection without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="f9577-115">次の2つの呼び出しを、前の例の呼び出しと比較します。</span><span class="sxs-lookup"><span data-stu-id="f9577-115">Compare the following two invocations to those of the previous example:</span></span>

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

<span data-ttu-id="f9577-116">どちらの構文も機能しますが、簡略化された構文は、スクリプトブロック内の自動変数を参照せずに結果を返し `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="f9577-116">While both syntaxes work, the simplified syntax returns results without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="f9577-117">メソッド名 `GetKeyAlgorithm` は、のパラメーターとして扱われ `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="f9577-117">The method name `GetKeyAlgorithm` is treated as a parameter of `ForEach-Object`.</span></span>
<span data-ttu-id="f9577-118">2番目のコマンドは、指定された引数が適用されなかった項目の結果を返さないようにするため、エラーが発生することなく、同じ結果を返します。</span><span class="sxs-lookup"><span data-stu-id="f9577-118">The second command returns the same results, but without errors, because the simplified syntax does not attempt to return results for items for which the specified argument did not apply.</span></span>

<span data-ttu-id="f9577-119">この例では、 `Process` プロパティ `Description` がメンバー名パラメーターとしてコマンドに渡され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="f9577-119">In this example, the `Process` property `Description` is passed as the member name parameter to the `ForEach-Object` command.</span></span> <span data-ttu-id="f9577-120">結果として、アクティブなプロセスの説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9577-120">The results are descriptions of active processes.</span></span>

```powershell
Get-Process | foreach Description
```

<span data-ttu-id="f9577-121">この例では、 `DirectoryInfo` メソッド `GetFiles` はコマンドのメンバー名パラメーターとして渡され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="f9577-121">In this example, the `DirectoryInfo` method `GetFiles` is passed as the member name parameter of the `ForEach-Object` command.</span></span>  
<span data-ttu-id="f9577-122">メソッドは、検索パターンパラメーターを使用して呼び出され `.*` ます。</span><span class="sxs-lookup"><span data-stu-id="f9577-122">The method is called with the search pattern parameter `.*`.</span></span>  
<span data-ttu-id="f9577-123">結果は、 `FileInfo` ユーザーのホームディレクトリにあるすべての Unix スタイルの隠しファイルのレコードになります。</span><span class="sxs-lookup"><span data-stu-id="f9577-123">The results are `FileInfo` records for all Unix-style hidden files in user home directories.</span></span> 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a><span data-ttu-id="f9577-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="f9577-124">SEE ALSO</span></span>

- [<span data-ttu-id="f9577-125">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="f9577-125">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="f9577-126">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="f9577-126">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="f9577-127">Where-Object</span><span class="sxs-lookup"><span data-stu-id="f9577-127">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
- [<span data-ttu-id="f9577-128">Foreach-オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f9577-128">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)

