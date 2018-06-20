---
ms.topic: reference
keywords: PowerShell, コマンドレット
ms.date: 12/12/2016
title: Uninstall-PswaWebApplication
ms.openlocfilehash: b2a3e4d584fd04ee49e1e6408dba39fd8bc555dc
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
ms.locfileid: "34221920"
---
# <a name="uninstall-pswawebapplication"></a><span data-ttu-id="33030-103">Uninstall-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="33030-103">Uninstall-PswaWebApplication</span></span>

## <a name="synopsis"></a><span data-ttu-id="33030-104">概要</span><span class="sxs-lookup"><span data-stu-id="33030-104">SYNOPSIS</span></span>

<span data-ttu-id="33030-105">Windows PowerShell® Web アプリケーションをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="33030-105">Uninstalls the Windows PowerShell® web application.</span></span>

## <a name="syntax"></a><span data-ttu-id="33030-106">構文</span><span class="sxs-lookup"><span data-stu-id="33030-106">SYNTAX</span></span>

### <a name="default"></a><span data-ttu-id="33030-107">既定</span><span class="sxs-lookup"><span data-stu-id="33030-107">Default</span></span>
```
Uninstall-PswaWebApplication [[-WebApplicationName] <String> ] [-DeleteTestCertificate] [-WebSiteName <String> ] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="33030-108">説明</span><span class="sxs-lookup"><span data-stu-id="33030-108">DESCRIPTION</span></span>

<span data-ttu-id="33030-109">**Uninstall-PswaWebApplication** コマンドレットは、Windows PowerShell Web アプリケーションをアンインストールし、IIS から Web サイトを削除します。</span><span class="sxs-lookup"><span data-stu-id="33030-109">The **Uninstall-PswaWebApplication** cmdlet uninstalls the Windows PowerShell web application and removes the website from IIS.</span></span> <span data-ttu-id="33030-110">このコマンドレットでは、Windows PowerShell の実行に必要なため、IIS やインストールされている他の機能はアンインストールされません。</span><span class="sxs-lookup"><span data-stu-id="33030-110">The cmdlet does not uninstall IIS, or any other features installed because they were required for Windows PowerShell to run.</span></span>

## <a name="parameters"></a><span data-ttu-id="33030-111">パラメータ</span><span class="sxs-lookup"><span data-stu-id="33030-111">PARAMETERS</span></span>

### <a name="-deletetestcertificate"></a><span data-ttu-id="33030-112">-DeleteTestCertificate</span><span class="sxs-lookup"><span data-stu-id="33030-112">-DeleteTestCertificate</span></span>

<span data-ttu-id="33030-113">**Install\_PswaWebApplication** コマンドレット (**UseTestCertificate** パラメーターを指定) で作成されたテスト証明書の削除を指定します。</span><span class="sxs-lookup"><span data-stu-id="33030-113">Indicates that the test certificates created by the **Install\_PswaWebApplication** cmdlet (with the **UseTestCertificate** parameter) is deleted.</span></span>
<span data-ttu-id="33030-114">**Install-PswaWebApplication** コマンドレットで作成されたテスト証明書と同じ名前のテスト証明書のみが削除されます。</span><span class="sxs-lookup"><span data-stu-id="33030-114">Only the test certificate with the same name as the one created by the **Install-PswaWebApplication** cmdlet is removed.</span></span>

|||
|-|-|
| <span data-ttu-id="33030-115">エイリアス</span><span class="sxs-lookup"><span data-stu-id="33030-115">Aliases</span></span>                              | <span data-ttu-id="33030-116">なし</span><span class="sxs-lookup"><span data-stu-id="33030-116">none</span></span>                                 |
| <span data-ttu-id="33030-117">必須?</span><span class="sxs-lookup"><span data-stu-id="33030-117">Required?</span></span>                            | <span data-ttu-id="33030-118">false</span><span class="sxs-lookup"><span data-stu-id="33030-118">false</span></span>                                |
| <span data-ttu-id="33030-119">位置は?</span><span class="sxs-lookup"><span data-stu-id="33030-119">Position?</span></span>                            | <span data-ttu-id="33030-120">名前付き</span><span class="sxs-lookup"><span data-stu-id="33030-120">named</span></span>                                |
| <span data-ttu-id="33030-121">既定値</span><span class="sxs-lookup"><span data-stu-id="33030-121">Default Value</span></span>                        | <span data-ttu-id="33030-122">true</span><span class="sxs-lookup"><span data-stu-id="33030-122">true</span></span>                                 |
| <span data-ttu-id="33030-123">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-123">Accept Pipeline Input?</span></span>               | <span data-ttu-id="33030-124">false</span><span class="sxs-lookup"><span data-stu-id="33030-124">false</span></span>                                |
| <span data-ttu-id="33030-125">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-125">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="33030-126">false</span><span class="sxs-lookup"><span data-stu-id="33030-126">false</span></span>                                |

### <a name="-webapplicationname-ltstringgt"></a><span data-ttu-id="33030-127">-WebApplicationName &lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="33030-127">-WebApplicationName &lt;String&gt;</span></span>

<span data-ttu-id="33030-128">アンインストールする Web アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="33030-128">Specifies the name of the web application to uninstall.</span></span>

|||
|-|-|
| <span data-ttu-id="33030-129">エイリアス</span><span class="sxs-lookup"><span data-stu-id="33030-129">Aliases</span></span>                              | <span data-ttu-id="33030-130">なし</span><span class="sxs-lookup"><span data-stu-id="33030-130">none</span></span>                                 |
| <span data-ttu-id="33030-131">必須?</span><span class="sxs-lookup"><span data-stu-id="33030-131">Required?</span></span>                            | <span data-ttu-id="33030-132">false</span><span class="sxs-lookup"><span data-stu-id="33030-132">false</span></span>                                |
| <span data-ttu-id="33030-133">位置は?</span><span class="sxs-lookup"><span data-stu-id="33030-133">Position?</span></span>                            | <span data-ttu-id="33030-134">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="33030-134">1</span></span>                                    |
| <span data-ttu-id="33030-135">既定値</span><span class="sxs-lookup"><span data-stu-id="33030-135">Default Value</span></span>                        | <span data-ttu-id="33030-136">pswa</span><span class="sxs-lookup"><span data-stu-id="33030-136">pswa</span></span>                                 |
| <span data-ttu-id="33030-137">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-137">Accept Pipeline Input?</span></span>               | <span data-ttu-id="33030-138">false</span><span class="sxs-lookup"><span data-stu-id="33030-138">false</span></span>                                |
| <span data-ttu-id="33030-139">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-139">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="33030-140">false</span><span class="sxs-lookup"><span data-stu-id="33030-140">false</span></span>                                |

### <a name="-websitename-ltstringgt"></a><span data-ttu-id="33030-141">-WebSiteName &lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="33030-141">-WebSiteName &lt;String&gt;</span></span>

<span data-ttu-id="33030-142">Web アプリケーションがインストールされている Web サイトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="33030-142">Specifies the name of the web site where the web application is installed.</span></span>

|||
|-|-|
| <span data-ttu-id="33030-143">エイリアス</span><span class="sxs-lookup"><span data-stu-id="33030-143">Aliases</span></span>                              | <span data-ttu-id="33030-144">なし</span><span class="sxs-lookup"><span data-stu-id="33030-144">none</span></span>                                 |
| <span data-ttu-id="33030-145">必須?</span><span class="sxs-lookup"><span data-stu-id="33030-145">Required?</span></span>                            | <span data-ttu-id="33030-146">false</span><span class="sxs-lookup"><span data-stu-id="33030-146">false</span></span>                                |
| <span data-ttu-id="33030-147">位置は?</span><span class="sxs-lookup"><span data-stu-id="33030-147">Position?</span></span>                            | <span data-ttu-id="33030-148">名前付き</span><span class="sxs-lookup"><span data-stu-id="33030-148">named</span></span>                                |
| <span data-ttu-id="33030-149">既定値</span><span class="sxs-lookup"><span data-stu-id="33030-149">Default Value</span></span>                        | <span data-ttu-id="33030-150">Default Web Site</span><span class="sxs-lookup"><span data-stu-id="33030-150">Default Web Site</span></span>                     |
| <span data-ttu-id="33030-151">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-151">Accept Pipeline Input?</span></span>               | <span data-ttu-id="33030-152">false</span><span class="sxs-lookup"><span data-stu-id="33030-152">false</span></span>                                |
| <span data-ttu-id="33030-153">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-153">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="33030-154">false</span><span class="sxs-lookup"><span data-stu-id="33030-154">false</span></span>                                |

### <a name="-confirm"></a><span data-ttu-id="33030-155">-Confirm</span><span class="sxs-lookup"><span data-stu-id="33030-155">-Confirm</span></span>

<span data-ttu-id="33030-156">コマンドレットを実行する前に、ユーザーに確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="33030-156">Prompts you for confirmation before running the cmdlet.</span></span>

|||
|-|-|
| <span data-ttu-id="33030-157">必須?</span><span class="sxs-lookup"><span data-stu-id="33030-157">Required?</span></span>                            | <span data-ttu-id="33030-158">false</span><span class="sxs-lookup"><span data-stu-id="33030-158">false</span></span>                                |
| <span data-ttu-id="33030-159">位置は?</span><span class="sxs-lookup"><span data-stu-id="33030-159">Position?</span></span>                            | <span data-ttu-id="33030-160">名前付き</span><span class="sxs-lookup"><span data-stu-id="33030-160">named</span></span>                                |
| <span data-ttu-id="33030-161">既定値</span><span class="sxs-lookup"><span data-stu-id="33030-161">Default Value</span></span>                        | <span data-ttu-id="33030-162">false</span><span class="sxs-lookup"><span data-stu-id="33030-162">false</span></span>                                |
| <span data-ttu-id="33030-163">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-163">Accept Pipeline Input?</span></span>               | <span data-ttu-id="33030-164">false</span><span class="sxs-lookup"><span data-stu-id="33030-164">false</span></span>                                |
| <span data-ttu-id="33030-165">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-165">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="33030-166">false</span><span class="sxs-lookup"><span data-stu-id="33030-166">false</span></span>                                |

### <a name="-whatif"></a><span data-ttu-id="33030-167">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="33030-167">-WhatIf</span></span>

<span data-ttu-id="33030-168">コマンドレットを実行するとどのような結果になるかを表示します。</span><span class="sxs-lookup"><span data-stu-id="33030-168">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="33030-169">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="33030-169">The cmdlet is not run.</span></span>

|||
|-|-|
| <span data-ttu-id="33030-170">必須?</span><span class="sxs-lookup"><span data-stu-id="33030-170">Required?</span></span>                            | <span data-ttu-id="33030-171">false</span><span class="sxs-lookup"><span data-stu-id="33030-171">false</span></span>                                |
| <span data-ttu-id="33030-172">位置は?</span><span class="sxs-lookup"><span data-stu-id="33030-172">Position?</span></span>                            | <span data-ttu-id="33030-173">名前付き</span><span class="sxs-lookup"><span data-stu-id="33030-173">named</span></span>                                |
| <span data-ttu-id="33030-174">既定値</span><span class="sxs-lookup"><span data-stu-id="33030-174">Default Value</span></span>                        | <span data-ttu-id="33030-175">false</span><span class="sxs-lookup"><span data-stu-id="33030-175">false</span></span>                                |
| <span data-ttu-id="33030-176">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-176">Accept Pipeline Input?</span></span>               | <span data-ttu-id="33030-177">false</span><span class="sxs-lookup"><span data-stu-id="33030-177">false</span></span>                                |
| <span data-ttu-id="33030-178">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="33030-178">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="33030-179">false</span><span class="sxs-lookup"><span data-stu-id="33030-179">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="33030-180">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="33030-180">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="33030-181">このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="33030-181">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="33030-182">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33030-182">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="33030-183">入力</span><span class="sxs-lookup"><span data-stu-id="33030-183">INPUTS</span></span>

<span data-ttu-id="33030-184">このコマンドレットは、入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="33030-184">This cmdlet takes no input.</span></span>

## <a name="outputs"></a><span data-ttu-id="33030-185">出力</span><span class="sxs-lookup"><span data-stu-id="33030-185">OUTPUTS</span></span>

<span data-ttu-id="33030-186">このコマンドレットは、出力を返しません。</span><span class="sxs-lookup"><span data-stu-id="33030-186">This cmdlet returns no output.</span></span>

## <a name="examples"></a><span data-ttu-id="33030-187">例</span><span class="sxs-lookup"><span data-stu-id="33030-187">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="33030-188">例 1</span><span class="sxs-lookup"><span data-stu-id="33030-188">EXAMPLE 1</span></span>

<span data-ttu-id="33030-189">このコマンドは、Windows PowerShell Web アプリケーションをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="33030-189">This command uninstalls the Windows PowerShell Web Application.</span></span>
<span data-ttu-id="33030-190">既定値を使用して Windows PowerShell Web アプリケーションをインストールした場合、そのアプリケーションをアンインストールするときにこのコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="33030-190">You can use this cmdlet to uninstall the Windows PowerShell Web Application if you installed it using the default values.</span></span>

```PowerShell
Uninstall-PswaWebApplication
```

### <a name="example-2"></a><span data-ttu-id="33030-191">例 2</span><span class="sxs-lookup"><span data-stu-id="33030-191">EXAMPLE 2</span></span>

<span data-ttu-id="33030-192">このコマンドは、Windows PowerShell Web アプリケーションをアンインストールし、アプリケーションに関連付けられているテスト証明書を削除します。</span><span class="sxs-lookup"><span data-stu-id="33030-192">This command uninstalls the Windows PowerShell Web Application, and deletes the test certificate associated with the application.</span></span>
<span data-ttu-id="33030-193">既定値を使用して Windows PowerShell Web アプリケーションをインストールし、テスト証明書を作成した場合、そのアプリケーションをアンインストールするときにこのコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="33030-193">You can use this cmdlet to uninstall the Windows PowerShell Web Application if you installed it using the default values and created a test certificate.</span></span>

```PowerShell
Uninstall-PswaWebApplication -DeleteTestCertificate
```

### <a name="example-3-example-3-subheading"></a><span data-ttu-id="33030-194">例 3 {#example-3 .subHeading}</span><span class="sxs-lookup"><span data-stu-id="33030-194">EXAMPLE 3 {#example-3 .subHeading}</span></span>

<span data-ttu-id="33030-195">インストール時にカスタム Web サイトおよびアプリケーションを指定した場合、このコマンドで Windows PowerShell Web アプリケーションがアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="33030-195">This command uninstalls the Windows PowerShell Web Application when a custom website and application were specified during the install.</span></span>
<span data-ttu-id="33030-196">このコマンドは、*MySite* という Web サイトと *TestApplication* というアプリケーションを削除し、アプリケーションに関連付けられているテスト証明書の削除も指定します。</span><span class="sxs-lookup"><span data-stu-id="33030-196">The command removes the website named *MySite* and the application named *TestApplication* and specifies that the test certificates associated with the application are also deleted.</span></span>

```
Uninstall-PswaWebApplication -WebApplicationName TestApplication -WebsiteName MySite -DeleteTestCertificate
```

## <a name="related-topics"></a><span data-ttu-id="33030-197">関連トピック</span><span class="sxs-lookup"><span data-stu-id="33030-197">Related topics</span></span>

- [<span data-ttu-id="33030-198">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="33030-198">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="33030-199">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="33030-199">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)
- [<span data-ttu-id="33030-200">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="33030-200">Install-PswaWebApplication</span></span>](install-pswawebapplication.md)
- [<span data-ttu-id="33030-201">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="33030-201">Remove-PswaAuthorizationRule</span></span>](remove-pswaauthorizationrule.md)
- [<span data-ttu-id="33030-202">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="33030-202">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)