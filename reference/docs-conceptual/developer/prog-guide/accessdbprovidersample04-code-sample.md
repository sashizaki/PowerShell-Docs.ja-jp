---
title: AccessDbProviderSample04 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 05509c5b36475bcd3f91c9ab7413974994d668d6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787276"
---
# <a name="accessdbprovidersample04-code-sample"></a><span data-ttu-id="32f4a-102">AccessDbProviderSample04 コード サンプル</span><span class="sxs-lookup"><span data-stu-id="32f4a-102">AccessDbProviderSample04 Code Sample</span></span>

<span data-ttu-id="32f4a-103">次のコードは、「 [Windows Powershell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」で説明されている windows powershell プロバイダーの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="32f4a-103">The following code shows the implementation of the Windows PowerShell provider described in [Creating a Windows PowerShell Container Provider](./creating-a-windows-powershell-container-provider.md).</span></span>
<span data-ttu-id="32f4a-104">このプロバイダーは、マルチレイヤーデータストアに対して機能します。</span><span class="sxs-lookup"><span data-stu-id="32f4a-104">This provider works on multi-layer data stores.</span></span> <span data-ttu-id="32f4a-105">この種類のデータストアの場合、ストアの最上位レベルにはルート項目が含まれ、それ以降の各レベルは子項目のノードと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="32f4a-105">For this type of data store, the top level of the store contains the root items and each subsequent level is referred to as a node of child items.</span></span> <span data-ttu-id="32f4a-106">ユーザーがこれらの子ノードを操作できるようにすることで、ユーザーはデータストアを介して階層的に対話できます。</span><span class="sxs-lookup"><span data-stu-id="32f4a-106">By allowing the user to work on these child nodes, a user can interact hierarchically through the data store.</span></span>

## <a name="code-sample"></a><span data-ttu-id="32f4a-107">コード サンプル</span><span class="sxs-lookup"><span data-stu-id="32f4a-107">Code Sample</span></span>

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a><span data-ttu-id="32f4a-108">参照</span><span class="sxs-lookup"><span data-stu-id="32f4a-108">See Also</span></span>

[<span data-ttu-id="32f4a-109">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="32f4a-109">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
