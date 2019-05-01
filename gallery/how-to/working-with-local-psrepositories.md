---
ms.date: 11/06/2018
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: ローカルの PSRepositories の操作
ms.openlocfilehash: 94824ea584c097838b24c6f2cd02407b6147a781
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62084098"
---
# <a name="working-with-local-powershellget-repositories"></a>ローカルの PowerShellGet リポジトリの操作

PowerShellGet モジュールでは、PowerShell ギャラリー以外のリポジトリがサポートされています。
これらのコマンドレットにより、次のシナリオが可能になります。

- 環境内で使用するための、信頼された事前検証済みの PowerShell モジュールのセットをサポートする
- PowerShell モジュールまたはスクリプトを構築する CI/CD パイプラインをテストする
- インターネットにアクセスできないシステムに PowerShell スクリプトおよびモジュールを提供する

この記事では、ローカル PowerShell リポジトリを設定する方法について説明します。 また、PowerShell ギャラリーから使用できる [OfflinePowerShellGetDeploy][] モジュールについても説明します。 このモジュールには、ローカル リポジトリに PowerShellGet の最新バージョンをインストールするためのコマンドレットが含まれています。

## <a name="local-repository-types"></a>ローカル リポジトリの種類

ローカル PSRepository を作成するには、次の 2 つの方法があります: NuGet サーバーまたはファイル共有。 種類ごとに長所と短所があります。

NuGet サーバー

| 長所| 短所 |
| --- | --- |
| PowerShellGallery の機能を正確に模倣します | 多層アプリでは、運用の計画とサポートが必要です |
| NuGet は、Visual Studio や他のツールと統合します | 認証モデルと NuGet アカウントの管理が必要です |
| NuGet では、`.Nupkg` パッケージ内のメタデータがサポートされます | 発行には、API キーの管理とメンテナンスが必要です |
| 検索、パッケージ管理などが提供されます | |

ファイル共有

| 長所| 短所 |
| --- | --- |
| セットアップ、バックアップ、メンテナンスが簡単です | PowerShellGet で使用されるメタデータは使用できません |
| セキュリティ モデルがシンプルです (共有に対するユーザーのアクセス許可) | 基本的なファイル共有以外の UI はありません |
| 既存の項目を置換などの制約はありません | セキュリティに制限があり、誰が何を更新したか記録されません |

PowerShellGet はどちらの種類およびサポートでも動作し、バージョンと依存関係のインストールを特定します。
ただし、PowerShell ギャラリーでは動作するいくつかの機能が、基本の NuGet サーバーまたはファイル共有に対しては使用できません。

- すべてはパッケージです。スクリプト、モジュール、DSC リソース、ロールの機能の区別はありません。
- ファイル共有サーバーは、タグを含むパッケージのメタデータを認識できません。

## <a name="creating-a-local-repository"></a>ローカル リポジトリを作成する

次の記事では、独自の NuGet サーバーを設定するための手順が示されています。

- [NuGet.Server][]

パッケージを追加する時点までの手順に従います。 [パッケージを公開する](#publishing-to-a-local-repository)ための手順は、この記事の後半で説明します。

ファイル共有ベースのリポジトリでは、ユーザーにファイル共有にアクセスするためのアクセス許可があることを確認します。

## <a name="registering-a-local-repository"></a>ローカル リポジトリを登録する

リポジトリを使用するには、その前に `Register-PSRepository` コマンドを使用して登録する必要があります。
次の例では、独自のリポジトリを信頼しているという前提で、**InstallationPolicy** を *Trusted* に設定しています。

```powershell
# Register a NuGet-based server
Register-PSRepository -Name LocalPSRepo -SourceLocation http://MyLocalNuget/Api/V2/ -ScriptSourceLocation http://MyLocalNuget/Api/V2 -InstallationPolicy Trusted

# Register a file share on my local machine
Register-PSRepository -Name LocalPSRepo -SourceLocation '\\localhost\PSRepoLocal\' -ScriptSourceLocation '\\localhost\PSRepoLocal\' -InstallationPolicy Trusted
```

2 つのコマンドでの **ScriptSourceLocation** の処理方法の違いに注意してください。 ファイル共有ベースのリポジトリでは、**SourceLocation** と **ScriptSourceLocation** が一致している必要があります。 Web ベースのリポジトリでは、それらが異なる必要があるため、この例では、**SourceLocation** の最後に "/" が追加されています。

新しく作成する PSRepository を既定のリポジトリにする場合は、他のすべての PSRepository の登録を解除する必要があります。 たとえば、次のように入力します。

```powershell
Unregister-PSRepository -Name PSGallery
```

> [!NOTE]
> リポジトリ名 "PSGallery" は、PowerShell ギャラリーで使用するために予約されています。 PSGallery を登録解除することはできますが、他のリポジトリに対して名前 PSGallery を再利用することはできません。

PSGallery を元に戻す必要がある場合は、次のコマンドを実行します。

```powershell
Register-PSRepository -Default
```

## <a name="publishing-to-a-local-repository"></a>ローカル リポジトリに発行する

ローカル PSRepository を登録した後は、ローカル PSRepository に対して発行できます。 2 つの主な発行シナリオがあります。独自のモジュールの発行と、PSGallery からのモジュールの発行です。

### <a name="publishing-a-module-you-authored"></a>自分で作成したモジュールを発行する

PowerShell ギャラリーの場合と同じように、`Publish-Module` および `Publish-Script` を使用してローカル環境の PSRepository に自分のモジュールを発行します。

- コードの場所を指定します
- API キーを指定します
- リポジトリ名を指定します。 たとえば、`-PSRepository LocalPSRepo` と記述します。

> [!NOTE]
> NuGet サーバーにアカウントを作成した後、サインインし、API キーを生成して保存する必要があります。
> ファイル共有の場合は、NuGetApiKey の値に対して任意の空白でない文字列を使用します。

例:

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'c:\projects\MyModule' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> セキュリティを確保するため、API キーをスクリプトにハード コーディングしてはなりません。 セキュリティ保護されたキー管理システムを使用します。

### <a name="publishing-a-module-from-the-psgallery"></a>PSGallery からモジュールを発行する

ローカル環境の PSRepository に PSGallery からモジュールを発行するには、"Save-Package" コマンドレットを使用できます。

- パッケージの名前を指定します
- プロバイダーとして "NuGet" を指定します
- ソースとして PSGallery の場所を指定します (https://www.powershellgallery.com/api/v2)
- ローカル リポジトリへのパスを指定します

次に例を示します。

```powershell
# Publish from the PSGallery to your local Repository
Save-Package -Name 'PackageName' -Provider Nuget -Source https://www.powershellgallery.com/api/v2 -Path '\\localhost\PSRepoLocal\'
```

ローカル PSRepository が Web ベースの場合は、nuget.exe を使用して発行する追加の手順が必要です。

[nuget.exe][] の使用についてはドキュメントをご覧ください。

## <a name="installing-powershellget-on-a-disconnected-system"></a>オフラインのシステムに PowerShellGet をインストールする

インターネットに接続されていないシステムが必要な環境に PowerShellGet を展開するのは困難です。 PowerShellGet を初めて使用するときは、最新バージョンをインストールするブートストラップ プロセスがあります。 PowerShell ギャラリーの OfflinePowerShellGetDeploy モジュールでは、このブートストラップ プロセスをサポートするコマンドレットが提供されています。

オフラインの展開をブートストラップするには、次のことを行う必要があります。

- OfflinePowerShellGetDeploy をダウンロードし、インターネットに接続されたシステムと接続されていないシステムにインストールします
- `Save-PowerShellGetForOffline` コマンドレットを使用して、PowerShellGet とその依存関係をインターネットに接続されたシステムにダウンロードします
- PowerShellGet とその依存関係を、インターネットに接続されたシステムから切断されたシステムにコピーします
- 切断されたシステムで `Install-PowerShellGetOffline` を使用して、PowerShellGet とその依存関係を適切なフォルダーに配置します

次のコマンドでは、`Save-PowerShellGetForOffline` を使用してすべてのコンポーネントを `f:\OfflinePowerShellGet` フォルダーに配置します

```powershell
# Requires -RunAsAdministrator
#Download the OfflinePowerShellGetDeploy to a location that can be accessed
# by both the connected and disconnected systems.
Save-Module -Name OfflinePowerShellGetDeploy -Path 'F:\' -Repository PSGallery
Import-Module F:\OfflinePowerShellGetDeploy

# Put PowerShellGet somewhere locally
Save-PowerShellGetForOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

この時点で、`F:\OfflinePowerShellGet` の内容を切断されたシステムで使用できるようにする必要があります。 `Install-PowerShellGetOffline` コマンドレットを実行し、切断されたシステムに PowerShellGet をインストールします。

> [!NOTE]
> これらのコマンドを実行する前に、PowerShell セッションで PowerShellGet を実行しないことが重要です。 PowerShellGet がセッションに読み込まれた後では、コンポーネントを更新できません。 誤って PowerShellGet を開始した場合は、終了して、PowerShell を再起動します。

```powershell
Import-Module F:\OfflinePowerShellGetDeploy

Install-PowerShellGetOffline -LocalFolder 'F:\OfflinePowerShellGet'
```

これらのコマンドの実行が済むと、ローカル リポジトリに PowerShellGet を発行できるようになります。

```powershell
# Publish to a NuGet Server repository using my NuGetAPI key
Publish-Module -Path 'F:\OfflinePowershellGet' -Repository LocalPsRepo -NuGetApiKey 'oy2bi4avlkjolp6bme6azdyssn6ps3iu7ib2qpiudrtbji'

# Publish to a file share repo - the NuGet API key must be a non-blank string
Publish-Module -Path 'F:\OfflinePowerShellGet' -Repository LocalPsRepo -NuGetApiKey 'AnyStringWillDo'
```

> [!IMPORTANT]
> セキュリティを確保するため、API キーをスクリプトにハード コーディングしてはなりません。 セキュリティ保護されたキー管理システムを使用します。

<!-- external links -->
[OfflinePowerShellGetDeploy]: https://www.powershellgallery.com/packages/OfflinePowerShellGetDeploy/0.1.1
[Nuget.Server]: /nuget/hosting-packages/nuget-server
[nuget.exe]: /nuget/tools/nuget-exe-cli-reference
