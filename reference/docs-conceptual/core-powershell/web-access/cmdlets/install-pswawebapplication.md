---
ms.topic: reference
keywords: PowerShell, コマンドレット
ms.date: 12/12/2016
title: Install-PswaWebApplication
ms.openlocfilehash: 68455d9490f7d5c33c1a928ac262a76a78ad7128
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="install-pswawebapplication"></a><span data-ttu-id="0489e-103">Install-PswaWebApplication</span><span class="sxs-lookup"><span data-stu-id="0489e-103">Install-PswaWebApplication</span></span>

## <a name="synopsis"></a><span data-ttu-id="0489e-104">概要</span><span class="sxs-lookup"><span data-stu-id="0489e-104">SYNOPSIS</span></span>

<span data-ttu-id="0489e-105">IIS で Windows PowerShell® Web Access Web アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0489e-105">Configures the Windows PowerShell® Web Access web application in IIS.</span></span>

## <a name="syntax"></a><span data-ttu-id="0489e-106">構文</span><span class="sxs-lookup"><span data-stu-id="0489e-106">SYNTAX</span></span>

### <a name="default"></a><span data-ttu-id="0489e-107">既定</span><span class="sxs-lookup"><span data-stu-id="0489e-107">Default</span></span>
```
Install-PswaWebApplication [[-WebApplicationName] <String> ] [-UseTestCertificate] [-WebSiteName <String> ] [-Confirm] [-WhatIf] [ <CommonParameters>]
```

## <a name="description"></a><span data-ttu-id="0489e-108">説明</span><span class="sxs-lookup"><span data-stu-id="0489e-108">DESCRIPTION</span></span>

<span data-ttu-id="0489e-109">**Install-PswaWebApplication** コマンドレットは、Windows PowerShell Web Access Web アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0489e-109">The **Install-PswaWebApplication** cmdlet configures Windows PowerShell Web Access web application.</span></span> <span data-ttu-id="0489e-110">このコマンドレットは、Web アプリケーションをインストールし、そのアプリケーションを Web サイトと関連付けます。また、必要に応じて **useTestCertificate** パラメーターを使用してテスト SSL 証明書を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="0489e-110">This cmdlet installs the web application, associates it with a web site, and optionally creates a test SSL certificate using the **useTestCertificate** parameter.</span></span> <span data-ttu-id="0489e-111">セキュリティ上の理由から、Web 管理者は運用環境にテスト証明書を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0489e-111">For security reasons web administrators should not use a test certificate for production environments.</span></span>

## <a name="parameters"></a><span data-ttu-id="0489e-112">パラメータ</span><span class="sxs-lookup"><span data-stu-id="0489e-112">PARAMETERS</span></span>

### <a name="-usetestcertificate"></a><span data-ttu-id="0489e-113">-UseTestCertificate</span><span class="sxs-lookup"><span data-stu-id="0489e-113">-UseTestCertificate</span></span>

<span data-ttu-id="0489e-114">テスト証明書が作成されることを指定します。</span><span class="sxs-lookup"><span data-stu-id="0489e-114">Specifies that a test certificate is created.</span></span> <span data-ttu-id="0489e-115">このパラメーターを true に設定すると、このコマンドレットはテスト証明書を作成し、HTTPS 要求にその証明書を使用するように Windows PowerShell Web Access Web アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="0489e-115">If this parameter is set to true, then this cmdlet creates a test certificate and configures the Windows PowerShell Web Access web application to use the certificate for HTTPS requests.</span></span> <span data-ttu-id="0489e-116">このパラメーターを false に設定すると、証明書またはバインディングは作成されません。</span><span class="sxs-lookup"><span data-stu-id="0489e-116">If this parameter is set to false, then no certificate or binding is created.</span></span> <span data-ttu-id="0489e-117">Windows PowerShell Web Access に別の証明書を使用する場合は、この値を false に設定します。</span><span class="sxs-lookup"><span data-stu-id="0489e-117">Set this value to false if another certificate is used for Windows PowerShell Web Access.</span></span>

|||
|-|-|
| <span data-ttu-id="0489e-118">エイリアス</span><span class="sxs-lookup"><span data-stu-id="0489e-118">Aliases</span></span>                              | <span data-ttu-id="0489e-119">なし</span><span class="sxs-lookup"><span data-stu-id="0489e-119">none</span></span>                                 |
| <span data-ttu-id="0489e-120">必須?</span><span class="sxs-lookup"><span data-stu-id="0489e-120">Required?</span></span>                            | <span data-ttu-id="0489e-121">false</span><span class="sxs-lookup"><span data-stu-id="0489e-121">false</span></span>                                |
| <span data-ttu-id="0489e-122">位置は?</span><span class="sxs-lookup"><span data-stu-id="0489e-122">Position?</span></span>                            | <span data-ttu-id="0489e-123">名前付き</span><span class="sxs-lookup"><span data-stu-id="0489e-123">named</span></span>                                |
| <span data-ttu-id="0489e-124">既定値</span><span class="sxs-lookup"><span data-stu-id="0489e-124">Default Value</span></span>                        | <span data-ttu-id="0489e-125">true</span><span class="sxs-lookup"><span data-stu-id="0489e-125">true</span></span>                                 |
| <span data-ttu-id="0489e-126">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-126">Accept Pipeline Input?</span></span>               | <span data-ttu-id="0489e-127">false</span><span class="sxs-lookup"><span data-stu-id="0489e-127">false</span></span>                                |
| <span data-ttu-id="0489e-128">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-128">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="0489e-129">false</span><span class="sxs-lookup"><span data-stu-id="0489e-129">false</span></span>                                |

### <a name="-webapplicationnameltstringgt"></a><span data-ttu-id="0489e-130">-WebApplicationName&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="0489e-130">-WebApplicationName&lt;String&gt;</span></span>

<span data-ttu-id="0489e-131">Web アプリケーションの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0489e-131">Specifies the name for your web application.</span></span> <span data-ttu-id="0489e-132">これは Windows PowerShell Web Access URL の末尾の部分に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0489e-132">This is displayed as the last part of the Windows PowerShell Web Access URL.</span></span>

|||
|-|-|
| <span data-ttu-id="0489e-133">エイリアス</span><span class="sxs-lookup"><span data-stu-id="0489e-133">Aliases</span></span>                              | <span data-ttu-id="0489e-134">なし</span><span class="sxs-lookup"><span data-stu-id="0489e-134">none</span></span>                                 |
| <span data-ttu-id="0489e-135">必須?</span><span class="sxs-lookup"><span data-stu-id="0489e-135">Required?</span></span>                            | <span data-ttu-id="0489e-136">false</span><span class="sxs-lookup"><span data-stu-id="0489e-136">false</span></span>                                |
| <span data-ttu-id="0489e-137">位置は?</span><span class="sxs-lookup"><span data-stu-id="0489e-137">Position?</span></span>                            | <span data-ttu-id="0489e-138">1 で保護されたプロセスとして起動されました</span><span class="sxs-lookup"><span data-stu-id="0489e-138">1</span></span>                                    |
| <span data-ttu-id="0489e-139">既定値</span><span class="sxs-lookup"><span data-stu-id="0489e-139">Default Value</span></span>                        | <span data-ttu-id="0489e-140">pswa</span><span class="sxs-lookup"><span data-stu-id="0489e-140">pswa</span></span>                                 |
| <span data-ttu-id="0489e-141">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-141">Accept Pipeline Input?</span></span>               | <span data-ttu-id="0489e-142">false</span><span class="sxs-lookup"><span data-stu-id="0489e-142">false</span></span>                                |
| <span data-ttu-id="0489e-143">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-143">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="0489e-144">false</span><span class="sxs-lookup"><span data-stu-id="0489e-144">false</span></span>                                |

### <a name="-websitenameltstringgt"></a><span data-ttu-id="0489e-145">-WebSiteName&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="0489e-145">-WebSiteName&lt;String&gt;</span></span>

<span data-ttu-id="0489e-146">この Windows PowerShell Web Access Web アプリケーションをインストールする Web サーバー (IIS) Web サイトの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0489e-146">Specifies the name of the Web Server (IIS) website on which to install this Windows PowerShell Web Access web application.</span></span>

|||
|-|-|
| <span data-ttu-id="0489e-147">エイリアス</span><span class="sxs-lookup"><span data-stu-id="0489e-147">Aliases</span></span>                              | <span data-ttu-id="0489e-148">なし</span><span class="sxs-lookup"><span data-stu-id="0489e-148">none</span></span>                                 |
| <span data-ttu-id="0489e-149">必須?</span><span class="sxs-lookup"><span data-stu-id="0489e-149">Required?</span></span>                            | <span data-ttu-id="0489e-150">false</span><span class="sxs-lookup"><span data-stu-id="0489e-150">false</span></span>                                |
| <span data-ttu-id="0489e-151">位置は?</span><span class="sxs-lookup"><span data-stu-id="0489e-151">Position?</span></span>                            | <span data-ttu-id="0489e-152">名前付き</span><span class="sxs-lookup"><span data-stu-id="0489e-152">named</span></span>                                |
| <span data-ttu-id="0489e-153">既定値</span><span class="sxs-lookup"><span data-stu-id="0489e-153">Default Value</span></span>                        | <span data-ttu-id="0489e-154">Default Web Site</span><span class="sxs-lookup"><span data-stu-id="0489e-154">Default Web Site</span></span>                     |
| <span data-ttu-id="0489e-155">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-155">Accept Pipeline Input?</span></span>               | <span data-ttu-id="0489e-156">false</span><span class="sxs-lookup"><span data-stu-id="0489e-156">false</span></span>                                |
| <span data-ttu-id="0489e-157">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-157">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="0489e-158">false</span><span class="sxs-lookup"><span data-stu-id="0489e-158">false</span></span>                                |

### <a name="-confirm"></a><span data-ttu-id="0489e-159">-Confirm</span><span class="sxs-lookup"><span data-stu-id="0489e-159">-Confirm</span></span>

<span data-ttu-id="0489e-160">コマンドレットを実行する前に、ユーザーに確認を求めます。</span><span class="sxs-lookup"><span data-stu-id="0489e-160">Prompts you for confirmation before running the cmdlet.</span></span>

|||
|-|-|
| <span data-ttu-id="0489e-161">必須?</span><span class="sxs-lookup"><span data-stu-id="0489e-161">Required?</span></span>                            | <span data-ttu-id="0489e-162">false</span><span class="sxs-lookup"><span data-stu-id="0489e-162">false</span></span>                                |
| <span data-ttu-id="0489e-163">位置は?</span><span class="sxs-lookup"><span data-stu-id="0489e-163">Position?</span></span>                            | <span data-ttu-id="0489e-164">名前付き</span><span class="sxs-lookup"><span data-stu-id="0489e-164">named</span></span>                                |
| <span data-ttu-id="0489e-165">既定値</span><span class="sxs-lookup"><span data-stu-id="0489e-165">Default Value</span></span>                        | <span data-ttu-id="0489e-166">false</span><span class="sxs-lookup"><span data-stu-id="0489e-166">false</span></span>                                |
| <span data-ttu-id="0489e-167">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-167">Accept Pipeline Input?</span></span>               | <span data-ttu-id="0489e-168">false</span><span class="sxs-lookup"><span data-stu-id="0489e-168">false</span></span>                                |
| <span data-ttu-id="0489e-169">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-169">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="0489e-170">false</span><span class="sxs-lookup"><span data-stu-id="0489e-170">false</span></span>                                |

### <a name="-whatif"></a><span data-ttu-id="0489e-171">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="0489e-171">-WhatIf</span></span>

<span data-ttu-id="0489e-172">コマンドレットを実行するとどのような結果になるかを表示します。</span><span class="sxs-lookup"><span data-stu-id="0489e-172">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="0489e-173">コマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="0489e-173">The cmdlet is not run.</span></span>

|||
|-|-|
| <span data-ttu-id="0489e-174">必須?</span><span class="sxs-lookup"><span data-stu-id="0489e-174">Required?</span></span>                            | <span data-ttu-id="0489e-175">false</span><span class="sxs-lookup"><span data-stu-id="0489e-175">false</span></span>                                |
| <span data-ttu-id="0489e-176">位置は?</span><span class="sxs-lookup"><span data-stu-id="0489e-176">Position?</span></span>                            | <span data-ttu-id="0489e-177">名前付き</span><span class="sxs-lookup"><span data-stu-id="0489e-177">named</span></span>                                |
| <span data-ttu-id="0489e-178">既定値</span><span class="sxs-lookup"><span data-stu-id="0489e-178">Default Value</span></span>                        | <span data-ttu-id="0489e-179">false</span><span class="sxs-lookup"><span data-stu-id="0489e-179">false</span></span>                                |
| <span data-ttu-id="0489e-180">パイプライン入力を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-180">Accept Pipeline Input?</span></span>               | <span data-ttu-id="0489e-181">false</span><span class="sxs-lookup"><span data-stu-id="0489e-181">false</span></span>                                |
| <span data-ttu-id="0489e-182">ワイルドカード文字を許可する</span><span class="sxs-lookup"><span data-stu-id="0489e-182">Accept Wildcard Characters?</span></span>          | <span data-ttu-id="0489e-183">false</span><span class="sxs-lookup"><span data-stu-id="0489e-183">false</span></span>                                |

### <a name="ltcommonparametersgt"></a><span data-ttu-id="0489e-184">&lt;CommonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="0489e-184">&lt;CommonParameters&gt;</span></span>

<span data-ttu-id="0489e-185">このコマンドレットは、-Verbose、-Debug、-ErrorAction、-ErrorVariable、-OutBuffer、および -OutVariable という共通パラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0489e-185">This cmdlet supports the common parameters: -Verbose, -Debug, -ErrorAction, -ErrorVariable, -OutBuffer, and -OutVariable.</span></span>
<span data-ttu-id="0489e-186">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0489e-186">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/p/?LinkID=113216).</span></span>

## <a name="inputs"></a><span data-ttu-id="0489e-187">入力</span><span class="sxs-lookup"><span data-stu-id="0489e-187">INPUTS</span></span>

<span data-ttu-id="0489e-188">このコマンドレットは、入力を受け取りません。</span><span class="sxs-lookup"><span data-stu-id="0489e-188">This cmdlet takes no input.</span></span>

## <a name="outputs"></a><span data-ttu-id="0489e-189">出力</span><span class="sxs-lookup"><span data-stu-id="0489e-189">OUTPUTS</span></span>

<span data-ttu-id="0489e-190">このコマンドレットから出力は生成されません。</span><span class="sxs-lookup"><span data-stu-id="0489e-190">This cmdlet produces no output.</span></span>

## <a name="examples"></a><span data-ttu-id="0489e-191">例</span><span class="sxs-lookup"><span data-stu-id="0489e-191">EXAMPLES</span></span>

### <a name="example-1"></a><span data-ttu-id="0489e-192">例 1</span><span class="sxs-lookup"><span data-stu-id="0489e-192">EXAMPLE 1</span></span>

<span data-ttu-id="0489e-193">この例では、**WebApplicationName** (*pswa*) パラメーターと **WebSiteName** (*Default Web Site*) パラメーターに既定値を使用して、PSWA Web アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0489e-193">This example installs the PSWA web application using the default values for the **WebApplicationName** (*pswa*) and **WebSiteName** (*Default Web Site*) parameters .</span></span>

```
Install-PswaWebApplication
```

### <a name="example-2"></a><span data-ttu-id="0489e-194">例 2</span><span class="sxs-lookup"><span data-stu-id="0489e-194">EXAMPLE 2</span></span>

<span data-ttu-id="0489e-195">この例では、テスト証明書を使用し、**WebApplicationName** パラメーターと **WebSiteName** パラメーターに既定値を使用して、PSWA Web アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0489e-195">This example installs the PSWA web application with a test certificate, and using the default values for the **WebApplicationName** and **WebSiteName** parameters.</span></span>

```
Install-PswaWebApplication -UseTestCertificate
```

## <a name="related-topics"></a><span data-ttu-id="0489e-196">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0489e-196">Related topics</span></span>

- [<span data-ttu-id="0489e-197">Add-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="0489e-197">Add-PswaAuthorizationRule</span></span>](add-pswaauthorizationrule.md)
- [<span data-ttu-id="0489e-198">Get-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="0489e-198">Get-PswaAuthorizationRule</span></span>](get-pswaauthorizationrule.md)
- [<span data-ttu-id="0489e-199">Remove-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="0489e-199">Remove-PswaAuthorizationRule</span></span>](remove-pswaauthorizationrule.md)
- [<span data-ttu-id="0489e-200">Test-PswaAuthorizationRule</span><span class="sxs-lookup"><span data-stu-id="0489e-200">Test-PswaAuthorizationRule</span></span>](test-pswaauthorizationrule.md)