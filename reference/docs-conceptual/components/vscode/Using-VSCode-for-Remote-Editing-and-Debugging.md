---
title: Visual Studio Code を使用したリモート編集およびデバッグ
description: Visual Studio Code を使用したリモート編集およびデバッグ
ms.date: 08/06/2018
ms.openlocfilehash: bab1a629a7e9dafd5957cf93025abb18b8a4f326
ms.sourcegitcommit: 548547b2d5fc73e726bb9fec6175d452a351d975
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2018
ms.locfileid: "53655609"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a>Visual Studio Code を使用したリモート編集およびデバッグ

それらの ISE に精通していることを実行できますを取り消すことがあります`psedit file.ps1`ファイル - ローカルまたはリモート - を開くための統合されたコンソールから、ISE で右します。

結局のところ、この機能は VSCode の PowerShell の拡張機能で使用できるもします。 このガイドでは、これを行う方法を説明します。

## <a name="prerequisites"></a>前提条件

このガイドでは、あることを前提としています。

- リモート リソース (例: VM、コンテナー) へのアクセスがあります。
- また、ホスト マシンで実行する PowerShell
- VSCode と for VSCode PowerShell 拡張機能

この機能は、Windows PowerShell と PowerShell Core で動作します。

この機能は、WinRM、PowerShell ダイレクトでは、または SSH を使用してリモート コンピューターに接続するときにも動作します。 SSH を使用する Windows を使用している場合は、チェック アウト、 [SSH の Win32 バージョン](https://github.com/PowerShell/Win32-OpenSSH)!

## <a name="lets-go"></a>始めましょう

このセクションでリモート編集、および Azure で実行されている Ubuntu VM に、MacBook Pro からデバッグを紹介します。 可能性がありますいない使用する、Windows が **、プロセスと同じです**します。

### <a name="local-file-editing-with-open-editorfile"></a>ローカル ファイルを開く EditorFile での編集

PowerShell の拡張機能で VSCode の開始し、PowerShell の統合されたコンソールを開く、入力も可能`Open-EditorFile foo.ps1`または`psedit foo.ps1`をエディターでローカル foo.ps1 ファイル権限を開きます。

![オープン EditorFile foo.ps1 がローカルで動作します。](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> foo.ps1 は既に存在する必要があります。

そこからできます。

余白にブレークポイントを追加![余白にブレークポイントを追加します。](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)

f5 キーを押して PowerShell スクリプトをデバッグします。
![ローカルの PowerShell スクリプトのデバッグ](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)

デバッグ中に、デバッグ コンソールとの対話、左、およびデバッグ ツールの他のすべての標準のスコープ内の変数を確認できます。

### <a name="remote-file-editing-with-open-editorfile"></a>リモート ファイルを開く EditorFile での編集

今すぐ編集とデバッグ、リモート ファイルを見ていきましょう。 手順はほぼ同じ、最初の操作を行います: リモート サーバーに、PowerShell セッションを入力する必要があります。 1 つだけのことです。

これを行うには、コマンドレットです。 呼び出された`Enter-PSSession`します。

コマンドレットの機能を削ったダウンについては次のとおりです。

- `Enter-PSSession -ComputerName foo` WinRM を使用してセッションを開始します。
- `Enter-PSSession -ContainerId foo` `Enter-PSSession -VmId foo` PowerShell Direct を使用してセッションを開始します。
- `Enter-PSSession -HostName foo` SSH を使用してセッションを開始します。

詳細について`Enter-PSSession`、ドキュメントのチェック アウト[ここ](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6)します。

使用する SSH リモート処理のため macOS から Azure で Ubuntu VM にします。

最初に、統合コンソールで、Enter-pssession を実行してみましょう。 セッションにいることがわかります`[something]`プロンプトの左側に表示されます。

![Enter-pssession への呼び出し](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

そこから、ローカル スクリプトを編集していた場合、正確な手順を実行しましたできます。

1. 実行`Open-EditorFile test.ps1`または`psedit test.ps1`を開くリモート`test.ps1`ファイル![オープン EditorFile test.ps1 ファイル](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)
2. ファイル/設定ブレークポイントを編集します。 ![編集し、ブレークポイントを設定](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. (F5)、リモート ファイルのデバッグを開始します。

![リモート ファイルのデバッグ](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

すべてです。 このガイドがリモート デバッグと VSCode での PowerShell の編集に関する質問を明確に役立ったことことと思います。

問題があれば、自由に未解決の問題[GitHub リポジトリで](http://github.com/powershell/vscode-powershell)します。
