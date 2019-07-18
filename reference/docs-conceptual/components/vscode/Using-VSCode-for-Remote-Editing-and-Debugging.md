---
title: Visual Studio Code を使用したリモート編集およびデバッグ
description: Visual Studio Code を使用したリモート編集およびデバッグ
ms.date: 06/13/2019
ms.openlocfilehash: ae3b7a3709498fcd547a48d0849b0dc880217225
ms.sourcegitcommit: 13f24786ed39ca1c07eff2b73a1974c366e31cb8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2019
ms.locfileid: "67263929"
---
# <a name="using-visual-studio-code-for-remote-editing-and-debugging"></a>Visual Studio Code を使用したリモート編集およびデバッグ

ISE に精通していれば、統合コンソールから `psedit file.ps1` を実行してファイル (ローカルまたはリモート) を ISE で開けることをご存じではないでしょうか。

この機能は、VSCode 用の PowerShell 拡張機能でも使用できます。 このガイドではそれを行う方法を説明します。

## <a name="prerequisites"></a>前提条件

このガイドでは、次のことを前提としています。

- アクセスできるリモート リソース (例: VM、コンテナー)
- その上で実行する PowerShell およびホスト マシン
- VSCode および VSCode 用 PowerShell 拡張機能

この機能は、Windows PowerShell と PowerShell Core で動作します。

また、この機能は、WinRM、PowerShell Direct、または SSH でリモート マシンに接続しているときにも動作します。 SSH を使用したいが、Windows を使用している場合は、[SSH の Win32 バージョン](https://github.com/PowerShell/Win32-OpenSSH)を確認してください。

> [!IMPORTANT]
> `Open-EditorFile` および `psedit` コマンドは、VSCode 用の PowerShell 拡張機能によって作成された **PowerShell 統合コンソール**でのみ機能します。

## <a name="usage-examples"></a>使用例

これらの例は、MacBook Pro から Azure で実行されている Ubuntu VM に対するリモート編集およびデバッグを示しています。 プロセスは Windows 上と同じです。

### <a name="local-file-editing-with-open-editorfile"></a>Open-EditorFile でのローカル ファイル編集

VSCode 用 PowerShell 拡張機能を開始し、PowerShell 統合コンソールを開くと、「`Open-EditorFile foo.ps1`」または「`psedit foo.ps1`」と入力してエディターでローカル環境の foo.ps1 ファイルを開くことができます。

![ローカルに動作する Open-EditorFile foo.ps1](images/Using-VSCode-for-Remote-Editing-and-Debugging/1-open-local-file.png)

>[!NOTE]
> ファイル `foo.ps1` は既に存在している必要があります。

そこから次のことができます。

- 余白にブレークポイントを追加します

  ![余白にブレークポイントを追加する](images/Using-VSCode-for-Remote-Editing-and-Debugging/2-adding-breakpoint-gutter.png)

- F5 キーを押して PowerShell スクリプトをデバッグします。

  ![PowerShell のローカル スクリプトをデバッグする](images/Using-VSCode-for-Remote-Editing-and-Debugging/3-local-debug.png)

デバッグ中に、デバッグ コンソールと対話し、左側でスコープ内の変数を確認し、他のすべての標準デバッグ ツールを使用できます。

### <a name="remote-file-editing-with-open-editorfile"></a>Open-EditorFile でのリモート ファイル編集

次に、リモート ファイルを編集してデバッグします。 手順はほぼ同じですが、最初に行う必要があることが 1 つだけあります。リモート サーバーへの PowerShell セッションに入ります。

それを行うためのコマンドレットがあります。 `Enter-PSSession` です。

コマンドレットの簡単な説明は次のとおりです。

- `Enter-PSSession -ComputerName foo` は WinRM でセッションを開始します
- `Enter-PSSession -ContainerId foo` と `Enter-PSSession -VmId foo` は PowerShell Direct でセッションを開始します
- `Enter-PSSession -HostName foo` は SSH でセッションを開始します

詳細については、[Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) のドキュメントを参照してください。

ここでは macOS から Azure の Ubuntu VM に移行するので、リモート処理に SSH を使用しています。

まず、統合コンソールで `Enter-PSSession` を実行します。 プロンプトの左側に `[<hostname>]` が表示されたら、リモート セッションに接続しています。

![Enter-PSSession の呼び出し](images/Using-VSCode-for-Remote-Editing-and-Debugging/4-enter-pssession.png)

これで、ローカル スクリプトを編集する場合と同じ手順を実行できるようになりました。

1. `Open-EditorFile test.ps1` または `psedit test.ps1` を実行してリモートの `test.ps1` ファイルを開きます

  ![Open-EditorFile the test.ps1 ファイル](images/Using-VSCode-for-Remote-Editing-and-Debugging/5-open-remote-file.png)

1. ファイルを編集し、ブレークポイントを設定します

   ![編集とブレークポイントの設定](images/Using-VSCode-for-Remote-Editing-and-Debugging/6-set-breakpoints.png)

1. リモート ファイルのデバッグを開始します (F5)

   ![リモート ファイルのデバッグ](images/Using-VSCode-for-Remote-Editing-and-Debugging/7-start-debugging.png)

何か問題があれば、[GitHub リポジトリ](https://github.com/powershell/vscode-powershell)で問題を開いてください。
