---
title: CAB ファイルを作成およびアップロードする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d35f233-5447-48a2-a961-9fbca763262b
caps.latest.revision: 7
ms.openlocfilehash: 37b31aa77dde23c1bd57a9af67e2232ef0827005
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83557586"
---
# <a name="how-to-create-and-upload-cab-files"></a><span data-ttu-id="44e9f-102">CAB ファイルを作成してアップロードする方法</span><span class="sxs-lookup"><span data-stu-id="44e9f-102">How to Create and Upload CAB Files</span></span>

<span data-ttu-id="44e9f-103">このトピックでは、更新可能なヘルプ CAB ファイルを作成し、更新可能なヘルプのコマンドレットで検出できる場所にアップロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="44e9f-103">This topic explains how to create Updatable Help CAB files and upload them to the location where the Updatable Help cmdlets can find them.</span></span>

## <a name="how-to-create-and-upload-updatable-help-cab-files"></a><span data-ttu-id="44e9f-104">更新可能なヘルプ CAB ファイルを作成およびアップロードする方法</span><span class="sxs-lookup"><span data-stu-id="44e9f-104">How to Create and Upload Updatable Help CAB Files</span></span>

<span data-ttu-id="44e9f-105">更新可能なヘルプ機能を使用して、複数の言語とカルチャのモジュールの新しいヘルプファイルまたは更新されたヘルプファイルを配信できます。</span><span class="sxs-lookup"><span data-stu-id="44e9f-105">You can use the Updatable Help feature to deliver new or updated help files for a module in multiple languages and cultures.</span></span> <span data-ttu-id="44e9f-106">モジュールの更新可能なヘルプパッケージは、1つの HelpInfo XML ファイルと1つ以上のキャビネット () で構成されています。CAB) ファイル。</span><span class="sxs-lookup"><span data-stu-id="44e9f-106">An Updatable Help package for a module consists of one HelpInfo XML file and one or more cabinet (.CAB) files.</span></span> <span data-ttu-id="44e9f-107">各 CAB ファイルには、モジュールのヘルプファイルが1つの UI カルチャで含まれています。</span><span class="sxs-lookup"><span data-stu-id="44e9f-107">Each CAB file contains help files for the module in one UI culture.</span></span> <span data-ttu-id="44e9f-108">更新可能なヘルプ用の CAB ファイルを作成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="44e9f-108">Use the following procedure to create CAB files for Updatable Help.</span></span>

1. <span data-ttu-id="44e9f-109">モジュールのヘルプファイルを UI カルチャで整理します。</span><span class="sxs-lookup"><span data-stu-id="44e9f-109">Organize the help files for the module by UI culture.</span></span> <span data-ttu-id="44e9f-110">更新可能な各ヘルプ CAB ファイルには、1つの UI カルチャの1つのモジュールのヘルプファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="44e9f-110">Each Updatable Help CAB file contains the help files for one module in one UI culture.</span></span> <span data-ttu-id="44e9f-111">モジュールに対して複数のヘルプ CAB ファイルを配信できます。それぞれ異なる UI カルチャを対象としています。</span><span class="sxs-lookup"><span data-stu-id="44e9f-111">You can deliver multiple help CAB files for the module, each for a different UI culture.</span></span>

2. <span data-ttu-id="44e9f-112">ヘルプファイルに、更新可能なヘルプで許可されているファイルの種類だけが含まれていること、およびヘルプファイルスキーマに対して検証されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="44e9f-112">Verify that help files include only the file types permitted for Updatable Help and validate them against a help file schema.</span></span> <span data-ttu-id="44e9f-113">`Update-Help`コマンドレットで、無効なファイルや許可されていない種類のファイルが検出された場合、無効なファイルはインストールされず、CAB からのファイルのインストールが停止します。</span><span class="sxs-lookup"><span data-stu-id="44e9f-113">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB.</span></span> <span data-ttu-id="44e9f-114">許可されるファイルの種類の一覧については、「[更新可能なヘルプ CAB ファイルで許可](./file-types-permitted-in-an-updatable-help-cab-file.md)されているファイルの種類」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44e9f-114">For a list of permitted file types, see [File Types Permitted in an Updatable Help CAB File](./file-types-permitted-in-an-updatable-help-cab-file.md).</span></span>

3. <span data-ttu-id="44e9f-115">ヘルプファイルにデジタル署名します。</span><span class="sxs-lookup"><span data-stu-id="44e9f-115">Digitally sign the help files.</span></span> <span data-ttu-id="44e9f-116">デジタル署名は必須ではありませんが、ベストプラクティスです。</span><span class="sxs-lookup"><span data-stu-id="44e9f-116">Digital signatures are not required, but they are a best practice.</span></span>

4. <span data-ttu-id="44e9f-117">新しいまたは変更されたファイルだけでなく、そのモジュールのすべてのヘルプファイルを UI カルチャに含めます。</span><span class="sxs-lookup"><span data-stu-id="44e9f-117">Include all of help files for the module in the UI culture, not only files that are new or have changed.</span></span> <span data-ttu-id="44e9f-118">CAB ファイルが不完全な場合は、ヘルプファイルを初めてダウンロードしたユーザー、またはすべての更新プログラムをダウンロードしていないユーザーは、モジュールのヘルプファイルをすべて保持できません。</span><span class="sxs-lookup"><span data-stu-id="44e9f-118">If the CAB file is incomplete, users who download help files for the first time or do not download every update, will not have all of the module help files.</span></span>

5. <span data-ttu-id="44e9f-119">MakeCab などのキャビネットファイルを作成するユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="44e9f-119">Use a utility that creates cabinet files, such as MakeCab.exe.</span></span> <span data-ttu-id="44e9f-120">Windows PowerShell には、CAB ファイルを作成するコマンドレットは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="44e9f-120">Windows PowerShell does not include cmdlets that create CAB files.</span></span>

6. <span data-ttu-id="44e9f-121">CAB ファイルに名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="44e9f-121">Name the CAB files.</span></span> <span data-ttu-id="44e9f-122">詳細については、「[更新可能なヘルプ CAB ファイルに名前を指定する方法](./how-to-name-an-updatable-help-cab-file.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="44e9f-122">For more information, see [How to Name an Updatable Help CAB File](./how-to-name-an-updatable-help-cab-file.md).</span></span>

7. <span data-ttu-id="44e9f-123">モジュールの CAB ファイルを、モジュールの HelpInfo XML ファイルの**Helpcontenturi**要素で指定された場所にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="44e9f-123">Upload the CAB files for the module to the location that is specified by the **HelpContentUri** element in the HelpInfo XML file for the module.</span></span> <span data-ttu-id="44e9f-124">次に、モジュールマニフェストの**Helpinfouri**キーによって指定された場所に HelpInfo XML ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="44e9f-124">Then upload the HelpInfo XML file to the location that is specified by the **HelpInfoUri** key of the module manifest.</span></span> <span data-ttu-id="44e9f-125">**Helpcontenturi**と**Helpinfouri**は同じ場所を指すことができます。</span><span class="sxs-lookup"><span data-stu-id="44e9f-125">The **HelpContentUri** and **HelpInfoUri** can point to the same location.</span></span>

> [!CAUTION]
> <span data-ttu-id="44e9f-126">**Helpinfouri**キーと**helpcontenturi**要素の値は、"http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="44e9f-126">The value of the **HelpInfoUri** key and the **HelpContentUri** element must begin with "http" or "https".</span></span> <span data-ttu-id="44e9f-127">値は、インターネット上の場所を示す必要があり、ファイル名を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="44e9f-127">The value must indicate an Internet location and it must not include a file name.</span></span>
