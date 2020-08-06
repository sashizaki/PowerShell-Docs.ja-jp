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
# <a name="accessdbprovidersample04-code-sample"></a>AccessDbProviderSample04 コード サンプル

次のコードは、「 [Windows Powershell コンテナープロバイダーの作成](./creating-a-windows-powershell-container-provider.md)」で説明されている windows powershell プロバイダーの実装を示しています。
このプロバイダーは、マルチレイヤーデータストアに対して機能します。 この種類のデータストアの場合、ストアの最上位レベルにはルート項目が含まれ、それ以降の各レベルは子項目のノードと呼ばれます。 ユーザーがこれらの子ノードを操作できるようにすることで、ユーザーはデータストアを介して階層的に対話できます。

## <a name="code-sample"></a>コード サンプル

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample04/AccessDBProviderSample04.cs" range="11-1635":::

## <a name="see-also"></a>参照

[Windows PowerShell SDK](../windows-powershell-reference.md)
