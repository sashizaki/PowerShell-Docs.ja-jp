---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: パッケージを削除する
ms.openlocfilehash: 6bfb43b95e51d38bd606198cb8d2d9af0aa0be1e
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "71327933"
---
# <a name="deleting-packages"></a><span data-ttu-id="2fd9e-103">パッケージを削除する</span><span class="sxs-lookup"><span data-stu-id="2fd9e-103">Deleting Packages</span></span>

<span data-ttu-id="2fd9e-104">PowerShell ギャラリーでは、パッケージを完全に削除することはできません。パッケージの依存関係がなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="2fd9e-104">The PowerShell Gallery does not support permanent deletion of packages, because that would break anyone who is depending on it remaining available.</span></span>

<span data-ttu-id="2fd9e-105">代わりに、PowerShell ギャラリーでは、Web サイトのパッケージ管理ページでパッケージを "リストから外す" ことができます。</span><span class="sxs-lookup"><span data-stu-id="2fd9e-105">Instead, the PowerShell Gallery supports a way to 'unlist' a package, which can be done in the package management page on the web site.</span></span>
<span data-ttu-id="2fd9e-106">パッケージがリストから外されると、PowerShell ギャラリーでも、PowerShellGet コマンドを使用しても、検索やパッケージ リストにそのパッケージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="2fd9e-106">When a package is unlisted, it no longer shows up in search and in any package listing, both on the PowerShell Gallery and using PowerShellGet commands.</span></span>
<span data-ttu-id="2fd9e-107">ただし、正しいバージョンを指定すればダウンロードできます。正しいバージョンを指定することで、自動スクリプトが引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="2fd9e-107">However, it remains downloadable by specifying its exact version, which is what allows the automated scripts to continue working.</span></span>

<span data-ttu-id="2fd9e-108">パッケージを削除しなければならない、例外的な状況になった場合、PowerShell ギャラリー チームが手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="2fd9e-108">If you run into an exceptional situation where you think one of your packages must be deleted, this can be handled manually by the PowerShell Gallery team.</span></span>
<span data-ttu-id="2fd9e-109">たとえば、著作権の侵害や有害なコンテンツがあれば、それはアイテムを削除する正当な理由となります。</span><span class="sxs-lookup"><span data-stu-id="2fd9e-109">For example, if there is a copyright infringement issue, or potentially harmful content, that could be a valid reason to delete it.</span></span>
<span data-ttu-id="2fd9e-110">その場合、[PowerShell ギャラリー](https://www.PowerShellGallery.com)からサポート要求を提出してください。</span><span class="sxs-lookup"><span data-stu-id="2fd9e-110">You should submit a support request through [PowerShell Gallery](https://www.PowerShellGallery.com) in that case.</span></span>
