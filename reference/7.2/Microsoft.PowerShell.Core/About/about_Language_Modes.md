---
description: 言語モードと PowerShell セッションへの影響について説明します。
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 9e4b1ec2dd16d3442c553460ff217e7e0223f41f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602752"
---
# <a name="about-language-modes"></a><span data-ttu-id="999e2-103">言語モードについて</span><span class="sxs-lookup"><span data-stu-id="999e2-103">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="999e2-104">概要</span><span class="sxs-lookup"><span data-stu-id="999e2-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="999e2-105">言語モードと PowerShell セッションへの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="999e2-105">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="999e2-106">詳細説明</span><span class="sxs-lookup"><span data-stu-id="999e2-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="999e2-107">PowerShell セッションの言語モードによって、PowerShell 言語のどの要素をセッションで使用できるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="999e2-107">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="999e2-108">PowerShell は、次の言語モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="999e2-108">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="999e2-109">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="999e2-109">FullLanguage</span></span>
- <span data-ttu-id="999e2-110">ConstrainedLanguage (PowerShell 3.0 で導入)</span><span class="sxs-lookup"><span data-stu-id="999e2-110">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="999e2-111">RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="999e2-111">RestrictedLanguage</span></span>
- <span data-ttu-id="999e2-112">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="999e2-112">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="999e2-113">言語モードとは</span><span class="sxs-lookup"><span data-stu-id="999e2-113">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="999e2-114">言語モードによって、セッションで許可される言語要素が決まります。</span><span class="sxs-lookup"><span data-stu-id="999e2-114">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="999e2-115">言語モードは、実際にはセッションの作成に使用されるセッション構成 (または "エンドポイント") のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="999e2-115">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="999e2-116">特定のセッション構成を使用するすべてのセッションには、セッション構成の言語モードがあります。</span><span class="sxs-lookup"><span data-stu-id="999e2-116">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="999e2-117">すべての PowerShell セッションには、コマンドレットを使用して作成した pssession `New-PSSession` 、ComputerName パラメーターを使用する一時的なセッション、powershell を起動したときに表示される既定のセッションなど、言語モードがあります。</span><span class="sxs-lookup"><span data-stu-id="999e2-117">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="999e2-118">リモートセッションは、リモートコンピューター上のセッション構成を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-118">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="999e2-119">セッション構成で設定されている言語モードによって、セッションの言語モードが決まります。</span><span class="sxs-lookup"><span data-stu-id="999e2-119">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="999e2-120">PSSession のセッション構成を指定するには、セッションを作成するコマンドレットの ConfigurationName パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="999e2-120">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="999e2-121">言語モード</span><span class="sxs-lookup"><span data-stu-id="999e2-121">LANGUAGE MODES</span></span>

<span data-ttu-id="999e2-122">このセクションでは、PowerShell セッションの言語モードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="999e2-122">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="999e2-123">全言語 (FullLanguage)</span><span class="sxs-lookup"><span data-stu-id="999e2-123">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="999e2-124">FullLanguage モードでは、セッションのすべての言語要素が許可されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-124">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="999e2-125">FullLanguage は、windows RT を除くすべてのバージョンの Windows で既定のセッションの既定の言語モードです。</span><span class="sxs-lookup"><span data-stu-id="999e2-125">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="999e2-126">制限付き言語 (RestrictedLanguage)</span><span class="sxs-lookup"><span data-stu-id="999e2-126">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="999e2-127">RestrictedLanguage モードでは、ユーザーはコマンド (コマンドレット、関数、CIM コマンド、ワークフロー) を実行できますが、スクリプトブロックの使用は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="999e2-127">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="999e2-128">既定では、RestrictedLanguage モードでは次の変数のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-128">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="999e2-129">RestrictedLanguage モードを使用するモジュールマニフェストでは、次の追加の変数も許可します。</span><span class="sxs-lookup"><span data-stu-id="999e2-129">Module manifests, which use RestrictedLanguage mode, permit the following additional variables as well:</span></span>

- `$PSScriptRoot`
- <span data-ttu-id="999e2-130">`$PSEdition` (PowerShell Core の場合)</span><span class="sxs-lookup"><span data-stu-id="999e2-130">`$PSEdition` (in PowerShell Core)</span></span>
- <span data-ttu-id="999e2-131">`$EnabledExperimentalFeatures` (PowerShell Core の場合)</span><span class="sxs-lookup"><span data-stu-id="999e2-131">`$EnabledExperimentalFeatures` (in PowerShell Core)</span></span>

<span data-ttu-id="999e2-132">次の比較演算子のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-132">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="999e2-133">`-eq` つの</span><span class="sxs-lookup"><span data-stu-id="999e2-133">`-eq` (equal)</span></span>
- <span data-ttu-id="999e2-134">`-gt` (より大きい)</span><span class="sxs-lookup"><span data-stu-id="999e2-134">`-gt` (greater-than)</span></span>
- <span data-ttu-id="999e2-135">`-lt` (より小さい)</span><span class="sxs-lookup"><span data-stu-id="999e2-135">`-lt` (less-than)</span></span>

<span data-ttu-id="999e2-136">代入ステートメント、プロパティ参照、およびメソッド呼び出しは許可されません。</span><span class="sxs-lookup"><span data-stu-id="999e2-136">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="999e2-137">言語なし (NoLanguage)</span><span class="sxs-lookup"><span data-stu-id="999e2-137">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="999e2-138">NoLanguage モードは API でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-138">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="999e2-139">NoLanguage モードは、任意の形式のスクリプトテキストが許可されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="999e2-139">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="999e2-140">これにより、PowerShell スクリプトのフラグメントを送信して解析および実行する **addscript ()** メソッドを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="999e2-140">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="999e2-141">**Addcommand ()** と **addcommand ()** のみを使用できます。この場合、パーサーは実行されません。</span><span class="sxs-lookup"><span data-stu-id="999e2-141">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="999e2-142">制約付き言語 (制約付き言語)</span><span class="sxs-lookup"><span data-stu-id="999e2-142">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="999e2-143">ConstrainedLanguage モードでは、すべてのコマンドレットとすべての PowerShell 言語要素が許可されますが、許可される種類は制限されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-143">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="999e2-144">ConstrainedLanguage モードは、Windows RT でのユーザーモードコードの整合性 (UMCI) をサポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="999e2-144">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="999e2-145">これは Windows RT で唯一サポートされている言語モードですが、サポートされているすべてのシステムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-145">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="999e2-146">UMCI は、Microsoft 署名および Microsoft 認定アプリのみを Windows RT ベースのデバイスにインストールできるようにすることで、ARM デバイスを保護します。</span><span class="sxs-lookup"><span data-stu-id="999e2-146">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="999e2-147">ConstrainedLanguage モードでは、ユーザーは PowerShell を使用して UMCI を回避または違反できません。</span><span class="sxs-lookup"><span data-stu-id="999e2-147">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="999e2-148">ConstrainedLanguage モードの機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="999e2-148">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="999e2-149">Windows モジュールのすべてのコマンドレット、およびその他の UMCI によって承認されたコマンドレットは完全に機能し、メモしている場合を除き、システムリソースに完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="999e2-149">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="999e2-150">PowerShell スクリプト言語のすべての要素が許可されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-150">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="999e2-151">Windows に含まれるすべてのモジュールをインポートし、モジュールがエクスポートするすべてのコマンドをセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-151">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="999e2-152">PowerShell ワークフローでは、スクリプトワークフロー (PowerShell 言語で記述されたワークフロー) を記述して実行できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-152">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="999e2-153">XAML ベースのワークフローはサポートされていないため、を使用するなどして、XAML をスクリプトワークフローで実行することはできません `Invoke-Expression -Language XAML` 。</span><span class="sxs-lookup"><span data-stu-id="999e2-153">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="999e2-154">また、入れ子になったワークフローを使用することもできますが、ワークフローで他のワークフローを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="999e2-154">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="999e2-155">コマンドレットは署名された `Add-Type` アセンブリを読み込むことができますが、任意の C# コードまたは Win32 api を読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="999e2-155">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="999e2-156">コマンドレットは、許可されて `New-Object` いる型 (以下の一覧を参照) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-156">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="999e2-157">PowerShell で使用できるのは、許可されている型のみです (以下を参照)。</span><span class="sxs-lookup"><span data-stu-id="999e2-157">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="999e2-158">その他の型は使用できません。</span><span class="sxs-lookup"><span data-stu-id="999e2-158">Other types are not permitted.</span></span>

- <span data-ttu-id="999e2-159">型変換は許可されますが、結果が許可される型である場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="999e2-159">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="999e2-160">文字列入力を型に変換するコマンドレットパラメーターは、結果の型が許可されている型である場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="999e2-160">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="999e2-161">**ToString ()** メソッドと、許可されている型 (以下の一覧を参照) の .net メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="999e2-161">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="999e2-162">他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="999e2-162">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="999e2-163">ユーザーは、許可された型のすべてのプロパティを取得できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-163">Users can get all properties of allowed types.</span></span> <span data-ttu-id="999e2-164">ユーザーは、コア型に対してのみプロパティの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-164">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="999e2-165">次の COM オブジェクトのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-165">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="999e2-166">**スクリプト. Dictionary**</span><span class="sxs-lookup"><span data-stu-id="999e2-166">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="999e2-167">**Scripting.FileSystemObject**</span><span class="sxs-lookup"><span data-stu-id="999e2-167">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="999e2-168">**VBScript. RegExp**</span><span class="sxs-lookup"><span data-stu-id="999e2-168">**VBScript.RegExp**</span></span>

<span data-ttu-id="999e2-169">ConstrainedLanguage モードでは、次の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-169">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="999e2-170">ユーザーは、プロパティの取得、メソッドの呼び出し、およびオブジェクトの型への変換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="999e2-170">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="999e2-171">許可される型:</span><span class="sxs-lookup"><span data-stu-id="999e2-171">Allowed Types:</span></span>

- <span data-ttu-id="999e2-172">エイリアス属性</span><span class="sxs-lookup"><span data-stu-id="999e2-172">AliasAttribute</span></span>
- <span data-ttu-id="999e2-173">AllowEmptyCollectionAttribute</span><span class="sxs-lookup"><span data-stu-id="999e2-173">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="999e2-174">AllowEmptyStringAttribute</span><span class="sxs-lookup"><span data-stu-id="999e2-174">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="999e2-175">AllowNullAttribute</span><span class="sxs-lookup"><span data-stu-id="999e2-175">AllowNullAttribute</span></span>
- <span data-ttu-id="999e2-176">Array</span><span class="sxs-lookup"><span data-stu-id="999e2-176">Array</span></span>
- <span data-ttu-id="999e2-177">Bool</span><span class="sxs-lookup"><span data-stu-id="999e2-177">Bool</span></span>
- <span data-ttu-id="999e2-178">byte</span><span class="sxs-lookup"><span data-stu-id="999e2-178">byte</span></span>
- <span data-ttu-id="999e2-179">char</span><span class="sxs-lookup"><span data-stu-id="999e2-179">char</span></span>
- <span data-ttu-id="999e2-180">属性の Bindingbindingattribute</span><span class="sxs-lookup"><span data-stu-id="999e2-180">CmdletBindingAttribute</span></span>
- <span data-ttu-id="999e2-181">DateTime</span><span class="sxs-lookup"><span data-stu-id="999e2-181">DateTime</span></span>
- <span data-ttu-id="999e2-182">decimal</span><span class="sxs-lookup"><span data-stu-id="999e2-182">decimal</span></span>
- <span data-ttu-id="999e2-183">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="999e2-183">DirectoryEntry</span></span>
- <span data-ttu-id="999e2-184">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="999e2-184">DirectorySearcher</span></span>
- <span data-ttu-id="999e2-185">double</span><span class="sxs-lookup"><span data-stu-id="999e2-185">double</span></span>
- <span data-ttu-id="999e2-186">float</span><span class="sxs-lookup"><span data-stu-id="999e2-186">float</span></span>
- <span data-ttu-id="999e2-187">Guid</span><span class="sxs-lookup"><span data-stu-id="999e2-187">Guid</span></span>
- <span data-ttu-id="999e2-188">Hashtable</span><span class="sxs-lookup"><span data-stu-id="999e2-188">Hashtable</span></span>
- <span data-ttu-id="999e2-189">INT</span><span class="sxs-lookup"><span data-stu-id="999e2-189">int</span></span>
- <span data-ttu-id="999e2-190">Int16</span><span class="sxs-lookup"><span data-stu-id="999e2-190">Int16</span></span>
- <span data-ttu-id="999e2-191">long</span><span class="sxs-lookup"><span data-stu-id="999e2-191">long</span></span>
- <span data-ttu-id="999e2-192">ManagementClass</span><span class="sxs-lookup"><span data-stu-id="999e2-192">ManagementClass</span></span>
- <span data-ttu-id="999e2-193">System.management.managementobject</span><span class="sxs-lookup"><span data-stu-id="999e2-193">ManagementObject</span></span>
- <span data-ttu-id="999e2-194">ManagementObjectSearcher</span><span class="sxs-lookup"><span data-stu-id="999e2-194">ManagementObjectSearcher</span></span>
- <span data-ttu-id="999e2-195">NullString</span><span class="sxs-lookup"><span data-stu-id="999e2-195">NullString</span></span>
- <span data-ttu-id="999e2-196">OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="999e2-196">OutputTypeAttribute</span></span>
- <span data-ttu-id="999e2-197">ParameterAttribute</span><span class="sxs-lookup"><span data-stu-id="999e2-197">ParameterAttribute</span></span>
- <span data-ttu-id="999e2-198">PSCredential</span><span class="sxs-lookup"><span data-stu-id="999e2-198">PSCredential</span></span>
- <span data-ttu-id="999e2-199">PSDefaultValueAttribute</span><span class="sxs-lookup"><span data-stu-id="999e2-199">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="999e2-200">PSListModifier</span><span class="sxs-lookup"><span data-stu-id="999e2-200">PSListModifier</span></span>
- <span data-ttu-id="999e2-201">PSObject</span><span class="sxs-lookup"><span data-stu-id="999e2-201">PSObject</span></span>
- <span data-ttu-id="999e2-202">PSPrimitiveDictionary</span><span class="sxs-lookup"><span data-stu-id="999e2-202">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="999e2-203">PSReference</span><span class="sxs-lookup"><span data-stu-id="999e2-203">PSReference</span></span>
- <span data-ttu-id="999e2-204">PSTypeNameAttribute</span><span class="sxs-lookup"><span data-stu-id="999e2-204">PSTypeNameAttribute</span></span>
- <span data-ttu-id="999e2-205">Regex</span><span class="sxs-lookup"><span data-stu-id="999e2-205">Regex</span></span>
- <span data-ttu-id="999e2-206">SByte</span><span class="sxs-lookup"><span data-stu-id="999e2-206">SByte</span></span>
- <span data-ttu-id="999e2-207">string</span><span class="sxs-lookup"><span data-stu-id="999e2-207">string</span></span>
- <span data-ttu-id="999e2-208">SupportsWildcardsAttribute</span><span class="sxs-lookup"><span data-stu-id="999e2-208">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="999e2-209">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="999e2-209">SwitchParameter</span></span>
- <span data-ttu-id="999e2-210">システムのグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="999e2-210">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="999e2-211">System .Net. IPAddress</span><span class="sxs-lookup"><span data-stu-id="999e2-211">System.Net.IPAddress</span></span>
- <span data-ttu-id="999e2-212">システム .Net. Mail. MailAddress</span><span class="sxs-lookup"><span data-stu-id="999e2-212">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="999e2-213">BigInteger</span><span class="sxs-lookup"><span data-stu-id="999e2-213">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="999e2-214">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="999e2-214">System.Security.SecureString</span></span>
- <span data-ttu-id="999e2-215">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="999e2-215">TimeSpan</span></span>
- <span data-ttu-id="999e2-216">UInt16</span><span class="sxs-lookup"><span data-stu-id="999e2-216">UInt16</span></span>
- <span data-ttu-id="999e2-217">UInt32</span><span class="sxs-lookup"><span data-stu-id="999e2-217">UInt32</span></span>
- <span data-ttu-id="999e2-218">UInt64</span><span class="sxs-lookup"><span data-stu-id="999e2-218">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="999e2-219">セッション構成の言語モードの検索</span><span class="sxs-lookup"><span data-stu-id="999e2-219">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="999e2-220">セッション構成ファイルを使用してセッション構成を作成する場合、セッション構成には LanguageMode プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="999e2-220">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="999e2-221">言語モードを確認するには、LanguageMode プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="999e2-221">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="999e2-222">他のセッション構成では、セッション構成を使用して作成されたセッションの言語モードを見つけることで、言語モードを間接的に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="999e2-222">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="999e2-223">セッションの言語モードの検索</span><span class="sxs-lookup"><span data-stu-id="999e2-223">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="999e2-224">セッション状態の LanguageMode プロパティの値を取得することで、FullLanguage または ConstrainedLanguage セッションの言語モードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="999e2-224">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="999e2-225">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="999e2-225">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="999e2-226">ただし、RestrictedLanguage モードと NoLanguage モードのセッションでは、ドットメソッドを使用してプロパティ値を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="999e2-226">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="999e2-227">代わりに、エラーメッセージに言語モードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-227">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="999e2-228">RestrictedLanguage セッションでコマンドを実行すると、 `$ExecutionContext.SessionState.LanguageMode` PowerShell は PropertyReferenceNotSupportedInDataSection および VariableReferenceNotSupportedInDataSection エラーメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="999e2-228">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="999e2-229">PropertyReferenceNotSupportedInDataSection: プロパティ参照は、制限付き言語モードまたはデータセクションでは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="999e2-229">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="999e2-230">VariableReferenceNotSupportedInDataSection は、制限された言語モードまたはデータセクションで参照できない変数を参照しています。</span><span class="sxs-lookup"><span data-stu-id="999e2-230">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="999e2-231">`$ExecutionContext.SessionState.LanguageMode`NoLanguage セッションでコマンドを実行すると、PowerShell によって、スクリプトで許可されているエラーメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="999e2-231">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="999e2-232">スクリプト Notallowed: 構文は、この実行空間ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="999e2-232">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="999e2-233">これは、言語なしモードであることが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="999e2-233">This might be because it is in no-language mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="999e2-234">関連項目</span><span class="sxs-lookup"><span data-stu-id="999e2-234">SEE ALSO</span></span>

- [<span data-ttu-id="999e2-235">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="999e2-235">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="999e2-236">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="999e2-236">about_Session_Configurations</span></span>](about_Session_Configurations.md)
