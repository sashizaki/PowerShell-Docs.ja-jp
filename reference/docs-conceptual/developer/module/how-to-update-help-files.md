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
ms.openlocfilehash: 2c1fbd70aab1f65f33ea206b7ab1e2bd3dfd8c7a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367141"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="0e4ae-102">ヘルプ ファイルを更新する方法</span><span class="sxs-lookup"><span data-stu-id="0e4ae-102">How to Update Help Files</span></span>

<span data-ttu-id="0e4ae-103">このトピックでは、更新可能なヘルプをサポートするモジュールのヘルプファイルを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-103">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="0e4ae-104">ヘルプファイルの更新</span><span class="sxs-lookup"><span data-stu-id="0e4ae-104">Updating Help Files</span></span>

<span data-ttu-id="0e4ae-105">ヘルプファイルの更新には、エラーの修正、概念の明確化、よく寄せられる質問への回答、新しいファイルの追加、新しい例の追加など、さまざまな理由があります。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-105">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="0e4ae-106">ヘルプファイルを更新するには:</span><span class="sxs-lookup"><span data-stu-id="0e4ae-106">To update a help file:</span></span>

1. <span data-ttu-id="0e4ae-107">ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-107">Change the files.</span></span>

2. <span data-ttu-id="0e4ae-108">ファイルを他の UI カルチャに変換します。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-108">Translate the files into other UI cultures.</span></span>

3. <span data-ttu-id="0e4ae-109">各 UI カルチャのモジュールについて、すべてのヘルプファイル (新規、変更済み、および変更されていない) を収集します。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-109">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>

4. <span data-ttu-id="0e4ae-110">XML スキーマに対してファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-110">Validate the files against the XML schema.</span></span>

5. <span data-ttu-id="0e4ae-111">各 UI カルチャの CAB ファイルをリビルドします。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-111">Rebuild the CAB files for each UI culture.</span></span>

6. <span data-ttu-id="0e4ae-112">HelpInfo XML ファイルで、各 UI カルチャの CAB ファイルのバージョン番号をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-112">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>

7. <span data-ttu-id="0e4ae-113">HelpInfo XML ファイルの**Helpcontenturi**要素の値によって指定された場所に新しい CAB ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-113">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="0e4ae-114">古い CAB ファイルを新しい CAB ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-114">Replace the older CAB files with the new CAB files.</span></span>

8. <span data-ttu-id="0e4ae-115">更新された HelpInfo XML ファイルを、モジュールマニフェストの**Helpinfouri**キーによって指定された場所にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-115">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="0e4ae-116">古い HelpInfo XML ファイルを新しいファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0e4ae-116">Replace the older HelpInfo XML file with the new file.</span></span>