---
title: PowerShell コマンドの承認された動詞 |Microsoft Docs
ms.custom: ''
ms.date: 09/07/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- action names [PowerShell SDK]
- verb names [PowerShell SDK]
- cmdlets [PowerShell SDK], verb names
ms.assetid: 2d4e58a9-05bc-437c-86b9-d8d55cba7d48
caps.latest.revision: 36
ms.openlocfilehash: b1e551c93540bd6769021aaa2bff08cfa3879e2c
ms.sourcegitcommit: 7c7f8bb9afdc592d07bf7ff4179d000a48716f13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2020
ms.locfileid: "82174111"
---
# <a name="approved-verbs-for-powershell-commands"></a>PowerShell コマンドの承認された動詞

PowerShell では、コマンドレットの名前に動詞と名詞の組み合わせを使用し、その派生 Microsoft .NET Framework クラスを使用します。 たとえば、powershell に`Get-Command`よって提供されるコマンドレットを使用して、powershell に登録されているすべてのコマンドを取得します。 名前の動詞部分は、コマンドレットで実行されるアクションを識別します。 名前の名詞部分は、アクションが実行されるエンティティを識別します。

> [!NOTE]
> PowerShell では、*動詞*という用語を使用して、その単語が英語の標準動詞ではない場合でも、アクションを意味する単語を記述します。 たとえば、 *New*という用語は、英語の動詞ではなくアクションを意味するので、有効な PowerShell 動詞名です。

## <a name="verb-naming-rules"></a>動詞の名前付け規則

次の一覧は、コマンドレット名の動詞を選択する際に考慮するガイドラインを示しています。

- 動詞を指定する場合は、PowerShell によって提供される定義済みの動詞名のいずれかを使用することをお勧めします (これらの定義済み動詞のエイリアスは次の表に含まれています)。 定義済みの動詞を使用すると、作成したコマンドレット、PowerShell によって提供されるコマンドレット、および他のユーザーが設計したコマンドレット間の一貫性が確保されます。

- 定義済みの動詞を使用してアクションの一般的なスコープを記述し、パラメーターを使用してコマンドレットのアクションをさらに絞り込むことができます。

- コマンドレット間で一貫性を確保するには、承認された動詞のシノニムを使用しないでください。

- このトピックに記載されている各動詞の形式のみを使用します。 たとえば、"Get" を使用しますが、"取得" または "取得" は使用しないでください。

- 動詞に Pascal 形式を使用します。 Pascal 形式では、各単語の最初の文字が "ForEach" のように大文字で表記されます。

- 次の予約された動詞またはエイリアスは使用しないでください。 これらの動詞は、powershell 言語、または PowerShell によって提供される特殊なケースのコマンドレットによって使用されます。
  - ForEach (foreach)
  - 形式 (f)
  - グループ (gp)
  - 並べ替え (sr)
  - T (te)
  - Where (wh)

`Get-Verb`コマンドレットを使用して、動詞の完全な一覧を表示できます。

## <a name="similar-verbs-for-different-actions"></a>さまざまなアクションに対する同様の動詞

次のような動詞は、さまざまなアクションを表します。

### <a name="new-vs-set"></a>新しい対セット

動詞`New`は、新しいリソースの作成に使用されます。 `Set`動詞は、既存のリソースを変更するために使用されます。必要に応じて、 `Set-Variable`コマンドレットなどのリソースが存在しない場合は作成します。

### <a name="find-vs-search"></a>検索と検索

動詞`Find`は、オブジェクトを検索するために使用されます。 動詞`Search`は、コンテナー内のリソースへの参照を作成するために使用されます。

### <a name="get-vs-read"></a>Get と Read

`Get`動詞は、ファイルなどのリソースを取得するために使用されます。 `Read`動詞は、ファイルなどのソースから情報を取得するために使用されます。

### <a name="invoke-vs-start"></a>呼び出しと開始

`Invoke`動詞は、通常、コマンドの実行などの同期操作である操作を実行するために使用されます。 `Start`動詞は、通常、プロセスの開始などの非同期操作である操作を開始するために使用されます。

### <a name="ping-vs-test"></a>Ping とテスト

`Test`動詞を使用します。

## <a name="common-verbs"></a>共通動詞

PowerShell では、 [VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)列挙クラスを使用して、ほぼすべてのコマンドレットに適用できる汎用アクションを定義します。 次の表は、定義されている動詞の大部分を示しています。

|動詞 (エイリアス)|アクション|説明|
|--------------------|------------|--------------|
|(A) を[追加](/dotnet/api/System.Management.Automation.VerbsCommon.Add)する|コンテナーにリソースを追加するか、別の項目に項目をアタッチします。 たとえば、コマンドレット`Add-Content`は、ファイルにコンテンツを追加します。 この動詞はとペア`Remove`になっています。|このアクションでは、追加、アタッチ、連結、挿入などの動詞は使用しないでください。|
|[Clear](/dotnet/api/System.Management.Automation.VerbsCommon.Clear) (cl)|コンテナーからすべてのリソースを削除しますが、コンテナーは削除しません。 たとえば、コマンドレット`Clear-Content`はファイルの内容を削除しますが、ファイルは削除しません。|このアクションでは、Flush、Erase、Release、アンマーク、Unset、または無効化などの動詞は使用しないでください。|
|[閉じる](/dotnet/api/System.Management.Automation.VerbsCommon.Close)(cs)|リソースの状態を変更して、アクセス不可能にするか、使用できないようにします。 この動詞はとペアになっています。`Open.`||
|[コピー](/dotnet/api/System.Management.Automation.VerbsCommon.Copy) (cp)|リソースを別の名前または別のコンテナーにコピーします。 たとえば、格納さ`Copy-Item`れたデータにアクセスするために使用されるコマンドレットは、データストア内のある場所から別の場所に項目をコピーします。|この操作では、複製、複製、複製、同期などの動詞は使用しないでください。|
|[Enter](/dotnet/api/System.Management.Automation.VerbsCommon.Enter) (et)|ユーザーがリソースへの移動を許可するアクションを指定します。 たとえば、コマンドレット`Enter-PSSession`はユーザーを対話型セッションに配置します。 この動詞はとペア`Exit`になっています。|このアクションでは、Push や Into などの動詞は使用しないでください。|
|[Exit](/dotnet/api/System.Management.Automation.VerbsCommon.Exit) (ex)|現在の環境またはコンテキストを、最近使用したコンテキストに設定します。 たとえば、コマンドレット`Exit-PSSession`は、対話型セッションを開始するために使用されたセッションにユーザーを配置します。 この動詞はとペア`Enter`になっています。|このアクションでは、Pop や Out などの動詞は使用しないでください。|
|[検索](/dotnet/api/System.Management.Automation.VerbsCommon.Find)(fd)|不明、暗黙的、オプション、または指定されたコンテナー内のオブジェクトを検索します。||
|[形式](/dotnet/api/System.Management.Automation.VerbsCommon.Format)(f)|指定されたフォームまたはレイアウトでオブジェクトを整列します。||
|[Get](/dotnet/api/System.Management.Automation.VerbsCommon.Get) (g)|リソースを取得するアクションを指定します。 この動詞はとペア`Set`になっています。|このアクションでは、読み取り、オープン、Cat、種類、Dir、取得、ダンプ、取得、検査、検索、検索などの動詞は使用しないでください。|
|[非表示](/dotnet/api/System.Management.Automation.VerbsCommon.Hide)(h)|リソースを検出できないようにします。 たとえば、名前に Hide 動詞が含まれているコマンドレットでは、ユーザーのサービスを隠すことができます。 この動詞はとペア`Show`になっています。|このアクションでは、Block などの動詞は使用しないでください。|
|[結合](/dotnet/api/System.Management.Automation.VerbsCommon.Join)(j)|リソースを1つのリソースに結合します。 たとえば、コマンドレット`Join-Path`は、パスとその子パスの1つを組み合わせて、1つのパスを作成します。 この動詞はとペア`Split`になっています。|このアクションでは、結合、結合、接続、関連付けなどの動詞は使用しないでください。|
|[Lock](/dotnet/api/System.Management.Automation.VerbsCommon.Lock) (lk)|リソースをセキュリティで保護します。 この動詞はとペア`Unlock`になっています。|このアクションでは、Restrict や Secure などの動詞は使用しないでください。|
|[移動](/dotnet/api/System.Management.Automation.VerbsCommon.Move)(m)|リソースをある場所から別の場所に移動します。 たとえば、コマンドレット`Move-Item`は、データストア内のある場所から別の場所に項目を移動します。|この操作では、転送、名前、移行などの動詞は使用しないでください。|
|[新規](/dotnet/api/System.Management.Automation.VerbsCommon.New)(n)|リソースを作成します。 ( `Set-Variable`コマンド`Set`レットなど、データを含むリソースを作成するときに動詞を使用することもできます)。|このアクションでは、作成、生成、ビルド、作成、割り当てなどの動詞は使用しないでください。|
|[開く](/dotnet/api/System.Management.Automation.VerbsCommon.Open)(op)|リソースの状態を変更して、アクセス可能、使用可能、または使用できるようにします。 この動詞はとペア`Close`になっています。||
|[Optimize](/dotnet/api/System.Management.Automation.VerbsCommon.Optimize) (om)|リソースの有効性を高めます。||
|[Pop](/dotnet/api/System.Management.Automation.VerbsCommon.Pop) (pop)|スタックの一番上から項目を削除します。 たとえば、コマンドレット`Pop-Location`は、現在の場所を、最後にスタックにプッシュされた場所に変更します。||
|[プッシュ](/dotnet/api/System.Management.Automation.VerbsCommon.Push)(pu)|スタックの一番上に項目を追加します。 たとえば、コマンドレット`Push-Location`は現在の場所をスタックにプッシュします。||
|[やり直し](/dotnet/api/System.Management.Automation.VerbsCommon.Redo)(re)|リソースを、元に戻された状態にリセットします。||
|[削除](/dotnet/api/System.Management.Automation.VerbsCommon.Remove)(r)|コンテナーからリソースを削除します。 たとえば、コマンドレット`Remove-Variable`は、変数とその値を削除します。 この動詞はとペア`Add`になっています。|このアクションでは、Clear、Cut、Dispose、Discard、Erase などの動詞は使用しないでください。|
|[Rename](/dotnet/api/System.Management.Automation.VerbsCommon.Rename) (rn)|リソースの名前を変更します。 たとえば、格納さ`Rename-Item`れているデータにアクセスするために使用されるコマンドレットは、データストア内の項目の名前を変更します。|このアクションでは、変更などの動詞は使用しないでください。|
|[リセット](/dotnet/api/System.Management.Automation.VerbsCommon.Reset)(rs)|リソースを元の状態に戻します。||
|[検索](/dotnet/api/System.Management.Automation.VerbsCommon.Search)(sr)|コンテナー内のリソースへの参照を作成します。|このアクションでは、[検索] や [検索] などの動詞は使用しないでください。|
|[選択](/dotnet/api/System.Management.Automation.VerbsCommon.Select)(sc)|コンテナー内のリソースを検索します。 たとえば、コマンドレット`Select-String`は文字列とファイル内のテキストを検索します。|このアクションでは、[検索] や [検索] などの動詞は使用しないでください。|
|[セット](/dotnet/api/System.Management.Automation.VerbsCommon.Set)(s)|既存のリソースのデータを置き換えるか、一部のデータを含むリソースを作成します。 たとえば、コマンドレット`Set-Date`は、ローカルコンピューターのシステム時刻を変更します。 (動詞`New`を使用してリソースを作成することもできます)。この動詞はとペア`Get`になっています。|この操作では、書き込み、リセット、割り当て、構成などの動詞は使用しないでください。|
|[表示](/dotnet/api/System.Management.Automation.VerbsCommon.Show)(sh)|リソースをユーザーに表示します。 この動詞はとペア`Hide`になっています。|このアクションでは、表示や生成などの動詞は使用しないでください。|
|[スキップ](/dotnet/api/System.Management.Automation.VerbsCommon.Skip)(sk)|シーケンス内の1つ以上のリソースまたはポイントをバイパスします。|このアクションでは、バイパスやジャンプなどの動詞は使用しないでください。|
|[分割](/dotnet/api/System.Management.Automation.VerbsCommon.Split)(sl)|リソースの一部を分割します。 たとえば、コマンドレット`Split-Path`はパスの異なる部分を返します。 この動詞はとペア`Join`になっています。|このアクションでは、独立した動詞を使用しないでください。|
|[ステップ](/dotnet/api/System.Management.Automation.VerbsCommon.Step)(st)|シーケンス内の次のポイントまたはリソースに移動します。||
|[スイッチ](/dotnet/api/System.Management.Automation.VerbsCommon.Switch)(sw)|2つの場所、責任、または状態を変更するなど、2つのリソースを交互に切り替えるアクションを指定します。||
|[元に戻す](/dotnet/api/System.Management.Automation.VerbsCommon.Undo)(un)|リソースを以前の状態に設定します。||
|[ロック解除](/dotnet/api/System.Management.Automation.VerbsCommon.Unlock)(uk)|ロックされていたリソースを解放します。 この動詞はとペア`Lock`になっています。|このアクションでは、Release、Unrestrict、またはセキュリティ保護されていないなどの動詞は使用しないでください。|
|[Watch](/dotnet/api/System.Management.Automation.VerbsCommon.Watch) (wc)|リソースの変更を継続的に検査または監視します。||

## <a name="communications-verbs"></a>通信動詞

PowerShell では、 [VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)クラスを使用して、通信に適用されるアクションを定義します。 次の表は、定義されている動詞の大部分を示しています。

|動詞 (エイリアス)|アクション|説明|
|--------------------|------------|--------------|
|[接続](/dotnet/api/System.Management.Automation.VerbsCommunications.Connect)(cc)|変換元と変換先の間のリンクを作成します。 この動詞はとペア`Disconnect`になっています。|このアクションでは、Join や Telnet などの動詞は使用しないでください。|
|[切断](/dotnet/api/System.Management.Automation.VerbsCommunications.Disconnect)(dc)|変換元と変換先の間のリンクを解除します。 この動詞はとペア`Connect`になっています。|この操作では、Break や Logoff などの動詞は使用しないでください。|
|[読み取り](/dotnet/api/System.Management.Automation.VerbsCommunications.Read)(rd)|ソースから情報を取得します。 この動詞はとペア`Write`になっています。|このアクションでは、Get、Prompt、Get などの動詞は使用しないでください。|
|[Receive](/dotnet/api/System.Management.Automation.VerbsCommunications.Receive) (rc)|ソースから送信された情報を受け入れます。 この動詞はとペア`Send`になっています。|この操作では、読み取り、受け入れ、ピークなどの動詞は使用しないでください。|
|[送信](/dotnet/api/System.Management.Automation.VerbsCommunications.Send)(sd)|宛先に情報を配信します。 この動詞はとペア`Receive`になっています。|このアクションでは、Put、Broadcast、Mail、Fax などの動詞は使用しないでください。|
|[書き込み](/dotnet/api/System.Management.Automation.VerbsCommunications.Write)(wr)|ターゲットに情報を追加します。 この動詞はとペア`Read`になっています。|このアクションでは、Put や Print などの動詞は使用しないでください。|

## <a name="data-verbs"></a>データ動詞

PowerShell では、 [VerbsData](/dotnet/api/System.Management.Automation.VerbsData)クラスを使用して、データ処理に適用されるアクションを定義します。 次の表は、定義されている動詞の大部分を示しています。

|動詞名 (エイリアス)|アクション|説明|
|-------------------------|------------|--------------|
|[バックアップ](/dotnet/api/System.Management.Automation.VerbsData.Backup)(ba)|データをレプリケートして格納します。|このアクションでは、保存、書き込み、複製、同期などの動詞は使用しないでください。|
|[チェックポイント](/dotnet/api/System.Management.Automation.VerbsData.Checkpoint)(ch)|データの現在の状態またはその構成のスナップショットを作成します。|このアクションでは、Diff などの動詞は使用しないでください。|
|[比較](/dotnet/api/System.Management.Automation.VerbsData.Compare)(cr)|あるリソースのデータを、別のリソースのデータと比較して評価します。|このアクションでは、Diff などの動詞は使用しないでください。|
|[圧縮](/dotnet/api/System.Management.Automation.VerbsData.Compress)(cm)|リソースのデータを圧縮します。 との`Expand`ペア。|このアクションでは、Compact などの動詞は使用しないでください。|
|[Convert](/dotnet/api/System.Management.Automation.VerbsData.Convert) (cv)|コマンドレットで双方向変換がサポートされている場合、またはコマンドレットが複数のデータ型間の変換をサポートしている場合は、ある表現から別の表現にデータを変更します。|このアクションでは、変更、サイズ変更、リサンプルなどの動詞は使用しないでください。|
|[Convertfrom-csv](/dotnet/api/System.Management.Automation.VerbsData.ConvertFrom) (cf)|1つのプライマリタイプの入力 (コマンドレットの名詞は入力を示します) を1つ以上のサポートされている出力の種類に変換します。|このアクションでは、Export、Output、Out などの動詞は使用しないでください。|
|[Convertto-html](/dotnet/api/System.Management.Automation.VerbsData.ConvertTo) (ct)|1つ以上の入力の型をプライマリ出力型に変換します (コマンドレットの名詞は出力の種類を示します)。|このアクションでは、Import、Input、In などの動詞は使用しないでください。|
|[マウント解除](/dotnet/api/System.Management.Automation.VerbsData.Dismount)(dm)|名前付きエンティティを場所からデタッチします。 この動詞はとペア`Mount`になっています。|この操作では、マウント解除やリンク解除などの動詞は使用しないでください。|
|[編集](/dotnet/api/System.Management.Automation.VerbsData.Edit)(ed)|コンテンツを追加または削除することによって既存のデータを変更します。|この操作では、変更、更新、変更などの動詞は使用しないでください。|
|[展開](/dotnet/api/System.Management.Automation.VerbsData.Expand)(en)|圧縮されたリソースのデータを元の状態に復元します。 この動詞はとペア`Compress`になっています。|この操作では、分解や圧縮解除などの動詞は使用しないでください。|
|[エクスポート](/dotnet/api/System.Management.Automation.VerbsData.Export)(ep)|ファイルなどの永続的なデータストアまたはインターチェンジ形式へのプライマリ入力をカプセル化します。 この動詞はとペア`Import`になっています。|この操作では、抽出やバックアップなどの動詞は使用しないでください。|
|[グループ](/dotnet/api/System.Management.Automation.VerbsData.Group)(gp)|1つ以上のリソースを配置または関連付けます。|このアクションでは、集計、整列、関連付け、関連付けなどの動詞は使用しないでください。|
|[インポート](/dotnet/api/System.Management.Automation.VerbsData.Import)(ip)|永続データストア (ファイルなど) またはインターチェンジ形式で格納されているデータからリソースを作成します。 たとえば、コマンドレット`Import-CSV`は、コンマ区切り値 (CSV) ファイルから、他のコマンドレットで使用できるオブジェクトにデータをインポートします。 この動詞はとペア`Export`になっています。|このアクションでは、BulkLoad や Load などの動詞は使用しないでください。|
|[Initialize](/dotnet/api/System.Management.Automation.VerbsData.Initialize) (in)|使用するリソースを準備し、それを既定の状態に設定します。|この操作では、消去、初期化、更新、リビルド、再初期化、セットアップなどの動詞は使用しないでください。|
|[制限](/dotnet/api/System.Management.Automation.VerbsData.Limit)(l)|リソースに制約を適用します。|このアクションでは、Quota などの動詞は使用しないでください。|
|[Merge](/dotnet/api/System.Management.Automation.VerbsData.Merge) (mg)|複数のリソースから1つのリソースを作成します。|このアクションでは、結合や結合などの動詞は使用しないでください。|
|[Mount](/dotnet/api/System.Management.Automation.VerbsData.Mount) (mt)|名前付きエンティティを場所にアタッチします。 この動詞はとペア`Dismount`になっています。|このアクションでは、Connect という動詞は使用しないでください。|
|[Out](/dotnet/api/System.Management.Automation.VerbsData.Out) (o)|環境からデータを送信します。 たとえば、コマンドレット`Out-Printer`はプリンターにデータを送信します。||
|[発行](/dotnet/api/System.Management.Automation.VerbsData.Publish)(pb)|他のユーザーがリソースを使用できるようにします。 この動詞はとペア`Unpublish`になっています。|この操作では、配置、リリース、インストールなどの動詞は使用しないでください。|
|[復元](/dotnet/api/System.Management.Automation.VerbsData.Restore)(rr)|によって`Checkpoint`設定された状態など、リソースを定義済みの状態に設定します。 たとえば、コマンドレット`Restore-Computer`は、ローカルコンピューターでシステムの復元を開始します。|このアクションでは、[修復]、[戻る]、[元に戻す]、[修正] などの動詞は使用しないでください。|
|[保存](/dotnet/api/System.Management.Automation.VerbsData.Save)(sv)|損失を防ぐためにデータを保持します。||
|[同期](/dotnet/api/System.Management.Automation.VerbsData.Sync)(sy)|2つ以上のリソースが同じ状態であることを保証します。|このアクションでは、Replicate、強制、一致などの動詞は使用しないでください。|
|[発行の取り消し](/dotnet/api/System.Management.Automation.VerbsData.Unpublish)(ub)|他のユーザーがリソースを使用できないようにします。 この動詞はとペア`Publish`になっています。|この操作では、[アンインストール]、[元に戻す]、[非表示] などの動詞は使用しないでください。|
|[更新](/dotnet/api/System.Management.Automation.VerbsData.Update)(ud)|状態、精度、準拠、またはコンプライアンスを維持するために、リソースを最新の状態にします。 たとえば、コマンドレット`Update-FormatData`は、現在の PowerShell コンソールに更新し、フォーマットファイルを追加します。|このアクションでは、更新、更新、再計算、インデックスの再作成などの動詞は使用しないでください。|

## <a name="diagnostic-verbs"></a>診断動詞

PowerShell では、 [VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)クラスを使用して、診断に適用されるアクションを定義します。 次の表は、定義されている動詞の大部分を示しています。

|動詞 (エイリアス)|アクション|説明|
|--------------------|------------|--------------|
|[デバッグ](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Debug)(db)|リソースを調べて、運用上の問題を診断します。|このアクションでは、診断などの動詞を使用しないでください。|
|[メジャー](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Measure) (ミリ秒)|指定された操作によって使用されるリソースを識別するか、リソースに関する統計情報を取得します。|このアクションでは、計算、決定、分析などの動詞は使用しないでください。|
|[Ping](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Ping) (pi)|`Test`動詞を使用します。||
|[修復](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Repair)(rp)|リソースを使用可能な状態に復元します。|この操作では、修正や復元などの動詞は使用しないでください。|
|[解決](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Resolve)(rv)|リソースの簡略表現をより完全な表現にマップします。|この操作では、展開や決定などの動詞は使用しないでください。|
|[テスト](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Test)(t)|リソースの操作または一貫性を検証します。|このアクションでは、診断、分析、回復、検証などの動詞は使用しないでください。|
|[トレース](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Trace)(tr)|リソースのアクティビティを追跡します。|このアクションでは、追跡、フォロー、検査、詳細などの動詞は使用しないでください。|

## <a name="lifecycle-verbs"></a>ライフサイクル動詞

PowerShell では、 [VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)クラスを使用して、リソースのライフサイクルに適用されるアクションを定義します。 次の表は、定義されている動詞の大部分を示しています。

|動詞 (エイリアス)|アクション|説明|
|--------------------|------------|--------------|
|[承認](/dotnet/api/System.Management.Automation.VerbsLifecycle.Approve)(ap)|リソースまたはプロセスの状態を確認または同意します。||
|[Assert](/dotnet/api/System.Management.Automation.VerbsLifecycle.Assert) (as)|リソースの状態をものします。|このアクションでは、証明などの動詞を使用しないでください。|
|[ビルド](/dotnet/api/System.Management.Automation.VerbsLifecycle.Build)(bd)|一部の入力ファイル (通常はソースコードまたは宣言ドキュメント) から成果物 (通常はバイナリまたはドキュメント) を作成します。|この動詞は PowerShell v6 で追加されました|
|[完了](/dotnet/api/system.management.automation.host.buffercelltype?view=powershellsdk-1.1.0)(cp)|操作を終了します。||
|[確認](/dotnet/api/System.Management.Automation.VerbsLifecycle.Confirm)(cn)|リソースまたはプロセスの状態を確認、検証、または検証します。|このアクションでは、承認、同意、認定、検証、検証などの動詞は使用しないでください。|
|[拒否](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deny)(dn)|リソースまたはプロセスの状態を拒否、オブジェクト、ブロック、または opposes します。|このアクションでは、Block、Object、拒否、または Reject などの動詞は使用しないでください。|
|[展開](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deploy)(dp)|配置の完了後にそのソリューションのコンシューマーがアクセスできるように、アプリケーション、web サイト、またはソリューションをリモートターゲット [s] に送信します。|この動詞は PowerShell v6 で追加されました|
|[無効化](/dotnet/api/System.Management.Automation.VerbsLifecycle.Disable)(d)|リソースを使用不可または非アクティブの状態に構成します。 たとえば、 `Disable-PSBreakpoint`コマンドレットを使用すると、ブレークポイントが非アクティブになります。 この動詞はとペア`Enable`になっています。|このアクションでは、Halt や Hide などの動詞は使用しないでください。|
|[有効化](/dotnet/api/System.Management.Automation.VerbsLifecycle.Enable)(e)|リソースを使用可能またはアクティブ状態に構成します。 たとえば、 `Enable-PSBreakpoint`コマンドレットを使用すると、ブレークポイントがアクティブになります。 この動詞はとペア`Disable`になっています。|このアクションでは、Start や Begin などの動詞は使用しないでください。|
|[Install](/dotnet/api/System.Management.Automation.VerbsLifecycle.Install) (is)|リソースを場所に配置し、必要に応じて初期化します。 この動詞はとペア`Uninstall`になっています。|この操作では、セットアップなどの動詞を使用しないでください。|
|[Invoke](/dotnet/api/System.Management.Automation.VerbsLifecycle.Invoke) (i)|コマンドまたはメソッドの実行などのアクションを実行します。|このアクションでは、Run や Start などの動詞は使用しないでください。|
|[登録](/dotnet/api/System.Management.Automation.VerbsLifecycle.Register)(rg)|データベースなどのリポジトリにリソースのエントリを作成します。 この動詞はとペア`Unregister`になっています。||
|[要求](/dotnet/api/System.Management.Automation.VerbsLifecycle.Request)(rq)|リソースを要求するか、アクセス許可を要求します。||
|[再起動](/dotnet/api/System.Management.Automation.VerbsLifecycle.Restart)(rt)|操作を停止し、再び開始します。 たとえば、コマンドレット`Restart-Service`はサービスを停止してから開始します。|このアクションでは、[リサイクル] などの動詞は使用しないでください。|
|[再開](/dotnet/api/System.Management.Automation.VerbsLifecycle.Resume)(ru)|中断された操作を開始します。 たとえば、コマンドレット`Resume-Service`は中断されたサービスを開始します。 この動詞はとペア`Suspend`になっています。||
|[開始](/dotnet/api/System.Management.Automation.VerbsLifecycle.Start)(sa)|操作を開始します。 たとえば、コマンドレット`Start-Service`はサービスを開始します。 この動詞はとペア`Stop`になっています。|この操作では、起動、開始、ブートなどの動詞は使用しないでください。|
|[停止](/dotnet/api/System.Management.Automation.VerbsLifecycle.Stop)(sp)|アクティビティを中断します。 この動詞はとペア`Start`になっています。|この操作では、End、Kill、Terminate、Cancel などの動詞は使用しないでください。|
|[送信](/dotnet/api/System.Management.Automation.VerbsLifecycle.Submit)(sb)|承認のためにリソースを提示します。|このアクションでは、Post などの動詞を使用しないでください。|
|[中断](/dotnet/api/System.Management.Automation.VerbsLifecycle.Suspend)(ss)|アクティビティを一時停止します。 たとえば、コマンドレット`Suspend-Service`はサービスを一時停止します。 この動詞はとペア`Resume`になっています。|このアクションでは、[一時停止] などの動詞は使用しないでください。|
|[アンインストール](/dotnet/api/System.Management.Automation.VerbsLifecycle.Uninstall)(us)|指定された場所からリソースを削除します。 この動詞はとペア`Install`になっています。||
|[登録解除](/dotnet/api/System.Management.Automation.VerbsLifecycle.Unregister)(お客様)|リポジトリからリソースのエントリを削除します。 この動詞はとペア`Register`になっています。|このアクションでは、[削除] などの動詞を使用しないでください。|
|[待機](/dotnet/api/System.Management.Automation.VerbsLifecycle.Wait)(w)|指定されたイベントが発生するまで、操作を一時停止します。 たとえば、コマンドレット`Wait-Job`は、1つ以上のバックグラウンドジョブが完了するまで操作を一時停止します。|この操作では、スリープや一時停止などの動詞は使用しないでください。|

## <a name="security-verbs"></a>セキュリティ動詞

PowerShell では、 [VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)クラスを使用して、セキュリティに適用されるアクションを定義します。 次の表は、定義されている動詞の大部分を示しています。

|動詞 (エイリアス)|アクション|説明|
|--------------------|------------|--------------|
|[ブロック](/dotnet/api/System.Management.Automation.VerbsSecurity.Block)(bl)|リソースへのアクセスを制限します。 この動詞はとペア`Unblock`になっています。|このアクションでは、禁止、制限、拒否などの動詞は使用しないでください。|
|[Grant](/dotnet/api/System.Management.Automation.VerbsSecurity.Grant) (gr)|リソースへのアクセスを許可します。 この動詞はとペア`Revoke`になっています。|このアクションでは、許可や有効化などの動詞は使用しないでください。|
|[保護](/dotnet/api/System.Management.Automation.VerbsSecurity.Protect)(pt)|リソースを攻撃や損失から保護します。 この動詞はとペア`Unprotect`になっています。|この操作では、暗号化、保護、封印などの動詞は使用しないでください。|
|[Revoke](/dotnet/api/System.Management.Automation.VerbsSecurity.Revoke) (rk)|リソースへのアクセスを許可しないアクションを指定します。 この動詞はとペア`Grant`になっています。|このアクションでは、Remove や Disable などの動詞は使用しないでください。|
|[ブロック解除](/dotnet/api/System.Management.Automation.VerbsSecurity.Unblock)(ul)|リソースに対する制限を削除します。 この動詞はとペア`Block`になっています。|このアクションでは、Clear や Allow などの動詞は使用しないでください。|
|[保護解除](/dotnet/api/System.Management.Automation.VerbsSecurity.Unprotect)(上)|攻撃や損失を防ぐために追加されたリソースから保護を削除します。 この動詞はとペア`Protect`になっています。|このアクションでは、暗号化解除や封印などの動詞は使用しないでください。|

## <a name="other-verbs"></a>その他の動詞

PowerShell では、 [VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)クラスを使用して、共通、通信、データ、ライフサイクル、セキュリティ動詞名の各動詞など、特定の動詞名カテゴリに適合しない正規の動詞名を定義します。

|動詞 (エイリアス)|アクション|説明|
|--------------------|------------|--------------|
|(U)[を使用する](/dotnet/api/System.Management.Automation.VerbsOther.Use)|を使用するか、リソースを使用して何らかの処理を行います。||

## <a name="see-also"></a>関連項目

[VerbsCommon (システム管理)](/dotnet/api/System.Management.Automation.VerbsCommon)

[VerbsCommunications (システム管理)](/dotnet/api/System.Management.Automation.VerbsCommunications)

[VerbsData (システム管理)](/dotnet/api/System.Management.Automation.VerbsData)

[VerbsDiagnostic (システム管理)](/dotnet/api/System.Management.Automation.VerbsDiagnostic)

[VerbsLifeCycle (システム管理)](/dotnet/api/System.Management.Automation.VerbsLifeCycle)

[VerbsSecurity (システム管理)](/dotnet/api/System.Management.Automation.VerbsSecurity)

[VerbsOther (システム管理)](/dotnet/api/System.Management.Automation.VerbsOther)

[コマンドレットの宣言](./cmdlet-class-declaration.md)

[Windows PowerShell プログラマー ガイド](../prog-guide/windows-powershell-programmer-s-guide.md)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
