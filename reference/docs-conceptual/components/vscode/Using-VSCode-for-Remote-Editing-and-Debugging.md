---
title: Visual Studio Code を使用したリモート編集およびデバッグ
description: Visual Studio Code を使用したリモート編集およびデバッグ
ms.date: 08/06/2018
ms.openlocfilehash: fbc1ee3556e822b4afb2b37111d0688dc89fdab3
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086675"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a>Visual Studio Code を使用したリモート編集およびデバッグ

ISE に精通している場合、統合コンソールから `psedit file.ps1` を実行してファイル (ローカルまたはリモート) を ISE で開くことができたことを憶えているかもしれません。

この機能は、VSCode 用の PowerShell 拡張機能でも使用できます。 このガイドではそれを行う方法を説明します。

## <a name="prerequisites"></a>前提条件

このガイドでは、次のことを前提としています。

- アクセスできるリモート リソース (例: VM、コンテナー)
- その上で実行する PowerShell およびホスト マシン
- VSCode および VSCode 用 PowerShell 拡張機能

この機能は、Windows PowerShell と PowerShell Core で動作します。

また、この機能は、WinRM、PowerShell Direct、または SSH でリモート マシンに接続しているときにも動作します。 SSH を使用したいが、Windows を使用している場合は、[SSH の Win32 バージョン](https://github.com/PowerShell/Win32-OpenSSH)を確認してください。

## <a name="lets-go"></a>始めましょう

このセクションでは、MacBook Pro から Azure で実行されている Ubuntu VM に対するリモート編集およびデバッグの手順を紹介します。 Windows を使用する場合も**プロセスと同じです**。

### <a name="local-file-editing-with-open-editorfile"></a>Open-EditorFile でのローカル ファイル編集

VSCode 用 PowerShell 拡張機能を開始し、PowerShell 統合コンソールを開くと、「`Open-EditorFile foo.ps1`」または「`psedit foo.ps1`」と入力してエディターでローカル環境の foo.ps1 ファイルを開くことができます。

![ローカルに動作する Open-EditorFile foo.ps1](https://user-images.githubusercontent.com/2644648/34895897-7c2c46ac-f79c-11e7-9410-a252aff52f13.png)

>[!NOTE]
> foo.ps1 が既に存在している必要があります。

そこから次のことができます。

余白にブレークポイントを追加します![余白にブレークポイントを追加](https://user-images.githubusercontent.com/2644648/34895893-7bdc38e2-f79c-11e7-8026-8ad53f9a1bad.png)

F5 キーを押して PowerShell スクリプトをデバッグします。
![ローカルの PowerShell スクリプトのデバッグ](https://user-images.githubusercontent.com/2644648/34895894-7bedb874-f79c-11e7-9180-7e0dc2d02af8.png)

デバッグ中に、デバッグ コンソールと対話し、左側でスコープ内の変数を確認し、他のすべての標準デバッグ ツールを使用できます。

### <a name="remote-file-editing-with-open-editorfile"></a>Open-EditorFile でのリモート ファイル編集

次に、リモート ファイルを編集してデバッグします。 手順はほぼ同じですが、最初に行う必要があることが 1 つだけあります。リモート サーバーへの PowerShell セッションに入ります。

それを行うためのコマンドレットがあります。 `Enter-PSSession` です。

コマンドレットの簡単な説明は次のとおりです。

- `Enter-PSSession -ComputerName foo` は WinRM でセッションを開始します
- `Enter-PSSession -ContainerId foo` と `Enter-PSSession -VmId foo` は PowerShell Direct でセッションを開始します
- `Enter-PSSession -HostName foo` は SSH でセッションを開始します

`Enter-PSSession` について詳しくは、[こちら](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession?view=powershell-6)のドキュメントをご覧ください。

ここでは、Azure の Ubuntu VM に macOS から接続するので、リモート処理に SSH を使用します。

最初に、統合コンソールで Enter-PSSession を実行します。 プロンプトの左側に `[something]` と表示されるので、セッション内にいることがわかります。

![Enter-PSSession の呼び出し](https://user-images.githubusercontent.com/2644648/34895896-7c18e0bc-f79c-11e7-9b36-6f4bd0e9b0db.png)

そこからは、ローカル スクリプトを編集する場合とまったく同じ手順を実行できます。

1. `Open-EditorFile test.ps1` または `psedit test.ps1` を実行して、リモートの `test.ps1` ファイルを開きます ![test.ps1 ファイルの Open-EditorFile](https://user-images.githubusercontent.com/2644648/34895898-7c3e6a12-f79c-11e7-8bdf-549b591ecbcb.png)
2. ファイルを編集し、ブレークポイントを設定します ![編集とブレークポイントの設定](https://user-images.githubusercontent.com/2644648/34895892-7bb68246-f79c-11e7-8c0a-c2121773afbb.png)
3. リモート ファイルのデバッグを開始します (F5)

![リモート ファイルのデバッグ](https://user-images.githubusercontent.com/2644648/34895895-7c040782-f79c-11e7-93ea-47724fa5c10d.png)

以上ですべてです。 VSCode での PowerShell のリモート編集とデバッグに関する質問に、このガイドが役立ったでしょうか。

何か問題があれば、[GitHub リポジトリ](http://github.com/powershell/vscode-powershell)で自由に問題を開いてください。
