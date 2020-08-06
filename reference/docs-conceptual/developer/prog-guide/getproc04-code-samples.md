---
title: GetProc04 のコードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: b90b7e96c1454e57df93863b526758f25d9be690
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87771959"
---
# <a name="getproc04-code-samples"></a>GetProc04 コード サンプル

GetProc04 サンプルコマンドレットのコードサンプルを次に示します。 これは、 `Get-Process` 「[コマンドレットに終了しないエラー報告を追加](../cmdlet/adding-non-terminating-error-reporting-to-your-cmdlet.md)する」で説明されているコマンドレットのサンプルです。 この `Get-Process` コマンドレットは、プロセス情報の取得中に無効な操作の例外がスローされた場合に、 [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出します。

> [!NOTE]
> この getprov04.cs コマンドレットの C# ソースファイル () をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および .NET Framework 3.0 ランタイムコンポーネントを使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
>
> ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。

完全なサンプルコードについては、次のトピックを参照してください。

|言語|トピック|
|--------------|-----------|
|C#|[GetProc04 (C#) サンプル コード](./getproc04-csharp-sample-code.md)|
|VB.NET|[GetProc04 (VB.NET) サンプル コード](./getproc04-vb-net-sample-code.md)|

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
