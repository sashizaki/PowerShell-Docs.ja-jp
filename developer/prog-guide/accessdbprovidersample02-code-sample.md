---
title: AccessDbProviderSample02 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b89a4903-3efc-4b08-9b20-2baadf1d1b66
caps.latest.revision: 6
ms.openlocfilehash: 67a169bfac0b0fc90e6ccd276d3d3592d1b70bb0
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082032"
---
# <a name="accessdbprovidersample02-code-sample"></a>AccessDbProviderSample02 コード サンプル

次のコードで説明されている Windows PowerShell プロバイダーの実装を示しています。 [Windows PowerShell ドライブ プロバイダーを作成する](./creating-a-windows-powershell-drive-provider.md)します。 この実装は、パスを作成し、Access データベースへの接続を確立して、ドライブを削除します。

> [!NOTE]
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、このプロバイダーのソース ファイル (AccessDBSampleProvider02.cs)。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。
>
> その他の Windows PowerShell プロバイダーの実装の詳細については、次を参照してください。 [Your Windows PowerShell プロバイダーの設計](./designing-your-windows-powershell-provider.md)します。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[AccessDBProviderSample02.cs](../../powershell-sdk-samples/SDK-2.0/csharp/AccessDBProviderSample02/AccessDBProviderSample02.cs#L11-L154 "AccessDBProviderSample02.cs")]


## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)