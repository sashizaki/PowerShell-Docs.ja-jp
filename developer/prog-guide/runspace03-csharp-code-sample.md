---
title: RunSpace03 (C#) コード サンプル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9ac8ab99-1856-4d6f-b30d-c0a18b8dd1fc
caps.latest.revision: 6
ms.openlocfilehash: e1fc91174a959d6acc306330afb8d5c2e7a9a860
ms.sourcegitcommit: 46bebe692689ebedfe65ff2c828fe666b443198d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "67735008"
---
# <a name="runspace03-c-code-sample"></a>RunSpace03 (C#) コード サンプル

ここでは、C#で説明されているコンソール アプリケーションのコードをソース[コンソール アプリケーションを実行に指定されたスクリプトを作成する](fd)します。 このサンプルでは、 [System.Management.Automation.Runspaceinvoke](/dotnet/api/System.Management.Automation.RunspaceInvoke)クラスを取得しますが、スクリプトに渡されるプロセス名のリストを使用して情報を処理するスクリプトを実行します。 入力オブジェクトをスクリプトに渡す方法と、エラー オブジェクトと出力オブジェクトを取得する方法を示しています。

> [!NOTE]
> ダウンロードすることができます、 C# Microsoft Windows ソフトウェア開発キットの Windows Vista と Microsoft .NET Framework 3.0 ランタイム コンポーネントを使用してこのサンプルのソース ファイル (runspace03.cs)。 ダウンロードの手順については、次を参照してください。 [Windows PowerShell のインストールと、Windows PowerShell SDK をダウンロードする方法](/powershell/developer/installing-the-windows-powershell-sdk)します。
>
> ダウンロードしたソース ファイルは、  **\<PowerShell のサンプル >** ディレクトリ。

## <a name="code-sample"></a>コード サンプル

[!code-csharp[Runspace03.cs](../../powershell-sdk-samples/SDK-2.0/csharp/Runspace03/Runspace03.cs#L11-L88 "Runspace03.cs")]

## <a name="see-also"></a>参照

[Windows PowerShell プログラマー ガイド](./windows-powershell-programmer-s-guide.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)