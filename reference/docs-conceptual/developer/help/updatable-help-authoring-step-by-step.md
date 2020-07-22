---
title: 更新可能なヘルプの作成-ステップバイステップ
ms.date: 09/13/2016
ms.openlocfilehash: c9214be3c3363a4e6354595b50cf76a17d49aa67
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893120"
---
# <a name="updatable-help-authoring-step-by-step"></a><span data-ttu-id="912ce-102">更新可能なヘルプの作成: ステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="912ce-102">Updatable Help Authoring: Step-by-Step</span></span>

<span data-ttu-id="912ce-103">このドキュメントでは、更新可能なヘルプを作成するプロセスの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="912ce-103">This documents lists the steps in the process of authoring Updatable Help.</span></span>

## <a name="authoring-updatable-help-step-by-step"></a><span data-ttu-id="912ce-104">更新可能なヘルプの作成: ステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="912ce-104">Authoring Updatable Help: Step-by-Step</span></span>

<span data-ttu-id="912ce-105">更新可能なヘルプはエンドユーザー向けに設計されていますが、モジュールの作成者やヘルプライターにも大きな利点があります。これには、コンテンツの追加、エラーの修正、複数の UI カルチャでの配信、およびモジュールが出荷された後のユーザーのコメントと要求への応答が含まれます。</span><span class="sxs-lookup"><span data-stu-id="912ce-105">Updatable Help is designed for end-users, but it also provides significant benefits to module authors and help writers, including the ability to add content, fix errors, deliver in multiple UI cultures, and respond to user comments and requests, long after the module has shipped.</span></span> <span data-ttu-id="912ce-106">このトピックでは、ヘルプファイルをパッケージ化してアップロード[し、ユーザーが update-help コマンド](/powershell/module/Microsoft.PowerShell.Core/Update-Help)[レットを](/powershell/module/Microsoft.PowerShell.Core/Save-Help)使用してダウンロードおよびインストールできるようにする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="912ce-106">This topic explains how you package and upload help files so that users can download and install them by using the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="912ce-107">次の手順では、更新可能なヘルプをサポートするプロセスの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="912ce-107">The following steps provide an overview of the process of supporting Updatable Help.</span></span>

### <a name="step-1-find-an-internet-site-for-your-help-files"></a><span data-ttu-id="912ce-108">手順 1: ヘルプファイルのインターネットサイトを検索する</span><span class="sxs-lookup"><span data-stu-id="912ce-108">Step 1: Find an internet site for your help files</span></span>

<span data-ttu-id="912ce-109">更新可能なヘルプを作成するための最初の手順は、モジュールのヘルプファイルのインターネット上の場所を見つけることです。</span><span class="sxs-lookup"><span data-stu-id="912ce-109">The first step in creating updatable help is to find an internet location for your module's help files.</span></span> <span data-ttu-id="912ce-110">実際には、2つの異なる場所を使用できます。</span><span class="sxs-lookup"><span data-stu-id="912ce-110">Actually, you can use two different locations.</span></span> <span data-ttu-id="912ce-111">モジュールのヘルプ情報ファイル (後述の HelpInfo XML) を1つのインターネット上の場所に保存し、ヘルプコンテンツの CAB ファイルを別のインターネット上の場所に保存することができます。</span><span class="sxs-lookup"><span data-stu-id="912ce-111">You can keep your module's help information file (HelpInfo XML - described below) at one internet location and the help content CAB files at another internet location.</span></span> <span data-ttu-id="912ce-112">モジュールのすべてのヘルプコンテンツ CAB ファイルは、同じ場所にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="912ce-112">All help content CAB files for a module must be in the same location.</span></span> <span data-ttu-id="912ce-113">異なるモジュールのヘルプコンテンツ CAB ファイルを同じ場所に配置することができます。</span><span class="sxs-lookup"><span data-stu-id="912ce-113">You can place help content CAB files for different modules in the same location.</span></span>

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a><span data-ttu-id="912ce-114">手順 2: HelpInfoURI キーをモジュールマニフェストに追加する</span><span class="sxs-lookup"><span data-stu-id="912ce-114">Step 2: Add a HelpInfoURI key to your module manifest</span></span>

<span data-ttu-id="912ce-115">**Helpinfouri**キーをモジュールマニフェストに追加します。</span><span class="sxs-lookup"><span data-stu-id="912ce-115">Add a **HelpInfoURI** key to your module manifest.</span></span> <span data-ttu-id="912ce-116">キーの値は、モジュールの HelpInfo XML 情報ファイルの場所の Uniform Resource Identifier (URI) です。</span><span class="sxs-lookup"><span data-stu-id="912ce-116">The value of the key is the Uniform Resource Identifier (URI) of the location of the HelpInfo XML information file for your module.</span></span> <span data-ttu-id="912ce-117">セキュリティのため、アドレスは "http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="912ce-117">For security, the address must begin with "http" or "https".</span></span> <span data-ttu-id="912ce-118">URI はインターネットの場所を指定する必要がありますが、HelpInfo XML ファイル名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="912ce-118">The URI should specify an internet location, but must not include the HelpInfo XML filename.</span></span>

<span data-ttu-id="912ce-119">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="912ce-119">For example:</span></span>

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'https://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a><span data-ttu-id="912ce-120">手順 3: HelpInfo XML ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="912ce-120">Step 3: Create a HelpInfo XML file</span></span>

<span data-ttu-id="912ce-121">HelpInfo XML 情報ファイルには、ヘルプファイルのインターネット上の場所の URI と、サポートされている各 UI カルチャのモジュールの最新のヘルプファイルのバージョン番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="912ce-121">The HelpInfo XML information file contains the URI of the internet location of your help files and the version numbers of the newest help files for your module in each supported UI culture.</span></span> <span data-ttu-id="912ce-122">すべての Windows PowerShell モジュールには、HelpInfo XML ファイルが1つあります。</span><span class="sxs-lookup"><span data-stu-id="912ce-122">Every Windows PowerShell module has one HelpInfo XML file.</span></span> <span data-ttu-id="912ce-123">ヘルプファイルを更新するときに、HelpInfo XML ファイルを編集または置換します。別のユーザーを追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="912ce-123">When you update your help files, you edit or replace the HelpInfo XML file; you do not add another one.</span></span> <span data-ttu-id="912ce-124">詳細については、「 [How To Create a HELPINFO XML File](./how-to-create-a-helpinfo-xml-file.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="912ce-124">For more information, see [How to Create a HelpInfo XML File](./how-to-create-a-helpinfo-xml-file.md).</span></span>

### <a name="step-4-create-cab-files"></a><span data-ttu-id="912ce-125">手順 4: CAB ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="912ce-125">Step 4: Create CAB files</span></span>

<span data-ttu-id="912ce-126">キャビネット () ファイルを作成するツール (など) を使用して `.cab` `MakeCab.exe` 、モジュールのヘルプファイルを含む CAB ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="912ce-126">Use a tool that creates cabinet (`.cab`) files, such as `MakeCab.exe`, to create a CAB file that contains the help files for your module.</span></span> <span data-ttu-id="912ce-127">サポートされている各 UI カルチャで、ヘルプファイル用の個別の CAB ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="912ce-127">Create a separate CAB file for the help files in each supported UI culture.</span></span> <span data-ttu-id="912ce-128">詳細については、「[更新可能なヘルプ CAB ファイルを準備する方法](./how-to-prepare-updatable-help-cab-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="912ce-128">For more information, see [How to Prepare Updatable Help CAB Files](./how-to-prepare-updatable-help-cab-files.md).</span></span>

### <a name="step-5-upload-your-files"></a><span data-ttu-id="912ce-129">手順 5: ファイルをアップロードする</span><span class="sxs-lookup"><span data-stu-id="912ce-129">Step 5: Upload your files</span></span>

<span data-ttu-id="912ce-130">新しいまたは更新されたヘルプファイルを発行するには、HelpInfo XML ファイルの**Helpcontenturi**要素によって指定されたインターネット上の場所に CAB ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="912ce-130">To publish new or updated help files, upload the CAB files to the internet location that is specified by the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="912ce-131">次に、モジュールマニフェストの**Helpinfouri**キーの値によって指定されたインターネット上の場所に、HelpInfo XML ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="912ce-131">Then, upload the HelpInfo XML file to the internet location that is specified by the value of the **HelpInfoUri** key in the module manifest.</span></span>
