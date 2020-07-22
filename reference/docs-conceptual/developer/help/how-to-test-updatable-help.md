---
title: 更新可能なヘルプをテストする方法
ms.date: 09/12/2016
ms.openlocfilehash: 0602349f853fddd0cadae545eaf0302c150e3a28
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86892967"
---
# <a name="how-to-test-updatable-help"></a><span data-ttu-id="31abb-102">更新可能なヘルプをテストする方法</span><span class="sxs-lookup"><span data-stu-id="31abb-102">How to Test Updatable Help</span></span>

<span data-ttu-id="31abb-103">このトピックでは、モジュールの更新可能なヘルプをテストする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="31abb-103">This topic describes approaches to testing Updatable Help for a module.</span></span>

## <a name="using-verbose-to-detect-errors"></a><span data-ttu-id="31abb-104">Verbose を使用してエラーを検出する</span><span class="sxs-lookup"><span data-stu-id="31abb-104">Using Verbose to Detect Errors</span></span>

<span data-ttu-id="31abb-105">モジュールの HelpInfo XML ファイルと CAB ファイルをアップロードしたら、 **Verbose**パラメーターを指定して[update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドを実行し、ファイルをテストします。</span><span class="sxs-lookup"><span data-stu-id="31abb-105">After uploading the HelpInfo XML file and CAB files for your module, test the files by running an [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) command with the **Verbose** parameter.</span></span> <span data-ttu-id="31abb-106">**Verbose**パラメーターは、 `Update-Help` アクションの重要なステップを報告するように指示します。これには、モジュールマニフェストの**helpinfouri**キーを読み取って、展開された CAB ファイル内のファイルの種類を検証し、それらのファイルを言語固有のモジュールディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="31abb-106">The **Verbose** parameter directs `Update-Help` to report the critical steps in its actions, from reading the **HelpInfoUri** key in the module manifest to validating the file types in the unpacked CAB file and placing the files in the language-specific module directory.</span></span>

<span data-ttu-id="31abb-107">すべての詳細メッセージを解決したら、 `Update-Help` **Debug**パラメーターを指定してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="31abb-107">When all verbose messages are resolved, run an `Update-Help` command with the **Debug** parameter.</span></span>
<span data-ttu-id="31abb-108">このパラメーターは、更新可能なヘルプファイルに関する残りの問題を検出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31abb-108">This parameter should detect any remaining problems with the Updatable Help files.</span></span>
