---
title: '更新可能なヘルプの作成: ステップ バイ ステップ |Microsoft Docs'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10098160-c6b4-4339-b8ff-2c4f8cc0699b
caps.latest.revision: 13
ms.openlocfilehash: fbc77cc0fafce93d239da1c459d4b761b21ef3cb
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56860318"
---
# <a name="updatable-help-authoring-step-by-step"></a><span data-ttu-id="7aef4-102">更新可能なヘルプの作成: ステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="7aef4-102">Updatable Help Authoring: Step-by-Step</span></span>

<span data-ttu-id="7aef4-103">このドキュメントでは、更新可能なヘルプの作成プロセスの手順が一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-103">This documents lists the steps in the process of authoring Updatable Help.</span></span>

## <a name="authoring-updatable-help-step-by-step"></a><span data-ttu-id="7aef4-104">更新可能なヘルプを作成するには。ステップバイステップ</span><span class="sxs-lookup"><span data-stu-id="7aef4-104">Authoring Updatable Help: Step-by-Step</span></span>

<span data-ttu-id="7aef4-105">更新可能なヘルプは、エンドユーザー向けに設計されていますが、モジュールの作成者に多大なメリットを提供およびヘルプのライター、コンテンツを追加する機能も含まれますエラーを修正、複数の UI カルチャで配信後、ユーザーのコメントと、要求に応答しますモジュールが付属しています。</span><span class="sxs-lookup"><span data-stu-id="7aef4-105">Updatable Help is designed for end-users, but it also provides significant benefits to module authors and help writers, including the ability to add content, fix errors, deliver in multiple UI cultures, and respond to user comments and requests, long after the module has shipped.</span></span> <span data-ttu-id="7aef4-106">このトピックでは、パッケージ化する方法について説明し、アップロードのヘルプ ファイルをユーザーがダウンロードしてそれらを使用してインストールできるように、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="7aef4-106">This topic explains how you package and upload help files so that users can download and install them by using the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="7aef4-107">次の手順では、更新可能なヘルプをサポートしているプロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-107">The following steps provide an overview of the process of supporting Updatable Help.</span></span>

### <a name="step-1-find-an-internet-site-for-your-help-files"></a><span data-ttu-id="7aef4-108">手順 1:インターネット サイトのヘルプ ファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-108">Step 1: Find an Internet site for your help files</span></span>

<span data-ttu-id="7aef4-109">更新可能なヘルプの作成の最初の手順では、モジュールのヘルプ ファイルをインターネット上の場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-109">The first step in creating updatable help is to find an Internet location for your module's help files.</span></span> <span data-ttu-id="7aef4-110">実際には、2 つの場所を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="7aef4-110">Actually, you can use two different locations.</span></span> <span data-ttu-id="7aef4-111">インターネット上の 1 つの場所とインターネット上の別の場所にあるヘルプ コンテンツ CAB ファイルには、モジュールのヘルプ情報ファイル (HelpInfo XML - 以下で説明) を保持できます。</span><span class="sxs-lookup"><span data-stu-id="7aef4-111">You can keep your module's help information file (HelpInfo XML - described below) at one Internet location and the help content CAB files at another Internet location.</span></span> <span data-ttu-id="7aef4-112">すべてヘルプ コンテンツ用の CAB ファイルをモジュールは、同じ場所にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aef4-112">All help content CAB files for a module must be in the same location.</span></span> <span data-ttu-id="7aef4-113">さまざまなモジュールのヘルプ コンテンツ CAB ファイルは、同じ場所に配置できます。</span><span class="sxs-lookup"><span data-stu-id="7aef4-113">You can place help content CAB files for different modules in the same location.</span></span>

### <a name="step-2-add-a-helpinfouri-key-to-your-module-manifest"></a><span data-ttu-id="7aef4-114">手順 2:HelpInfoURI キー、モジュール マニフェストを追加します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-114">Step 2: Add a HelpInfoURI key to your module manifest</span></span>

<span data-ttu-id="7aef4-115">追加、 **HelpInfoURI**がモジュール マニフェスト キー。</span><span class="sxs-lookup"><span data-stu-id="7aef4-115">Add a **HelpInfoURI** key to your module manifest.</span></span> <span data-ttu-id="7aef4-116">キーの値は、モジュールの HelpInfo XML 情報ファイルの場所の統一リソース識別子 (URI) です。</span><span class="sxs-lookup"><span data-stu-id="7aef4-116">The value of the key is the Uniform Resource Identifier (URI) of the location of the HelpInfo XML information file for your module.</span></span> <span data-ttu-id="7aef4-117">セキュリティ、アドレスは、"http"または"https"で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aef4-117">For security, the address must begin with "http" or "https".</span></span> <span data-ttu-id="7aef4-118">URI は、インターネット上の場所を指定する必要がありますが、HelpInfo XML ファイルの名前を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="7aef4-118">The URI should specify an Internet location, but must not include the HelpInfo XML file name.</span></span>

<span data-ttu-id="7aef4-119">たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-119">For example:</span></span>

```powershell

@{
RootModule = TestModule.psm1
ModuleVersion = '2.0'
HelpInfoURI = 'http://go.microsoft.com/fwlink/?LinkID=0123'
}
```

### <a name="step-3-create-a-helpinfo-xml-file"></a><span data-ttu-id="7aef4-120">手順 3:HelpInfo XML ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-120">Step 3: Create a HelpInfo XML file</span></span>

<span data-ttu-id="7aef4-121">HelpInfo XML ファイルには、ヘルプ ファイルとサポートされている各 UI カルチャでモジュールの最新のヘルプ ファイルのバージョン番号のインターネット上の場所の URI が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7aef4-121">The HelpInfo XML information file contains the URI of the Internet location of your help files and the version numbers of the newest help files for your module in each supported UI culture.</span></span> <span data-ttu-id="7aef4-122">すべての Windows PowerShell モジュールでは、1 つの HelpInfo XML ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="7aef4-122">Every Windows PowerShell module has one HelpInfo XML file.</span></span> <span data-ttu-id="7aef4-123">編集または HelpInfo XML ファイルを置換するのヘルプ ファイルを更新するときにもう 1 つを入れないでください。</span><span class="sxs-lookup"><span data-stu-id="7aef4-123">When you update your help files, you edit or replace the HelpInfo XML file; you do not add another one.</span></span> <span data-ttu-id="7aef4-124">詳細については、次を参照してください。 [HelpInfo XML ファイルを作成する方法](./how-to-create-a-helpinfo-xml-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-124">For more information, see [How to Create a HelpInfo XML File](./how-to-create-a-helpinfo-xml-file.md).</span></span>

### <a name="step-4-sign-your-help-files"></a><span data-ttu-id="7aef4-125">手順 4:ヘルプ ファイルに署名します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-125">Step 4: Sign your help files</span></span>

<span data-ttu-id="7aef4-126">デジタル署名が必須ではありませんが、ファイルを共有しているときに、ベスト プラクティスの推奨事項。</span><span class="sxs-lookup"><span data-stu-id="7aef4-126">Digital signatures are not required, but they are a best-practice recommendation whenever you are sharing files.</span></span>

### <a name="step-5-create-cab-files"></a><span data-ttu-id="7aef4-127">手順 5:CAB ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-127">Step 5: Create CAB files</span></span>

<span data-ttu-id="7aef4-128">作成する、MakeCab.exe などのキャビネット (.cab) ファイルを作成するツールを使用して、します。モジュールのヘルプ ファイルを含む CAB ファイル。</span><span class="sxs-lookup"><span data-stu-id="7aef4-128">Use a tool that creates cabinet (.cab) files, such as MakeCab.exe, to create a .CAB file that contains the help files for your module.</span></span> <span data-ttu-id="7aef4-129">サポートされている各 UI カルチャのヘルプ ファイルに個別の CAB ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-129">Create a separate CAB file for the help files in each supported UI culture.</span></span> <span data-ttu-id="7aef4-130">詳細については、次を参照してください。[を準備する更新可能なヘルプ CAB ファイルの追加方法](./how-to-prepare-updatable-help-cab-files.md)します。</span><span class="sxs-lookup"><span data-stu-id="7aef4-130">For more information, see [How to Prepare Updatable Help CAB Files](./how-to-prepare-updatable-help-cab-files.md).</span></span>

### <a name="step-6-upload-your-files"></a><span data-ttu-id="7aef4-131">手順 6:ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="7aef4-131">Step 6: Upload your files</span></span>

<span data-ttu-id="7aef4-132">新しいまたは更新されたヘルプ ファイルを発行するで指定されたインターネット上の場所に CAB ファイルをアップロード、 **HelpContentUri** HelpInfo XML ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="7aef4-132">To publish new or updated help files, upload the CAB files to the Internet location that is specified by the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="7aef4-133">値で指定されたインターネット上の場所に HelpInfo XML ファイルをアップロードし、 **HelpInfoUri**モジュール マニフェストでキー。</span><span class="sxs-lookup"><span data-stu-id="7aef4-133">Then, upload the HelpInfo XML file to the Internet location that is specified by the value of the **HelpInfoUri** key in the module manifest.</span></span>
