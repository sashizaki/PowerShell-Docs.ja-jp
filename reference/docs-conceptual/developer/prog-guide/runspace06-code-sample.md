---
title: RunSpace06 コードサンプル |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: c8767ac8dc3a3d9253c2a53a4754d9bd54304abb
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784726"
---
# <a name="runspace06-code-sample"></a>RunSpace06 コード サンプル

次に示すのは、「 [Windows PowerShell スナップインを使用して実行空間を構成](https://msdn.microsoft.com/a7289ee8-9732-49ee-91c7-d533e9538b83)する」で説明されている Runspace06 サンプルのソースコードです。
このサンプルアプリケーションでは、Windows PowerShell スナップインに基づいて実行空間を作成します。これは、1つのコマンドでパイプラインを実行するために使用されます。 これを行うために、アプリケーションは実行空間の構成情報を作成し、実行空間を作成し、1つのコマンドを使用してパイプラインを作成してから、パイプラインを実行します。

> [!NOTE]
> C# ソースファイル (runspace06.cs) は、windows Vista 用 Windows ソフトウェア開発キットおよび Microsoft .NET Framework 3.0 ランタイムコンポーネントを使用してダウンロードできます。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
> ダウンロードしたソースファイルは、ディレクトリにあり **\<PowerShell Samples>** ます。

## <a name="code-sample"></a>コード サンプル

:::code language="csharp" source="~/../powershell-sdk-samples/SDK-2.0/csharp/Runspace06/Runspace06.cs" range="11-85":::

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
