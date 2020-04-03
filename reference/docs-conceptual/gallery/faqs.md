---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: PowerShell ギャラリーに関してよく寄せられる質問
ms.openlocfilehash: 035681e108e1a3e05fe5d659d527ae1ad1c64cf4
ms.sourcegitcommit: 30ccbbb32915b551c4cd4c91ef1df96b5b7514c4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "80500583"
---
# <a name="frequently-asked-questions"></a>よく寄せられる質問

## <a name="what-is-a-powershell-module"></a>PowerShell モジュールとは何ですか。

PowerShell モジュールは、いくつかの PowerShell 機能を含む再利用可能なパッケージです。 PowerShell のすべてのもの (関数、変数、DSC リソースなど) がモジュールでパッケージ化されます。 通常、モジュールとは、特定のパス上に保存される、特定の種類のファイルを含むフォルダーです。 PowerShell モジュールには、いくつかの種類があります。

## <a name="what-is-a-powershell-script"></a>PowerShell スクリプトとは何ですか。

PowerShell スクリプトとは、再利用と共有を可能にするため、.ps1 ファイルに保存される一連のコマンドです。 PowerShell ワークフローは PowerShell スクリプトでもあり、一連のタスクとそのタスクの順序の概要を示します。 詳細については、「[PowerShell ファースト ステップ ガイド](https://technet.microsoft.com/library/jj134242.aspx)」を参照してください。

## <a name="how-are-powershell-scripts-different-from-powershell-modules"></a>PowerShell スクリプトと PowerShell モジュールの違いは何ですか。

モジュールは一般に共有に適していますが、ワークフローとスクリプトのコミュニティへの投稿を容易にするため、スクリプト共有を有効にしています。 詳細については、次のブログを参照してください。

- [スクリプトを作成するのではなく、PowerShell モジュールを作成しよう](https://blogs.technet.microsoft.com/heyscriptingguy/2011/06/27/dont-write-scripts-write-powershell-modules/)
- [PowerShell モジュールの概要](https://blogs.technet.microsoft.com/heyscriptingguy/2015/07/10/understanding-powershell-modules/)

## <a name="how-can-i-publish-to-the-powershell-gallery"></a>どのようにして PowerShell ギャラリーに公開できますか。

パッケージを PowerShell ギャラリーに公開するには、ギャラリーにアカウントを登録する必要があります。 これは、登録時に提供される NuGetApiKey がパッケージの公開に必要になるためです。 登録するには、個人、職場、または学校のアカウントを使用して PowerShell ギャラリーにサインインします。 初めてサインインするときは、1 回限りの登録処理が必要です。
その後、NuGetApiKey キーをプロファイル ページで使用できるようになります。

ギャラリーに登録したら、[Publish-Module][] または [Publish-Script][] コマンドレットを使用してパッケージをギャラリーに公開します。 これらのコマンドレットを実行する方法の詳細については、[公開] タブにアクセスするか、[Publish-Module][] および [Publish-Script][] のドキュメントを参照してください。

**パッケージをインストールまたは保存するためにギャラリーに登録またはサインインする必要はありません。**

## <a name="i-received-failed-to-process-request-the-specified-api-key-is-invalid-or-does-not-have-permission-to-access-the-specified-package-the-remote-server-returned-an-error-403-forbidden-error-when-i-tried-to-publish-a-package-to-the-powershell-gallery-what-does-that-mean"></a>PowerShell ギャラリーに項目を公開しようとして、"要求を処理できませんでした。 '指定した API キーが無効か、指定したパッケージへのアクセス許可がありません。' リモート サーバーがエラー"(403) Forbidden" というエラーを受信しました。 これはどういう意味でしょうか。

このエラーは、次の理由で発生することがあります。

- **指定された API キーが無効である。** 自分のアカウントから有効な API キーを指定したことを確認します。 API キーを取得するには、プロファイル ページを表示します。
- **指定されたパッケージ名を所有していない。** 自分の API キーが正しいことを確認できた場合、使用しようとしているものと同じ名前のパッケージが既に存在すると考えられます。 パッケージが所有者によってリストから外されている場合は、検索結果には表示されません。 同じ名前のパッケージが既に存在するかどうかを確認するには、ブラウザーを開き、パッケージの詳細ページ (`https://www.powershellgallery.com/packages/<packageName>`) に移動します。 たとえば、`https://www.powershellgallery.com/packages/pester` に直接移動すると、Pester モジュールの詳細ページが表示され、リストから外されているかどうかがわかります。 競合するパッケージが既に存在し、リストから外されている場合は、次のようにできます。
  - 別のパッケージ名を選択する。
  - 既存のパッケージの所有者に問い合わせる。

## <a name="why-cant-i-sign-in-with-my-personal-account-but-i-could-sign-in-yesterday"></a>昨日はサインインできましたが、個人アカウントにサインインできないのはなぜですか。

ギャラリー アカウントがプライマリ電子メールのエイリアスの変更に対応していないことに注意してください。
詳細については、「[Microsoft アカウントのエイリアスを管理する](https://windows.microsoft.com/windows/outlook/add-alias-account)」を参照してください。

## <a name="why-dont-i-see-all-the-gallery-packages-when-i-select-all-the-category-checkboxes-on-the-packages-tab"></a>パッケージ タブの [カテゴリ] チェックボックスをすべてオンにすると、ギャラリーのパッケージがすべて表示されなくなるのはなぜですか。

[カテゴリ] チェックボックスをオンにすることは、"このカテゴリのパッケージをすべて表示したい" ということを意味します。 選択したカテゴリのパッケージのみが表示されます。 同様に、[カテゴリ] チェックボックスをすべてオンにすることは、"任意のカテゴリのパッケージをすべて表示したい" ということを意味します。 しかし、ギャラリーの一部のパッケージは、一覧に表示されているどのカテゴリにも属さないため、結果には表示されなくなります。 ギャラリー内のすべてのパッケージを表示するには、すべての [カテゴリ] のチェックを外すか、パッケージ タブを再度選択します。

## <a name="what-are-the-requirements-to-publish-a-module-to-the-powershell-gallery"></a>モジュールを PowerShell ギャラリーに公開するための要件は何ですか。

PowerShell モジュールのどの種類 (スクリプト モジュール、バイナリ モジュール、マニフェスト モジュールなど) でも、ギャラリーに公開できます。 モジュールを公開するには、PowerShellGet がそのバージョン、説明、作成者、そのライセンス取得方法について認識している必要があります。 この情報は、*モジュール マニフェスト* (.psd1) ファイル、または[Publish-Module][] コマンドレットの **LicenseUri** パラメーターの値から公開プロセスの一環として読み取られます。 ギャラリーに公開されるすべてのモジュールに、モジュール マニフェストが必要です。 マニフェストに次の情報を含むモジュールはすべて、ギャラリーに公開できます。

- Version
- 説明
- Author
- マニフェストの **PrivateData** セクションの一部として、または [Publish-Module][] コマンドレットの **LicenseUri** パラメーターの、モジュールのライセンス条項への URI。

## <a name="how-do-i-create-a-correctly-formatted-module-manifest"></a>正しい形式のモジュール マニフェストはどのように作成できますか。

モジュール マニフェストを作成する最も簡単な方法は、[New-ModuleManifest][] コマンドレットを実行することです。 PowerShell 5.0 以降、New-ModuleManifest によって、**ProjectUri**、**LicenseUri**、**Tags** などの有用なメタデータのフィールドが空白のまま、正しい形式のマニフェストが生成されるようになりました。 空白を埋めるか、正しい形式のサンプルとして生成されたマニフェストを使用します。

必要なメタデータ フィールドがすべて正しく入力されているかどうかを確認するには、[Test-ModuleManifest][] コマンドレットを使用します。

モジュール マニフェスト ファイルのフィールドを更新するには、[Update-ModuleManifest][] コマンドレットを使用します。

## <a name="what-are-the-requirements-to-publish-a-script-to-the-gallery"></a>スクリプトをギャラリーに公開するための要件は何ですか。

PowerShell スクリプトのどの種類 (スクリプトまたはワークフロー) でも、ギャラリーに公開できます。 スクリプトを公開するには、PowerShellGet がそのバージョン、説明、作成者、そのライセンス取得方法について認識している必要があります。 この情報は、スクリプト ファイルの *PSScriptInfo* セクション、または [Publish-Script][] コマンドレットの **LicenseUri** パラメーターの値から公開プロセスの一環として読み取られます。 ギャラリーに公開されるすべてのスクリプトに、メタデータ情報が必要です。 PSScriptInfo セクションに次の情報を含むスクリプトはすべて、ギャラリーに公開できます。

- Version
- 説明
- Author
- スクリプトの **PSScriptInfo** セクションの一部として、または [Publish-Script][] コマンドレットの **LicenseUri** パラメーターの、スクリプトのライセンス条項への URI。

## <a name="how-do-i-search"></a>どのように検索しますか。

検索したいものをテキスト ボックスに入力します。 たとえば、Azure SQL に関連するモジュールを検索する場合は、「azure sql」と入力します。 検索エンジンによって、タイトル、説明、全体のメタデータを含む、公開されているすべてのパッケージでこれらのキーワードが検索されます。 次に、重み付けされた品質スコアに基づき、もっとも近い一致が表示されます。 また、次のフィールドについて、検索クエリで field:"value" 構文を使用して、特定のフィールドを検索することもできます。

- Tags
- 関数
- コマンドレット
- DscResources
- PowerShellVersion

たとえば、PowerShellVersion:"2.0" と検索すると、PowerShellVersion 2.0 (モジュール/スクリプト マニフェストに基づく) に対応する結果のみが表示されます。

## <a name="how-do-i-create-a-correctly-formatted-script-file"></a>正しい形式のスクリプト ファイルはどのように作成できますか。

正しく書式設定されたスクリプトを作成する最も簡単な方法は、[New-ScriptFileInfo][] コマンドレットを実行することです。 PowerShell 5.0 以降、New-ScriptFileInfo によって、**ProjectUri**、**LicenseUri**、**Tags** などの有用なメタデータのフィールドが空白のまま、正しい形式のスクリプト ファイルが生成されるようになりました。 空白を埋めるか、正しい形式のサンプルとして生成されたスクリプト ファイルを使用します。

必要なメタデータ フィールドがすべて正しく入力されているかどうかを確認するには、[Test-ScriptFileInfo][] コマンドレットを使用します。

スクリプト メタデータ フィールドを更新するには、[Update-ScriptFileInfo][] コマンドレットを使用します。

## <a name="what-other-types-of-powershell-modules-exist"></a>その他にどのような PowerShell モジュールがありますか。

PowerShell モジュールという用語は、実際の機能を実装するファイルも意味します。 スクリプト モジュール ファイル (.psm1) には PowerShell コードが含まれます。 バイナリ モジュール ファイル (.dll) にはコンパイルされたコードが含まれます。

ここでは、1 つの考え方があります。モジュールをカプセル化したフォルダーは、モジュール フォルダーです。 モジュール フォルダーには、フォルダーの内容を説明するモジュール マニフェスト (.psd1) が含まれることがあります。 実際に機能するファイルはスクリプト モジュール ファイル (.psm1) とバイナリ モジュール ファイル (.dll) です。 DSC リソースは特定のサブフォルダーにあり、スクリプト モジュール ファイルまたはバイナリ モジュール ファイルとして実装されます。

ギャラリー内のモジュールにはすべてモジュール マニフェストが含まれ、これらのモジュールの大部分にスクリプト モジュール ファイルまたはバイナリ モジュール ファイルが含まれています。 モジュールという用語は、このような意味の違いから混乱することがあります。 とくに明示しない限り、このページで使用するモジュールという用語は、このようなファイルを含むモジュール フォルダーを意味しています。

## <a name="how-does-packagemanagement-relate-to-powershellget-high-level-answer"></a>PackageManagement は PowerShellGet にどのように関連しているでしょうか。 (大まかな回答)

PackageManagement はどのパッケージ マネージャーでも機能する一般的なインターフェイスです。 最終的には、PowerShell モジュール、MSI、Ruby gem、NuGet パッケージ、Perl モジュールのどれを扱っていても、その検索とインストールには、PackageManagement のコマンド(Find-Package および Install-Package) を使用できる必要があります。 PackageManagement では、PackageManagement に差し込まれるそれぞれのパッケージ マネージャーのパッケージ プロバイダーを指定することによってこれを実行します。 プロバイダーは、実際の作業をすべて行います。リポジトリからコンテンツをフェッチし、そのコンテンツをローカルにインストールします。 多くの場合、パッケージ プロバイダーは、指定したパッケージの種類の既存のパッケージ マネージャー ツールを単にラップするだけです。

PowerShellGet は PowerShell パッケージのパッケージ マネージャーです。 PackageManagement を介して PowerShellGet 機能を公開する PSModule パッケージ プロバイダーがあります。 このため、[Install-Module][] または Install-Package -Provider PSModule を実行して、PowerShell ギャラリーからモジュールをインストールすることができます。 [Update-Module][] および [Publish-Module][] を含む特定の PowerShellGet 機能には、PackageManagement コマンドではアクセスできません。

つまり、PowerShellGet はPowerShell コンテンツのプレミアム パッケージ管理エクスペリエンスにのみ重点を置いています。 PackageManagement は、単一の一般的なツール セットによるすべてのパッケージ管理エクスペリエンスの公開に重点を置いています。 この回答では不十分な場合は、このドキュメントの下部にある「**PackageManagement は実際に PowerShellGet にどのように関連しているでしょうか。** 」のセクションに詳しい回答があります。

詳細については、[PackageManagement プロジェクトのページ](https://oneget.org/)にアクセスしてください。

## <a name="how-does-nuget-relate-to-powershellget"></a>NuGet は PowerShellGet にどのように関連しているでしょうか。

PowerShell ギャラリーは、[NuGet ギャラリー](https://www.nuget.org/)に変更を加えたバージョンです。
PowerShellGet は、NuGet プロバイダーを使用して、PowerShell ギャラリーなどの NuGet ベースのリポジトリで機能します。

PowerShellGet は任意の有効な NuGet リポジトリまたはファイル共有に対して使用することができます。 単に [Register-PSRepository][] コマンドレットを実行して、リポジトリを追加する必要があります。

## <a name="does-that-mean-i-can-use-nugetexe-to-work-with-the-gallery"></a>NuGet.exe をギャラリーで使用できるという意味でしょうか。

はい。

## <a name="how-does-packagemanagement-actually-relate-to-powershellget-technical-details"></a>PackageManagement は実際に PowerShellGet にどのように関連しているでしょうか。 (技術的な詳細)

内部的に、PowerShellGet は PackageManagement インフラストラクチャを大きく活用しています。

PowerShell コマンドレット層で、[Install-Module][] は実際には `Install-Package -Provider PSModule` の thin ラッパーです。

PackageManagement パッケージ プロバイダー層では、PSModule パッケージ プロバイダーは実際に他の PackageManagement パッケージ プロバイダーを呼び出します。 たとえば、NuGet ベースのギャラリー (PowerShell ギャラリーなど) を使用している場合、PSModule パッケージ プロバイダーでは、リポジトリで使用できるように NuGet パッケージ プロバイダーを使用します。

![PowerShellGet アーキテクチャ](media/faqs/powershellgetArchitecture.png)

図 1: PowerShellGet アーキテクチャ

## <a name="what-is-required-to-run-powershellget"></a>PowerShellGet を実行するには何が必要ですか。

一般的には、PowerShellGet モジュールの最新バージョンを選択することをお勧めします (これには .NET 4.5 が必要です)。

**PowerShellGet** モジュールは **PowerShell 3.0 以降**を必要とします。

そのため、**PowerShellGet** は次のいずれかのオペレーティング システムを必要とします。

- Windows 10
- Windows 8.1 Pro
- Windows 8.1 Enterprise
- Windows 7 SP1
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2008 R2 SP1

**PowerShellGet** には、.NET Framework 4.5 以降も必要です。 .NET Framework 4.5 以降を[ここ](https://msdn.microsoft.com/library/5a4x27ek.aspx)からインストールできます。

## <a name="is-it-possible-to-reserve-names-for-packages-that-will-be-published-in-future"></a>将来的に公開されるパッケージの名前を予約することはできますか。

パッケージ名をとっておくことはできません。 既存のパッケージより、その名前が自分のパッケージに適していると思われる場合は、[パッケージの所有者に問い合わせてみてください](./how-to/working-with-packages/contacting-package-owners.md)。
2、3 週間連絡がない場合は、サポートに連絡いただければ PowerShell Gallery チームが調査にあたります。

## <a name="how-do-i-claim-ownership-for-packages"></a>パッケージの所有権はどのように主張できますか。

詳細については、[PowerShellGallery.com でのパッケージ所有者の管理](./how-to/publishing-packages/managing-package-owners.md)に関するページを参照してください。

## <a name="how-do-i-deal-with-a-package-owner-who-is-violating-my-package-license"></a>自分のパッケージ ライセンスを侵害しているパッケージ所有者にはどう対処しますか。

そのパッケージ所有者とその他のパッケージ所有者の間で生じる争いについては、PowerShell コミュニティでの解決をお勧めします。 [争いの解決プロセス](./how-to/getting-support/dispute-resolution.md)を用意しておりますので、PowerShellGallery.com の管理者が仲裁に入る前に確認してください。

<!-- link references-->
[New-ModuleManifest]: /powershell/module/Microsoft.PowerShell.Core/New-ModuleManifest
[Test-ModuleManifest]: /powershell/module/Microsoft.PowerShell.Core/Test-ModuleManifest
[Update-ModuleManifest]: /powershell/module/PowerShellGet/Update-ModuleManifest
[Install-Module]: /powershell/module/PowershellGet/Install-Module
[New-ScriptFileInfo]: /powershell/module/PowershellGet/New-ScriptFileInfo
[Publish-Module]: /powershell/module/PowershellGet/Publish-Module
[Publish-Script]: /powershell/module/PowershellGet/Publish-Script
[Register-PSRepository]: /powershell/module/PowershellGet/Register-PSRepository
[Test-ScriptFileInfo]: /powershell/module/PowershellGet/Test-ScriptFileInfo
[Update-Module]: /powershell/module/PowershellGet/Update-Module
[Update-ScriptFileInfo]: /powershell/module/PowershellGet/Update-ScriptFileInfo
