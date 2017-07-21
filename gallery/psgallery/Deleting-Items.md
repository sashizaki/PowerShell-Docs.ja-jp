---
ms.date: 2017-06-12
contributor: JKeithB
ms.topic: conceptual
keywords: "ギャラリー, PowerShell, コマンドレット, PSGallery"
title: "アイテムを削除する"
ms.openlocfilehash: 00452f9b6625a51e95f3f46dbd66291fa20e17ad
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="deleting-items"></a><span data-ttu-id="b8733-103">アイテムを削除する</span><span class="sxs-lookup"><span data-stu-id="b8733-103">Deleting items</span></span>

<span data-ttu-id="b8733-104">PowerShell ギャラリーでは、アイテムを完全に削除することはできません。アイテムの依存関係がなくなるためです。</span><span class="sxs-lookup"><span data-stu-id="b8733-104">The PowerShell Gallery does not support permanent deletion of items, because that would break anyone who is depending on it remaining available.</span></span>

<span data-ttu-id="b8733-105">代わりに、PowerShell ギャラリーでは、Web サイトのアイテム管理ページでアイテムを "リストから外す" ことができます。</span><span class="sxs-lookup"><span data-stu-id="b8733-105">Instead, the PowerShell Gallery supports a way to 'unlist' an item, which can be done in the item management page on the web site.</span></span> <span data-ttu-id="b8733-106">アイテムがリストから外されると、PowerShell ギャラリーでも、PowerShellGet コマンドを使用しても、検索やアイテム リストにそのアイテムが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="b8733-106">When an item is unlisted, it no longer shows up in search and in any item listing, both on the PowerShell Gallery and using PowerShellGet commands.</span></span> <span data-ttu-id="b8733-107">ただし、正しいバージョンを指定すればダウンロードできます。正しいバージョンを指定することで、自動スクリプトが引き続き動作します。</span><span class="sxs-lookup"><span data-stu-id="b8733-107">However, it remains downloadable by specifying its exact version, which is what allows the automated scripts to continue working.</span></span>

<span data-ttu-id="b8733-108">アイテムを削除しなければならない、例外的な状況になった場合、PowerShell ギャラリー チームが手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="b8733-108">If you run into an exceptional situation where you think one of your items must be deleted, this can be handled manually by the PowerShell Gallery team.</span></span> <span data-ttu-id="b8733-109">たとえば、著作権の侵害や有害なコンテンツがあれば、それはアイテムを削除する正当な理由となります。</span><span class="sxs-lookup"><span data-stu-id="b8733-109">For example, if there is a copyright infringement issue, or potentially harmful content, that could be a valid reason to delete it.</span></span> <span data-ttu-id="b8733-110">その場合、[PowerShell ギャラリー] (http://www.PowerShellGallery.com) からサポート依頼を提出してください。</span><span class="sxs-lookup"><span data-stu-id="b8733-110">You should submit a support request through [PowerShell Gallery] (http://www.PowerShellGallery.com) in that case.</span></span>

