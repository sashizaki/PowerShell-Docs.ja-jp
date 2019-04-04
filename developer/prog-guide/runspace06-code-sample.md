---
title: RunSpace06 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d71f86d5-eb62-4b16-aa95-5fd3f314ffd3
caps.latest.revision: 6
ms.openlocfilehash: d0330f082262b68486a582ed95c7a520be1e184c
ms.sourcegitcommit: 69abc5ad16e5dd29ddfb1853e266a4bfd1d59d59
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57429535"
---
# <a name="runspace06-code-sample"></a>RunSpace06 コード サンプル

記載されている Runspace06 サンプルのソース コードを次に示します[、Windows PowerShell スナップインを使用して、実行空間を構成する](http://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83)します。 このサンプル アプリケーションは、Windows PowerShell スナップインを 1 つのコマンドを使用して、パイプラインの実行を使用して、これに基づいて、実行空間を作成します。 これを行うには、アプリケーション実行空間の構成情報を作成、実行空間を作成します、1 つのコマンドでパイプラインを作成しますおよびし、パイプラインを実行します。

> [!NOTE]
> ダウンロードすることができます、 C# Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (runspace06.cs)。 ダウンロードの手順については、[Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)を参照してください。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace06.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs#L11-L85 "Runspace06.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)