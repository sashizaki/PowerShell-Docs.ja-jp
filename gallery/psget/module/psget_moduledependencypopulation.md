---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: psget_moduledependencypopulation
ms.openlocfilehash: c4c9f203e9c526ff532c2388acb6334515d66934
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="logic-for-preparing-the-module-dependencies-during-publish-operation"></a><span data-ttu-id="a1491-103">発行操作中にモジュールの依存関係を準備するためのロジック</span><span class="sxs-lookup"><span data-stu-id="a1491-103">Logic for preparing the module dependencies during Publish operation</span></span>
1.  <span data-ttu-id="a1491-104">RequiredModules の一部として一覧表示されているモジュールは、依存関係として見なされます。</span><span class="sxs-lookup"><span data-stu-id="a1491-104">Modules listed as part of RequiredModules are considered as dependencies.</span></span>
2.  <span data-ttu-id="a1491-105">NestedModules の一部として一覧表示されているモジュール (モジュール ベースが指定されたモジュール ベースの下にないモジュール) は、依存関係として見なされます。</span><span class="sxs-lookup"><span data-stu-id="a1491-105">Modules listed as part of NestedModules, whose module base is not under the specified module base, are considered as dependencies.</span></span>

3.  <span data-ttu-id="a1491-106">上記の依存関係は同じターゲット リポジトリで利用できる必要があります。それ以外の場合、発行操作を実行するとエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="a1491-106">Above dependencies should be available on the same target repository, otherwise publish operation will result in an error.</span></span>
    <span data-ttu-id="a1491-107">たとえば、'SnippetPx' をリポジトリで使用できない場合は、以下のエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="a1491-107">For example: If 'SnippetPx' is not available on the repository, below error will be thrown.</span></span>
    ```powershell
    Publish-PSArtifactUtility : PowerShellGet cannot resolve the module dependency 'SnippetPx' of the module 'TypePx' on the repository 'LocalRepo'. Verify that the dependent module 'SnippetPx' is available in the repository 'LocalRepo'. If this dependent
    'SnippetPx' is managed externally, add it to the ExternalModuleDependencies entry in the PSData section of the module manifest.
    ```
4.  <span data-ttu-id="a1491-108">一部のモジュールの依存関係は外部で管理できます。その場合は、モジュール マニフェストの PSData セクション内の ExternalModuleDependencies エントリに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1491-108">Some module dependencies can be managed externally, in that case they should be added to the ExternalModuleDependencies entry in the PSData section of the module manifest.</span></span>
    <span data-ttu-id="a1491-109">上記のエラー メッセージの後半部分</span><span class="sxs-lookup"><span data-stu-id="a1491-109">Below part in the above error message</span></span>
    ```powershell
    If this dependent 'SnippetPx' is managed externally, add it to the ExternalModuleDependencies entry in the PSData section of the module manifest.
    ```

<span data-ttu-id="a1491-110">*モジュールのインストール時に、上記の準備された依存関係一覧が依存関係のインストールに使用されます。*</span><span class="sxs-lookup"><span data-stu-id="a1491-110">*During the module installation, above prepared dependencies list is used for installing the dependencies.*</span></span>

<span data-ttu-id="a1491-111">*発行操作中にモジュールの依存関係がシステムの $env:PSModulePath で使用可能なことを確認してください。*</span><span class="sxs-lookup"><span data-stu-id="a1491-111">*Please ensure that your module’s dependencies are available under $env:PSModulePath on your system during publish operation.*</span></span>