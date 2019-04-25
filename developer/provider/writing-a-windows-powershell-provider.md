---
title: Windows PowerShell プロバイダーの記述 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a54ce657-e0e0-4b3e-b9dc-aed39876f933
caps.latest.revision: 11
ms.openlocfilehash: 58252956184703fdcdb3aa9b1db617c6e91294c1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62080836"
---
# <a name="writing-a-windows-powershell-provider"></a><span data-ttu-id="bd3d8-102">Windows PowerShell プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="bd3d8-102">Writing a Windows PowerShell Provider</span></span>

<span data-ttu-id="bd3d8-103">Windows PowerShell プロバイダーを設計する場合に、プログラム マネージャー、プロバイダー コードを実装している開発者は、「Windows PowerShell プロバイダーの記述」。</span><span class="sxs-lookup"><span data-stu-id="bd3d8-103">"Writing a Windows PowerShell Provider" is for program managers who are designing Windows PowerShell providers and for developers who are implementing provider code.</span></span> <span data-ttu-id="bd3d8-104">Windows PowerShell プロバイダーの連携方法を理解するのに役立ち、設計または独自のプロバイダーの書き込みを開始するために使用できるサンプル コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd3d8-104">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="bd3d8-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="bd3d8-105">In This Section</span></span>

<span data-ttu-id="bd3d8-106">[Windows PowerShell プロバイダーのクイック スタート](./windows-powershell-provider-quickstart.md)のコード例と、非常に基本的なプロバイダーのチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="bd3d8-106">[Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md) Example code and walkthrough of a very basic provider.</span></span>

<span data-ttu-id="bd3d8-107">[Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)ここには、Windows PowerShell プロバイダーの概要とそのしくみを説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bd3d8-107">[Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md) This section contains topics that describe what Windows PowerShell providers are and how they work.</span></span>

<span data-ttu-id="bd3d8-108">[項目プロバイダーの作成](./writing-an-item-provider.md)のコード例とチュートリアルの取得および設定項目をサポートするメソッド。</span><span class="sxs-lookup"><span data-stu-id="bd3d8-108">[Writing an item provider](./writing-an-item-provider.md) Example code and walkthrough of methods that support getting and setting items.</span></span>

<span data-ttu-id="bd3d8-109">[コンテナーのプロバイダーを記述](./writing-a-container-provider.md)のコード例とコンテナー (子として他の項目がある項目) をサポートする方法のチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="bd3d8-109">[Writing a container provider](./writing-a-container-provider.md) Example code and walkthrough of methods that support containers (items that have other items as children).</span></span>

<span data-ttu-id="bd3d8-110">[書き込みナビゲーション プロバイダー](./writing-a-navigation-provider.md)のコード例と入れ子になったコンテナー、相対パスは、1 つのパスから間の移動の項目をサポートする方法のチュートリアル。</span><span class="sxs-lookup"><span data-stu-id="bd3d8-110">[Writing a navigation provider](./writing-a-navigation-provider.md) Example code and walkthrough of methods that support nested containers, relative paths, and moving items from one path to another.</span></span>

<span data-ttu-id="bd3d8-111">[プロバイダーのサンプル](./provider-samples.md)このセクションでは、プロバイダーのサンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="bd3d8-111">[Provider Samples](./provider-samples.md) This section provides samples of providers.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd3d8-112">参照</span><span class="sxs-lookup"><span data-stu-id="bd3d8-112">See Also</span></span>

[<span data-ttu-id="bd3d8-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="bd3d8-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)