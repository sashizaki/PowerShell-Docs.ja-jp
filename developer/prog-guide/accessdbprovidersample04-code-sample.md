---
title: AccessDbProviderSample04 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9374c4a-e499-4516-9eb6-107c59df98d9
caps.latest.revision: 7
ms.openlocfilehash: 43f01b9cd6af3ab6c26f88ee0c1e9269499b2bc3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62081956"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="e77f0-102">AccessDbProviderSample04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="e77f0-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="e77f0-103">次のコードで説明されている Windows PowerShell プロバイダーの実装を示しています。 [Windows PowerShell コンテナー プロバイダーを作成する](./creating-a-windows-powershell-container-provider.md)します。</span><span class="sxs-lookup"><span data-stu-id="e77f0-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span> <span data-ttu-id="e77f0-104">このプロバイダーは、複数レイヤーのデータ ストアで動作します。</span><span class="sxs-lookup"><span data-stu-id="e77f0-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="e77f0-105">この種類のデータ ストアでのストアの最上位レベルには、ルート項目が含まれています。 と後続の各レベルは子項目のノードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="e77f0-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="e77f0-106">これらの子ノードで作業するユーザーを許可すると、ユーザーから操作できる階層的に、データ ストア。</span><span class="sxs-lookup"><span data-stu-id="e77f0-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="e77f0-107">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="e77f0-107">Code Sample</span></span>

[!code-csharp[AccessDBProviderSample04.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs#L11-L1635 "AccessDBProviderSample04.cs")]

## <a name="see-also"></a><span data-ttu-id="e77f0-108">参照</span><span class="sxs-lookup"><span data-stu-id="e77f0-108">See Also</span></span>

[<span data-ttu-id="e77f0-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e77f0-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)