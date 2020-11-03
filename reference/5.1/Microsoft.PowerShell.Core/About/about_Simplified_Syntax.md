---
description: オブジェクトのコレクションに対するスクリプトフィルターの、より簡単で自然言語の方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_simplified_syntax?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Simplified_Syntax
ms.openlocfilehash: ffa499fd618d0d31dec470b0c35c902eba26eb0a
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223243"
---
# <a name="about_simplified_syntax"></a><span data-ttu-id="d1233-104">about_Simplified_Syntax</span><span class="sxs-lookup"><span data-stu-id="d1233-104">about_Simplified_Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="d1233-105">概要</span><span class="sxs-lookup"><span data-stu-id="d1233-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="d1233-106">オブジェクトのコレクションに対するスクリプトフィルターの、より簡単で自然言語の方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d1233-106">Describes easier, more natural-language ways of scripting filters for collections of objects.</span></span>

## <a name="long-description"></a><span data-ttu-id="d1233-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="d1233-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="d1233-108">Windows PowerShell 3.0 で導入された簡略化された構文を使用すると、スクリプトブロックを使用せずにいくつかのフィルターコマンドを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d1233-108">Simplified syntax, introduced in Windows PowerShell 3.0, lets you build some filter commands without using script blocks.</span></span> <span data-ttu-id="d1233-109">簡略化された構文は自然言語に似ています。これは主に、コマンドと、 `Where-Object` `ForEach-Object` それに対応するエイリアスおよびにパイプされるオブジェクトのコレクションに役立ち `where` `foreach` ます。</span><span class="sxs-lookup"><span data-stu-id="d1233-109">The simplified syntax more closely resembles natural language, and is primarily useful with collections of objects that get piped into commands `Where-Object` and `ForEach-Object` and their corresponding aliases `where` and `foreach`.</span></span>

<span data-ttu-id="d1233-110">スクリプトブロック内の自動変数を参照せずに、コレクションのメンバー (通常は配列) に対してメソッドを使用でき `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="d1233-110">You can use a method on the members of a collection (most commonly, an array) without referring to the automatic variable `$_` inside a script block.</span></span>

<span data-ttu-id="d1233-111">次の2つの呼び出しについて考えてみます。</span><span class="sxs-lookup"><span data-stu-id="d1233-111">Consider the following two invocations:</span></span>

### <a name="standard-syntax"></a><span data-ttu-id="d1233-112">標準構文</span><span class="sxs-lookup"><span data-stu-id="d1233-112">Standard Syntax</span></span>

```powershell
dir Cert:\LocalMachine\Root | where { $_.FriendlyName -eq 'Verisign' }
dir Cert:\ -Recurse | foreach { $_.GetKeyAlgorithm() }
```

### <a name="simplified-syntax"></a><span data-ttu-id="d1233-113">簡略化された構文</span><span class="sxs-lookup"><span data-stu-id="d1233-113">Simplified syntax</span></span>

<span data-ttu-id="d1233-114">簡略化された構文では、コレクション内のオブジェクトのメンバーに対して機能する比較演算子は、パラメーターとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="d1233-114">Under the simplified syntax, comparison operators that work on members of objects in a collection are treated as parameters.</span></span> <span data-ttu-id="d1233-115">スクリプトブロック内の自動変数を参照せずに、コレクション内のオブジェクトに対してメソッドを呼び出すことができ `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="d1233-115">You can invoke a method on objects in a collection without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="d1233-116">次の2つの呼び出しを、前の例の呼び出しと比較します。</span><span class="sxs-lookup"><span data-stu-id="d1233-116">Compare the following two invocations to those of the previous example:</span></span>

```powershell
dir Cert:\LocalMachine\Root | where FriendlyName -eq 'Verisign'
dir Cert:\ -Recurse | foreach GetKeyAlgorithm
```

<span data-ttu-id="d1233-117">どちらの構文も機能しますが、簡略化された構文は、スクリプトブロック内の自動変数を参照せずに結果を返し `$_` ます。</span><span class="sxs-lookup"><span data-stu-id="d1233-117">While both syntaxes work, the simplified syntax returns results without referring to the automatic variable `$_` inside a script block.</span></span>
<span data-ttu-id="d1233-118">メソッド名 `GetKeyAlgorithm` は、のパラメーターとして扱われ `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d1233-118">The method name `GetKeyAlgorithm` is treated as a parameter of `ForEach-Object`.</span></span>
<span data-ttu-id="d1233-119">2番目のコマンドは、指定された引数が適用されなかった項目の結果を返さないようにするため、エラーが発生することなく、同じ結果を返します。</span><span class="sxs-lookup"><span data-stu-id="d1233-119">The second command returns the same results, but without errors, because the simplified syntax does not attempt to return results for items for which the specified argument did not apply.</span></span>

<span data-ttu-id="d1233-120">この例では、 `Process` プロパティ `Description` がメンバー名パラメーターとしてコマンドに渡され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d1233-120">In this example, the `Process` property `Description` is passed as the member name parameter to the `ForEach-Object` command.</span></span> <span data-ttu-id="d1233-121">結果として、アクティブなプロセスの説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d1233-121">The results are descriptions of active processes.</span></span>

```powershell
Get-Process | foreach Description
```

<span data-ttu-id="d1233-122">この例では、 `DirectoryInfo` メソッド `GetFiles` はコマンドのメンバー名パラメーターとして渡され `ForEach-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="d1233-122">In this example, the `DirectoryInfo` method `GetFiles` is passed as the member name parameter of the `ForEach-Object` command.</span></span>  
<span data-ttu-id="d1233-123">メソッドは、検索パターンパラメーターを使用して呼び出され `.*` ます。</span><span class="sxs-lookup"><span data-stu-id="d1233-123">The method is called with the search pattern parameter `.*`.</span></span>  
<span data-ttu-id="d1233-124">結果は、 `FileInfo` ユーザーのホームディレクトリにあるすべての Unix スタイルの隠しファイルのレコードになります。</span><span class="sxs-lookup"><span data-stu-id="d1233-124">The results are `FileInfo` records for all Unix-style hidden files in user home directories.</span></span> 

```powershell
Get-ChildItem /home -Directory | foreach GetFiles .*
```

## <a name="see-also"></a><span data-ttu-id="d1233-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="d1233-125">SEE ALSO</span></span>

- [<span data-ttu-id="d1233-126">about_Comparison_Operators</span><span class="sxs-lookup"><span data-stu-id="d1233-126">about_Comparison_Operators</span></span>](about_Comparison_Operators.md)
- [<span data-ttu-id="d1233-127">about_Foreach</span><span class="sxs-lookup"><span data-stu-id="d1233-127">about_Foreach</span></span>](about_Foreach.md)
- [<span data-ttu-id="d1233-128">Where-Object</span><span class="sxs-lookup"><span data-stu-id="d1233-128">Where-Object</span></span>](xref:Microsoft.PowerShell.Core.Where-Object)
- [<span data-ttu-id="d1233-129">Foreach-オブジェクト</span><span class="sxs-lookup"><span data-stu-id="d1233-129">Foreach-Object</span></span>](xref:Microsoft.PowerShell.Core.ForEach-Object)
