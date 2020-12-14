---
ms.date: 09/13/2016
ms.topic: reference
title: オンライン ヘルプのサポート
description: オンライン ヘルプのサポート
ms.openlocfilehash: 0164b5e6c6c8d66a6ab2467a8adfb7efffe0fe17
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645414"
---
# <a name="supporting-online-help"></a><span data-ttu-id="02f2a-103">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="02f2a-103">Supporting Online Help</span></span>

<span data-ttu-id="02f2a-104">PowerShell 3.0 以降では、 `Get-Help` powershell コマンドのオンライン機能をサポートする方法が2つあります。</span><span class="sxs-lookup"><span data-stu-id="02f2a-104">Beginning in PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for PowerShell commands.</span></span> <span data-ttu-id="02f2a-105">このトピックでは、さまざまなコマンドの種類に対してこの機能を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02f2a-105">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="02f2a-106">オンラインヘルプについて</span><span class="sxs-lookup"><span data-stu-id="02f2a-106">About Online Help</span></span>

<span data-ttu-id="02f2a-107">オンラインヘルプは、常に PowerShell の重要な部分でした。</span><span class="sxs-lookup"><span data-stu-id="02f2a-107">Online help has always been a vital part of PowerShell.</span></span> <span data-ttu-id="02f2a-108">コマンドレットでは、 `Get-Help` コマンドプロンプトでヘルプトピックを表示しますが、多くのユーザーは、色のコーディング、ハイパーリンク、コミュニティコンテンツおよび wiki ベースのドキュメントでのアイデアの共有など、オンラインでの閲覧のエクスペリエンスを好むことができます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-108">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="02f2a-109">最も重要なのは、更新可能なヘルプが登場する前に、オンラインヘルプで最新バージョンのヘルプファイルが提供されていたことです。</span><span class="sxs-lookup"><span data-stu-id="02f2a-109">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="02f2a-110">PowerShell 3.0 で更新可能なヘルプが登場したことにより、オンラインヘルプは依然として重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="02f2a-110">With the advent of Updatable Help in PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="02f2a-111">柔軟なユーザーエクスペリエンスに加えて、オンラインヘルプでは、ヘルプトピックをダウンロードするために更新可能なヘルプを使用しない、または使用できないユーザーにヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="02f2a-111">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="02f2a-112">Get-Help-オンラインのしくみ</span><span class="sxs-lookup"><span data-stu-id="02f2a-112">How Get-Help -Online Works</span></span>

<span data-ttu-id="02f2a-113">コマンドのオンラインヘルプトピックをユーザーが検索できるように、コマンドに `Get-Help` はオンラインパラメーターがあり、ユーザーの既定のインターネットブラウザーでコマンドのヘルプトピックのオンラインバージョンを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-113">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default internet browser.</span></span>

<span data-ttu-id="02f2a-114">たとえば、次のコマンドは、コマンドレットのオンラインヘルプトピックを開き `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-114">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="02f2a-115">を実装するために `Get-Help -Online` 、 `Get-Help` コマンドレットは次の場所にあるオンラインバージョンヘルプトピックの UNIFORM RESOURCE IDENTIFIER (URI) を検索します。</span><span class="sxs-lookup"><span data-stu-id="02f2a-115">To implement `Get-Help -Online`, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="02f2a-116">コマンドのヘルプトピックの「 **関連リンク** 」セクションの最初のリンク。</span><span class="sxs-lookup"><span data-stu-id="02f2a-116">The first link in the **Related Links** section of the help topic for the command.</span></span> <span data-ttu-id="02f2a-117">ヘルプトピックは、ユーザーのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f2a-117">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="02f2a-118">この機能は、PowerShell 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="02f2a-118">This feature was introduced in PowerShell 2.0.</span></span>

- <span data-ttu-id="02f2a-119">任意 **のコマンドのプロパティ。**</span><span class="sxs-lookup"><span data-stu-id="02f2a-119">The **HelpUri** property of any command.</span></span> <span data-ttu-id="02f2a-120">コマンドのヘルプトピックがユーザーのコンピューターにインストールされていない場合でも、**このプロパティにアクセスできます。**</span><span class="sxs-lookup"><span data-stu-id="02f2a-120">The **HelpUri** property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="02f2a-121">この機能は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="02f2a-121">This feature was introduced in PowerShell 3.0.</span></span>

  <span data-ttu-id="02f2a-122">`Get-Help` によって、[ **関連リンク** ] セクションの最初のエントリで URI が検索されてから **、"" というプロパティ** 値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-122">`Get-Help` looks for a URI in the first entry in the **Related Links** section before getting the **HelpUri** property value.</span></span> <span data-ttu-id="02f2a-123">プロパティ値が間違っているか変更されている場合は、最初の関連リンクに別の値を入力することで上書きできます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-123">If the property value is incorrect or has changed, you can override it by entering a different value in the first related link.</span></span> <span data-ttu-id="02f2a-124">ただし、最初の関連リンクは、ヘルプトピックがユーザーのコンピューターにインストールされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="02f2a-124">However, the first related link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="02f2a-125">コマンドヘルプトピックの最初の関連リンクへの URI の追加</span><span class="sxs-lookup"><span data-stu-id="02f2a-125">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="02f2a-126">コマンドの `Get-Help -Online` XML ベースのヘルプトピックの「 **関連リンク** 」セクションの最初のエントリに有効な URI を追加することで、任意のコマンドをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-126">You can support `Get-Help -Online` for any command by adding a valid URI to the first entry in the **Related Links** section of the XML-based help topic for the command.</span></span> <span data-ttu-id="02f2a-127">このオプションは、XML ベースのヘルプトピックでのみ有効で、ヘルプトピックがユーザーのコンピューターにインストールされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="02f2a-127">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="02f2a-128">ヘルプトピックがインストールされていて、URI が設定されている場合 **、この** 値はコマンドのプロパティよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-128">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span>

<span data-ttu-id="02f2a-129">この機能をサポートするには、要素内の最初の要素の下の要素に URI を記述する必要があり `maml:uri` `maml:relatedLinks/maml:navigationLink` `maml:relatedLinks` ます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-129">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="02f2a-130">次の XML は、正しい URI の配置を示しています。</span><span class="sxs-lookup"><span data-stu-id="02f2a-130">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="02f2a-131">`Online version:`要素内のテキストはベストプラクティスですが、 `maml:linkText` 必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="02f2a-131">The `Online version:` text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

```xml
<maml:relatedLinks>
    <maml:navigationLink>
        <maml:linkText>Online version:</maml:linkText>
        <maml:uri>https://go.microsoft.com/fwlink/?LinkID=113279</maml:uri>
    </maml:navigationLink>
    <maml:navigationLink>
        <maml:linkText>about_History</maml:linkText>
        <maml:uri/>
    </maml:navigationLink>
</maml:relatedLinks>
```

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="02f2a-132">コマンドへのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="02f2a-132">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="02f2a-133">このセクションでは、異なる種類のコマンドに、"コマンド" プロパティを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02f2a-133">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="02f2a-134">コマンドレットへのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="02f2a-134">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="02f2a-135">C# で記述さ **れたコマンド** レットの場合は、コマンドレットクラスに **コマンドレット** を追加します。</span><span class="sxs-lookup"><span data-stu-id="02f2a-135">For cmdlets written in C#, add a **HelpUri** attribute to the **Cmdlet** class.</span></span> <span data-ttu-id="02f2a-136">属性の値は、またはで始まる URI である必要があり `http` `https` ます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-136">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="02f2a-137">次のコードは、コマンドレットクラスのすべて **の属性を** 示して `Get-History` います。</span><span class="sxs-lookup"><span data-stu-id="02f2a-137">The following code shows the **HelpUri** attribute of the `Get-History` cmdlet class.</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "https://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="02f2a-138">高度な関数へのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="02f2a-138">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="02f2a-139">高度な関数の **場合は、** [属性] に [プロパティ] を **追加します** 。</span><span class="sxs-lookup"><span data-stu-id="02f2a-139">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="02f2a-140">プロパティの値は、"http" または "https" で始まる URI である必要があります。</span><span class="sxs-lookup"><span data-stu-id="02f2a-140">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="02f2a-141">次のコードは、関数のすべて **の属性を** 示しています。 `New-Calendar`</span><span class="sxs-lookup"><span data-stu-id="02f2a-141">The following code shows the **HelpUri** attribute of the `New-Calendar` function</span></span>

```powershell
function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="https://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="02f2a-142">CIM コマンドへの属性の追加</span><span class="sxs-lookup"><span data-stu-id="02f2a-142">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="02f2a-143">CIM コマンドの **場合は、** CDXML ファイル内のコマンド **レットメタデータ** 要素に、"/" 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="02f2a-143">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span>
<span data-ttu-id="02f2a-144">属性の値は、またはで始まる URI である必要があり `http` `https` ます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-144">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="02f2a-145">次のコードは、CIM コマンドのすべての属性を示しています。 `Start-Debug`</span><span class="sxs-lookup"><span data-stu-id="02f2a-145">The following code shows the HelpUri attribute of the `Start-Debug` CIM command</span></span>

```xml
<CmdletMetadata Verb="Debug" HelpUri="https://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="02f2a-146">ワークフローへの属性の追加</span><span class="sxs-lookup"><span data-stu-id="02f2a-146">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="02f2a-147">PowerShell 言語で記述されたワークフローの場合は、を追加 **します。** ワークフローコードに対する ExternalHelp コメントディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="02f2a-147">For workflows that are written in the PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="02f2a-148">ディレクティブの値は、またはで始まる URI である必要があり `http` `https` ます。</span><span class="sxs-lookup"><span data-stu-id="02f2a-148">The value of the directive must be a URI that begins with `http` or `https`.</span></span>

> [!NOTE]
> <span data-ttu-id="02f2a-149">このプロパティは、PowerShell の XAML ベースのワークフローではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="02f2a-149">The HelpUri property is not supported for XAML-based workflows in PowerShell.</span></span>

<span data-ttu-id="02f2a-150">次のコードは、を示しています。ワークフローファイル内の ExternalHelp ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="02f2a-150">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "https://go.microsoft.com/fwlink/?LinkID=138338"
```
