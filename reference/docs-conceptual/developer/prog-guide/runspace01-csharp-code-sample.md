---
title: Runspace01 (C#) コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 418162731b4a98989642e1c61c655fdb0f002698
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787060"
---
# <a name="runspace01-c-code-sample"></a>Runspace01 (C#) コード サンプル

ここでは、「[指定されたコマンドを実行するコンソールアプリケーションの作成](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)」で説明されている実行空間のコードサンプルを示します。
これを行うには、アプリケーションが実行空間を呼び出し、コマンドを呼び出します。 (このアプリケーションは実行空間の構成情報を指定せず、明示的にパイプラインを作成しないことに注意してください)。 呼び出されるコマンドは、コマンド `Get-Process` レットです。

> [!NOTE]
> この実行空間の C# ソースファイル (runspace01.cs) をダウンロードするには、Microsoft Windows Software Development Kit for Windows Vista および Microsoft .NET Framework 3.0 Runtime Components を使用します。
> ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
> ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。

## <a name="code-sample"></a>コード サンプル

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs" range="11-62":::

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
