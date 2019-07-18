---
title: Runspace01 (C#) コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d59f8b7c-e800-4633-aa5b-74d4c57e2706
caps.latest.revision: 6
ms.openlocfilehash: ab067485d70523a16493eb57170615ab300eaa98
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735057"
---
# <a name="runspace01-c-code-sample"></a>Runspace01 (C#) コード サンプル

記載されている、実行空間のサンプル コードをここでは[コンソール アプリケーションを実行に指定されたコマンドを作成する](/dotnet/csharp/programming-guide/inside-a-program/hello-world-your-first-program)します。 これを行うには、アプリケーションは、実行空間を指定するには、呼び出しをコマンドを呼び出します。 (このアプリケーションは、実行空間の構成情報を指定しないもないは、明示的にパイプラインを作成することに注意してください。) 呼び出されるコマンドは、`Get-Process`コマンドレット。

> [!NOTE]
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用して、この実行空間のソース ファイル (runspace01.cs)。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace01.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace01/Runspace01.cs#L11-L62 "Runspace01.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)