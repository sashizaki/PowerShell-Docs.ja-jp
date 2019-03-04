---
title: 作成して、CAB ファイルをアップロードする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d35f233-5447-48a2-a961-9fbca763262b
caps.latest.revision: 7
ms.openlocfilehash: 9928a0b31a57d42eb39cea1af0509613c483caf7
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56858648"
---
# <a name="how-to-create-and-upload-cab-files"></a><span data-ttu-id="cdea3-102">CAB ファイルを作成してアップロードする方法</span><span class="sxs-lookup"><span data-stu-id="cdea3-102">How to Create and Upload CAB Files</span></span>

<span data-ttu-id="cdea3-103">このトピックでは、ヘルプの更新可能な CAB ファイルを作成し、更新可能なヘルプ コマンドレットが検索できる場所の場所にアップロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-103">This topic explains how to create Updatable Help CAB files and upload them to the location where the Updatable Help cmdlets can find them.</span></span>

## <a name="how-to-create-and-upload-updatable-help-cab-files"></a><span data-ttu-id="cdea3-104">作成して、更新可能なヘルプの CAB ファイルをアップロードする方法</span><span class="sxs-lookup"><span data-stu-id="cdea3-104">How to Create and Upload Updatable Help CAB Files</span></span>

<span data-ttu-id="cdea3-105">更新可能なヘルプ機能を使用すると、複数の言語と文化のモジュールの新しいまたは更新されたヘルプ ファイルを配信します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-105">You can use the Updatable Help feature to deliver new or updated help files for a module in multiple languages and cultures.</span></span> <span data-ttu-id="cdea3-106">モジュールの更新可能なヘルプ パッケージを 1 つの HelpInfo XML ファイルから成ると 1 つまたは複数のキャビネット (します。CAB) ファイル。</span><span class="sxs-lookup"><span data-stu-id="cdea3-106">An Updatable Help package for a module consists of one HelpInfo XML file and one or more cabinet (.CAB) files.</span></span> <span data-ttu-id="cdea3-107">各 CAB ファイルには、1 つの UI カルチャでモジュールのヘルプ ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdea3-107">Each CAB file contains help files for the module in one UI culture.</span></span> <span data-ttu-id="cdea3-108">更新可能なヘルプの CAB ファイルを作成するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-108">Use the following procedure to create CAB files for Updatable Help.</span></span>

1. <span data-ttu-id="cdea3-109">UI カルチャでモジュールのヘルプ ファイルを整理します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-109">Organize the help files for the module by UI culture.</span></span> <span data-ttu-id="cdea3-110">各ヘルプの更新可能な CAB ファイルには、1 つの UI カルチャの 1 つのモジュールのヘルプ ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cdea3-110">Each Updatable Help CAB file contains the help files for one module in one UI culture.</span></span> <span data-ttu-id="cdea3-111">複数のヘルプに、モジュールごとに別の UI カルチャ用の CAB ファイルを配信できます。</span><span class="sxs-lookup"><span data-stu-id="cdea3-111">You can deliver multiple help CAB files for the module, each for a different UI culture.</span></span>

2. <span data-ttu-id="cdea3-112">確認するヘルプ ファイル更新可能なヘルプで許可されているファイルの種類のみを含めるし、ヘルプ ファイルのスキーマに対して検証します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-112">Verify that help files include only the file types permitted for Updatable Help and validate them against a help file schema.</span></span> <span data-ttu-id="cdea3-113">場合、`Update-Help`コマンドレットには、正しくないか許可されている型ではないファイルが検出すると、無効なファイルはインストールされませんし、cab ファイルからファイルのインストールを停止します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-113">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB.</span></span> <span data-ttu-id="cdea3-114">許可されているファイルの種類の一覧は、次を参照してください。[更新可能なヘルプ CAB ファイルのファイルの種類が許可される](./file-types-permitted-in-an-updatable-help-cab-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-114">For a list of permitted file types, see [File Types Permitted in an Updatable Help CAB File](./file-types-permitted-in-an-updatable-help-cab-file.md).</span></span>

3. <span data-ttu-id="cdea3-115">ヘルプ ファイルにデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-115">Digitally sign the help files.</span></span> <span data-ttu-id="cdea3-116">デジタル署名が必須ではありませんが、ベスト プラクティスは。</span><span class="sxs-lookup"><span data-stu-id="cdea3-116">Digital signatures are not required, but they are a best practice.</span></span>

4. <span data-ttu-id="cdea3-117">すべてのヘルプが新しいファイルだけでなくのカルチャまたは変更されてください、UI でモジュールのファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cdea3-117">Include all of help files for the module in the UI culture, not only files that are new or have changed.</span></span> <span data-ttu-id="cdea3-118">CAB ファイルが完全でない場合、最初にヘルプ ファイルをダウンロードまたはすべての更新をダウンロードしないユーザーはありませんすべてのモジュールのヘルプ ファイル。</span><span class="sxs-lookup"><span data-stu-id="cdea3-118">If the CAB file is incomplete, users who download help files for the first time or do not download every update, will not have all of the module help files.</span></span>

5. <span data-ttu-id="cdea3-119">MakeCab.exe などのキャビネット ファイルを作成するユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-119">Use a utility that creates cabinet files, such as MakeCab.exe.</span></span> <span data-ttu-id="cdea3-120">Windows PowerShell では、CAB ファイルを作成するコマンドレットは含まれません。</span><span class="sxs-lookup"><span data-stu-id="cdea3-120">Windows PowerShell does not include cmdlets that create CAB files.</span></span>

6. <span data-ttu-id="cdea3-121">CAB ファイルの名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="cdea3-121">Name the CAB files.</span></span> <span data-ttu-id="cdea3-122">詳細については、次を参照してください。[更新可能なヘルプ CAB ファイルの名前を付ける方法](./how-to-name-an-updatable-help-cab-file.md)します。</span><span class="sxs-lookup"><span data-stu-id="cdea3-122">For more information, see [How to Name an Updatable Help CAB File](./how-to-name-an-updatable-help-cab-file.md).</span></span>

7. <span data-ttu-id="cdea3-123">指定された場所に、モジュール用の CAB ファイルをアップロード、 **HelpContentUri**モジュールの HelpInfo XML ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="cdea3-123">Upload the CAB files for the module to the location that is specified by the **HelpContentUri** element in the HelpInfo XML file for the module.</span></span> <span data-ttu-id="cdea3-124">指定された場所に HelpInfo XML ファイルをアップロード、 **HelpInfoUri**モジュール マニフェストのキー。</span><span class="sxs-lookup"><span data-stu-id="cdea3-124">Then upload the HelpInfo XML file to the location that is specified by the **HelpInfoUri** key of the module manifest.</span></span> <span data-ttu-id="cdea3-125">**HelpContentUri**と**HelpInfoUri**同じ場所を指すことができます。</span><span class="sxs-lookup"><span data-stu-id="cdea3-125">The **HelpContentUri** and **HelpInfoUri** can point to the same location.</span></span>

> [!CAUTION]
> <span data-ttu-id="cdea3-126">値、 **HelpInfoUri**キーと**HelpContentUri**要素は、"http"または"https"で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdea3-126">The value of the **HelpInfoUri** key and the **HelpContentUri** element must begin with "http" or "https".</span></span> <span data-ttu-id="cdea3-127">値は、インターネット上の場所を示す必要があり、ファイル名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="cdea3-127">The value must indicate an Internet location and it must not include a file name.</span></span>