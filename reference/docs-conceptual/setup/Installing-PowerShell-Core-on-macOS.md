---
title: macOS への PowerShell Core のインストール
description: macOS への PowerShell Core のインストールに関する情報
ms.date: 08/06/2018
ms.openlocfilehash: 042c933dfa83f3ab52e315036e4f817145116d00
ms.sourcegitcommit: aa41249f153bbc6e11667ade60c878980c15abc6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45611489"
---
# <a name="installing-powershell-core-on-macos"></a>macOS への PowerShell Core のインストール

PowerShell Core は、macOS 10.12 以降をサポートしています。
すべてのパッケージは GitHub [リリース][] ページにあります。
パッケージがインストールされたら、ターミナルから `pwsh` を実行します。

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a>macOS 10.12 以降で Homebrew を使用した最新の安定版リリースのインストール

[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。
`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。

これで PowerShell をインストールできます。

```sh
brew cask install powershell
```

最後に、インストールが正常に動作していることを確認します。

```sh
pwsh
```

新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。

```sh
brew update
brew cask upgrade powershell
```

> [!NOTE]
> 上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、
> $PSVersionTable に表示される値を更新する必要があります。

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a>macOS 10.12 以降で Homebrew を使用した最新のプレビュー リリースのインストール

[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。
`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。

Homebrew をインストールすると、PowerShell のインストールが簡単になります。
最初に、[Cask-Versions][cask-versions] をインストールします。これにより、cask パッケージの代替バージョンをインストールすることができます。

```sh
brew tap homebrew/cask-versions
```

これで PowerShell をインストールできます。

```sh
brew cask install powershell-preview
```

最後に、インストールが正常に動作していることを確認します。

```sh
pwsh-preview
```

新しいバージョンの PowerShell がリリースされたら、Homebrew の式を更新し、PowerShell をアップグレードしてください。

```sh
brew update
brew cask upgrade powershell-preview
```

> [!NOTE]
> 上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、PowerShell シェルを終了し、再起動して、アップグレードを完了し、
> $PSVersionTable に表示される値を更新する必要があります。

## <a name="installation-via-direct-download"></a>直接ダウンロードによるインストール

PKG パッケージ `powershell-6.1.0-osx-x64.pkg` を
[リリース][] ページから macOS コンピューターにダウンロードします。

ファイルをダブルクリックして画面の指示に従うか、ターミナルからインストールします。

```sh
sudo installer -pkg powershell-6.1.0-osx-x64.pkg -target /
```

## <a name="binary-archives"></a>バイナリ アーカイブ

macOS プラットフォームで高度な展開シナリオを実行するために、PowerShell バイナリ `tar.gz` アーカイブが用意されています。

### <a name="installing-binary-archives-on-macos"></a>macOS へのバイナリ アーカイブのインストール

```sh
# Download the powershell '.tar.gz' archive
curl -L -o /tmp/powershell.tar.gz https://github.com/PowerShell/PowerShell/releases/download/v6.1.0/powershell-6.1.0-osx-x64.tar.gz

# Create the target folder where powershell will be placed
sudo mkdir -p /usr/local/microsoft/powershell/6.1.0

# Expand powershell to the target folder
sudo tar zxf /tmp/powershell.tar.gz -C /usr/local/microsoft/powershell/6.1.0

# Set execute permissions
sudo chmod +x /usr/local/microsoft/powershell/6.1.0/pwsh

# Create the symbolic link that points to pwsh
sudo ln -s /usr/local/microsoft/powershell/6.1.0/pwsh /usr/local/bin/pwsh
```

## <a name="uninstalling-powershell-core"></a>PowerShell Core のアンインストール

Homebrew で PowerShell をインストールした場合、アンインストールが簡単になります。

```sh
brew cask uninstall powershell
```

直接ダウンロードで PowerShell をインストールした場合、手動で PowerShell を削除する必要があります。

```sh
sudo rm -rf /usr/local/bin/pwsh /usr/local/microsoft/powershell
```

追加の PowerShell パスを削除するには、このドキュメントの「[パス](#paths)」セクションを参照し、`sudo rm` を使用して目的のパスを削除してください。

> [!NOTE]
> Homebrew でインストールした場合、この操作は不要です。

## <a name="paths"></a>パス

* `$PSHOME` は `/usr/local/microsoft/powershell/6.1.0/` です
* ユーザー プロファイルは `~/.config/powershell/profile.ps1` から読み込まれます
* 既定のプロファイルは `$PSHOME/profile.ps1` から読み込まれます
* ユーザー モジュールは `~/.local/share/powershell/Modules` から読み込まれます
* 共有モジュールは `/usr/local/share/powershell/Modules` から読み込まれます
* 既定のモジュールは `$PSHOME/Modules` から読み込まれます
* PSReadline 履歴は `~/.local/share/powershell/PSReadLine/ConsoleHost_history.txt` に記録されます

プロファイルには、PowerShell のホスト単位の構成が考慮されています。
そのため、既定のホスト固有のプロファイルは、同じ場所の `Microsoft.PowerShell_profile.ps1` に存在します。

PowerShell は、macOS の [XDG ベース ディレクトリ仕様][xdg-bds]を尊重しています。

macOS は BSD から派生しているので、プレフィックスに `/opt` ではなく `/usr/local` が使用されます。
そのため、`$PSHOME` は `/usr/local/microsoft/powershell/6.1.0/` です。シンボリックリンクは `/usr/local/bin/pwsh` にあります。

## <a name="additional-resources"></a>その他の情報

* [Homebrew Web][brew]
* [Homebrew Github リポジトリ][GitHub]
* [Homebrew-Cask][cask]

[brew]: http://brew.sh/
[Cask]: https://github.com/Homebrew/homebrew-cask
[cask-versions]: https://github.com/Homebrew/homebrew-cask-versions
[GitHub]: https://github.com/Homebrew
[リリース]: https://github.com/PowerShell/PowerShell/releases/latest
[xdg-bds]: https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html
