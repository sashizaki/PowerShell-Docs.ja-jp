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
ms.openlocfilehash: 06b5a06ae20a4bbb2c58eaa1776700aa8f80555c
ms.sourcegitcommit: d43f66071f1f33b350d34fa1f46f3a35910c5d24
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74416070"
---
# <a name="runspace03-c-code-sample"></a>RunSpace03 (C#) コード サンプル

「指定さC#れたスクリプトを実行するコンソールアプリケーションの作成」で説明されているコンソールアプリケーションのソースコードを次に示します。 このサンプルでは、 [Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを使用して、スクリプトに渡されたプロセス名のリストを使用してプロセス情報を取得するスクリプトを実行します。 この例では、入力オブジェクトをスクリプトに渡す方法と、エラーオブジェクトおよび出力オブジェクトを取得する方法を示します。

> [!NOTE]
> このサンプルのC#ソースファイル (runspace03.cs) をダウンロードするには、Microsoft Windows Software Development Kit For windows Vista および Microsoft .NET Framework 3.0 Runtime Components を使用します。 ダウンロードの手順については、「 [Windows powershell をインストールする方法」および「Windows POWERSHELL SDK をダウンロードする方法](/powershell/scripting/developer/installing-the-windows-powershell-sdk)」を参照してください。
> ダウンロードしたソースファイルは、 **\<PowerShell Samples >** ディレクトリにあります。

## <a name="code-sample"></a>コードサンプル

[!code-csharp[Runspace03.cs](../../../../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs#L11-L88 "Runspace03.cs")]

## <a name="see-also"></a>関連項目

[Windows PowerShell プログラマーズガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
