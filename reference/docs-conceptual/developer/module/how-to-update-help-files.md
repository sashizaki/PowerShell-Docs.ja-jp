---
title: ヘルプファイルを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 35b3fd696419d0135fd6f662223e6c8586df443a
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83561392"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="00160-102">ヘルプ ファイルを更新する方法</span><span class="sxs-lookup"><span data-stu-id="00160-102">How to Update Help Files</span></span>

<span data-ttu-id="00160-103">このトピックでは、更新可能なヘルプをサポートするモジュールのヘルプファイルを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00160-103">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="00160-104">ヘルプファイルの更新</span><span class="sxs-lookup"><span data-stu-id="00160-104">Updating Help Files</span></span>

<span data-ttu-id="00160-105">ヘルプファイルの更新には、エラーの修正、概念の明確化、よく寄せられる質問への回答、新しいファイルの追加、新しい例の追加など、さまざまな理由があります。</span><span class="sxs-lookup"><span data-stu-id="00160-105">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="00160-106">ヘルプファイルを更新するには:</span><span class="sxs-lookup"><span data-stu-id="00160-106">To update a help file:</span></span>

1. <span data-ttu-id="00160-107">ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="00160-107">Change the files.</span></span>

2. <span data-ttu-id="00160-108">ファイルを他の UI カルチャに変換します。</span><span class="sxs-lookup"><span data-stu-id="00160-108">Translate the files into other UI cultures.</span></span>

3. <span data-ttu-id="00160-109">各 UI カルチャのモジュールについて、すべてのヘルプファイル (新規、変更済み、および変更されていない) を収集します。</span><span class="sxs-lookup"><span data-stu-id="00160-109">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>

4. <span data-ttu-id="00160-110">XML スキーマに対してファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="00160-110">Validate the files against the XML schema.</span></span>

5. <span data-ttu-id="00160-111">各 UI カルチャの CAB ファイルをリビルドします。</span><span class="sxs-lookup"><span data-stu-id="00160-111">Rebuild the CAB files for each UI culture.</span></span>

6. <span data-ttu-id="00160-112">HelpInfo XML ファイルで、各 UI カルチャの CAB ファイルのバージョン番号をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="00160-112">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>

7. <span data-ttu-id="00160-113">HelpInfo XML ファイルの**Helpcontenturi**要素の値によって指定された場所に新しい CAB ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="00160-113">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="00160-114">古い CAB ファイルを新しい CAB ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="00160-114">Replace the older CAB files with the new CAB files.</span></span>

8. <span data-ttu-id="00160-115">更新された HelpInfo XML ファイルを、モジュールマニフェストの**Helpinfouri**キーによって指定された場所にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="00160-115">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="00160-116">古い HelpInfo XML ファイルを新しいファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="00160-116">Replace the older HelpInfo XML file with the new file.</span></span>
