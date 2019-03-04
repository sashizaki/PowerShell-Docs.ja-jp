---
title: ヘルプ ファイルを更新する方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 495869a6-080e-4401-9ddc-16edd2f86857
caps.latest.revision: 6
ms.openlocfilehash: 2c1fbd70aab1f65f33ea206b7ab1e2bd3dfd8c7a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855528"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="79180-102">ヘルプ ファイルを更新する方法</span><span class="sxs-lookup"><span data-stu-id="79180-102">How to Update Help Files</span></span>

<span data-ttu-id="79180-103">このトピックでは、更新可能なヘルプをサポートするモジュールのヘルプ ファイルを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="79180-103">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="79180-104">ヘルプ ファイルを更新しています</span><span class="sxs-lookup"><span data-stu-id="79180-104">Updating Help Files</span></span>

<span data-ttu-id="79180-105">エラーを修正、概念を明確化、よく寄せられる質問に答えの新しいファイルを追加する新しいより良い例の追加などのヘルプ ファイルを更新する多くの理由があります。</span><span class="sxs-lookup"><span data-stu-id="79180-105">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="79180-106">ヘルプ ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="79180-106">To update a help file:</span></span>

1. <span data-ttu-id="79180-107">ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="79180-107">Change the files.</span></span>

2. <span data-ttu-id="79180-108">ファイルを他の UI カルチャに翻訳します。</span><span class="sxs-lookup"><span data-stu-id="79180-108">Translate the files into other UI cultures.</span></span>

3. <span data-ttu-id="79180-109">すべてのヘルプ ファイル (新しい、変更、および変更されていない) 各 UI カルチャでモジュールを収集します。</span><span class="sxs-lookup"><span data-stu-id="79180-109">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>

4. <span data-ttu-id="79180-110">XML スキーマに対してファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="79180-110">Validate the files against the XML schema.</span></span>

5. <span data-ttu-id="79180-111">各 UI カルチャ用の CAB ファイルを再構築します。</span><span class="sxs-lookup"><span data-stu-id="79180-111">Rebuild the CAB files for each UI culture.</span></span>

6. <span data-ttu-id="79180-112">HelpInfo XML ファイルでは、各 UI カルチャ用の CAB ファイルのバージョン番号をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="79180-112">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>

7. <span data-ttu-id="79180-113">値によって指定されている場所に新しい CAB ファイルをアップロード、 **HelpContentUri** HelpInfo XML ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="79180-113">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="79180-114">以前の CAB ファイルを新しい CAB ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="79180-114">Replace the older CAB files with the new CAB files.</span></span>

8. <span data-ttu-id="79180-115">指定された場所に更新された HelpInfo XML ファイルをアップロード、 **HelpInfoUri**モジュール マニフェストでキー。</span><span class="sxs-lookup"><span data-stu-id="79180-115">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="79180-116">古い HelpInfo XML ファイルを新しいファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="79180-116">Replace the older HelpInfo XML file with the new file.</span></span>