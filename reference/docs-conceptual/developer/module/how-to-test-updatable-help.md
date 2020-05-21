---
title: 更新可能なヘルプのテスト方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e064048-2b94-4365-bdb7-f1ee7c0a7fd7
caps.latest.revision: 6
ms.openlocfilehash: 8dd3770a60ca56634ad1eb1ac8cf89d96c975c90
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83560510"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="960a8-102">更新可能なヘルプをテストする方法</span><span class="sxs-lookup"><span data-stu-id="960a8-102">How to Test Updatable Help</span></span>

<span data-ttu-id="960a8-103">このトピックでは、モジュールの更新可能なヘルプをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="960a8-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="960a8-104">Verbose を使用してエラーを検出する</span><span class="sxs-lookup"><span data-stu-id="960a8-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="960a8-105">モジュールの HelpInfo XML ファイルと CAB ファイルをアップロードしたら、 **Verbose**パラメーターを指定して[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドを実行し、ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="960a8-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="960a8-106">**Verbose**パラメーターは、 `Update-Help` アクションの重要なステップを報告するように指示します。これには、モジュールマニフェストの**helpinfouri**キーを読み取って、展開された CAB ファイル内のファイルの種類を検証し、それらのファイルを言語固有のモジュールディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="960a8-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="960a8-107">すべての詳細メッセージを解決したら、 `Update-Help` **Debug**パラメーターを指定してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="960a8-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span> <span data-ttu-id="960a8-108">このパラメーターは、更新可能なヘルプファイルに関する残りの問題を検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="960a8-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>
