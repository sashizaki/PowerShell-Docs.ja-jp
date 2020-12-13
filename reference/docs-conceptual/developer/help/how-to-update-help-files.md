---
ms.date: 09/12/2016
ms.topic: reference
title: ヘルプ ファイルを更新する方法
description: ヘルプ ファイルを更新する方法
ms.openlocfilehash: 19bf501cf91b1eb5dabb334c2179953590b40232
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649580"
---
# <a name="how-to-update-help-files"></a><span data-ttu-id="8278d-103">ヘルプ ファイルを更新する方法</span><span class="sxs-lookup"><span data-stu-id="8278d-103">How to Update Help Files</span></span>

<span data-ttu-id="8278d-104">このトピックでは、更新可能なヘルプをサポートするモジュールのヘルプファイルを更新する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8278d-104">This topic explains how to update help files for a module that supports Updatable Help.</span></span>

## <a name="updating-help-files"></a><span data-ttu-id="8278d-105">ヘルプファイルの更新</span><span class="sxs-lookup"><span data-stu-id="8278d-105">Updating Help Files</span></span>

<span data-ttu-id="8278d-106">ヘルプファイルの更新には、エラーの修正、概念の明確化、よく寄せられる質問への回答、新しいファイルの追加、新しい例の追加など、さまざまな理由があります。</span><span class="sxs-lookup"><span data-stu-id="8278d-106">There are many reasons to update help files, such as correcting errors, clarifying a concept, answering a frequently-asked question, adding new files, or adding new and better examples.</span></span>

<span data-ttu-id="8278d-107">ヘルプファイルを更新するには:</span><span class="sxs-lookup"><span data-stu-id="8278d-107">To update a help file:</span></span>

1. <span data-ttu-id="8278d-108">ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="8278d-108">Change the files.</span></span>
1. <span data-ttu-id="8278d-109">ファイルを他の UI カルチャに変換します。</span><span class="sxs-lookup"><span data-stu-id="8278d-109">Translate the files into other UI cultures.</span></span>
1. <span data-ttu-id="8278d-110">各 UI カルチャのモジュールについて、すべてのヘルプファイル (新規、変更済み、および変更されていない) を収集します。</span><span class="sxs-lookup"><span data-stu-id="8278d-110">Collect all help files (new, changed, and unchanged) for the module in each UI culture.</span></span>
1. <span data-ttu-id="8278d-111">XML スキーマに対してファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="8278d-111">Validate the files against the XML schema.</span></span>
1. <span data-ttu-id="8278d-112">各 UI カルチャの CAB ファイルをリビルドします。</span><span class="sxs-lookup"><span data-stu-id="8278d-112">Rebuild the CAB files for each UI culture.</span></span>
1. <span data-ttu-id="8278d-113">HelpInfo XML ファイルで、各 UI カルチャの CAB ファイルのバージョン番号をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="8278d-113">In the HelpInfo XML file, increment the version numbers of the CAB file for each UI culture.</span></span>
1. <span data-ttu-id="8278d-114">HelpInfo XML ファイルの **Helpcontenturi** 要素の値によって指定された場所に新しい CAB ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8278d-114">Upload the new CAB files to the location that is specified by the value of the **HelpContentUri** element in the HelpInfo XML file.</span></span> <span data-ttu-id="8278d-115">古い CAB ファイルを新しい CAB ファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8278d-115">Replace the older CAB files with the new CAB files.</span></span>
1. <span data-ttu-id="8278d-116">更新された HelpInfo XML ファイルを、モジュールマニフェストの **Helpinfouri** キーによって指定された場所にアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8278d-116">Upload the updated HelpInfo XML file to the location that is specified by the **HelpInfoUri** key in the module manifest.</span></span> <span data-ttu-id="8278d-117">古い HelpInfo XML ファイルを新しいファイルに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="8278d-117">Replace the older HelpInfo XML file with the new file.</span></span>
