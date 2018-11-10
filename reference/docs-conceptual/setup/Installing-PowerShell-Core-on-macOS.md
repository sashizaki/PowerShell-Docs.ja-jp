---
title: macOS への PowerShell Core のインストール
description: macOS への PowerShell Core のインストールに関する情報
ms.date: 11/02/2018
ms.openlocfilehash: 162e841bf71d708e9db84ea1bb2dbef13924783b
ms.sourcegitcommit: f4247d3f91d06ec392c4cd66921ce7d0456a2bd9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2018
ms.locfileid: "50998505"
---
# <a name="installing-powershell-core-on-macos"></a>macOS への PowerShell Core のインストール

PowerShell Core は、macOS 10.12 以降をサポートしています。
すべてのパッケージは GitHub [リリース][] ページにあります。
パッケージがインストールされたら、ターミナルから `pwsh` を実行します。

## <a name="about-brew"></a>Brew について

[Homebrew][brew] は、macOS 用の推奨されるパッケージ マネージャーです。
`brew` コマンドが見つからない場合、[指示][brew]に従い、Homebrew をインストールする必要があります。

## <a name="installation-of-latest-stable-release-via-homebrew-on-macos-1012-or-higher"></a>macOS 10.12 以降で Homebrew を使用した最新の安定版リリースのインストール

Brew の詳細については、「[Brew について](#about-brew)」を参照してください。

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
> 上記のコマンドは PowerShell (pwsh) ホストから呼び出すことができますが、その場合、アップグレードを完了するには、PowerShell シェルを終了し、再起動して、$PSVersionTable に表示される値を更新する必要があります。

[brew]: http://brew.sh/

## <a name="installation-of-latest-preview-release-via-homebrew-on-macos-1012-or-higher"></a>macOS 10.12 以降で Homebrew を使用した最新のプレビュー リリースのインストール

Brew の詳細については、「[Brew について](#about-brew)」を参照してください。

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

PowerShell リモート処理および CIM 操作の場合に [OpenSSL](#install-openssl) が必要となるので、これをインストールします。

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

PowerShell リモート処理および CIM 操作の場合に [OpenSSL](#install-openssl) が必要となるので、これをインストールします。

## <a name="installing-dependencies"></a>依存関係のインストール

### <a name="install-xcode-command-line-tools"></a>XCode コマンド ライン ツールをインストールする

```shell
xcode-select -install
```

### <a name="install-openssl"></a>OpenSSL をインストールする

PowerShell リモート処理および CIM 操作の場合は OpenSSL が必要です。  MacPorts または Brew を介してインストールすることができます。

#### <a name="install-openssl-via-brew"></a>Brew を介して OpenSSL をインストールする

Brew の詳細については、「[Brew について](#about-brew)」を参照してください。

`brew install openssl` を実行することで、OpenSSL をインストールします。

#### <a name="install-openssl-via-macports"></a>MacPorts を介して OpenSSL をインストールする

1. [XCode コマンド ライン ツール](#install-xcode-command-line-tools)をインストールします。
1. MacPorts をインストールします。
   手順の説明が必要な場合は、[インストール ガイド](https://guide.macports.org/chunked/installing.macports.html)を参照してください。
1. `sudo port selfupdate` を実行して MacPorts を更新します。
1. `sudo port upgrade outdated` を実行して MacPorts パッケージをアップグレードします。
1. `sudo port instal openssl` を実行して OpenSSL をインストールします。
1. ライブラリを PowerShell で使用できるようにリンクします。

```shell
sudo mkdir -p /usr/local/opt/openssl
sudo ln -s /opt/local/lib /usr/local/opt/openssl/lib
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
そのため、`$PSHOME` は `/usr/local/microsoft/powershell/6.1.0/` となり、シンボリック リンクは `/usr/local/bin/pwsh` に配置されます。

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
