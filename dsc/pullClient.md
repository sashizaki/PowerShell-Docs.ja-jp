---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC プル クライアントのセットアップ"
ms.openlocfilehash: d2d1bab7ba2b482b2a66ce59b5f80ea32c242c47
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="setting-up-a-dsc-pull-client"></a><span data-ttu-id="d19ad-103">DSC プル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="d19ad-103">Setting up a DSC pull client</span></span>

> <span data-ttu-id="d19ad-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="d19ad-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="d19ad-105">各ターゲット ノードに対し、プル モードを使用するように指示する必要があります。また、プル サーバーに接続して構成とリソースを取得し、レポート データの送信先にするための URL またはファイルの場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d19ad-105">Each target node has to be told to use pull mode and given the URL or file location where it can contact the pull server to get configurations and resources, and where it should send report data.</span></span>


<span data-ttu-id="d19ad-106">次のトピックでは、プル クライアントをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d19ad-106">The following topics explain how to set up pull clients:</span></span>

* [<span data-ttu-id="d19ad-107">構成名を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="d19ad-107">Setting up a pull client using configuration names</span></span>](pullClientConfigNames.md)
* [<span data-ttu-id="d19ad-108">構成 ID を使用したプル クライアントのセットアップ</span><span class="sxs-lookup"><span data-stu-id="d19ad-108">Setting up a pull client using configuration ID</span></span>](pullClientConfigID.md)

> <span data-ttu-id="d19ad-109">**注**: これらのトピックは、PowerShell 5.0 に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d19ad-109">**Note**: These topics apply to PowerShell 5.0.</span></span> <span data-ttu-id="d19ad-110">PowerShell 4.0 でのプル クライアントのセットアップについては、「[PowerShell 4.0 での構成 ID を使用したプル クライアントのセットアップ](pullClientConfigID4.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d19ad-110">To set up a pull client in PowerShell 4.0, see [Setting up a pull client using configuration ID in PowerShell 4.0](pullClientConfigID4.md).</span></span>

