---
title: StopProcessSample04 (C#) Sample Code |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 778ce1a2-e16d-4af5-b15b-77ca4326bdc4
caps.latest.revision: 5
ms.openlocfilehash: df5591e351790d18bf2a5b5554d792ab8175dcc6
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74416046"
---
# <a name="stopprocesssample04-c-sample-code"></a>StopProcessSample04 (C#) サンプル コード

StopProc04 sample コマンドレットC#の完全なサンプルコードを次に示します。 これは、「[コマンドレットにパラメーターセットを追加する](../cmdlet/adding-parameter-sets-to-a-cmdlet.md)」で説明されている `Stop-Process` コマンドレットのコードです。 `Stop-Process` コマンドレットは、Get Proc コマンドレットを使用して取得されたプロセスを停止するように設計されています ([最初のコマンドレットの作成](../cmdlet/creating-a-cmdlet-without-parameters.md)に関するページを参照してください)。

> [!NOTE]
> この Stop Proc コマンドC#レットの (stopprocesssample04.cs) ソースファイルをダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
>
> ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。

[!code-csharp[StopProcessSample04.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/StopProcessSample04/StopProcessSample04.cs#L11-L435 "StopProcessSample04.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell プログラマーズガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
