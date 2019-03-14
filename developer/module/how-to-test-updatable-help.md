---
title: 更新可能なヘルプをテストする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: cecc6c26ccaece06462ddd74b53534137fcf3037
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794265"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="38679-102">更新可能なヘルプをテストする方法</span><span class="sxs-lookup"><span data-stu-id="38679-102">How to Test Updatable Help</span></span>

<span data-ttu-id="38679-103">このトピックでは、モジュールの更新可能なヘルプをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38679-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="38679-104">エラーを検出する詳細な使用</span><span class="sxs-lookup"><span data-stu-id="38679-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="38679-105">HelpInfo XML ファイルと、モジュール用の CAB ファイルをアップロードした後、ファイルをテストを実行して、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドと、 **Verbose**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="38679-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="38679-106">**Verbose**パラメーター`Update-Help`読み取りから、その操作で重要な手順を報告する、 **HelpInfoUri**アンパックされた CAB ファイルのファイルの種類を検証するモジュール マニフェストでキー言語固有のモジュール ディレクトリにファイルを配置します。</span><span class="sxs-lookup"><span data-stu-id="38679-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="38679-107">すべての詳細なメッセージが解決された場合は、実行、`Update-Help`コマンドと、**デバッグ**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="38679-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span> <span data-ttu-id="38679-108">このパラメーターは、更新可能なヘルプ ファイルの残りの問題を検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38679-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>