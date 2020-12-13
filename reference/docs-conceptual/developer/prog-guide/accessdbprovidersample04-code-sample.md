---
ms.date: 09/13/2016
ms.topic: reference
title: AccessDbProviderSample04 コード サンプル
description: AccessDbProviderSample04 コード サンプル
ms.openlocfilehash: bb70ce9f1b1c94349c354a8771fedf7fcb1bb320
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647571"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="92fe6-103">AccessDbProviderSample04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="92fe6-103">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="92fe6-104">次のコードは、「 [Windows Powershell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」で説明されている windows powershell プロバイダーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="92fe6-104">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="92fe6-105">このプロバイダーは、マルチレイヤーデータストアに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="92fe6-105">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="92fe6-106">この種類のデータストアの場合、ストアの最上位レベルにはルート項目が含まれ、それ以降の各レベルは子項目のノードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="92fe6-106">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="92fe6-107">ユーザーがこれらの子ノードを操作できるようにすることで、ユーザーはデータストアを介して階層的に対話できます。</span><span class="sxs-lookup"><span data-stu-id="92fe6-107">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="92fe6-108">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="92fe6-108">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="92fe6-109">参照</span><span class="sxs-lookup"><span data-stu-id="92fe6-109">See Also</span></span>

[<span data-ttu-id="92fe6-110">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="92fe6-110">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
