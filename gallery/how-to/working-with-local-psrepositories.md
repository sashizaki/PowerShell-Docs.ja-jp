---
ms.date: 11/06/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: ローカル PSRepositories の操作
ms.openlocfilehash: 94824ea584c097838b24c6f2cd02407b6147a781
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55682671"
---
# <a name="working-with-local-powershellget-repositories"></a>ローカルの PowerShellGet リポジトリの操作

PowerShell ギャラリー以外の PowerShellGet モジュール サポート リポジトリ。
これらのコマンドレットは、次のシナリオを有効にします。

- 環境内で使用するため、信頼されている、事前に検証された PowerShell モジュールのセットをサポートします。
- PowerShell モジュールまたはスクリプトをビルドする CI/CD パイプラインをテストします。
- インターネットにアクセスできないシステムに PowerShell スクリプトおよびモジュールを配信します。

この記事では、ローカル PowerShell リポジトリを設定する方法について説明します。 についても説明します、 [OfflinePowerShellGetDeploy][] PowerShell ギャラリーからモジュールを使用できます。 このモジュールには、ローカル リポジトリに PowerShellGet の最新バージョンをインストールするためのコマンドレットが含まれています。

## <a name="local-repository-types"></a>ローカル リポジトリの種類

ローカル PSRepository を作成する 2 つの方法はあります。NuGet のサーバーまたはファイル共有。 各種は、長所と短所があります。

NuGet サーバー

| 長所| 短所 |
| --- | --- |
| PowerShellGallery 機能を正確に模倣します。 | 多層アプリケーションは、操作の計画とサポートが必要です。 |
| NuGet は、Visual Studio、その他のツールと統合します。 | 認証モデルと必要な NuGet アカウント管理 |
| NuGet でメタデータをサポートする`.Nupkg`パッケージ | 発行は、API キーの管理とメンテナンスが必要です。 |
| 検索、パッケージの管理などを提供します。 | |

ファイル共有

| 長所| 短所 |
| --- | --- |
| 簡単設定、バックアップ、および管理するには | PowerShellGet で使用されるメタデータは使用できません。 |
| 単純なセキュリティ モデル、共有のユーザーのアクセス許可 | 基本的なファイル共有を超える UI なし |
| 既存の項目を置換などの制約のないです。 | 限られたセキュリティと内容を更新するユーザーの記録がありません。 |

PowerShellGet は、特定のバージョンと依存関係のインストールをサポートして型のいずれかで動作します。
ただし、PowerShell ギャラリーを使用できるいくつかの機能は、基本の NuGet サーバーやファイル共有に対して使用できません。

- すべては、パッケージのスクリプトやモジュール、DSC リソース、ロール機能のない差別化要因です。
- ファイル共有サーバーには、タグを含むパッケージのメタデータを表示できません。

## <a name="creating-a-local-repository"></a>ローカル リポジトリを作成します。

次の記事では、独自の NuGet サーバーを設定するための手順を示します。

- [NuGet.Server][]

パッケージを追加する時点までの手順に従います。 手順[パッケージを公開する](#publishing-to-a-local-repository)はこの記事の後半で説明します。

ファイル共有ベースのリポジトリでは、ユーザーにファイル共有にアクセスする権限があることを確認します。

## <a name="registering-a-local-repository"></a>ローカル リポジトリを登録します。

リポジトリを使用できますが、前に、登録する必要を使用して、`Register-PSRepository`コマンド。
以下の例で、 **InstallationPolicy**に設定されている*信頼済み*、独自のリポジトリを信頼できることを前提としています。

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

2 つのコマンドを処理する方法の違いをメモしておきます**ScriptSourceLocation**します。 ファイル共有ベースのリポジトリでは、 **SourceLocation**と**ScriptSourceLocation**と一致する必要があります。 Web ベースのリポジトリでは、する必要があるさまざまな、最後には、この例では「/」に追加されます、 **SourceLocation**します。

既定のリポジトリを新しく作成された PSRepository にする場合は、その他のすべての PSRepositories の登録を解除する必要があります。 たとえば、次のように入力します。

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> リポジトリ名 'PSGallery' は、PowerShell ギャラリーで使用するために予約されています。 PSGallery、登録を解除することができますが、その他の任意のリポジトリの名前 PSGallery を再利用することはできません。

PSGallery を復元する必要がある場合は、次のコマンドを実行します。

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a>ローカル リポジトリに公開します。

ローカル PSRepository を登録したら、ローカル、PSRepository に発行できます。 2 つの主な発行シナリオがあります。 独自のモジュールを発行および PSGallery からモジュールを発行します。

### <a name="publishing-a-module-you-authored"></a>作成したモジュールの発行

使用`Publish-Module`と`Publish-Script`PowerShell ギャラリーのと同じ方法をローカル PSRepository にモジュールを発行します。

- コードの場所を指定します。
- API キーを指定します。
- リポジトリ名を指定します。 たとえば、`-PSRepository LocalPSRepo` と記述します。

> [!NOTE]
> NuGet のサーバーでアカウントを作成しにサインインを生成し、API キーを保存する必要があります。
> ファイル共有の場合は、NuGetApiKey 値の任意の空白でない文字列を使用します。

例:

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> セキュリティを確保するには、API キーのスクリプトにハード コーディングされてはなりません。 セキュリティで保護されたキー管理システムを使用します。

### <a name="publishing-a-module-from-the-psgallery"></a>PSGallery からモジュールの発行

ローカル、PSRepository に PSGallery からモジュールを発行するには、' Save-package ' コマンドレットを使用することができます。

- パッケージの名前を指定します。
- プロバイダーとしての 'NuGet' の指定します。
- ソース (として PSGallery 場所を指定します。 https://www.powershellgallery.com/api/v2)
- ローカル リポジトリへのパスを指定します。

次に例を示します。

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider Nuget -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

場合は、ローカル PSRepository には web ベースでは、nuget.exe を使用して発行する追加の手順が必要です。

使用してドキュメントを参照して[nuget.exe][]します。

## <a name="installing-powershellget-on-a-disconnected-system"></a>接続されていないシステムに PowerShellGet をインストールします。

PowerShellGet の展開は、システムがインターネットから切断する必要がある環境では困難です。 PowerShellGet では、最初に使用されるときに、最新バージョンをインストールするブートス トラップ プロセスがあります。 PowerShell ギャラリーで OfflinePowerShellGetDeploy モジュールは、このブートス トラップ プロセスをサポートするコマンドレットを提供します。

オフラインの展開をブートス トラップする必要があります。

- インターネットに接続されたは、OfflinePowerShellGetDeploy システムと、接続されていないシステム ダウンロードしてインストール
- PowerShellGet とその依存関係を使用して、インターネットに接続されたシステムでダウンロード、`Save-PowerShellGetForOffline`コマンドレット
- インターネットに接続されたシステムから切断されているシステムに PowerShellGet とその依存関係をコピーします。
- 使用して、`Install-PowerShellGetOffline`切断されているシステムに PowerShellGet とその依存関係を適切なフォルダーに配置

使用して、次のコマンド`Save-PowerShellGetForOffline`フォルダーにすべてのコンポーネントを配置するには `f:\OfflinePowerShellGet`

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

この時点での内容を行う必要があります`F:\OfflinePowerShellGet`切断されているシステムを使用できます。 実行、`Install-PowerShellGetOffline`コマンドレットを切断されているシステムに PowerShellGet をインストールします。

> [!NOTE]
> これらのコマンドを実行する前に、PowerShell セッションで PowerShellGet を実行しないことが重要です。 PowerShellGet がセッションに読み込まれると、コンポーネントを更新できません。 PowerShellGet を誤ってを開始する実行を終了し、PowerShell を再起動します。

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

これらのコマンドを実行した後、ローカル リポジトリに PowerShellGet を発行する準備が完了したら。

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> セキュリティを確保するには、API キーのスクリプトにハード コーディングされてはなりません。 セキュリティで保護されたキー管理システムを使用します。

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
