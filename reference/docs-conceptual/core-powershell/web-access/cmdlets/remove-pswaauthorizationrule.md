---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: remove pswaauthorizationrule
ms.technology: powershell
ms.openlocfilehash: a8304b68a446de0be98aa732304c71302fb8389e
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="remove-pswaauthorizationrule"></a><span data-ttu-id="21099-103">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="21099-103">Remove-PswaAuthorizationRule</span></span>

## <a name="synopsis"></a><span data-ttu-id="21099-104">概要</span><span class="sxs-lookup"><span data-stu-id="21099-104">SYNOPSIS</span></span>

<span data-ttu-id="21099-105">指定された承認規則を Windows PowerShell® Web Access から削除します。</span><span class="sxs-lookup"><span data-stu-id="21099-105">Removes a specified authorization rule from Windows PowerShell® Web Access.</span></span>

## <a name="syntax"></a><span data-ttu-id="21099-106">構文</span><span class="sxs-lookup"><span data-stu-id="21099-106">SYNTAX</span></span>

### <a name="id"></a><span data-ttu-id="21099-107">Id</span><span class="sxs-lookup"><span data-stu-id="21099-107">Id</span></span>
```
Remove-PswaAuthorizationRule [-Id] <Int32[]> [-Force] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

### <a name="rule"></a><span data-ttu-id="21099-108">ルール</span><span class="sxs-lookup"><span data-stu-id="21099-108">Rule</span></span>
```
Remove-PswaAuthorizationRule [-Rule] <PswaAuthorizationRule[]> [-Force] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="21099-109">説明</span><span class="sxs-lookup"><span data-stu-id="21099-109">DESCRIPTION</span></span>

<span data-ttu-id="21099-110">指定された承認規則を Windows PowerShell Web Access から削除します。</span><span class="sxs-lookup"><span data-stu-id="21099-110">Removes a specified authorization rule from Windows PowerShell Web Access.</span></span>

## <a name="parameters"></a><span data-ttu-id="21099-111">パラメータ</span><span class="sxs-lookup"><span data-stu-id="21099-111">PARAMETERS</span></span>

### <a name="-force"></a><span data-ttu-id="21099-112">-Force</span><span class="sxs-lookup"><span data-stu-id="21099-112">-Force</span></span>

<span data-ttu-id="21099-113">ユーザーの確認を求めずにコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="21099-113">Runs the cmdlet without prompting for confirmation.</span></span> <span data-ttu-id="21099-114">既定では、コマンドレットにより続行前に確認が求められます。</span><span class="sxs-lookup"><span data-stu-id="21099-114">By default the cmdlet asks for confirmation before proceeding.</span></span>

|||  
|-|-|
| <span data-ttu-id="21099-115">エイリアス</span><span class="sxs-lookup"><span data-stu-id="21099-115">Aliases</span></span>                              | <span data-ttu-id="21099-116">なし</span><span class="sxs-lookup"><span data-stu-id="21099-116">none</span></span>                                 |
| <span data-ttu-id="21099-117">必須?</span><span class="sxs-lookup"><span data-stu-id="21099-117">Required?</span></span>                            | <span data-ttu-id="21099-118">false</span><span class="sxs-lookup"><span data-stu-id="21099-118">false</span></span>                                |
| <span data-ttu-id="21099-119">位置は?</span><span class="sxs-lookup"><span data-stu-id="21099-119">Position?</span></span>                            | <span data-ttu-id="21099-120">名前付き</span><span class="sxs-lookup"><span data-stu-id="21099-120">named</span></span>                                |
| <span data-ttu-id="21099-121">既定値</span><span class="sxs-lookup"><span data-stu-id="21099-121">Default Value</span></span>                        | <span data-ttu-id="21099-122">なし</span><span class="sxs-lookup"><span data-stu-id="21099-122">none</span></span>                                 |
| <span data-ttu-id="21099-123">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-123">Accept Pipeline Input?</span></span>               | <span data-ttu-id="21099-124">false</span><span class="sxs-lookup"><span data-stu-id="21099-124">false</span></span>                                |
| <span data-ttu-id="21099-125">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-125">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="21099-126">false</span><span class="sxs-lookup"><span data-stu-id="21099-126">false</span></span>                                |

### <a name="-id-ltint32gt"></a><span data-ttu-id="21099-127">-Id &lt;Int32\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="21099-127">-Id &lt;Int32\[\]&gt;</span></span>

<span data-ttu-id="21099-128">削除する 1 つまたは複数の規則の識別子 (ID) を指定します。</span><span class="sxs-lookup"><span data-stu-id="21099-128">Specifies the identifiers (IDs) of one or more rules to remove.</span></span>

|||  
|-|-|
| <span data-ttu-id="21099-129">エイリアス</span><span class="sxs-lookup"><span data-stu-id="21099-129">Aliases</span></span>                              | <span data-ttu-id="21099-130">なし</span><span class="sxs-lookup"><span data-stu-id="21099-130">none</span></span>                                 |
| <span data-ttu-id="21099-131">必須?</span><span class="sxs-lookup"><span data-stu-id="21099-131">Required?</span></span>                            | <span data-ttu-id="21099-132">true</span><span class="sxs-lookup"><span data-stu-id="21099-132">true</span></span>                                 |
| <span data-ttu-id="21099-133">位置は?</span><span class="sxs-lookup"><span data-stu-id="21099-133">Position?</span></span>                            | <span data-ttu-id="21099-134">2</span><span class="sxs-lookup"><span data-stu-id="21099-134">2</span></span>                                    |
| <span data-ttu-id="21099-135">既定値</span><span class="sxs-lookup"><span data-stu-id="21099-135">Default Value</span></span>                        | <span data-ttu-id="21099-136">なし</span><span class="sxs-lookup"><span data-stu-id="21099-136">none</span></span>                                 |
| <span data-ttu-id="21099-137">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-137">Accept Pipeline Input?</span></span>               | <span data-ttu-id="21099-138">True (ByValue, ByPropertyName)</span><span class="sxs-lookup"><span data-stu-id="21099-138">True (ByValue, ByPropertyName)</span></span>       |
| <span data-ttu-id="21099-139">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-139">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="21099-140">false</span><span class="sxs-lookup"><span data-stu-id="21099-140">false</span></span>                                |

### <a name="-rule-ltpswaauthorizationrulegt"></a><span data-ttu-id="21099-141">-Rule &lt;PswaAuthorizationRule\[\]&gt;</span><span class="sxs-lookup"><span data-stu-id="21099-141">-Rule &lt;PswaAuthorizationRule\[\]&gt;</span></span>

<span data-ttu-id="21099-142">削除する規則を指定します。</span><span class="sxs-lookup"><span data-stu-id="21099-142">Specifies the rules to remove.</span></span>

|||  
|-|-|
| <span data-ttu-id="21099-143">エイリアス</span><span class="sxs-lookup"><span data-stu-id="21099-143">Aliases</span></span>                              | <span data-ttu-id="21099-144">なし</span><span class="sxs-lookup"><span data-stu-id="21099-144">none</span></span>                                 |
| <span data-ttu-id="21099-145">必須?</span><span class="sxs-lookup"><span data-stu-id="21099-145">Required?</span></span>                            | <span data-ttu-id="21099-146">true</span><span class="sxs-lookup"><span data-stu-id="21099-146">true</span></span>                                 |
| <span data-ttu-id="21099-147">位置は?</span><span class="sxs-lookup"><span data-stu-id="21099-147">Position?</span></span>                            | <span data-ttu-id="21099-148">2</span><span class="sxs-lookup"><span data-stu-id="21099-148">2</span></span>                                    |
| <span data-ttu-id="21099-149">既定値</span><span class="sxs-lookup"><span data-stu-id="21099-149">Default Value</span></span>                        | <span data-ttu-id="21099-150">なし</span><span class="sxs-lookup"><span data-stu-id="21099-150">none</span></span>                                 |
| <span data-ttu-id="21099-151">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-151">Accept Pipeline Input?</span></span>               | <span data-ttu-id="21099-152">True (ByValue)</span><span class="sxs-lookup"><span data-stu-id="21099-152">True (ByValue)</span></span>                       |
| <span data-ttu-id="21099-153">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-153">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="21099-154">false</span><span class="sxs-lookup"><span data-stu-id="21099-154">false</span></span>                                |

### <a name="-confirm"></a><span data-ttu-id="21099-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="21099-155">-Confirm</span></span>

<span data-ttu-id="21099-156">コマンドレットを実行する前に、ユーザーに確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="21099-156">Prompts you for confirmation before running the cmdlet.</span></span>

|||  
|-|-|
| <span data-ttu-id="21099-157">必須?</span><span class="sxs-lookup"><span data-stu-id="21099-157">Required?</span></span>                            | <span data-ttu-id="21099-158">false</span><span class="sxs-lookup"><span data-stu-id="21099-158">false</span></span>                                |
| <span data-ttu-id="21099-159">位置は?</span><span class="sxs-lookup"><span data-stu-id="21099-159">Position?</span></span>                            | <span data-ttu-id="21099-160">名前付き</span><span class="sxs-lookup"><span data-stu-id="21099-160">named</span></span>                                |
| <span data-ttu-id="21099-161">既定値</span><span class="sxs-lookup"><span data-stu-id="21099-161">Default Value</span></span>                        | <span data-ttu-id="21099-162">false</span><span class="sxs-lookup"><span data-stu-id="21099-162">false</span></span>                                |
| <span data-ttu-id="21099-163">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-163">Accept Pipeline Input?</span></span>               | <span data-ttu-id="21099-164">false</span><span class="sxs-lookup"><span data-stu-id="21099-164">false</span></span>                                |
| <span data-ttu-id="21099-165">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-165">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="21099-166">false</span><span class="sxs-lookup"><span data-stu-id="21099-166">false</span></span>                                |

### <a name="-whatif"></a><span data-ttu-id="21099-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="21099-167">-WhatIf</span></span>

<span data-ttu-id="21099-168">コマンドレットを実行するとどのような結果になるかを表示します。</span><span class="sxs-lookup"><span data-stu-id="21099-168">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="21099-169">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="21099-169">The cmdlet is not run.</span></span>

|||  
|-|-|
| <span data-ttu-id="21099-170">必須?</span><span class="sxs-lookup"><span data-stu-id="21099-170">Required?</span></span>                            | <span data-ttu-id="21099-171">false</span><span class="sxs-lookup"><span data-stu-id="21099-171">false</span></span>                                |
| <span data-ttu-id="21099-172">位置は?</span><span class="sxs-lookup"><span data-stu-id="21099-172">Position?</span></span>                            | <span data-ttu-id="21099-173">名前付き</span><span class="sxs-lookup"><span data-stu-id="21099-173">named</span></span>                                |
| <span data-ttu-id="21099-174">既定値</span><span class="sxs-lookup"><span data-stu-id="21099-174">Default Value</span></span>                        | <span data-ttu-id="21099-175">false</span><span class="sxs-lookup"><span data-stu-id="21099-175">false</span></span>                                |
| <span data-ttu-id="21099-176">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-176">Accept Pipeline Input?</span></span>               | <span data-ttu-id="21099-177">false</span><span class="sxs-lookup"><span data-stu-id="21099-177">false</span></span>                                |
| <span data-ttu-id="21099-178">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="21099-178">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="21099-179">false</span><span class="sxs-lookup"><span data-stu-id="21099-179">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="21099-180">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="21099-180">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="21099-181">このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="21099-181">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="21099-182">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="21099-182">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="21099-183">入力</span><span class="sxs-lookup"><span data-stu-id="21099-183">INPUTS</span></span>

### <a name="int"></a><span data-ttu-id="21099-184">int\[\]</span><span class="sxs-lookup"><span data-stu-id="21099-184">int\[\]</span></span>

<span data-ttu-id="21099-185">このコマンドレットは、整数の配列、または PswaAuthorizationRule オブジェクトの配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="21099-185">This cmdlet accepts either an array of integers or an array of PswaAuthorizationRule objects.</span></span>

### <a name="pswaauthorizationrule"></a><span data-ttu-id="21099-186">PswaAuthorizationRule\[\]</span><span class="sxs-lookup"><span data-stu-id="21099-186">PswaAuthorizationRule\[\]</span></span>

<span data-ttu-id="21099-187">このコマンドレットは、整数の配列、または PswaAuthorizationRule オブジェクトの配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="21099-187">This cmdlet accepts either an array of integers or an array of PswaAuthorizationRule objects.</span></span>

## <a name="outputs"></a><span data-ttu-id="21099-188">出力</span><span class="sxs-lookup"><span data-stu-id="21099-188">OUTPUTS</span></span>

<span data-ttu-id="21099-189">このコマンドレットから出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="21099-189">This cmdlet produces no output.</span></span>

## <a name="examples"></a><span data-ttu-id="21099-190">例</span><span class="sxs-lookup"><span data-stu-id="21099-190">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="21099-191">例 1</span><span class="sxs-lookup"><span data-stu-id="21099-191">EXAMPLE 1</span></span>

<span data-ttu-id="21099-192">この例では、ID が *2* の承認規則が削除されます。</span><span class="sxs-lookup"><span data-stu-id="21099-192">This example removes the authorization rule with an ID of *2*.</span></span>

```
Remove-PswaAuthorizationRule –Id 2
```

### <a name="example-2-example-2-subheading"></a><span data-ttu-id="21099-193">例 2 {#example-2 .subHeading}</span><span class="sxs-lookup"><span data-stu-id="21099-193">EXAMPLE 2 {#example-2 .subHeading}</span></span>

<span data-ttu-id="21099-194">この例では、すべての承認規則が削除されます。また、ユーザーの確認が必要です。</span><span class="sxs-lookup"><span data-stu-id="21099-194">This example removes all authorization rules and also requires confirmation by the user.</span></span>

```
Get-PswaAuthorizationRule | Remove-PswaAuthorizationRule -Confirm
```

## <a name="related-topics"></a><span data-ttu-id="21099-195">関連トピック</span><span class="sxs-lookup"><span data-stu-id="21099-195">Related topics</span></span>

- [<span data-ttu-id="21099-196">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="21099-196">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="21099-197">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="21099-197">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)
- [<span data-ttu-id="21099-198">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="21099-198">Install-PswaWebApplication</span></span>](install-pswawebapplication.md)
- [<span data-ttu-id="21099-199">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="21099-199">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)
