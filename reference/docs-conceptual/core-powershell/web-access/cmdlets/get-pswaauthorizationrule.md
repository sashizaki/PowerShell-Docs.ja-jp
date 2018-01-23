---
description: 
ms.topic: article
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: get pswaauthorizationrule
ms.technology: powershell
ms.openlocfilehash: 003195457660a18b9bbed065181b6d8c23835348
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="get-pswaauthorizationrule"></a><span data-ttu-id="84974-103">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="84974-103">Get-PswaAuthorizationRule</span></span>

## <a name="synopsis"></a><span data-ttu-id="84974-104">概要</span><span class="sxs-lookup"><span data-stu-id="84974-104">SYNOPSIS</span></span>

<span data-ttu-id="84974-105">Windows PowerShell® Web Access の承認規則のセットを返します。</span><span class="sxs-lookup"><span data-stu-id="84974-105">Returns a set of the Windows PowerShell® Web Access authorization rules.</span></span>

## <a name="syntax"></a><span data-ttu-id="84974-106">構文</span><span class="sxs-lookup"><span data-stu-id="84974-106">Syntax</span></span>

### <a name="id"></a><span data-ttu-id="84974-107">ID</span><span class="sxs-lookup"><span data-stu-id="84974-107">ID</span></span>
```
Get-PswaAuthorizationRule [[-Id] <Int32[]> ] [ <CommonParameters>]
```

### <a name="name"></a><span data-ttu-id="84974-108">名前</span><span class="sxs-lookup"><span data-stu-id="84974-108">Name</span></span>
```
Get-PswaAuthorizationRule [-RuleName] <String[]> [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="84974-109">説明</span><span class="sxs-lookup"><span data-stu-id="84974-109">DESCRIPTION</span></span>

<span data-ttu-id="84974-110">**Get-PswaAuthorizationRule** コマンドレットは、Windows PowerShell® Web Access 承認規則のセットを返します。</span><span class="sxs-lookup"><span data-stu-id="84974-110">The **Get-PswaAuthorizationRule** cmdlet returns a set of the Windows PowerShell® Web Access authorization rules.</span></span>
<span data-ttu-id="84974-111">**Id** パラメーターも **RuleName** パラメーターも指定されていない場合、コマンドレットによりすべての規則が列挙されます。</span><span class="sxs-lookup"><span data-stu-id="84974-111">If neither the **Id** parameter nor the **RuleName** parameter is specified, then this cmdlet lists all rules.</span></span> <span data-ttu-id="84974-112">**Id** パラメーターは、結果を絞り込むために使用できます。</span><span class="sxs-lookup"><span data-stu-id="84974-112">The **Id** parameter can be used to filter the results.</span></span>

## <a name="parameters"></a><span data-ttu-id="84974-113">パラメータ</span><span class="sxs-lookup"><span data-stu-id="84974-113">PARAMETERS</span></span>

### <a name="-idltint32gt"></a><span data-ttu-id="84974-114">-Id&lt;Int32\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="84974-114">-Id&lt;Int32\[\]&gt;</span></span>

<span data-ttu-id="84974-115">このコマンドレットで取得する規則の識別子 (ID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="84974-115">Specifies the identifiers (IDs) of the rules that this cmdlet should get.</span></span> <span data-ttu-id="84974-116">ID を指定しない場合、このコマンドレットによりすべての承認規則が返されます。</span><span class="sxs-lookup"><span data-stu-id="84974-116">If no IDs are specified, then this cmdlet returns all authorization rules.</span></span>

|||  
|-|-|
| <span data-ttu-id="84974-117">エイリアス</span><span class="sxs-lookup"><span data-stu-id="84974-117">Aliases</span></span>                              | <span data-ttu-id="84974-118">なし</span><span class="sxs-lookup"><span data-stu-id="84974-118">none</span></span>                                 |
| <span data-ttu-id="84974-119">必須?</span><span class="sxs-lookup"><span data-stu-id="84974-119">Required?</span></span>                            | <span data-ttu-id="84974-120">false</span><span class="sxs-lookup"><span data-stu-id="84974-120">false</span></span>                                |
| <span data-ttu-id="84974-121">位置は?</span><span class="sxs-lookup"><span data-stu-id="84974-121">Position?</span></span>                            | <span data-ttu-id="84974-122">2</span><span class="sxs-lookup"><span data-stu-id="84974-122">2</span></span>                                    |
| <span data-ttu-id="84974-123">既定値</span><span class="sxs-lookup"><span data-stu-id="84974-123">Default Value</span></span>                        | <span data-ttu-id="84974-124">なし</span><span class="sxs-lookup"><span data-stu-id="84974-124">none</span></span>                                 |
| <span data-ttu-id="84974-125">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="84974-125">Accept Pipeline Input?</span></span>               | <span data-ttu-id="84974-126">True (ByValue, ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="84974-126">True (ByValue, ByPropertyName)</span></span>       |
| <span data-ttu-id="84974-127">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="84974-127">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="84974-128">false</span><span class="sxs-lookup"><span data-stu-id="84974-128">false</span></span>                                |

### <a name="-rulenameltstringgt"></a><span data-ttu-id="84974-129">-RuleName&lt;String\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="84974-129">-RuleName&lt;String\[\]&gt;</span></span>

<span data-ttu-id="84974-130">取得する承認規則の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="84974-130">Specifies the names of authorization rules to retrieve.</span></span> <span data-ttu-id="84974-131">このパラメーターを指定すると、この配列内の文字列の規則名と正確に一致する規則が返されます。</span><span class="sxs-lookup"><span data-stu-id="84974-131">This parameter returns any rules that exactly match the rule names of the strings in this array.</span></span>

|||  
|-|-|
| <span data-ttu-id="84974-132">エイリアス</span><span class="sxs-lookup"><span data-stu-id="84974-132">Aliases</span></span>                              | <span data-ttu-id="84974-133">なし</span><span class="sxs-lookup"><span data-stu-id="84974-133">none</span></span>                                 |
| <span data-ttu-id="84974-134">必須?</span><span class="sxs-lookup"><span data-stu-id="84974-134">Required?</span></span>                            | <span data-ttu-id="84974-135">true</span><span class="sxs-lookup"><span data-stu-id="84974-135">true</span></span>                                 |
| <span data-ttu-id="84974-136">位置は?</span><span class="sxs-lookup"><span data-stu-id="84974-136">Position?</span></span>                            | <span data-ttu-id="84974-137">2</span><span class="sxs-lookup"><span data-stu-id="84974-137">2</span></span>                                    |
| <span data-ttu-id="84974-138">既定値</span><span class="sxs-lookup"><span data-stu-id="84974-138">Default Value</span></span>                        | <span data-ttu-id="84974-139">なし</span><span class="sxs-lookup"><span data-stu-id="84974-139">none</span></span>                                 |
| <span data-ttu-id="84974-140">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="84974-140">Accept Pipeline Input?</span></span>               | <span data-ttu-id="84974-141">True (ByValue, ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="84974-141">True (ByValue, ByPropertyName)</span></span>       |
| <span data-ttu-id="84974-142">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="84974-142">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="84974-143">false</span><span class="sxs-lookup"><span data-stu-id="84974-143">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="84974-144">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="84974-144">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="84974-145">このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="84974-145">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="84974-146">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84974-146">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="84974-147">入力</span><span class="sxs-lookup"><span data-stu-id="84974-147">INPUTS</span></span>

### <a name="int"></a><span data-ttu-id="84974-148">int\[\]</span><span class="sxs-lookup"><span data-stu-id="84974-148">int\[\]</span></span>

<span data-ttu-id="84974-149">このコマンドレットは、入力として整数の配列または文字列値の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="84974-149">This cmdlet accepts an array of integers or an array of string values as input.</span></span>

### <a name="string"></a><span data-ttu-id="84974-150">String\[\]</span><span class="sxs-lookup"><span data-stu-id="84974-150">String\[\]</span></span>

<span data-ttu-id="84974-151">このコマンドレットは、入力として整数の配列または文字列値の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="84974-151">This cmdlet accepts an array of integers or an array of string values as input.</span></span>

## <a name="outputs"></a><span data-ttu-id="84974-152">出力</span><span class="sxs-lookup"><span data-stu-id="84974-152">OUTPUTS</span></span>

### <a name="microsoftmanagementpowershellwebaccesspswaauthorizationrule"></a><span data-ttu-id="84974-153">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]</span><span class="sxs-lookup"><span data-stu-id="84974-153">Microsoft.Management.PowerShellWebAccess.PswaAuthorizationRule\[\]</span></span>

<span data-ttu-id="84974-154">このコマンドレットは、出力として PswaAuthorizationRule オブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="84974-154">This cmdlet produces a PswaAuthorizationRule object as output.</span></span>


## <a name="examples"></a><span data-ttu-id="84974-155">例</span><span class="sxs-lookup"><span data-stu-id="84974-155">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="84974-156">例 1</span><span class="sxs-lookup"><span data-stu-id="84974-156">EXAMPLE 1</span></span>

<span data-ttu-id="84974-157">この例では、すべての規則を取得します。</span><span class="sxs-lookup"><span data-stu-id="84974-157">This example gets all of the rules.</span></span>

```PowerShell
    PS C:\> Get-PswaAuthorizationRule
```

### <a name="example-2"></a><span data-ttu-id="84974-158">例 2</span><span class="sxs-lookup"><span data-stu-id="84974-158">EXAMPLE 2</span></span>

<span data-ttu-id="84974-159">この例では、ID が *2* の規則を取得します。</span><span class="sxs-lookup"><span data-stu-id="84974-159">This example gets a rule with an ID of *2*.</span></span>

```PowerShell
    PS C:\> Get-PswaAuthorizationRule –Id 2
```

### <a name="example-3-example-3-subheading"></a><span data-ttu-id="84974-160">例 3 {#example-3 .subHeading}</span><span class="sxs-lookup"><span data-stu-id="84974-160">EXAMPLE 3 {#example-3 .subHeading}</span></span>

<span data-ttu-id="84974-161">この例は、コマンドレットでパイプラインの値を受け入れる方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="84974-161">This example illustrates how the cmdlet accepts a value from pipeline.</span></span>
<span data-ttu-id="84974-162">規則の ID と規則の名前がこのコマンドレットで渡されます。</span><span class="sxs-lookup"><span data-stu-id="84974-162">A rule id and a rule name are passed in this cmdlet.</span></span>

```PowerShell
    PS C:\> "rule1",0 | Get-PswaAuthorizationRule
```

## <a name="related-topics"></a><span data-ttu-id="84974-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="84974-163">Related topics</span></span>

- [<span data-ttu-id="84974-164">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="84974-164">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="84974-165">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="84974-165">Remove-PswaAuthorizationRule</span></span>](remove-pswaauthorizationrule.md)
- [<span data-ttu-id="84974-166">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="84974-166">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)
- [<span data-ttu-id="84974-167">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="84974-167">Install-PswaWebApplication</span></span>](install-pswawebapplication.md)
