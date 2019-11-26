---
title: RunSpace06 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d71f86d5-eb62-4b16-aa95-5fd3f314ffd3
caps.latest.revision: 6
ms.openlocfilehash: c3ae45ae9587bd130bbe9bb65ef47dc246f6e465
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74417923"
---
# <a name="runspace06-code-sample"></a>RunSpace06 コード サンプル

次に示すのは、「 [Windows PowerShell スナップインを使用して実行空間を構成](https://msdn.microsoft.com/en-us/a7289ee8-9732-49ee-91c7-d533e9538b83)する」で説明されている Runspace06 サンプルのソースコードです。 このサンプルアプリケーションでは、Windows PowerShell スナップインに基づいて実行空間を作成します。これは、1つのコマンドでパイプラインを実行するために使用されます。 これを行うために、アプリケーションは実行空間の構成情報を作成し、実行空間を作成し、1つのコマンドを使用してパイプラインを作成してから、パイプラインを実行します。

> [!NOTE]
> C#ソースファイル (runspace06.cs) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
>
> ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。

## <a name="code-sample"></a>コードサンプル

[!code-csharp[Runspace06.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs#L11-L85 "Runspace06.cs")]

## <a name="see-also"></a>関連項目

[Windows PowerShell プログラマーズガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
