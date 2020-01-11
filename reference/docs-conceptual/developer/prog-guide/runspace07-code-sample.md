---
title: RunSpace07 コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ad306d9-45c2-4d55-8e64-fdcba43402c5
caps.latest.revision: 6
ms.openlocfilehash: f40b24951c44c228d85524845045aea58f680f2e
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870610"
---
# <a name="runspace07-code-sample"></a>RunSpace07 コード サンプル

[パイプラインにコマンドを追加するコンソールアプリケーションの作成](https://msdn.microsoft.com/01eb7808-e97b-4905-80be-9e2fa38c262e)に関するページで説明されている Runspace07 サンプルのソースコードを次に示します。
このサンプルアプリケーションでは、実行空間を作成し、パイプラインを作成して、パイプラインに2つのコマンドを追加してから、パイプラインを実行します。 パイプラインに追加されたコマンドは、`Get-Process` と `Measure-Object` のコマンドレットです。

> [!NOTE]
> C#ソースファイル (runspace07.cs) は、windows Vista 用の Microsoft Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
> ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace07.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace07/Runspace07.cs#L11-L108 "Runspace07.cs")]

## <a name="see-also"></a>関連項目

[Windows PowerShell プログラマーズガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
