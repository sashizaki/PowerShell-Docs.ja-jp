---
title: Windows PowerShell プロバイダーを作成する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a54ce657-e0e0-4b3e-b9dc-aed39876f933
caps.latest.revision: 11
ms.openlocfilehash: 74e11e03e8a01568dad7c038de0b3ecebb2117e5
ms.sourcegitcommit: 173556307d45d88de31086ce776770547eece64c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "83562241"
---
# <a name="writing-a-windows-powershell-provider"></a><span data-ttu-id="24d91-102">Windows PowerShell プロバイダーを記述する</span><span class="sxs-lookup"><span data-stu-id="24d91-102">Writing a Windows PowerShell Provider</span></span>

<span data-ttu-id="24d91-103">「Windows PowerShell プロバイダーの記述」は、Windows PowerShell プロバイダーを設計するプログラムマネージャーと、プロバイダーコードを実装する開発者を対象としています。</span><span class="sxs-lookup"><span data-stu-id="24d91-103">"Writing a Windows PowerShell Provider" is for program managers who are designing Windows PowerShell providers and for developers who are implementing provider code.</span></span> <span data-ttu-id="24d91-104">これは、Windows PowerShell プロバイダーの動作を理解するのに役立ちます。また、独自のプロバイダーの設計または作成を開始するために使用できるサンプルコードも用意されています。</span><span class="sxs-lookup"><span data-stu-id="24d91-104">It will help you understand how Windows PowerShell providers work, and it provides sample code that you can use to start designing or writing your own providers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="24d91-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="24d91-105">In This Section</span></span>

<span data-ttu-id="24d91-106">[Windows PowerShell プロバイダーのクイックスタート](./windows-powershell-provider-quickstart.md)非常に基本的なプロバイダーのコード例とチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="24d91-106">[Windows PowerShell Provider QuickStart](./windows-powershell-provider-quickstart.md) Example code and walkthrough of a very basic provider.</span></span>

<span data-ttu-id="24d91-107">[Windows PowerShell プロバイダーの概要](./windows-powershell-provider-overview.md)このセクションには、Windows PowerShell プロバイダーの概要としくみについて説明するトピックが含まれています。</span><span class="sxs-lookup"><span data-stu-id="24d91-107">[Windows PowerShell Provider Overview](./windows-powershell-provider-overview.md) This section contains topics that describe what Windows PowerShell providers are and how they work.</span></span>

<span data-ttu-id="24d91-108">[項目プロバイダーの作成](./writing-an-item-provider.md)項目の取得と設定をサポートするメソッドのコード例とチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="24d91-108">[Writing an item provider](./writing-an-item-provider.md) Example code and walkthrough of methods that support getting and setting items.</span></span>

<span data-ttu-id="24d91-109">[コンテナープロバイダーの作成](./writing-a-container-provider.md)コンテナー (他の項目が子として設定されている項目) をサポートするメソッドのコード例とチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="24d91-109">[Writing a container provider](./writing-a-container-provider.md) Example code and walkthrough of methods that support containers (items that have other items as children).</span></span>

<span data-ttu-id="24d91-110">[ナビゲーションプロバイダーの作成](./writing-a-navigation-provider.md)入れ子になったコンテナー、相対パス、および1つのパスから別のパスへの項目の移動をサポートするメソッドのコード例とチュートリアルです。</span><span class="sxs-lookup"><span data-stu-id="24d91-110">[Writing a navigation provider](./writing-a-navigation-provider.md) Example code and walkthrough of methods that support nested containers, relative paths, and moving items from one path to another.</span></span>

<span data-ttu-id="24d91-111">[プロバイダーのサンプル](./provider-samples.md)ここでは、プロバイダーのサンプルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="24d91-111">[Provider Samples](./provider-samples.md) This section provides samples of providers.</span></span>

## <a name="see-also"></a><span data-ttu-id="24d91-112">参照</span><span class="sxs-lookup"><span data-stu-id="24d91-112">See Also</span></span>

[<span data-ttu-id="24d91-113">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="24d91-113">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
