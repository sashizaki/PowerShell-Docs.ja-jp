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
ms.openlocfilehash: 8326d1f47ce07698f09ade9ba97154ecc358465a
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74417461"
---
# <a name="getproc04-code-samples"></a>GetProc04 コード サンプル

GetProc04 サンプルコマンドレットのコードサンプルを次に示します。 これは、「[コマンドレットに終了しないエラー報告を追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)する」で説明されている `Get-Process` コマンドレットのサンプルです。 この `Get-Process` コマンドレットは、プロセス情報の取得中に無効な操作の例外がスローされるたびに[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出します。

> [!NOTE]
> この getprov04.cs コマンドレットC#のソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
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
