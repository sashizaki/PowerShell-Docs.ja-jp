---
title: PlatyPS を使用して XML ベースのヘルプを作成する
description: PlatyPS の使用は、XML ベースのヘルプを作成するための高速で効率的な方法です。
ms.date: 07/21/2020
ms.openlocfilehash: 79cf8c077a07bf1e7aa8ea1ea799be5f8d4af12c
ms.sourcegitcommit: 37abf054ad9eda8813be8ff4487803b10e1842ef
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "86972584"
---
# <a name="create-xml-based-help-using-platyps"></a><span data-ttu-id="cbea1-103">PlatyPS を使用して XML ベースのヘルプを作成する</span><span class="sxs-lookup"><span data-stu-id="cbea1-103">Create XML-based help using PlatyPS</span></span>

<span data-ttu-id="cbea1-104">PowerShell モジュールを作成するときは、作成するコマンドレットの詳細なヘルプを必ず含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cbea1-104">When creating a PowerShell module, it is always recommended that you include detailed help for the cmdlets you create.</span></span> <span data-ttu-id="cbea1-105">コンパイル済みのコードにコマンドレットが実装されている場合は、XML ベースのヘルプを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-105">If your cmdlets are implemented in compiled code, you must use the XML-based help.</span></span> <span data-ttu-id="cbea1-106">この XML 形式は、Microsoft Assistance Markup Language (MAML) と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="cbea1-106">This XML format is known as the Microsoft Assistance Markup Language (MAML).</span></span>

<span data-ttu-id="cbea1-107">従来の PowerShell SDK のドキュメントでは、モジュールにパッケージ化された PowerShell コマンドレットのヘルプを作成する方法の詳細について説明しています。</span><span class="sxs-lookup"><span data-stu-id="cbea1-107">The legacy PowerShell SDK documentation covers the details of creating help for PowerShell cmdlets packaged into modules.</span></span> <span data-ttu-id="cbea1-108">ただし、PowerShell には、XML ベースのヘルプを作成するためのツールは用意されていません。</span><span class="sxs-lookup"><span data-stu-id="cbea1-108">However, PowerShell does not provide any tools for creating the XML-based help.</span></span> <span data-ttu-id="cbea1-109">SDK ドキュメントでは、MAML ヘルプの構造について説明していますが、複雑で深く入れ子になった MAML コンテンツを作成するタスクは手動で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-109">The SDK documentation explains the structure of MAML help, but leaves you the task of creating the complex, and deeply nested, MAML content by hand.</span></span>

<span data-ttu-id="cbea1-110">ここで [PlatyPS][] モジュールが役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-110">This is where the [PlatyPS][] module can help.</span></span>

## <a name="what-is-platyps"></a><span data-ttu-id="cbea1-111">PlatyPS とは</span><span class="sxs-lookup"><span data-stu-id="cbea1-111">What is PlatyPS?</span></span>

<span data-ttu-id="cbea1-112">PlatyPS は、MAML の作成とメンテナンスを容易にするために "_ハッカソン_" プロジェクトとして始まった、[オープンソース][platyps-repo]のツールです。</span><span class="sxs-lookup"><span data-stu-id="cbea1-112">PlatyPS is an [open-source][platyps-repo] tool that started as a _hackathon_ project to make the creation and maintenance of MAML easier.</span></span> <span data-ttu-id="cbea1-113">PlatyPS を使用すると、ご自身のモジュール内の各コマンドレットについて、パラメーター セットの構文と個々のパラメーターを文書化できます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-113">PlatyPS documents the syntax of parameter sets and the individual parameters for each cmdlet in your module.</span></span> <span data-ttu-id="cbea1-114">PlatyPS によって、構文情報を含む構造化された[マークダウン][] ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-114">PlatyPS creates structured [Markdown][] files that contain the syntax information.</span></span> <span data-ttu-id="cbea1-115">説明が作成されたり、例が提供されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="cbea1-115">It can't create descriptions or provide examples.</span></span>

<span data-ttu-id="cbea1-116">PlatyPS によって、説明と例を入力するためのプレースホルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-116">PlatyPS creates placeholders for you to fill in descriptions and examples.</span></span> <span data-ttu-id="cbea1-117">必要な情報を追加した後、PlatyPS でマークダウン ファイルを MAML ファイルにコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="cbea1-117">After adding the required information, PlatyPS compiles the Markdown files into MAML files.</span></span> <span data-ttu-id="cbea1-118">PowerShell のヘルプ システムでは、プレーンテキストの概念説明ヘルプ ファイル (about トピック) も使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-118">PowerShell's help system also allows for plain-text conceptual help files (about topics).</span></span> <span data-ttu-id="cbea1-119">PlatyPS には、新しい _about_ ファイル用の構造化された Markdown テンプレートを作成するためのコマンドレットがありますが、これらの `about_*.help.txt` ファイルは手動でメンテナンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-119">PlatyPS has a cmdlet to create a structured Markdown template for a new _about_ file, but these `about_*.help.txt` files must be maintained manually.</span></span>

<span data-ttu-id="cbea1-120">モジュールには、MAML とテキストのヘルプ ファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-120">You can include the MAML and Text help files with your module.</span></span> <span data-ttu-id="cbea1-121">PlatyPS を使用して、ヘルプ ファイルを CAB パッケージにコンパイルし、更新可能なヘルプ用にホストすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-121">You can also use PlatyPS to compile the help files into a CAB package that can be hosted for updateable help.</span></span>

## <a name="get-started-using-platyps"></a><span data-ttu-id="cbea1-122">PlatyPS を使用して開始する</span><span class="sxs-lookup"><span data-stu-id="cbea1-122">Get started using PlatyPS</span></span>

<span data-ttu-id="cbea1-123">まず、PowerShell ギャラリーから PlatyPS をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-123">First you must install PlatyPS from the PowerShell Gallery.</span></span>

```powershell
Install-Module platyps -Force
Import-Module platyps
```

<span data-ttu-id="cbea1-124">次のフローチャートは、PowerShell のリファレンス コンテンツを作成または更新するプロセスの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="cbea1-124">The following flowchart outlines the process for creating or updating PowerShell reference content.</span></span>

:::image type="content" source="./media/create-help-using-platyps/cmdlet-ref-flow-v2.png" alt-text="PlatyPS を使用して XML ベースのヘルプを作成するためのワークフロー":::

##  <a name="create-markdown-content-for-a-powershell-module"></a><span data-ttu-id="cbea1-126">PowerShell モジュールの Markdown コンテンツを作成する</span><span class="sxs-lookup"><span data-stu-id="cbea1-126">Create Markdown content for a PowerShell module</span></span>

1. <span data-ttu-id="cbea1-127">新しいモジュールをセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="cbea1-127">Import your new module into the session.</span></span> <span data-ttu-id="cbea1-128">文書化する必要があるモジュールごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-128">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="cbea1-129">次のコマンドを実行してモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="cbea1-129">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="cbea1-130">PlatyPS を使用して、モジュール ページのマークダウン ファイルと、モジュール内の関連するすべてのコマンドレットを生成します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-130">Use PlatyPS to generate Markdown files for your module page and all associated cmdlets within the module.</span></span> <span data-ttu-id="cbea1-131">文書化する必要があるモジュールごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-131">Repeat this step for each module you need to document.</span></span>

   ```powershell
   $OutputFolder = <output path>
   $parameters = @{
       Module = <ModuleName>
       OutputFolder = $OutputFolder
       AlphabeticParamsOrder = $true
       WithModulePage = $true
       ExcludeDontShow = $true
       Encoding = 'UTF8BOM'
   }
   New-MarkdownHelp @parameters

   New-MarkdownAboutHelp -OutputFolder $OutputFolder -AboutName "topic_name"
   ```

   <span data-ttu-id="cbea1-132">出力フォルダーが存在しない場合は、`New-MarkdownHelp` によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-132">If the output folder does not exist, `New-MarkdownHelp` creates it.</span></span> <span data-ttu-id="cbea1-133">この例では、`New-MarkdownHelp` によって、モジュール内のコマンドレットごとにマークダウン ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-133">In this example, `New-MarkdownHelp` creates a Markdown file for each cmdlet in the module.</span></span> <span data-ttu-id="cbea1-134">また、`<ModuleName>.md` という名前のファイル内に "_モジュール ページ_" も作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-134">It also creates the _module page_ in a file named `<ModuleName>.md`.</span></span> <span data-ttu-id="cbea1-135">このモジュール ページには、モジュールに含まれるコマンドレットの一覧と、**概要**説明のプレースホルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cbea1-135">This module page contains a list of the cmdlets contained in the module and placeholders for the **Synopsis** description.</span></span> <span data-ttu-id="cbea1-136">モジュール ページのメタデータは、モジュール マニフェストから取得され、PlatyPS で HelpInfo XML ファイルを作成するために使用されます ([以下](#creating-an-updateable-help-package)を参照)。</span><span class="sxs-lookup"><span data-stu-id="cbea1-136">The metadata in the module page comes from the module manifest and is used by PlatyPS to create the HelpInfo XML file (as explained [below](#creating-an-updateable-help-package)).</span></span>

   <span data-ttu-id="cbea1-137">`New-MarkdownAboutHelp` によって、`about_topic_name.md` という名前の _about_ ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-137">`New-MarkdownAboutHelp` creates a new _about_ file named `about_topic_name.md`.</span></span>

   <span data-ttu-id="cbea1-138">詳細については、「[New-MarkdownHelp][]」と「[New-MarkdownAboutHelp][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-138">For more information, see [New-MarkdownHelp][] and [New-MarkdownAboutHelp][].</span></span>

### <a name="update-existing-markdown-content-when-the-module-changes"></a><span data-ttu-id="cbea1-139">モジュールを変更したときに既存の Markdown コンテンツを更新する</span><span class="sxs-lookup"><span data-stu-id="cbea1-139">Update existing Markdown content when the module changes</span></span>

<span data-ttu-id="cbea1-140">PlatyPS を使用して、モジュールの既存のマークダウン ファイルを更新することもできます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-140">PlatyPS can also update existing Markdown files for a module.</span></span> <span data-ttu-id="cbea1-141">この手順は、新しいコマンドレット、新しいパラメーター、または変更されたパラメーターを持つ既存のモジュールを更新するために使用します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-141">Use this step to update existing modules that have new cmdlets, new parameters, or parameters that have changed.</span></span>

1. <span data-ttu-id="cbea1-142">新しいモジュールをセッションにインポートします。</span><span class="sxs-lookup"><span data-stu-id="cbea1-142">Import your new module into the session.</span></span> <span data-ttu-id="cbea1-143">文書化する必要があるモジュールごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-143">Repeat this step for each module you need to document.</span></span>

   <span data-ttu-id="cbea1-144">次のコマンドを実行してモジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="cbea1-144">Run the following command to import your modules:</span></span>

   ```powershell
   Import-Module <your module name>
   ```

1. <span data-ttu-id="cbea1-145">PlatyPS を使用して、モジュールのランディング ページのマークダウン ファイルと、モジュール内のすべての関連コマンドレットを更新します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-145">Use PlatyPS to update Markdown files for your module landing page and all associated cmdlets within the module.</span></span> <span data-ttu-id="cbea1-146">文書化する必要があるモジュールごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-146">Repeat this step for each module you need to document.</span></span>

   ```powershell
   $parameters = @{
       Path = <folder with Markdown>
       RefreshModulePage = $true
       AlphabeticParamsOrder = $true
       UpdateInputOutput = $true
       ExcludeDontShow = $true
       LogPath = <path to store log file>
       Encoding = 'UTF8BOM'
   }
   Update-MarkdownHelpModule @parameters
   ```

   <span data-ttu-id="cbea1-147">`Update-MarkdownHelpModule` によって、指定したフォルダー内のコマンドレットとモジュールのマークダウン ファイルが更新されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-147">`Update-MarkdownHelpModule` updates the cmdlet and module Markdown files in the specified folder.</span></span>
   <span data-ttu-id="cbea1-148">`about_*.md` ファイルは更新されません。</span><span class="sxs-lookup"><span data-stu-id="cbea1-148">It does not update the `about_*.md` files.</span></span> <span data-ttu-id="cbea1-149">モジュール ファイル (`ModuleName.md`) に、コマンドレット ファイルに追加された新しい**概要**のテキストが渡されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-149">The module file (`ModuleName.md`) receives any new **Synopsis** text that has been added to the cmdlet files.</span></span> <span data-ttu-id="cbea1-150">コマンドレット ファイルの更新には、次の変更が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-150">Updates to cmdlet files include the following change:</span></span>

   - <span data-ttu-id="cbea1-151">新しいパラメーター セット</span><span class="sxs-lookup"><span data-stu-id="cbea1-151">New parameter sets</span></span>
   - <span data-ttu-id="cbea1-152">新しいパラメーター</span><span class="sxs-lookup"><span data-stu-id="cbea1-152">New parameters</span></span>
   - <span data-ttu-id="cbea1-153">更新されたパラメーターのメタデータ</span><span class="sxs-lookup"><span data-stu-id="cbea1-153">Updated parameter metadata</span></span>
   - <span data-ttu-id="cbea1-154">更新された入力および出力の種類の情報</span><span class="sxs-lookup"><span data-stu-id="cbea1-154">Updated input and output type information</span></span>

   <span data-ttu-id="cbea1-155">詳細については、「[Update-MarkdownHelpModule][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-155">For more information, see [Update-MarkdownHelpModule][].</span></span>

## <a name="edit-the-new-or-updated-markdown-files"></a><span data-ttu-id="cbea1-156">新しいまたは更新されたマークダウン ファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="cbea1-156">Edit the new or updated Markdown files</span></span>

<span data-ttu-id="cbea1-157">PlatyPS によって、パラメーター セットの構文と個々のパラメーターが文書化されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-157">PlatyPS documents the syntax of the parameter sets and the individual parameters.</span></span> <span data-ttu-id="cbea1-158">説明が作成されたり、例が提供されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="cbea1-158">It can't create descriptions or provide examples.</span></span> <span data-ttu-id="cbea1-159">コンテンツが必要な特定の領域は、中かっこ内に含まれています。</span><span class="sxs-lookup"><span data-stu-id="cbea1-159">The specific areas where content is needed are contained in curly braces.</span></span> <span data-ttu-id="cbea1-160">例: `{{ Fill in the Description }}`</span><span class="sxs-lookup"><span data-stu-id="cbea1-160">For example: `{{ Fill in the Description }}`</span></span>

:::image type="content" source="./media/create-help-using-platyps/placeholders-example.png" alt-text="VS Code にプレースホルダーが表示されている Markdown テンプレート":::

<span data-ttu-id="cbea1-162">概要、コマンドレットの説明、各パラメーターの説明、および少なくとも 1 つの例を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-162">You need to add a synopsis, a description of the cmdlet, descriptions for each parameter, and at least one example.</span></span>

<span data-ttu-id="cbea1-163">PowerShell コンテンツの記述の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-163">For detailed information about writing PowerShell content, see the following articles:</span></span>

- [<span data-ttu-id="cbea1-164">PowerShell のスタイル ガイド</span><span class="sxs-lookup"><span data-stu-id="cbea1-164">PowerShell style guide</span></span>](/powershell/scripting/community/contributing/powershell-style-guide)
- [<span data-ttu-id="cbea1-165">参照記事の編集</span><span class="sxs-lookup"><span data-stu-id="cbea1-165">Editing reference articles</span></span>](/powershell/scripting/community/contributing/editing-cmdlet-ref)

> [!NOTE]
> <span data-ttu-id="cbea1-166">PlatyPS には、コマンドレット リファレンスに使用する特定のスキーマがあります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-166">PlatyPS has a specific schema that is uses for cmdlet reference.</span></span> <span data-ttu-id="cbea1-167">そのスキーマでは、ドキュメントの特定のセクションの特定の Markdown ブロックのみが許可されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-167">That schema only allows certain Markdown blocks in specific sections of the document.</span></span> <span data-ttu-id="cbea1-168">コンテンツを間違った場所に配置すると、PlatyPS のビルド ステップは失敗します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-168">If you put content in the wrong location, the PlatyPS build step fails.</span></span> <span data-ttu-id="cbea1-169">詳細については、PlatyPS リポジトリにある[スキーマ][]のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-169">For more information, see the [schema][] documentation in the PlatyPS repository.</span></span> <span data-ttu-id="cbea1-170">整形式のコマンドレット リファレンスの完全な例については、「[Get-Item][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-170">For a complete example of well-formed cmdlet reference, see [Get-Item][].</span></span>

<span data-ttu-id="cbea1-171">各コマンドレットに必要なコンテンツを指定したら、モジュールのランディング ページを必ず更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-171">After providing the required content for each of your cmdlets, you need to make sure that you update the module landing page.</span></span> <span data-ttu-id="cbea1-172">`<module-name>.md` ファイル内の YAML メタデータでモジュールの `Module Guid` と `Download Help Link` の値が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-172">Verify your module has the correct `Module Guid` and `Download Help Link` values in the YAML metadata of the `<module-name>.md` file.</span></span> <span data-ttu-id="cbea1-173">不足しているメタデータがあれば追加します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-173">Add any missing metadata.</span></span>

<span data-ttu-id="cbea1-174">また、一部のコマンドレットに**概要** (_短い説明_) がないことに気付く場合もあります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-174">Also, you may notice that some cmdlets may be missing a **Synopsis** (_short description_).</span></span> <span data-ttu-id="cbea1-175">次のコマンドを実行すると、モジュールのランディング ページが**概要**説明のテキストで更新されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-175">The following command updates the module landing page with your **Synopsis** description text.</span></span> <span data-ttu-id="cbea1-176">モジュールのランディング ページを開いて、説明を確認します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-176">Open the module landing page to verify the descriptions.</span></span>

```powershell
Update-MarkdownHelpModule –Path <full path output folder> -RefreshModulePage
```

<span data-ttu-id="cbea1-177">すべてのコンテンツを入力したので、PowerShell コンソールで `Get-Help` によって表示される MAML ヘルプ ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-177">Now that you have entered all the content, you can create the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

## <a name="create-the-external-help-files"></a><span data-ttu-id="cbea1-178">外部ヘルプ ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cbea1-178">Create the external help files</span></span>

<span data-ttu-id="cbea1-179">この手順では、PowerShell コンソールで `Get-Help` によって表示される MAML ヘルプ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-179">This step creates the MAML help files that are displayed by `Get-Help` in the PowerShell console.</span></span>

<span data-ttu-id="cbea1-180">MAML ファイルをビルドするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-180">To build the MAML files, run the following command:</span></span>

```powershell
New-ExternalHelp –Path <folder with MDs> -OutputPath <output help folder>
```

<span data-ttu-id="cbea1-181">`New-ExternalHelp` によって、すべてのコマンドレット マークダウン ファイルが 1 つ以上の MAML ファイルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-181">`New-ExternalHelp` converts all of the cmdlet Markdown files into one (or more) MAML files.</span></span> <span data-ttu-id="cbea1-182">概要ファイルは、`about_topic_name.help.txt` という形式の名前を持つプレーンテキスト ファイルに変換されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-182">About files are converted to plain-text files with the following name format: `about_topic_name.help.txt`.</span></span>
<span data-ttu-id="cbea1-183">Markdown コンテンツは、PlatyPS スキーマの要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-183">The Markdown content must meet the requirement of the PlatyPS schema.</span></span> <span data-ttu-id="cbea1-184">コンテンツがスキーマに従っていない場合、`New-ExternalHelp` はエラーで終了します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-184">`New-ExternalHelp` will exits with errors when the content does not follow the schema.</span></span> <span data-ttu-id="cbea1-185">ファイルを編集してスキーマ違反を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-185">You must edit the files to fix the schema violations.</span></span>

> [!CAUTION]
> <span data-ttu-id="cbea1-186">PlatyPS は、`about_*.md` ファイルのプレーンテキストへの変換には適していません。</span><span class="sxs-lookup"><span data-stu-id="cbea1-186">PlatyPS does a poor job converting the `about_*.md` files to plain text.</span></span> <span data-ttu-id="cbea1-187">許容できる結果を得るには、非常に単純な Markdown を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-187">You must use very simple Markdown to get acceptable results.</span></span> <span data-ttu-id="cbea1-188">ファイルを PlatyPS で変換するのではなく、プレーンテキストの `about_topic_name.help.txt` 形式のままにすることも検討してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-188">You may want to maintain the files in plain-text `about_topic_name.help.txt` format, rather than allowing PlatyPS to convert them.</span></span>

<span data-ttu-id="cbea1-189">この手順が完了すると、出力先フォルダーに `*-help.xml` と `about_*.help.txt` ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-189">Once this step is complete, you will see `*-help.xml` and `about_*.help.txt` files in the target output folder.</span></span>

<span data-ttu-id="cbea1-190">詳細については、「[New-ExternalHelp][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-190">For more information, see [New-ExternalHelp][]</span></span>

### <a name="test-the-compiled-help-files"></a><span data-ttu-id="cbea1-191">コンパイル済みヘルプ ファイルをテストする</span><span class="sxs-lookup"><span data-stu-id="cbea1-191">Test the compiled help files</span></span>

<span data-ttu-id="cbea1-192">[Get-HelpPreview][] コマンドレットを使用して、コンテンツを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-192">You can verify the content with the [Get-HelpPreview][] cmdlet:</span></span>

```powershell
Get-HelpPreview -Path "<ModuleName>-Help.xml"
```

<span data-ttu-id="cbea1-193">このコマンドレットによって、コンパイルされた MAML ファイルが読み取られ、`Get-Help` から返されるのと同じ形式でコンテンツが出力されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-193">The cmdlet reads the compiled MAML file and outputs the content in the same format you would receive from `Get-Help`.</span></span> <span data-ttu-id="cbea1-194">これにより、結果を検査して、マークダウン ファイルが正しくコンパイルされていて必要な結果が生成されることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-194">This allows you to inspect the results to verify that the Markdown files compiled correctly and produce the desired results.</span></span> <span data-ttu-id="cbea1-195">エラーが見つかった場合は、マークダウン ファイルを再編集して MAML を再コンパイルします。</span><span class="sxs-lookup"><span data-stu-id="cbea1-195">If you find an error, re-edit the Markdown files and recompile the MAML.</span></span>

<span data-ttu-id="cbea1-196">これで、ヘルプ ファイルを公開する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="cbea1-196">Now you are ready to publish your help files.</span></span>

## <a name="publishing-your-help"></a><span data-ttu-id="cbea1-197">ヘルプを公開する</span><span class="sxs-lookup"><span data-stu-id="cbea1-197">Publishing your help</span></span>

<span data-ttu-id="cbea1-198">これでマークダウン ファイルが PowerShell ヘルプ ファイルにコンパイルされたので、ファイルをユーザーが使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-198">Now that you have compiled the Markdown files into PowerShell help files, you are ready to make the files available to users.</span></span> <span data-ttu-id="cbea1-199">PowerShell コンソールでヘルプを提供するには、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-199">There are two options for providing help in the PowerShell console.</span></span>

- <span data-ttu-id="cbea1-200">ヘルプ ファイルをモジュールと共にパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="cbea1-200">Package the help files with the module</span></span>
- <span data-ttu-id="cbea1-201">`Update-Help` コマンドレットを使用して、ユーザーがインストールする更新可能なヘルプ パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="cbea1-201">Create an updateable help package that users install with the `Update-Help` cmdlet</span></span>

### <a name="packaging-help-with-the-module"></a><span data-ttu-id="cbea1-202">ヘルプをモジュールと共にパッケージ化する</span><span class="sxs-lookup"><span data-stu-id="cbea1-202">Packaging help with the module</span></span>

<span data-ttu-id="cbea1-203">ヘルプ ファイルは、モジュールと共にパッケージ化することができます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-203">The help files can be packaged with your module.</span></span> <span data-ttu-id="cbea1-204">フォルダー構造の詳細については、[モジュールのヘルプの記述][]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-204">See [Writing Help for Modules][] for details of the folder structure.</span></span> <span data-ttu-id="cbea1-205">モジュール マニフェストの **FileList** キーの値にヘルプ ファイルのリストを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-205">You should include the list of Help files in the value of the **FileList** key in the module manifest.</span></span>

### <a name="creating-an-updateable-help-package"></a><span data-ttu-id="cbea1-206">更新可能なヘルプ パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="cbea1-206">Creating an updateable help package</span></span>

<span data-ttu-id="cbea1-207">更新可能なヘルプを作成する手順は大まかに次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cbea1-207">At a high level, the steps to create updateable help include:</span></span>

1. <span data-ttu-id="cbea1-208">ヘルプ ファイルをホストするインターネット サイトを検索する</span><span class="sxs-lookup"><span data-stu-id="cbea1-208">Find an internet site to host your help files</span></span>
1. <span data-ttu-id="cbea1-209">**HelpInfoURI** キーをモジュール マニフェストに追加する</span><span class="sxs-lookup"><span data-stu-id="cbea1-209">Add a **HelpInfoURI** key to your module manifest</span></span>
1. <span data-ttu-id="cbea1-210">HelpInfo XML ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cbea1-210">Create a HelpInfo XML file</span></span>
1. <span data-ttu-id="cbea1-211">CAB ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="cbea1-211">Create CAB files</span></span>
1. <span data-ttu-id="cbea1-212">ファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="cbea1-212">Upload your files</span></span>

<span data-ttu-id="cbea1-213">詳細については、[更新可能なヘルプのサポート: ステップバイステップ][step-by-step]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-213">For more information, see [Supporting Updateable Help: Step-by-step][step-by-step].</span></span>

<span data-ttu-id="cbea1-214">PlatyPS によって、これらの手順の一部が支援されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-214">PlatyPS assists you with  some of these steps.</span></span>

<span data-ttu-id="cbea1-215">**HelpInfoURI** は、ヘルプ ファイルがインターネット上でホストされている場所を指す URL です。</span><span class="sxs-lookup"><span data-stu-id="cbea1-215">The **HelpInfoURI** is a URL that points to location where your help files are hosted on the internet.</span></span> <span data-ttu-id="cbea1-216">モジュール マニフェスト内にこの値を構成します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-216">This value is configured in the module manifest.</span></span> <span data-ttu-id="cbea1-217">`Update-Help` によって、モジュール マニフェストが読み取られ、この URL が取得されて、更新可能なヘルプ コンテンツがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-217">`Update-Help` reads the module manifest to get this URL and download the updateable help content.</span></span> <span data-ttu-id="cbea1-218">この URL は、個別のファイルではなく、フォルダーの場所のみを指している必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-218">This URL should only point to the folder location and not to individual files.</span></span> <span data-ttu-id="cbea1-219">`Update-Help` を使用すると、モジュール マニフェストと HelpInfo XML ファイルにあるその他の情報に基づいて、ダウンロードするファイル名を構築できます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-219">`Update-Help` constructs the filenames to download based on other information from the module manifest and the HelpInfo XML file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbea1-220">**HelpInfoURI** は、スラッシュ (`/`) で終わる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-220">The **HelpInfoURI** must end with a forward-slash character (`/`).</span></span> <span data-ttu-id="cbea1-221">この文字がない場合、`Update-Help` によって、コンテンツをダウンロードするための正しいファイル パスが作成されません。</span><span class="sxs-lookup"><span data-stu-id="cbea1-221">Without that character, `Update-Help` cannot construct the correct file paths to download the content.</span></span> <span data-ttu-id="cbea1-222">また、ほとんどの HTTP ベースのファイル サービスでは大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-222">Also, most HTTP-based file services are case-sensitive.</span></span> <span data-ttu-id="cbea1-223">HelpInfo XML ファイル内のモジュール メタデータでは、大文字と小文字を適切に区別した文字が含まれていることが重要です。</span><span class="sxs-lookup"><span data-stu-id="cbea1-223">It is important that the module metadata in the HelpInfo XML file contains the proper letter case.</span></span>

<span data-ttu-id="cbea1-224">`New-ExternalHelp` コマンドレットによって、HelpInfo XML ファイルが出力フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-224">The `New-ExternalHelp` cmdlet creates the HelpInfo XML file in the output folder.</span></span> <span data-ttu-id="cbea1-225">HelpInfo XML ファイルは、モジュールのマークダウン ファイル (`ModuleName.md`) に含まれている YAML メタデータを使用して構築されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-225">The HelpInfo XML file is built using YAML metadata contained in the module Markdown files (`ModuleName.md`).</span></span>

<span data-ttu-id="cbea1-226">`New-ExternalHelpCab` コマンドレットによって、コンパイルした MAML ファイルと `about_*.help.txt` ファイルを含む ZIP ファイルと CAB ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-226">The `New-ExternalHelpCab` cmdlet creates ZIP and CAB files containing the MAML and `about_*.help.txt` files you compiled.</span></span> <span data-ttu-id="cbea1-227">CAB ファイルは、PowerShell のすべてのバージョンと互換性があります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-227">CAB files are compatible with all versions of PowerShell.</span></span>
<span data-ttu-id="cbea1-228">PowerShell 6 以降では、ZIP ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-228">PowerShell 6 and higher can use ZIP files.</span></span>

```powershell
$helpCabParameters = @{
    CabFilesFolder = $MamlOutputFolder
    LandingPagePath = $LandingPage
    OutputFolder = $CabOutputFolder
}
New-ExternalHelpCab @helpCabParameters
```

<span data-ttu-id="cbea1-229">ZIP ファイルと CAB ファイルを作成した後、ZIP、CAB、および HelpInfo XML ファイルを HTTP ファイル サーバーにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="cbea1-229">After creating the ZIP and CAB files, upload the ZIP, CAB, and HelpInfo XML files to your HTTP file server.</span></span> <span data-ttu-id="cbea1-230">**HelpInfoURI** によって示されている場所にファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="cbea1-230">Put the files in the location indicated by the **HelpInfoURI**.</span></span>

<span data-ttu-id="cbea1-231">詳細については、「[New-ExternalHelpCab][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-231">For more information, see [New-ExternalHelpCab][].</span></span>

### <a name="other-publishing-options"></a><span data-ttu-id="cbea1-232">その他の公開オプション</span><span class="sxs-lookup"><span data-stu-id="cbea1-232">Other publishing options</span></span>

<span data-ttu-id="cbea1-233">Markdown は、公開するために他の形式に簡単に変換できる、汎用性のある形式です。</span><span class="sxs-lookup"><span data-stu-id="cbea1-233">Markdown is a versatile format that is easy to transform to other formats for publishing.</span></span> <span data-ttu-id="cbea1-234">[Pandoc][] などのツールを使用すると、Markdown のヘルプ ファイルを、プレーンテキスト、HTML、PDF、Office ドキュメント形式などのさまざまなドキュメント形式に変換できます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-234">Using a tool like [Pandoc][], you can convert your Markdown help files to many different document formats, including plain text, HTML, PDF, and Office document formats.</span></span>

<span data-ttu-id="cbea1-235">また、PowerShell 6 以降では、コマンドレット [ConvertFrom-Markdown][] と [Show-Markdown][] を使用して、Markdown を HTML に変換したり、PowerShell コンソールにカラフルな表示を作成したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-235">Also, the cmdlets [ConvertFrom-Markdown][] and [Show-Markdown][] in PowerShell 6 and higher can be used to convert Markdown to HTML or create a colorful display in the PowerShell console.</span></span>

## <a name="known-issues"></a><span data-ttu-id="cbea1-236">既知の問題</span><span class="sxs-lookup"><span data-stu-id="cbea1-236">Known issues</span></span>

<span data-ttu-id="cbea1-237">PlatyPS は、作成およびコンパイルするマークダウン ファイルの構造の[スキーマ][]が非常に厳密に認識されます。</span><span class="sxs-lookup"><span data-stu-id="cbea1-237">PlatyPS is very sensitive to the [schema][] for the structure of the Markdown files it creates and compiles.</span></span> <span data-ttu-id="cbea1-238">有効な Markdown を記述し、それがこのスキーマに違反していることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="cbea1-238">It is very easy write valid Markdown that violates this schema.</span></span> <span data-ttu-id="cbea1-239">詳細については、[PowerShell のスタイル ガイド][]に関するページと「[参照記事の編集][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cbea1-239">For more information, consult the [PowerShell style guide][] and [Editing reference articles][].</span></span>

<!-- link references -->
[platyps-repo]: https://github.com/PowerShell/platyps
[PlatyPS]: https://www.powershellgallery.com/packages/platyPS/
[Markdown]: https://commonmark.org
[markdig]: https://github.com/lunet-io/markdig
[schema]: https://github.com/PowerShell/platyPS/blob/master/platyPS.schema.md
[Get-Item]: https://github.com/MicrosoftDocs/PowerShell-Docs/blob/staging/reference/7.0/Microsoft.PowerShell.Management/Get-Item.md
[New-MarkdownHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownHelp.md
[Update-MarkdownHelpModule]: https://github.com/PowerShell/platyPS/blob/master/docs/Update-MarkdownHelpModule.md
[New-MarkdownAboutHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-MarkdownAboutHelp.md
[New-ExternalHelp]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelp.md
[Get-HelpPreview]: https://github.com/PowerShell/platyPS/blob/master/docs/Get-HelpPreview.md
[New-ExternalHelpCab]: https://github.com/PowerShell/platyPS/blob/master/docs/New-ExternalHelpCab.md
[PowerShell のスタイル ガイド]: /powershell/scripting/community/contributing/powershell-style-guide
[PowerShell style guide]: /powershell/scripting/community/contributing/powershell-style-guide
[参照記事の編集]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[Editing reference articles]: /powershell/scripting/community/contributing/editing-cmdlet-ref
[モジュールのヘルプの記述]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[Writing Help for Modules]: /powershell/scripting/developer/help/writing-help-for-windows-powershell-modules
[step-by-step]: /powershell/scripting/developer/help/updatable-help-authoring-step-by-step
[Pandoc]: https://pandoc.org
[ConvertFrom-Markdown]: /powershell/module/microsoft.powershell.utility/convertfrom-markdown
[Show-Markdown]: /powershell/module/microsoft.powershell.utility/show-markdown
