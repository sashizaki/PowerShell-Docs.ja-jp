---
title: RunSpace05 コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9688cd69-07ea-4ea0-8822-0a4850bcf86c
caps.latest.revision: 7
ms.openlocfilehash: abf19d848f6150d005c63bb0fc2ffbe1de405e2a
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67734959"
---
# <a name="runspace05-code-sample"></a>RunSpace05 コード サンプル

説明されている Runspace05 サンプルのソース コードを次に示します[構成、実行空間を使用して RunspaceConfiguration](https://msdn.microsoft.com/en-us/42681d19-2d05-4975-befd-afb1990e79b2)します。 このサンプルでは、実行空間の構成情報を作成、実行空間を作成、1 つのコマンドでパイプラインを作成、およびパイプラインを実行する方法を示します。 実行されるコマンドは、`Get-Process`コマンドレット。

> [!NOTE]
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してソース ファイル (runspace05.cs)。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace05.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace05/Runspace05.cs#L11-L86 "Runspace05.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)