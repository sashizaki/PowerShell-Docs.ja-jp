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
ms.openlocfilehash: cecc6c26ccaece06462ddd74b53534137fcf3037
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367151"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="2f284-102">更新可能なヘルプをテストする方法</span><span class="sxs-lookup"><span data-stu-id="2f284-102">How to Test Updatable Help</span></span>

<span data-ttu-id="2f284-103">このトピックでは、モジュールの更新可能なヘルプをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2f284-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="2f284-104">Verbose を使用してエラーを検出する</span><span class="sxs-lookup"><span data-stu-id="2f284-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="2f284-105">モジュールの HelpInfo XML ファイルと CAB ファイルをアップロードしたら、 **Verbose**パラメーターを指定して[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドを実行し、ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="2f284-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="2f284-106">**Verbose**パラメーターは、アクションの重要なステップを報告するように `Update-Help` に指示します。これには、モジュールマニフェストの**Helpinfouri**キーを読み取って、展開された CAB ファイル内のファイルの種類を検証し、ファイルを言語固有のものに配置します。モジュールディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="2f284-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="2f284-107">すべての詳細メッセージを解決したら、 **Debug**パラメーターを指定して @no__t 0 のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2f284-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span> <span data-ttu-id="2f284-108">このパラメーターは、更新可能なヘルプファイルに関する残りの問題を検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f284-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>