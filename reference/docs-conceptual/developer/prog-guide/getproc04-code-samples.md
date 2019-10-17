---
title: GetProc04 のコードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c00afd46-758a-4aec-b865-2c9d8f6a17ad
caps.latest.revision: 5
ms.openlocfilehash: 67081528ebe14fbb082091c1b9500de82069b48f
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360321"
---
# <a name="getproc04-code-samples"></a>GetProc04 コード サンプル

GetProc04 サンプルコマンドレットのコードサンプルを次に示します。 これは、「[コマンドレットに終了しないエラー報告を追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)する」で説明されている @no__t 0 コマンドレットのサンプルです。 プロセス情報の取得中に無効な操作の例外がスローされるたびに、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドが呼び出されます。 @no__t

> [!NOTE]
> この getprov04.cs コマンドレットC#のソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。
>
> ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。

完全なサンプルコードについては、次のトピックを参照してください。

|Language|トピック|
|--------------|-----------|
|C#|[GetProc04 (C#) サンプルコード](./getproc04-csharp-sample-code.md)|
|VB.NET|[GetProc04 (VB.NET) サンプルコード](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a>参照

[Windows PowerShell プログラマーズガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)