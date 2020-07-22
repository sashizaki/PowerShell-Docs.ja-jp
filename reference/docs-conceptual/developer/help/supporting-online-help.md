---
title: オンライン ヘルプのサポート
ms.date: 09/13/2016
ms.openlocfilehash: b2d8eae2137e0e564a9baf271962b8669dd5eac5
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892865"
---
# <a name="supporting-online-help"></a><span data-ttu-id="42f2d-102">オンライン ヘルプのサポート</span><span class="sxs-lookup"><span data-stu-id="42f2d-102">Supporting Online Help</span></span>

<span data-ttu-id="42f2d-103">PowerShell 3.0 以降では、 `Get-Help` powershell コマンドのオンライン機能をサポートする方法が2つあります。</span><span class="sxs-lookup"><span data-stu-id="42f2d-103">Beginning in PowerShell 3.0, there are two ways to support the `Get-Help` Online feature for PowerShell commands.</span></span> <span data-ttu-id="42f2d-104">このトピックでは、さまざまなコマンドの種類に対してこの機能を実装する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42f2d-104">This topic explains how to implement this feature for different command types.</span></span>

## <a name="about-online-help"></a><span data-ttu-id="42f2d-105">オンラインヘルプについて</span><span class="sxs-lookup"><span data-stu-id="42f2d-105">About Online Help</span></span>

<span data-ttu-id="42f2d-106">オンラインヘルプは、常に PowerShell の重要な部分でした。</span><span class="sxs-lookup"><span data-stu-id="42f2d-106">Online help has always been a vital part of PowerShell.</span></span> <span data-ttu-id="42f2d-107">コマンドレットでは、 `Get-Help` コマンドプロンプトでヘルプトピックを表示しますが、多くのユーザーは、色のコーディング、ハイパーリンク、コミュニティコンテンツおよび wiki ベースのドキュメントでのアイデアの共有など、オンラインでの閲覧のエクスペリエンスを好むことができます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-107">Although the `Get-Help` cmdlet displays help topics at the command prompt, many users prefer the experience of reading online, including color-coding, hyperlinks, and sharing ideas in Community Content and wiki-based documents.</span></span> <span data-ttu-id="42f2d-108">最も重要なのは、更新可能なヘルプが登場する前に、オンラインヘルプで最新バージョンのヘルプファイルが提供されていたことです。</span><span class="sxs-lookup"><span data-stu-id="42f2d-108">Most importantly, before the advent of Updatable Help, online help provided the most up-to-date version of the help files.</span></span>

<span data-ttu-id="42f2d-109">PowerShell 3.0 で更新可能なヘルプが登場したことにより、オンラインヘルプは依然として重要な役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="42f2d-109">With the advent of Updatable Help in PowerShell 3.0, online help still plays a vital role.</span></span> <span data-ttu-id="42f2d-110">柔軟なユーザーエクスペリエンスに加えて、オンラインヘルプでは、ヘルプトピックをダウンロードするために更新可能なヘルプを使用しない、または使用できないユーザーにヘルプを提供します。</span><span class="sxs-lookup"><span data-stu-id="42f2d-110">In addition to the flexible user experience, online help provides help to users who do not or cannot use Updatable Help to download help topics.</span></span>

## <a name="how-get-help--online-works"></a><span data-ttu-id="42f2d-111">Get-help-Online のしくみ</span><span class="sxs-lookup"><span data-stu-id="42f2d-111">How Get-Help -Online Works</span></span>

<span data-ttu-id="42f2d-112">コマンドのオンラインヘルプトピックをユーザーが検索できるように、コマンドに `Get-Help` はオンラインパラメーターがあり、ユーザーの既定のインターネットブラウザーでコマンドのヘルプトピックのオンラインバージョンを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-112">To help users find the online help topics for commands, the `Get-Help` command has an Online parameter that opens the online version of help topic for a command in the user's default internet browser.</span></span>

<span data-ttu-id="42f2d-113">たとえば、次のコマンドは、コマンドレットのオンラインヘルプトピックを開き `Invoke-Command` ます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-113">For example, the following command opens the online help topic for the `Invoke-Command` cmdlet.</span></span>

```powershell
Get-Help Invoke-Command -Online
```

<span data-ttu-id="42f2d-114">を実装するために `Get-Help -Online` 、 `Get-Help` コマンドレットは次の場所にあるオンラインバージョンヘルプトピックの UNIFORM RESOURCE IDENTIFIER (URI) を検索します。</span><span class="sxs-lookup"><span data-stu-id="42f2d-114">To implement `Get-Help -Online`, the `Get-Help` cmdlet looks for a Uniform Resource Identifier (URI) for the online version help topic in the following locations.</span></span>

- <span data-ttu-id="42f2d-115">コマンドのヘルプトピックの「**関連リンク**」セクションの最初のリンク。</span><span class="sxs-lookup"><span data-stu-id="42f2d-115">The first link in the **Related Links** section of the help topic for the command.</span></span> <span data-ttu-id="42f2d-116">ヘルプトピックは、ユーザーのコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f2d-116">The help topic must be installed on the user's computer.</span></span> <span data-ttu-id="42f2d-117">この機能は、PowerShell 2.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="42f2d-117">This feature was introduced in PowerShell 2.0.</span></span>

- <span data-ttu-id="42f2d-118">任意**のコマンドのプロパティ。**</span><span class="sxs-lookup"><span data-stu-id="42f2d-118">The **HelpUri** property of any command.</span></span> <span data-ttu-id="42f2d-119">コマンドのヘルプトピックがユーザーのコンピューターにインストールされていない場合でも、**このプロパティにアクセスできます。**</span><span class="sxs-lookup"><span data-stu-id="42f2d-119">The **HelpUri** property is accessible even when the help topic for the command is not installed on the user's computer.</span></span> <span data-ttu-id="42f2d-120">この機能は、PowerShell 3.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="42f2d-120">This feature was introduced in PowerShell 3.0.</span></span>

  <span data-ttu-id="42f2d-121">`Get-Help`によって、[**関連リンク**] セクションの最初のエントリで URI が検索されてから **、"" というプロパティ**値が取得されます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-121">`Get-Help` looks for a URI in the first entry in the **Related Links** section before getting the **HelpUri** property value.</span></span> <span data-ttu-id="42f2d-122">プロパティ値が間違っているか変更されている場合は、最初の関連リンクに別の値を入力することで上書きできます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-122">If the property value is incorrect or has changed, you can override it by entering a different value in the first related link.</span></span> <span data-ttu-id="42f2d-123">ただし、最初の関連リンクは、ヘルプトピックがユーザーのコンピューターにインストールされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="42f2d-123">However, the first related link works only when the help topics are installed on the user's computer.</span></span>

## <a name="adding-a-uri-to-the-first-related-link-of-a-command-help-topic"></a><span data-ttu-id="42f2d-124">コマンドヘルプトピックの最初の関連リンクへの URI の追加</span><span class="sxs-lookup"><span data-stu-id="42f2d-124">Adding a URI to the first related link of a command help topic</span></span>

<span data-ttu-id="42f2d-125">コマンドの `Get-Help -Online` XML ベースのヘルプトピックの「**関連リンク**」セクションの最初のエントリに有効な URI を追加することで、任意のコマンドをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-125">You can support `Get-Help -Online` for any command by adding a valid URI to the first entry in the **Related Links** section of the XML-based help topic for the command.</span></span> <span data-ttu-id="42f2d-126">このオプションは、XML ベースのヘルプトピックでのみ有効で、ヘルプトピックがユーザーのコンピューターにインストールされている場合にのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="42f2d-126">This option is valid only in XML-based help topics and works only when the help topic is installed on the user's computer.</span></span> <span data-ttu-id="42f2d-127">ヘルプトピックがインストールされていて、URI が設定されている場合 **、この**値はコマンドのプロパティよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-127">When the help topic is installed and the URI is populated, this value takes precedence over the **HelpUri** property of the command.</span></span>

<span data-ttu-id="42f2d-128">この機能をサポートするには、要素内の最初の要素の下の要素に URI を記述する必要があり `maml:uri` `maml:relatedLinks/maml:navigationLink` `maml:relatedLinks` ます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-128">To support this feature, the URI must appear in the `maml:uri` element under the first `maml:relatedLinks/maml:navigationLink` element in the `maml:relatedLinks` element.</span></span>

<span data-ttu-id="42f2d-129">次の XML は、正しい URI の配置を示しています。</span><span class="sxs-lookup"><span data-stu-id="42f2d-129">The following XML shows the correct placement of the URI.</span></span> <span data-ttu-id="42f2d-130">`Online version:`要素内のテキストはベストプラクティスですが、 `maml:linkText` 必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="42f2d-130">The `Online version:` text in the `maml:linkText` element is a best practice, but it is not required.</span></span>

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

## <a name="adding-the-helpuri-property-to-a-command"></a><span data-ttu-id="42f2d-131">コマンドへのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="42f2d-131">Adding the HelpUri property to a command</span></span>

<span data-ttu-id="42f2d-132">このセクションでは、異なる種類のコマンドに、"コマンド" プロパティを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42f2d-132">This section shows how to add the HelpUri property to commands of different types.</span></span>

### <a name="adding-a-helpuri-property-to-a-cmdlet"></a><span data-ttu-id="42f2d-133">コマンドレットへのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="42f2d-133">Adding a HelpUri Property to a Cmdlet</span></span>

<span data-ttu-id="42f2d-134">C# で記述さ**れたコマンド**レットの場合は、コマンドレットクラスに**コマンドレット**を追加します。</span><span class="sxs-lookup"><span data-stu-id="42f2d-134">For cmdlets written in C#, add a **HelpUri** attribute to the **Cmdlet** class.</span></span> <span data-ttu-id="42f2d-135">属性の値は、またはで始まる URI である必要があり `http` `https` ます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-135">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="42f2d-136">次のコードは、コマンドレットクラスのすべて**の属性を**示して `Get-History` います。</span><span class="sxs-lookup"><span data-stu-id="42f2d-136">The following code shows the **HelpUri** attribute of the `Get-History` cmdlet class.</span></span>

```csharp
[Cmdlet(VerbsCommon.Get, "History", HelpUri = "https://go.microsoft.com/fwlink/?LinkID=001122")]
```

### <a name="adding-a-helpuri-property-to-an-advanced-function"></a><span data-ttu-id="42f2d-137">高度な関数へのプロパティの追加</span><span class="sxs-lookup"><span data-stu-id="42f2d-137">Adding a HelpUri Property to an Advanced Function</span></span>

<span data-ttu-id="42f2d-138">高度な関数の**場合は、** [属性] に [プロパティ] を**追加します**。</span><span class="sxs-lookup"><span data-stu-id="42f2d-138">For advanced functions, add a **HelpUri** property to the **CmdletBinding** attribute.</span></span> <span data-ttu-id="42f2d-139">プロパティの値は、"http" または "https" で始まる URI である必要があります。</span><span class="sxs-lookup"><span data-stu-id="42f2d-139">The value of the property must be a URI that begins with "http" or "https".</span></span>

<span data-ttu-id="42f2d-140">次のコードは、関数のすべて**の属性を**示しています。 `New-Calendar`</span><span class="sxs-lookup"><span data-stu-id="42f2d-140">The following code shows the **HelpUri** attribute of the `New-Calendar` function</span></span>

```powershell
function New-Calendar {
    [CmdletBinding(SupportsShouldProcess=$true,
    HelpURI="https://go.microsoft.com/fwlink/?LinkID=01122")]
```

### <a name="adding-a-helpuri-attribute-to-a-cim-command"></a><span data-ttu-id="42f2d-141">CIM コマンドへの属性の追加</span><span class="sxs-lookup"><span data-stu-id="42f2d-141">Adding a HelpUri Attribute to a CIM Command</span></span>

<span data-ttu-id="42f2d-142">CIM コマンドの**場合は、** CDXML ファイル内のコマンド**レットメタデータ**要素に、"/" 属性を追加します。</span><span class="sxs-lookup"><span data-stu-id="42f2d-142">For CIM commands, add a **HelpUri** attribute to the **CmdletMetadata** element in the CDXML file.</span></span>
<span data-ttu-id="42f2d-143">属性の値は、またはで始まる URI である必要があり `http` `https` ます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-143">The value of the attribute must be a URI that begins with `http` or `https`.</span></span>

<span data-ttu-id="42f2d-144">次のコードは、CIM コマンドのすべての属性を示しています。 `Start-Debug`</span><span class="sxs-lookup"><span data-stu-id="42f2d-144">The following code shows the HelpUri attribute of the `Start-Debug` CIM command</span></span>

```xml
<CmdletMetadata Verb="Debug" HelpUri="https://go.microsoft.com/fwlink/?LinkID=001122"/>
```

### <a name="adding-a-helpuri-attribute-to-a-workflow"></a><span data-ttu-id="42f2d-145">ワークフローへの属性の追加</span><span class="sxs-lookup"><span data-stu-id="42f2d-145">Adding a HelpUri Attribute to a Workflow</span></span>

<span data-ttu-id="42f2d-146">PowerShell 言語で記述されたワークフローの場合は、を追加**します。** ワークフローコードに対する ExternalHelp コメントディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="42f2d-146">For workflows that are written in the PowerShell language, add an **.ExternalHelp** comment directive to the workflow code.</span></span> <span data-ttu-id="42f2d-147">ディレクティブの値は、またはで始まる URI である必要があり `http` `https` ます。</span><span class="sxs-lookup"><span data-stu-id="42f2d-147">The value of the directive must be a URI that begins with `http` or `https`.</span></span>

> [!NOTE]
> <span data-ttu-id="42f2d-148">このプロパティは、PowerShell の XAML ベースのワークフローではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="42f2d-148">The HelpUri property is not supported for XAML-based workflows in PowerShell.</span></span>

<span data-ttu-id="42f2d-149">次のコードは、を示しています。ワークフローファイル内の ExternalHelp ディレクティブ。</span><span class="sxs-lookup"><span data-stu-id="42f2d-149">The following code shows the .ExternalHelp directive in a workflow file.</span></span>

```powershell
# .ExternalHelp "https://go.microsoft.com/fwlink/?LinkID=138338"
```
