---
title: AccessDbProviderSample04 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9374c4a-e499-4516-9eb6-107c59df98d9
caps.latest.revision: 7
ms.openlocfilehash: ff43286bc90c1a4d2270be0ee03ca5910867cec2
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72366971"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="2f990-102">AccessDbProviderSample04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="2f990-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="2f990-103">次のコードは、「 [Windows Powershell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」で説明されている windows powershell プロバイダーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="2f990-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span> <span data-ttu-id="2f990-104">このプロバイダーは、マルチレイヤーデータストアに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="2f990-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="2f990-105">この種類のデータストアの場合、ストアの最上位レベルにはルート項目が含まれ、それ以降の各レベルは子項目のノードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="2f990-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="2f990-106">ユーザーがこれらの子ノードを操作できるようにすることで、ユーザーはデータストアを介して階層的に対話できます。</span><span class="sxs-lookup"><span data-stu-id="2f990-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="2f990-107">コードサンプル</span><span class="sxs-lookup"><span data-stu-id="2f990-107">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="2f990-108">参照</span><span class="sxs-lookup"><span data-stu-id="2f990-108">See Also</span></span>

[<span data-ttu-id="2f990-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="2f990-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
