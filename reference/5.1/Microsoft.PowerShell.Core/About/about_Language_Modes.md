---
description: 言語モードと PowerShell セッションへの影響について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 09/09/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_language_modes?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Language_Modes
ms.openlocfilehash: 91e3021c854945d86822c5d8219542eff7118aa7
ms.sourcegitcommit: fb1a4bc4b249afd3513663de2e1ba3025d63467e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2020
ms.locfileid: "94625654"
---
# <a name="about-language-modes"></a><span data-ttu-id="7de22-104">言語モードについて</span><span class="sxs-lookup"><span data-stu-id="7de22-104">About Language Modes</span></span>

## <a name="short-description"></a><span data-ttu-id="7de22-105">概要</span><span class="sxs-lookup"><span data-stu-id="7de22-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="7de22-106">言語モードと PowerShell セッションへの影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="7de22-106">Explains language modes and their effect on PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="7de22-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="7de22-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="7de22-108">PowerShell セッションの言語モードによって、PowerShell 言語のどの要素をセッションで使用できるかが決まります。</span><span class="sxs-lookup"><span data-stu-id="7de22-108">The language mode of a PowerShell session determines, in part, which elements of the PowerShell language can be used in the session.</span></span>

<span data-ttu-id="7de22-109">PowerShell は、次の言語モードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="7de22-109">PowerShell supports the following language modes:</span></span>

- <span data-ttu-id="7de22-110">FullLanguage</span><span class="sxs-lookup"><span data-stu-id="7de22-110">FullLanguage</span></span>
- <span data-ttu-id="7de22-111">ConstrainedLanguage (PowerShell 3.0 で導入)</span><span class="sxs-lookup"><span data-stu-id="7de22-111">ConstrainedLanguage (introduced in PowerShell 3.0)</span></span>
- <span data-ttu-id="7de22-112">RestrictedLanguage</span><span class="sxs-lookup"><span data-stu-id="7de22-112">RestrictedLanguage</span></span>
- <span data-ttu-id="7de22-113">NoLanguage</span><span class="sxs-lookup"><span data-stu-id="7de22-113">NoLanguage</span></span>

### <a name="what-is-a-language-mode"></a><span data-ttu-id="7de22-114">言語モードとは</span><span class="sxs-lookup"><span data-stu-id="7de22-114">WHAT IS A LANGUAGE MODE?</span></span>

<span data-ttu-id="7de22-115">言語モードによって、セッションで許可される言語要素が決まります。</span><span class="sxs-lookup"><span data-stu-id="7de22-115">The language mode determines the language elements that are permitted in the session.</span></span>

<span data-ttu-id="7de22-116">言語モードは、実際にはセッションの作成に使用されるセッション構成 (または "エンドポイント") のプロパティです。</span><span class="sxs-lookup"><span data-stu-id="7de22-116">The language mode is actually a property of the session configuration (or "endpoint") that is used to create the session.</span></span> <span data-ttu-id="7de22-117">特定のセッション構成を使用するすべてのセッションには、セッション構成の言語モードがあります。</span><span class="sxs-lookup"><span data-stu-id="7de22-117">All sessions that use a particular session configuration have the language mode of the session configuration.</span></span>

<span data-ttu-id="7de22-118">すべての PowerShell セッションには、コマンドレットを使用して作成した pssession `New-PSSession` 、ComputerName パラメーターを使用する一時的なセッション、powershell を起動したときに表示される既定のセッションなど、言語モードがあります。</span><span class="sxs-lookup"><span data-stu-id="7de22-118">All PowerShell sessions have a language mode, including PSSessions that you create by using the `New-PSSession` cmdlet, temporary sessions that use the ComputerName parameter, and the default sessions that appear when you start PowerShell.</span></span>

<span data-ttu-id="7de22-119">リモートセッションは、リモートコンピューター上のセッション構成を使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-119">Remote sessions are created by using the session configurations on the remote computer.</span></span> <span data-ttu-id="7de22-120">セッション構成で設定されている言語モードによって、セッションの言語モードが決まります。</span><span class="sxs-lookup"><span data-stu-id="7de22-120">The language mode set in the session configuration determines the language mode of the session.</span></span> <span data-ttu-id="7de22-121">PSSession のセッション構成を指定するには、セッションを作成するコマンドレットの ConfigurationName パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="7de22-121">To specify the session configuration of a PSSession, use the ConfigurationName parameter of cmdlets that create a session.</span></span>

### <a name="language-modes"></a><span data-ttu-id="7de22-122">言語モード</span><span class="sxs-lookup"><span data-stu-id="7de22-122">LANGUAGE MODES</span></span>

<span data-ttu-id="7de22-123">このセクションでは、PowerShell セッションの言語モードについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7de22-123">This section describes the language modes in PowerShell sessions.</span></span>

#### <a name="full-language-fulllanguage"></a><span data-ttu-id="7de22-124">全言語 (FullLanguage)</span><span class="sxs-lookup"><span data-stu-id="7de22-124">FULL LANGUAGE (FullLanguage)</span></span>

<span data-ttu-id="7de22-125">FullLanguage モードでは、セッションのすべての言語要素が許可されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-125">The FullLanguage mode permits all language elements in the session.</span></span>
<span data-ttu-id="7de22-126">FullLanguage は、windows RT を除くすべてのバージョンの Windows で既定のセッションの既定の言語モードです。</span><span class="sxs-lookup"><span data-stu-id="7de22-126">FullLanguage is the default language mode for default sessions on all versions of Windows except for Windows RT.</span></span>

#### <a name="restricted-language-restrictedlanguage"></a><span data-ttu-id="7de22-127">制限付き言語 (RestrictedLanguage)</span><span class="sxs-lookup"><span data-stu-id="7de22-127">RESTRICTED LANGUAGE (RestrictedLanguage)</span></span>

<span data-ttu-id="7de22-128">RestrictedLanguage モードでは、ユーザーはコマンド (コマンドレット、関数、CIM コマンド、ワークフロー) を実行できますが、スクリプトブロックの使用は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="7de22-128">In RestrictedLanguage mode, users may run commands (cmdlets, functions, CIM commands, and workflows) but are not permitted to use script blocks.</span></span>

<span data-ttu-id="7de22-129">既定では、RestrictedLanguage モードでは次の変数のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-129">By default, only the following variables are permitted in RestrictedLanguage mode:</span></span>

- `$PSCulture`
- `$PSUICulture`
- `$True`
- `$False`
- `$Null`

<span data-ttu-id="7de22-130">次の比較演算子のみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-130">Only the following comparison operators are permitted:</span></span>

- <span data-ttu-id="7de22-131">`-eq` つの</span><span class="sxs-lookup"><span data-stu-id="7de22-131">`-eq` (equal)</span></span>
- <span data-ttu-id="7de22-132">`-gt` (より大きい)</span><span class="sxs-lookup"><span data-stu-id="7de22-132">`-gt` (greater-than)</span></span>
- <span data-ttu-id="7de22-133">`-lt` (より小さい)</span><span class="sxs-lookup"><span data-stu-id="7de22-133">`-lt` (less-than)</span></span>

<span data-ttu-id="7de22-134">代入ステートメント、プロパティ参照、およびメソッド呼び出しは許可されません。</span><span class="sxs-lookup"><span data-stu-id="7de22-134">Assignment statements, property references, and method calls are not permitted.</span></span>

#### <a name="no-language-nolanguage"></a><span data-ttu-id="7de22-135">言語なし (NoLanguage)</span><span class="sxs-lookup"><span data-stu-id="7de22-135">NO LANGUAGE (NoLanguage)</span></span>

<span data-ttu-id="7de22-136">NoLanguage モードは API でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-136">NoLanguage mode can only be used through the API.</span></span> <span data-ttu-id="7de22-137">NoLanguage モードは、任意の形式のスクリプトテキストが許可されないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7de22-137">NoLanguage mode means no script text of any form is permitted.</span></span> <span data-ttu-id="7de22-138">これにより、PowerShell スクリプトのフラグメントを送信して解析および実行する **addscript ()** メソッドを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="7de22-138">This precludes the use of the **AddScript()** method which sends fragments of PowerShell script to be parsed and executed.</span></span> <span data-ttu-id="7de22-139">**Addcommand ()** と **addcommand ()** のみを使用できます。この場合、パーサーは実行されません。</span><span class="sxs-lookup"><span data-stu-id="7de22-139">You can only use **AddCommand()** and **AddParameter()** which don't go through the parser.</span></span>

#### <a name="constrained-language-constrained-language"></a><span data-ttu-id="7de22-140">制約付き言語 (制約付き言語)</span><span class="sxs-lookup"><span data-stu-id="7de22-140">CONSTRAINED LANGUAGE (Constrained Language)</span></span>

<span data-ttu-id="7de22-141">ConstrainedLanguage モードでは、すべてのコマンドレットとすべての PowerShell 言語要素が許可されますが、許可される種類は制限されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-141">The ConstrainedLanguage mode permits all cmdlets and all PowerShell language elements, but it limits permitted types.</span></span>

<span data-ttu-id="7de22-142">ConstrainedLanguage モードは、Windows RT でのユーザーモードコードの整合性 (UMCI) をサポートするように設計されています。</span><span class="sxs-lookup"><span data-stu-id="7de22-142">ConstrainedLanguage mode is designed to support User Mode Code Integrity (UMCI) on Windows RT.</span></span> <span data-ttu-id="7de22-143">これは Windows RT で唯一サポートされている言語モードですが、サポートされているすべてのシステムで使用できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-143">It is the only supported language mode on Windows RT, but it is available on all supported systems.</span></span>

<span data-ttu-id="7de22-144">UMCI は、Microsoft 署名および Microsoft 認定アプリのみを Windows RT ベースのデバイスにインストールできるようにすることで、ARM デバイスを保護します。</span><span class="sxs-lookup"><span data-stu-id="7de22-144">UMCI protects ARM devices by allowing only Microsoft-signed and Microsoft-certified apps to be installed on Windows RT-based devices.</span></span>
<span data-ttu-id="7de22-145">ConstrainedLanguage モードでは、ユーザーは PowerShell を使用して UMCI を回避または違反できません。</span><span class="sxs-lookup"><span data-stu-id="7de22-145">ConstrainedLanguage mode prevents users from using PowerShell to circumvent or violate UMCI.</span></span>

<span data-ttu-id="7de22-146">ConstrainedLanguage モードの機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="7de22-146">The features of ConstrainedLanguage mode are as follows:</span></span>

- <span data-ttu-id="7de22-147">Windows モジュールのすべてのコマンドレット、およびその他の UMCI によって承認されたコマンドレットは完全に機能し、メモしている場合を除き、システムリソースに完全にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7de22-147">All cmdlets in Windows modules, and other UMCI-approved cmdlets, are fully functional and have complete access to system resources, except as noted.</span></span>

- <span data-ttu-id="7de22-148">PowerShell スクリプト言語のすべての要素が許可されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-148">All elements of the PowerShell scripting language are permitted.</span></span>

- <span data-ttu-id="7de22-149">Windows に含まれるすべてのモジュールをインポートし、モジュールがエクスポートするすべてのコマンドをセッションで実行できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-149">All modules included in Windows can be imported and all commands that the modules export run in the session.</span></span>

- <span data-ttu-id="7de22-150">PowerShell ワークフローでは、スクリプトワークフロー (PowerShell 言語で記述されたワークフロー) を記述して実行できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-150">In PowerShell Workflow, you can write and run script workflows (workflows written in the PowerShell language).</span></span> <span data-ttu-id="7de22-151">XAML ベースのワークフローはサポートされていないため、を使用するなどして、XAML をスクリプトワークフローで実行することはできません `Invoke-Expression -Language XAML` 。</span><span class="sxs-lookup"><span data-stu-id="7de22-151">XAML-based workflows are not supported and you cannot run XAML in a script workflow, such as by using `Invoke-Expression -Language XAML`.</span></span> <span data-ttu-id="7de22-152">また、入れ子になったワークフローを使用することもできますが、ワークフローで他のワークフローを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7de22-152">Also, workflows cannot call other workflows, although nested workflows are permitted.</span></span>

- <span data-ttu-id="7de22-153">コマンドレットは署名された `Add-Type` アセンブリを読み込むことができますが、任意の C# コードまたは Win32 api を読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="7de22-153">The `Add-Type` cmdlet can load signed assemblies, but it cannot load arbitrary C# code or Win32 APIs.</span></span>

- <span data-ttu-id="7de22-154">コマンドレットは、許可されて `New-Object` いる型 (以下の一覧を参照) でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-154">The `New-Object` cmdlet can be used only on allowed types (listed below).</span></span>

- <span data-ttu-id="7de22-155">PowerShell で使用できるのは、許可されている型のみです (以下を参照)。</span><span class="sxs-lookup"><span data-stu-id="7de22-155">Only allowed types (listed below) can be used in PowerShell.</span></span> <span data-ttu-id="7de22-156">その他の型は使用できません。</span><span class="sxs-lookup"><span data-stu-id="7de22-156">Other types are not permitted.</span></span>

- <span data-ttu-id="7de22-157">型変換は許可されますが、結果が許可される型である場合に限ります。</span><span class="sxs-lookup"><span data-stu-id="7de22-157">Type conversion is permitted, but only when the result is an allowed type.</span></span>

- <span data-ttu-id="7de22-158">文字列入力を型に変換するコマンドレットパラメーターは、結果の型が許可されている型である場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="7de22-158">Cmdlet parameters that convert string input to types work only when the resulting type is an allowed type.</span></span>

- <span data-ttu-id="7de22-159">**ToString ()** メソッドと、許可されている型 (以下の一覧を参照) の .net メソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="7de22-159">The **ToString()** method and the .NET methods of allowed types (listed below) can be invoked.</span></span> <span data-ttu-id="7de22-160">他のメソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="7de22-160">Other methods cannot be invoked.</span></span>

- <span data-ttu-id="7de22-161">ユーザーは、許可された型のすべてのプロパティを取得できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-161">Users can get all properties of allowed types.</span></span> <span data-ttu-id="7de22-162">ユーザーは、コア型に対してのみプロパティの値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-162">Users can set the values of properties only on Core types.</span></span> <span data-ttu-id="7de22-163">次の COM オブジェクトのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-163">Only the following COM objects are permitted:</span></span>

  - <span data-ttu-id="7de22-164">**スクリプト. Dictionary**</span><span class="sxs-lookup"><span data-stu-id="7de22-164">**Scripting.Dictionary**</span></span>
  - <span data-ttu-id="7de22-165">**Scripting.FileSystemObject**</span><span class="sxs-lookup"><span data-stu-id="7de22-165">**Scripting.FileSystemObject**</span></span>
  - <span data-ttu-id="7de22-166">**VBScript. RegExp**</span><span class="sxs-lookup"><span data-stu-id="7de22-166">**VBScript.RegExp**</span></span>

<span data-ttu-id="7de22-167">ConstrainedLanguage モードでは、次の型を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-167">The following types are permitted in ConstrainedLanguage mode.</span></span> <span data-ttu-id="7de22-168">ユーザーは、プロパティの取得、メソッドの呼び出し、およびオブジェクトの型への変換を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7de22-168">Users can get properties, invoke methods, and convert objects to these types.</span></span>

<span data-ttu-id="7de22-169">許可される型:</span><span class="sxs-lookup"><span data-stu-id="7de22-169">Allowed Types:</span></span>

- <span data-ttu-id="7de22-170">エイリアス属性</span><span class="sxs-lookup"><span data-stu-id="7de22-170">AliasAttribute</span></span>
- <span data-ttu-id="7de22-171">AllowEmptyCollectionAttribute</span><span class="sxs-lookup"><span data-stu-id="7de22-171">AllowEmptyCollectionAttribute</span></span>
- <span data-ttu-id="7de22-172">AllowEmptyStringAttribute</span><span class="sxs-lookup"><span data-stu-id="7de22-172">AllowEmptyStringAttribute</span></span>
- <span data-ttu-id="7de22-173">AllowNullAttribute</span><span class="sxs-lookup"><span data-stu-id="7de22-173">AllowNullAttribute</span></span>
- <span data-ttu-id="7de22-174">Array</span><span class="sxs-lookup"><span data-stu-id="7de22-174">Array</span></span>
- <span data-ttu-id="7de22-175">Bool</span><span class="sxs-lookup"><span data-stu-id="7de22-175">Bool</span></span>
- <span data-ttu-id="7de22-176">byte</span><span class="sxs-lookup"><span data-stu-id="7de22-176">byte</span></span>
- <span data-ttu-id="7de22-177">char</span><span class="sxs-lookup"><span data-stu-id="7de22-177">char</span></span>
- <span data-ttu-id="7de22-178">属性の Bindingbindingattribute</span><span class="sxs-lookup"><span data-stu-id="7de22-178">CmdletBindingAttribute</span></span>
- <span data-ttu-id="7de22-179">DateTime</span><span class="sxs-lookup"><span data-stu-id="7de22-179">DateTime</span></span>
- <span data-ttu-id="7de22-180">decimal</span><span class="sxs-lookup"><span data-stu-id="7de22-180">decimal</span></span>
- <span data-ttu-id="7de22-181">DirectoryEntry</span><span class="sxs-lookup"><span data-stu-id="7de22-181">DirectoryEntry</span></span>
- <span data-ttu-id="7de22-182">DirectorySearcher</span><span class="sxs-lookup"><span data-stu-id="7de22-182">DirectorySearcher</span></span>
- <span data-ttu-id="7de22-183">double</span><span class="sxs-lookup"><span data-stu-id="7de22-183">double</span></span>
- <span data-ttu-id="7de22-184">float</span><span class="sxs-lookup"><span data-stu-id="7de22-184">float</span></span>
- <span data-ttu-id="7de22-185">Guid</span><span class="sxs-lookup"><span data-stu-id="7de22-185">Guid</span></span>
- <span data-ttu-id="7de22-186">Hashtable</span><span class="sxs-lookup"><span data-stu-id="7de22-186">Hashtable</span></span>
- <span data-ttu-id="7de22-187">INT</span><span class="sxs-lookup"><span data-stu-id="7de22-187">int</span></span>
- <span data-ttu-id="7de22-188">Int16</span><span class="sxs-lookup"><span data-stu-id="7de22-188">Int16</span></span>
- <span data-ttu-id="7de22-189">long</span><span class="sxs-lookup"><span data-stu-id="7de22-189">long</span></span>
- <span data-ttu-id="7de22-190">ManagementClass</span><span class="sxs-lookup"><span data-stu-id="7de22-190">ManagementClass</span></span>
- <span data-ttu-id="7de22-191">System.management.managementobject</span><span class="sxs-lookup"><span data-stu-id="7de22-191">ManagementObject</span></span>
- <span data-ttu-id="7de22-192">ManagementObjectSearcher</span><span class="sxs-lookup"><span data-stu-id="7de22-192">ManagementObjectSearcher</span></span>
- <span data-ttu-id="7de22-193">NullString</span><span class="sxs-lookup"><span data-stu-id="7de22-193">NullString</span></span>
- <span data-ttu-id="7de22-194">OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="7de22-194">OutputTypeAttribute</span></span>
- <span data-ttu-id="7de22-195">ParameterAttribute</span><span class="sxs-lookup"><span data-stu-id="7de22-195">ParameterAttribute</span></span>
- <span data-ttu-id="7de22-196">PSCredential</span><span class="sxs-lookup"><span data-stu-id="7de22-196">PSCredential</span></span>
- <span data-ttu-id="7de22-197">PSDefaultValueAttribute</span><span class="sxs-lookup"><span data-stu-id="7de22-197">PSDefaultValueAttribute</span></span>
- <span data-ttu-id="7de22-198">PSListModifier</span><span class="sxs-lookup"><span data-stu-id="7de22-198">PSListModifier</span></span>
- <span data-ttu-id="7de22-199">PSObject</span><span class="sxs-lookup"><span data-stu-id="7de22-199">PSObject</span></span>
- <span data-ttu-id="7de22-200">PSPrimitiveDictionary</span><span class="sxs-lookup"><span data-stu-id="7de22-200">PSPrimitiveDictionary</span></span>
- <span data-ttu-id="7de22-201">PSReference</span><span class="sxs-lookup"><span data-stu-id="7de22-201">PSReference</span></span>
- <span data-ttu-id="7de22-202">PSTypeNameAttribute</span><span class="sxs-lookup"><span data-stu-id="7de22-202">PSTypeNameAttribute</span></span>
- <span data-ttu-id="7de22-203">Regex</span><span class="sxs-lookup"><span data-stu-id="7de22-203">Regex</span></span>
- <span data-ttu-id="7de22-204">SByte</span><span class="sxs-lookup"><span data-stu-id="7de22-204">SByte</span></span>
- <span data-ttu-id="7de22-205">string</span><span class="sxs-lookup"><span data-stu-id="7de22-205">string</span></span>
- <span data-ttu-id="7de22-206">SupportsWildcardsAttribute</span><span class="sxs-lookup"><span data-stu-id="7de22-206">SupportsWildcardsAttribute</span></span>
- <span data-ttu-id="7de22-207">SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="7de22-207">SwitchParameter</span></span>
- <span data-ttu-id="7de22-208">システムのグローバリゼーション</span><span class="sxs-lookup"><span data-stu-id="7de22-208">System.Globalization.CultureInfo</span></span>
- <span data-ttu-id="7de22-209">System .Net. IPAddress</span><span class="sxs-lookup"><span data-stu-id="7de22-209">System.Net.IPAddress</span></span>
- <span data-ttu-id="7de22-210">システム .Net. Mail. MailAddress</span><span class="sxs-lookup"><span data-stu-id="7de22-210">System.Net.Mail.MailAddress</span></span>
- <span data-ttu-id="7de22-211">BigInteger</span><span class="sxs-lookup"><span data-stu-id="7de22-211">System.Numerics.BigInteger</span></span>
- <span data-ttu-id="7de22-212">System.Security.SecureString</span><span class="sxs-lookup"><span data-stu-id="7de22-212">System.Security.SecureString</span></span>
- <span data-ttu-id="7de22-213">TimeSpan</span><span class="sxs-lookup"><span data-stu-id="7de22-213">TimeSpan</span></span>
- <span data-ttu-id="7de22-214">UInt16</span><span class="sxs-lookup"><span data-stu-id="7de22-214">UInt16</span></span>
- <span data-ttu-id="7de22-215">UInt32</span><span class="sxs-lookup"><span data-stu-id="7de22-215">UInt32</span></span>
- <span data-ttu-id="7de22-216">UInt64</span><span class="sxs-lookup"><span data-stu-id="7de22-216">UInt64</span></span>

### <a name="finding-the-language-mode-of-a-session-configuration"></a><span data-ttu-id="7de22-217">セッション構成の言語モードの検索</span><span class="sxs-lookup"><span data-stu-id="7de22-217">FINDING THE LANGUAGE MODE OF A SESSION CONFIGURATION</span></span>

<span data-ttu-id="7de22-218">セッション構成ファイルを使用してセッション構成を作成する場合、セッション構成には LanguageMode プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="7de22-218">When a session configuration is created by using a session configuration file, the session configuration has a LanguageMode property.</span></span> <span data-ttu-id="7de22-219">言語モードを確認するには、LanguageMode プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="7de22-219">You can find the language mode by getting the value of the LanguageMode property.</span></span>

```powershell
(Get-PSSessionConfiguration -Name Test).LanguageMode
FullLanguage
```

<span data-ttu-id="7de22-220">他のセッション構成では、セッション構成を使用して作成されたセッションの言語モードを見つけることで、言語モードを間接的に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="7de22-220">On other session configurations, you can find the language mode indirectly by finding the language mode of a session that is created by using the session configuration.</span></span>

### <a name="finding-the-language-mode-of-a-session"></a><span data-ttu-id="7de22-221">セッションの言語モードの検索</span><span class="sxs-lookup"><span data-stu-id="7de22-221">FINDING THE LANGUAGE MODE OF A SESSION</span></span>

<span data-ttu-id="7de22-222">セッション状態の LanguageMode プロパティの値を取得することで、FullLanguage または ConstrainedLanguage セッションの言語モードを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7de22-222">You can find the language mode of a FullLanguage or ConstrainedLanguage session by getting the value of the LanguageMode property of the session state.</span></span>

<span data-ttu-id="7de22-223">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7de22-223">For example:</span></span>

```powershell
$ExecutionContext.SessionState.LanguageMode
ConstrainedLanguage
```

<span data-ttu-id="7de22-224">ただし、RestrictedLanguage モードと NoLanguage モードのセッションでは、ドットメソッドを使用してプロパティ値を取得することはできません。</span><span class="sxs-lookup"><span data-stu-id="7de22-224">However, in sessions with RestrictedLanguage and NoLanguage modes, you cannot use the dot method to get property values.</span></span> <span data-ttu-id="7de22-225">代わりに、エラーメッセージに言語モードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-225">Instead, the error message reveals the language mode.</span></span>

<span data-ttu-id="7de22-226">RestrictedLanguage セッションでコマンドを実行すると、 `$ExecutionContext.SessionState.LanguageMode` PowerShell は PropertyReferenceNotSupportedInDataSection および VariableReferenceNotSupportedInDataSection エラーメッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="7de22-226">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a RestrictedLanguage session, PowerShell returns the PropertyReferenceNotSupportedInDataSection and VariableReferenceNotSupportedInDataSection error messages.</span></span>

- <span data-ttu-id="7de22-227">PropertyReferenceNotSupportedInDataSection: プロパティ参照は、制限付き言語モードまたはデータセクションでは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="7de22-227">PropertyReferenceNotSupportedInDataSection: Property references are not allowed in restricted language mode or a Data section.</span></span>
- <span data-ttu-id="7de22-228">VariableReferenceNotSupportedInDataSection は、制限された言語モードまたはデータセクションで参照できない変数を参照しています。</span><span class="sxs-lookup"><span data-stu-id="7de22-228">VariableReferenceNotSupportedInDataSection A variable that cannot be referenced in restricted language mode or a Data section is being referenced.</span></span>

<span data-ttu-id="7de22-229">`$ExecutionContext.SessionState.LanguageMode`NoLanguage セッションでコマンドを実行すると、PowerShell によって、スクリプトで許可されているエラーメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="7de22-229">When you run the `$ExecutionContext.SessionState.LanguageMode` command in a NoLanguage session, PowerShell returns the ScriptsNotAllowed error message.</span></span>

- <span data-ttu-id="7de22-230">スクリプト Notallowed: 構文は、この実行空間ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="7de22-230">ScriptsNotAllowed: The syntax is not supported by this runspace.</span></span> <span data-ttu-id="7de22-231">これは、言語なしモードであることが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7de22-231">This might be because it is in no-language mode.</span></span>

## <a name="see-also"></a><span data-ttu-id="7de22-232">関連項目</span><span class="sxs-lookup"><span data-stu-id="7de22-232">SEE ALSO</span></span>

- [<span data-ttu-id="7de22-233">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="7de22-233">about_Session_Configuration_Files</span></span>](about_Session_Configuration_Files.md)
- [<span data-ttu-id="7de22-234">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="7de22-234">about_Session_Configurations</span></span>](about_Session_Configurations.md)
