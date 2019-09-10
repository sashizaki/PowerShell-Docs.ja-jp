---
title: RunSpace03 (C#) コードサンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: 9afdb97b8ae2919f091ca5bacccedbe37c2e1584
ms.sourcegitcommit: 00083f07b13c73b86936e7d7307397df27c63c04
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2019
ms.locfileid: "70848029"
---
# <a name="runspace03-c-code-sample"></a>RunSpace03 (C#) コード サンプル

「指定さC#れたスクリプトを実行するコンソールアプリケーションの作成」で説明されているコンソールアプリケーションのソースコードを次に示します。 このサンプルでは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して、スクリプトに渡されたプロセス名のリストを使用してプロセス情報を取得するスクリプトを実行します。 この例では、入力オブジェクトをスクリプトに渡す方法と、エラーオブジェクトおよび出力オブジェクトを取得する方法を示します。

> [!NOTE]
> このサンプルのC#ソースファイル (runspace03.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および Microsoft .NET Framework 3.0 Runtime Components を使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)」を参照してください。
> ダウンロードしたソースファイルは、  **\<PowerShell Samples >** ディレクトリにあります。

## <a name="code-sample"></a>コードサンプル

[!code-csharp[Runspace03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs#L11-L88 "Runspace03.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell プログラマーズガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)