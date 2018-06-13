---
ms.date: 08/23/2017
keywords: PowerShell, コマンドレット
title: Web ベースの Windows PowerShell コンソールの使用
ms.openlocfilehash: 5d29a6f97fddf4b329fcc7097cf7d40d47d22cca
ms.sourcegitcommit: 01d6985ed190a222e9da1da41596f524f607a5bc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/07/2018
ms.locfileid: "34483153"
---
# <a name="use-the-web-based-windows-powershell-console"></a>Web ベースの Windows PowerShell コンソールの使用

最終更新日 : 2013 年 6 月 24 日

適用対象: Windows Server 2012 R2、Windows Server 2012

Windows PowerShell Web Access を利用すると、セキュリティで保護された Web サイトにサインインし、Windows PowerShell セッション、コマンドレット、スクリプトを利用してリモート コンピューターを管理できます。

Windows PowerShell コンソールは Web ブラウザーで実行されるため、さまざまなクライアント デバイス (Web ブラウザーが動作するほとんどのデバイス) で開くことができます。

Web ベースの Windows PowerShell コンソールは、サインイン プロセスでユーザーが指定するリモート コンピューターを対象としています。

このトピックでは、Windows PowerShell Web Access の Web ベース コンソールにサインインして使用を開始する方法について説明します。

Windows PowerShell の使用方法や、コマンドレットまたはスクリプトの実行方法はこのトピックの対象外です。
Windows PowerShell およびスクリプト リソースの使用方法の詳細については、このトピックの最後にある「[関連項目](#see-also)」セクションを参照してください。

## <a name="supported-browsers-and-client-devices"></a>サポートされているブラウザーとクライアント デバイス

Windows PowerShell Web Access は次のインターネット ブラウザーをサポートします。
モバイル ブラウザーは公式にはサポートされていませんが、それらの多くが Web ベースの Windows PowerShell コンソールを実行できるようです。
その他のブラウザーも、Cookie の許可、JavaScript の実行、および HTTPS Web サイトの実行に対応している場合は動作すると思われますが、公式にはテストされていません。

### <a name="supported-desktop-computer-browsers"></a>サポート対象のデスクトップ コンピューター ブラウザー

- Microsoft Windows 8.0、9.0、10.0、11.0 の Windows Internet Explorer
- Mozilla Firefox 10.0.2
- Google Chrome 17.0.963.56m for Windows
- Apple Safari 5.1.2 for Windows
- Apple Safari 5.1.2 for Mac OS

### <a name="minimally-tested-mobile-devices-or-browsers"></a>最低限のテストを実施済みのモバイル デバイスまたはブラウザー

- Windows Phone 7 と 7.5
- Google Android WebKit 3.1 Browser Android 2.2.1 (Kernel 2.6)
- Apple Safari for iPhone operating system 5.0.1
- Apple Safari for iPad 2 オペレーティング システム 5.0.1

### <a name="browser-requirements"></a>ブラウザーの要件

Web ベースの Windows PowerShell コンソールを使うには、ブラウザーが次の操作を実行できる必要があります。

- Windows PowerShell Web Access ゲートウェイ Web サイトの Cookie を許可する。
- HTTPS ページを開き、読み取る。
- JavaScript を使う Web サイトを開き、実行する。

## <a name="signing-in-to-windows-powershell-web-access"></a>Windows PowerShell Web Access へのサインイン

Windows PowerShell Web Access 管理者は、所属組織の Windows PowerShell Web Access ゲートウェイ Web サイトのアドレスを示す URL を担当者に提供する必要があります。
この Web サイトのアドレスは、既定で *https://\<server_name\>/pswa* となっています。

Windows PowerShell Web Access にサインインする前に、管理対象のリモート コンピューターの名前または IP アドレスがわかっていることを確認してください。
また担当者がリモート コンピューターの承認済みユーザーであることと、リモート コンピューターがリモート管理を許可するよう構成されている必要があります。
リモート管理を許可するようコンピューターを構成する方法の詳細については、[Windows PowerShell でのリモート コマンドの有効化および使用](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enable-psremoting)に関するページを参照してください。

コンピューターを構成してリモート管理を有効にする最も簡単な方法は、Windows PowerShell セッションを管理者特権で開き (**[管理者として実行]**)、コンピューター上で **Enable-PSRemoting -force** コマンドレットを実行することです。

### <a name="to-sign-in-to-windows-powershell-web-access"></a>Windows PowerShell Web Access にサインインするには

1. Windows PowerShell Web Access Web サイトをインターネット ブラウザーのウィンドウまたはタブで開きます。

1. Windows PowerShell Web Access のサインイン ページで、ネットワーク ユーザー名、パスワード、および管理対象の (自分が承認済みユーザーとなっている) コンピューター名を入力します。 コンピューター名の代わりにカスタム サイトまたはプロキシ サーバーの URI を使うよう Windows PowerShell Web Access 管理者から指示されている場合は、**"接続の種類"** フィールドの **[接続 URI]** を選択し、URI を入力してください。

    > ![注](images/Note.jpeg) **注**:
    >
    > - 対象のコンピューターがワークグループに含まれている場合、次の構文を使ってユーザー名を入力し、コンピューターにサインインします: `<workgroup_name>\<user_name>`
    > - 対象のコンピューターがゲートウェイ サーバーの場合、"コンピューター名" フィールドに `localhost` を指定できます。
    > - 対象のコンピューターがゲートウェイ サーバーで、そのゲートウェイ サーバーがワークグループに含まれている場合、"ユーザー名" フィールドには `<workgroup name>\<user_name>` を使用する必要があります。 "コンピューター名" フィールドには `localhost` を使用できます。

1. **[オプションの接続設定]** セクションは、管理対象のリモート コンピューターの承認要件に関連しています。 オプションの接続設定に相当するパラメーターの詳細については、[Enter-PSSession](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/enter-pssession) コマンドレットのヘルプを参照してください。

    通常、Windows PowerShell Web Access ゲートウェイの通過に使う資格情報は、管理対象のリモート コンピューターが認識する資格情報と同じです。 ただし、手順 2. で指定したリモート コンピューターを別の資格情報を使って管理する場合、**[オプションの接続設定]** セクションを展開して、別の資格情報を入力します。 それ以外の場合、手順 6. に進みます。

1. Windows PowerShell Web Access 管理者が Windows PowerShell Web Access ユーザー用にカスタムのセッション構成を作成している場合、そのセッション構成の名前を **"構成名"** フィールドに入力します。 セッション構成の詳細については、「[about_Session_Configurations](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_session_configurations)」を参照してください。

1. **[認証の種類]** の設定は、それ以外にするよう Windows PowerShell Web Access 管理者から指示された場合を除き、**[既定]** が設定されたままにしておきます。

1. **[サインイン]** をクリックします。

## <a name="signing-out-and-timing-out"></a>サインアウトとタイムアウト

次のいずれかの操作を実行すると、Web ベースの Windows PowerShell セッションからサインアウトします。

- コンソールの右下隅にある **[サインアウト]** をクリックする (Windows Server 2012 のみ)

- コンソールの右下隅にある **[保存]** または **[終了]** をクリックする (Windows Server 2012 R2 のみ)。 **[保存]** をクリックすると Windows PowerShell Web Access セッションが保存されて閉じます。後でセッションに再接続できます。 Windows PowerShell Web Access に再びサインインすると、保存したセッションの一覧が Windows PowerShell Web Access に表示されます。保存されているセッションを選択して再接続することも、新しいセッションを開始することもできます。 ユーザーが開くことのできるセッションの最大数 (保存されているものとアクティブの両方) は、ゲートウェイの管理者が構成します。

    **[終了]** をクリックすると、Windows PowerShell Web Access セッションが保存されずにサインアウトします。

- 同じブラウザー セッションまたは同じブラウザー セッションの新しいタブで、別のリモート コンピューターを管理するためにサインインする。 (これは、ゲートウェイ サーバーが Windows Server 2012 R2 を実行している場合は適用されません。Windows Server 2012 R2 で実行している Windows PowerShell Web Access では、同じブラウザー セッションの新しいタブで複数のユーザー セッションを開くことができます)。同じコンピューターで複数のアクティブ セッションを使う方法の詳細については、このトピックの「[Web ベース コンソールの制限事項](#limitations-of-the-web-based-console)」セクションの「複数の対象コンピューターへの同時接続」を参照してください。

- セッションの非アクティブな状態が 20 分続いた場合。 ゲートウェイの管理者は、非アクティブ状態によるタイムアウトの長さをカスタマイズできます。詳細については、「[セッションの管理](authorization-rules-and-security-features-of-windows-powershell-web-access.md#session-management)」を参照してください。

    - ユーザー自身がセッションを閉じたためではなく、ネットワーク エラーまたはその他の予期しないシャットダウンや障害のために、ユーザーがセッションから切断された場合、クライアント側でタイムアウト期間が経過するまで Windows PowerShell Web Access セッションは実行を続け、ターゲット コンピューターに接続されたままになります。 既定ではこのタイムアウト期間は 20 分であり、ゲートウェイ管理者が構成します。 既定の 20 分またはゲートウェイ管理者が指定したタイムアウト期間のどちらか短い方が経過すると、セッションは切断されます。

        ゲートウェイ サーバーが Windows Server 2012 R2 を実行している場合の Windows PowerShell Web Access では、ユーザーは保存されているセッションに再接続できますが、ゲートウェイ管理者によって指定されたタイムアウト期間が経過するまでは、保存されているセッションを表示または再接続できません。

- ブラウザー ウィンドウまたはタブを閉じる。

- ブラウザーが実行されているクライアント デバイスの電源を切る、またはネットワークから切断する。

- Web コンソールで **[終了]** コマンドを実行する。 接続先のセッション構成が [NoLanguage](https://msdn.microsoft.com/library/windows/desktop/system.management.automation.pslanguagemode.aspx) モードをサポートするよう構成されている場合、または制限付き実行空間が指定されている場合は、このコマンドは機能しません。

もう一度サインインする場合は、Windows PowerShell Web Access の Web ページをもう一度開き、このトピックの「[Windows PowerShell Web Access へのサインイン](#signing-in-to-windows-powershell-web-access)」の手順に従ってサインインします。

## <a name="differences-in-the-web-based-windows-powershell-console"></a>Web ベースの Windows PowerShell コンソールにおける相違点

Windows PowerShell Web Access にサインインすると、Web ベースの Windows PowerShell コンソールがブラウザー ウィンドウまたはタブに表示されます。コンソールはサインイン プロセスで指定したリモート コンピューターに接続されているため、このコンソールで使える Windows PowerShell コマンドレットまたはスクリプトは、対象のリモート コンピューターで利用可能なものだけです。 このセクションでは、Windows PowerShell Web Access コンソールにおけるその他の制限事項と、Windows PowerShell Web Access コンソールとインストール型の **PowerShell.exe** コンソールとの間の違いについて説明します。

### <a name="functional-disparity-with-powershellexe"></a>PowerShell.exe との機能面の相違点

Windows PowerShell のホスト機能の大部分は Windows PowerShell Web Access の Web ベース コンソールでも利用できますが、いくつかの機能は利用できません。

- 入れ子になった進行状況の表示。

  進行状況を報告するコマンドレットを使用すると、Windows PowerShell Web Access が表示する進行状況 GUI には、最上位レベルの情報だけが表示されます。

- 入力色の変更。

  入力色 (前景と背景) は変更できません。 出力、警告、詳細、およびエラー メッセージのスタイルは、スクリプトを実行することで変更できます。

- PSHostRawUserInterface。

  Windows PowerShell Web Accessは Windows PowerShell リモート管理経由で実装され、リモートの実行空間を使います。 たとえば Windows コンソールへの書き込みを実行するあらゆるコマンドなど、一部のメソッドは Windows PowerShell Web Access によってこのインターフェイスに実装されません。 **PowerTab** などのコマンドは、Windows PowerShell Web Access では動作しません。

- ファンクション キー。

  一部のファンクション キーは Windows PowerShell Web Access によってサポートされません。多くの場合、それらのコマンドがブラウザーによって予約されていることが原因です。

### <a name="unsupported-shortcut-keys"></a>サポートされていないショートカット キー

ファンクション キー | 操作
-- | --
Ctrl+C | Windows PowerShell Web Access では、**Ctrl + C** はブラウザーによるコンテンツのコピーに使われます。 コンソールが提供する **[キャンセル]** ボタンのほか、ユーザーは **Ctrl + Q** を使ってコマンドをキャンセルできます。
Alt + Space、e、l | 画面バッファーをスクロール
Alt + Space、e、f | 画面バッファー内のテキストを検索
Alt + Space、e、k | コピーするテキストを画面バッファーから選択
Alt + Space、e、p | クリップボードのコンテンツを Windows PowerShell コンソールに貼り付け
Alt + Space、c | Windows PowerShell コンソールを閉じる
Ctrl + Break | Windows PowerShell ウィンドウを強制的に閉じる
Ctrl + Home | 現在のコマンド ラインの先頭から削除
Ctrl + End | コマンド ラインの末尾まで削除
F1 | コマンド ライン上でカーソルを 1 文字分移動
F2 | 最後のコマンドをコピーし、入力する文字に合わせて新しいコマンドを作成
F3 | 最後のコマンド ラインの内容を使ってコマンド ラインを完成させる
F4 | カーソル位置から文字を削除
F5 | コマンド履歴をさかのぼってスキャン Windows PowerShell Web Access のコマンド履歴にあるコマンドにアクセスするには、Web ベース コンソールで **[履歴]** スクロール ボタンをクリックします。
F7 | コマンド履歴のコマンドを対話的に選択
F8 | 現在のテキストに一致するコマンドが表示された履歴をスキャン
F9 | 履歴から特定の番号の付いたコマンドを実行
PageUp | 履歴内の最初のコマンドを実行
PageDown | 履歴内の最後のコマンドを実行
Alt + F7 | コマンド履歴の一覧を消去

### <a name="limitations-of-the-web-based-console"></a>Web ベース コンソールの制限事項

- ダブルホップ

    Windows PowerShell Web Access を使って新しいセッションを作成または操作しようとすると、ダブルホップ (最初の接続から 2 つ目のコンピューターに接続すること) の制限が発生します。 Windows PowerShell Web Access はリモートの実行空間を使いますが、現時点では、リモートの実行空間から 2 つ目のコンピューターへのリモート接続の確立を **PowerShell.exe** がサポートしていません。 たとえば、**Enter-PSSession** コマンドレットを使って既存の接続から 2 つ目のリモート コンピューターに接続しようとすると、"ネットワーク リソースを取得できません" など、さまざまなエラーが発生します。

    ダブルホップのエラーを避けるには、管理者が組織のネットワーク環境に CredSSP 認証を構成する必要があります。 CredSSP 認証の構成方法の詳細については、Microsoft Web サイトの [CredSSP による次ホップのリモート処理](http://blogs.msdn.com/b/powershell/archive/2008/06/05/credssp-for-second-hop-remoting-part-i-domain-account.aspx)に関するページを参照してください。 2 つ目のリモート コンピューターを管理する場合、明示的な資格情報を提供することも可能です。暗黙的な資格情報の場合、次ホップが許可される可能性が低くなります。

- リモート処理

    Windows PowerShell Web Access に使用され適用される制限事項は、リモートの Windows PowerShell セッションと同じです。 コンソールベースのエディターやテキストベースのメニュー プログラムなど、Windows コンソール API を直接呼び出すコマンドは動作しません。これは、これらのコマンドが、標準入力、出力、エラーの各パイプの読み取りと書き込みを実行しないためです。 このため、実行可能ファイルを起動するコマンド (**notepad.exe** など) や GUI を表示するコマンド (`OpenGridView` または `ogv` など) は動作しません。 この動作は担当者のエクスペリエンスに影響を与えます。つまり、担当者には Windows PowerShell Web Access がコマンドに応答していないように見えます。

- Tab 補完機能

    タブ補完は、制限付き実行空間が指定されたセッション構成、または **NoLanguage** モードのセッション構成では動作しません。 管理者がタブ補完をサポートするようセッションを構成できますが、承認されていないユーザーに次の情報が公開される可能性があるというセキュリティ上の理由から推奨されません。

    - 内部ファイル システムのパス

    - 内部コンピューターの共有フォルダー

    - 実行空間の変数

    - 読み込まれる型または .NET Framework の名前空間

    - 環境変数

- **NoLanguage** セッション、または制限付き実行空間

    **NoLanguage** の Windows PowerShell Web Access セッション構成または制限付き実行空間にサインインしているユーザーは **[終了]** コマンドを実行してセッションを終了できません。 サインアウトするには、コンソール ページの **[サインアウト]** をクリックする必要があります。

- 複数の対象コンピューターへの同時接続。

    ゲートウェイ サーバーが Windows Server 2012 を実行している場合、Windows PowerShell Web Access では、ブラウザー セッションごとに接続できるリモート コンピューターは 1 つだけです。一度サインインした後に別のブラウザー タブを使って複数のリモート コンピューターに接続することはできません。 新しいタブまたはブラウザー ウィンドウを開くと、現在のセッションの切断と新しいセッションの開始を確認するメッセージが Windows PowerShell Web Access により表示されます。このメッセージから新しい (または同じ) リモート コンピューターに接続できます。 ただし、異なるリモート コンピューターに対して個別のセッションを 2 つ以上実行する必要がある場合、Internet Explorer の機能を使って新しいセッションを作成できます。 Internet Explorer で新しいブラウザー セッションを開始するには、**Alt** キーを押して **[ファイル]** メニューを開き、**[新しいセッション]** をクリックします。 次に新しいセッションで Windows PowerShell Web Access の Web サイトを開き、サインインして別のリモート コンピューターにアクセスします。

    Windows PowerShell Web Access ゲートウェイが Windows Server 2012 R2 で実行されている場合、ユーザーは異なるブラウザー タブでリモート コンピューターへの複数の接続を開くことができます。 Web ベースの Windows PowerShell コンソールを使用してリモート コンピューターへの複数の接続を開く必要がある場合は、ゲートウェイ サーバーがこの機能をサポートしているかどうかを Windows PowerShell Web Access ゲートウェイ管理者に確認してください。

- 永続的な Windows PowerShell セッション (再接続)。

    Windows PowerShell Web Access ゲートウェイがタイムアウトすると、ゲートウェイと対象コンピューターとのリモート接続は閉じられます。 これによって、現在処理中のすべてのコマンドレットとスクリプトが停止されます。 実行時間の長いタスクを実行している場合は、Windows PowerShell の **-Job** インフラストラクチャを使うことが推奨されます。これにより、ジョブを開始し、コンピューターから切断した後に再接続して、ジョブを永続的なものにすることができます。 **-Job** コマンドレットを使うもう 1 つのメリットは、Windows PowerShell Web Access を使ってジョブを開始し、サインアウトした後に、Windows PowerShell Web Access またはその他のホスト (Windows PowerShell 統合スクリプティング環境 (ISE) など) を使って再接続できる点です。

- コンソールのサイズ変更。

    **PowerShell.exe** コンソール ウィンドウのサイズは次の 3 つの方法で変更できます。

    - マウスを使ってコンソール ウィンドウをドラッグして調整する

    - コンソール プロパティの GUI を使って高さと幅のプロパティを変更する

    - コマンドレットを使ってコンソール ウィンドウの高さと幅を変更する

        Windows PowerShell Web Access のコンソール ウィンドウは、次のコマンドレットを使って構成できます。 次の例では、ユーザーが Windows PowerShell Web Access コンソールの幅を **20** に変更しています。

            $newSize = $Host.UI.RawUI.WindowSize
            $newSize.Width = $newSize.Width - 20

            $oldSize = $Host.UI.RawUI.WindowSize

            $Host.UI.RawUI.WindowSize = $newSize

        同じ方法でコンソールの高さを変更できます。

        コンソール ビューをカスタマイズするその他の例については、[Windows PowerShell チームのブログ](http://blogs.msdn.com/b/powershell/)を参照してください。

## <a name="see-also"></a>参照

- [Windows PowerShell コマンドレット リファレンス](https://technet.microsoft.com/library/ee407531(ws.10).aspx)
- [Microsoft TechNet の Windows PowerShell](https://technet.microsoft.com/library/bb978526.aspx)
- [TechNet スクリプト センター リポジトリ](http://gallery.technet.microsoft.com/scriptcenter)
- [スクリプト センター - Hey, Scripting Guy!](https://technet.microsoft.com/scriptcenter)
- [Windows PowerShell チーム ブログ](http://blogs.msdn.com/b/powershell/)