---
title: 承認済みの PowerShell コマンドの動詞 |Microsoft Docs
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
ms.openlocfilehash: 4475b3f5e15826efbe8bab867011985cd7e2e1ae
ms.sourcegitcommit: 806cf87488b80800b9f50a8af286e8379519a034
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2019
ms.locfileid: "59293352"
---
# <a name="approved-verbs-for-powershell-commands"></a>PowerShell コマンドの承認された動詞

PowerShell は、コマンドレットの名前とその派生の Microsoft .NET Framework クラスの動詞-名詞形式のペアを使用します。
たとえば、 `Get-Command` PowerShell によって提供されるコマンドレットを使用して、PowerShell に登録されているすべてのコマンドを取得します。
名前の動詞部分は、コマンドレットを実行するアクションを識別します。
名前の名詞の部分は、アクションが実行されるエンティティを識別します。

> [!NOTE]
> PowerShell は、用語を使用して*動詞*その単語が英語での標準的な動詞ではない場合でも、アクションのことを意味する単語を記述します。
> 用語など*新規*有効な PowerShell の動詞名は、動詞を英語でない場合でも、アクションを意味します。

## <a name="verb-naming-rules"></a>動詞の名前付け規則

コマンドレット名の動詞を選択するときに考慮するためのガイドラインを次に示します。

* PowerShell によって提供される定義済みの動詞名のいずれかを使用することをお勧め、動詞を指定すると (次の表に含まれている定義済みの動詞はこれらの別名)。
  定義済みの動詞を使用する場合を作成するコマンドレット、PowerShell、によって提供されるコマンドレットおよび他のユーザーができるように設計されたコマンドレットとの間の一貫性を確保します。

* 定義済みの動詞を使用して、アクションの一般的なスコープを記述して、コマンドレットのアクションをさらに改良するパラメータを使用します。

* コマンドレット間で一貫性を強制するには、承認された動詞のシノニムを使用しないでください。

* このトピックに記載されている動詞はそれぞれの形式のみを使用します。
  たとえば、"Get"を使用しますが、「取得」または「取得」を使用しないでください。

* Pascal 形式を使用して、動詞の大文字小文字の区別します。
  Pascal 形式で各単語の最初の文字を大文字と小文字が大文字に、"ForEach"など。

* 次の予約済み動詞またはエイリアスは使用しないでください。
  これらの動詞は、PowerShell 言語で、または PowerShell によって提供される、特殊なケース コマンドレットによって使用されます。
  - ForEach (foreach)
  - 形式 (f)
  - グループ (gp)
  - 並べ替え (sr)
  - Tee (te)
  - 場所 (値を下回った場合)

## <a name="similar-verbs-for-different-actions"></a>ようなさまざまなアクション動詞

次のような動詞は、さまざまなアクションを表します。

### <a name="new-vs-set"></a>新しい vs します。設定
`New`動詞は、新しいリソースの作成に使用されます。
`Set`動詞を使用して、それが存在しない場合、よう必要に応じて、リソースの作成、既存のリソースを変更する、`Set-Variable`コマンドレット。

### <a name="find-vs-search"></a>Vs を検索します。検索
`Find`オブジェクトの検索に動詞を使用します。
`Search`でコンテナー リソースへの参照を作成する動詞が使用されます。

### <a name="get-vs-read"></a>Vs を取得します。読み取り
`Get`動詞を使用して、ファイルなどのリソースを取得します。
`Read`ファイルなどのソースから情報を取得する動詞が使用されます。

### <a name="invoke-vs-start"></a>Vs を起動します。管理者として
`Invoke`操作は、通常のコマンドを実行するなどの同期操作を実行する動詞が使用されます。
`Start`操作は、通常のプロセスを開始するなど、非同期操作を開始する動詞が使用されます。

### <a name="ping-vs-test"></a>Ping vs します。Server1
使用して、`Test`動詞。

## <a name="common-verbs"></a>一般的な動詞

PowerShell を使用して、 [System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)ほとんどのコマンドレットに適用できる一般的なアクションを定義するクラスを列挙します。
次の表では、ほとんど定義されている動詞の一覧表示します。

|動詞 (エイリアス)|操作|備考|
|--------------------|------------|--------------|
|[追加](/dotnet/api/System.Management.Automation.VerbsCommon.Add)(a)|コンテナーにリソースを追加します。 または、項目を別の項目にアタッチします。 たとえば、`Add-Content`コマンドレットは、ファイルにコンテンツを追加します。 この動詞を組み合わせて`Remove`します。|このアクションでは、Append、Attach、連結などの動詞を使用して、挿入または行わないでください。|
|[クリア](/dotnet/api/System.Management.Automation.VerbsCommon.Clear)(cl)|コンテナーからすべてのリソースを削除しますが、コンテナーは削除されません。 たとえば、`Clear-Content`コマンドレットでは、ファイルの内容を削除しますが、ファイルは削除されません。|このアクションでは、フラッシュ、消去、リリース、マークの解除、設定を解除、または 無効化などの動詞を使用しないでください。|
|[閉じる](/dotnet/api/System.Management.Automation.VerbsCommon.Close)(cs)|アクセスできない、使用不可能、または使用できないようにするリソースの状態を変更します。 この動詞を組み合わせる `Open.`||
|[コピー](/dotnet/api/System.Management.Automation.VerbsCommon.Copy) (cp)|別の名前に、または別のコンテナーには、リソースをコピーします。 たとえば、`Copy-Item`格納されたデータにアクセスするために使用するコマンドレットは、データ ストア内の 1 つの場所から項目を別の場所にコピーします。|この操作によって、複製、複製、レプリケーション、または同期などの動詞を使用しないでください。|
|[入力](/dotnet/api/System.Management.Automation.VerbsCommon.Enter)(英語)|ユーザーがリソースに移動できるアクションを指定します。 たとえば、`Enter-PSSession`コマンドレットは、対話型セッションでユーザーを配置します。 この動詞を組み合わせて`Exit`します。|この操作によって、またはプッシュなどの動詞を使用しないでください。|
|[終了](/dotnet/api/System.Management.Automation.VerbsCommon.Exit)(ex)|最近使用したコンテキストに現在の環境またはコンテキストを設定します。 たとえば、`Exit-PSSession`コマンドレットは、対話型セッションを開始するために使用されたセッションでユーザーを配置します。 この動詞を組み合わせて`Enter`します。|このアクションでは、Pop など Out 動詞を使用しないでください。|
|[検索](/dotnet/api/System.Management.Automation.VerbsCommon.Find)(fd)|不明な黙示的、省略可能なまたは指定したコンテナー内のオブジェクトを検索します。||
|[形式](/dotnet/api/System.Management.Automation.VerbsCommon.Format)(f)|指定されたフォームまたはレイアウト内のオブジェクトを整列します。||
|[取得](/dotnet/api/System.Management.Automation.VerbsCommon.Get)(g)|リソースを取得するアクションを指定します。 この動詞を組み合わせて`Set`します。|このアクションでは、読み取り、オープン、Cat、型、Dir、取得、ダンプ、取得、調査、検索、または検索などの動詞を使用しないでください。|
|[非表示に](/dotnet/api/System.Management.Automation.VerbsCommon.Hide)(h)|検出できないリソースを使用します。 など、コマンドレットを非表示の動詞を含む名前は、ユーザーからサービスを非表示可能性があります。 この動詞を組み合わせて`Show`します。|このアクションでは、ブロックなどの動詞を使用しないでください。|
|[参加](/dotnet/api/System.Management.Automation.VerbsCommon.Join)(j)|1 つのリソースには、リソースを結合します。 たとえば、`Join-Path`コマンドレットは、1 つのパスを作成するには、その子パスのいずれかのパスを結合します。 この動詞を組み合わせて`Split`します。|このアクションでは、結合、Unite、Connect、あるいは関連付けなどの動詞を使用しないでください。|
|[ロック](/dotnet/api/System.Management.Automation.VerbsCommon.Lock)(lk)|リソースをセキュリティで保護します。 この動詞を組み合わせて`Unlock`します。|このアクションでは、制限や保護などの動詞を使用しないでください。|
|[移動](/dotnet/api/System.Management.Automation.VerbsCommon.Move)(m)|1 つの場所からリソースを移動します。 たとえば、`Move-Item`コマンドレットは、別の場所にデータ ストア内の 1 つの場所から項目を移動します。|このアクションでは、転送、名、または移行などの動詞を使用しないでください。|
|[新しい](/dotnet/api/System.Management.Automation.VerbsCommon.New)(n)|リソースを作成します。 (、`Set`動詞などのデータが含まれるリソースを作成する場合にも使用できます、`Set-Variable`コマンドレットです)。|このアクションでは、作成、生成、ビルド、Make、または割り当てなどの動詞を使用しないでください。|
|[開いている](/dotnet/api/System.Management.Automation.VerbsCommon.Open)(op)|アクセスできる、使用可能なまたは使用可能なリソースの状態を変更します。 この動詞を組み合わせて`Close`します。||
|[最適化](/dotnet/api/System.Management.Automation.VerbsCommon.Optimize)(om)|リソースの有効性が向上します。||
|[Pop](/dotnet/api/System.Management.Automation.VerbsCommon.Pop) (pop)|スタックの一番上から項目を削除します。 たとえば、`Pop-Location`コマンドレットは、スタックにプッシュされた最後の場所に現在の場所を変更します。||
|[プッシュ](/dotnet/api/System.Management.Automation.VerbsCommon.Push)(pu)|スタックの一番上に項目を追加します。 たとえば、`Push-Location`コマンドレットは、スタックには、現在の場所をプッシュします。||
|[やり直し](/dotnet/api/System.Management.Automation.VerbsCommon.Redo)(re)|リソースを取り消された状態にリセットします。||
|[削除](/dotnet/api/System.Management.Automation.VerbsCommon.Remove)(r)|コンテナーからリソースを削除します。 たとえば、`Remove-Variable`コマンドレット、変数とその値を削除します。 この動詞を組み合わせて`Add`します。|このアクションでは、明確にこのような動詞を使用して、切り取り、Dispose、破棄、およびはありませんを消去します。|
|[名前を変更](/dotnet/api/System.Management.Automation.VerbsCommon.Rename)(rn)|リソースの名前を変更します。 たとえば、`Rename-Item`の格納されているデータへのアクセスに使用されているコマンドレットは、データ ストア内の項目の名前を変更します。|このアクションでは、変更などの動詞を使用しないでください。|
|[リセット](/dotnet/api/System.Management.Automation.VerbsCommon.Reset)(rs)|リソースを元の状態に設定します。||
|[検索](/dotnet/api/System.Management.Automation.VerbsCommon.Search)(sr)|コンテナー内のリソースへの参照を作成します。|このアクションでは、検索や検索などの動詞を使用しないでください。|
|[選択](/dotnet/api/System.Management.Automation.VerbsCommon.Select)(sc)|コンテナー内のリソースを検索します。 たとえば、`Select-String`コマンドレットは、文字列とファイルのテキストを検索します。|このアクションでは、検索や検索などの動詞を使用しないでください。|
|[設定](/dotnet/api/System.Management.Automation.VerbsCommon.Set)(s)|既存のリソースにデータを置き換えるか、一部のデータを含むリソースを作成します。 たとえば、`Set-Date`コマンドレットは、ローカル コンピューター上のシステム時刻を変更します。 (、`New`動詞がリソースを作成することもできます)。この動詞を組み合わせて`Get`します。|このアクションでは、書き込み、リセット、割り当て、または構成などの動詞を使用しないでください。|
|[表示](/dotnet/api/System.Management.Automation.VerbsCommon.Show)(sh)|リソースは、ユーザーに表示します。 この動詞を組み合わせて`Hide`します。|このアクションでは、表示や生成などの動詞を使用しないでください。|
|[Skip](/dotnet/api/System.Management.Automation.VerbsCommon.Skip) (sk)|1 つまたは複数のリソースまたはシーケンス内のポイントがバイパスされます。|このアクションでは、バイパスやジャンプなどの動詞を使用しないでください。|
|[分割](/dotnet/api/System.Management.Automation.VerbsCommon.Split)(sl)|リソースの部分を分離します。 たとえば、`Split-Path`コマンドレットは、パスのさまざまな部分を返します。 この動詞を組み合わせて`Join`します。|このアクションで使用しないでください、動詞をこのような個別をします。|
|[手順](/dotnet/api/System.Management.Automation.VerbsCommon.Step)(st)|次の点またはシーケンス内のリソースに移動します。||
|[スイッチ](/dotnet/api/System.Management.Automation.VerbsCommon.Switch)(sw)|2 つの場所、責任、または状態間を変更するように、2 つのリソース間代替アクションを指定します。||
|[元に戻す](/dotnet/api/System.Management.Automation.VerbsCommon.Undo)(un)|リソースを以前の状態に設定します。||
|[ロックを解除](/dotnet/api/System.Management.Automation.VerbsCommon.Unlock)(英国)|ロックされたリソースを解放します。 この動詞を組み合わせて`Lock`します。|このアクションでは、リリース、Unrestrict、またはセキュリティ保護なしなどの動詞を使用しないでください。|
|[ウォッチ](/dotnet/api/System.Management.Automation.VerbsCommon.Watch)(wc)|継続的に検査または変更のリソースを監視します。||

## <a name="communications-verbs"></a>通信の動詞

PowerShell を使用して、 [System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)通信に適用されるアクションを定義するクラス。
次の表では、ほとんど定義されている動詞の一覧表示します。

|動詞 (エイリアス)|操作|備考|
|--------------------|------------|--------------|
|[接続](/dotnet/api/System.Management.Automation.VerbsCommunications.Connect)(cc)|ソースと変換先の間のリンクを作成します。 この動詞を組み合わせて`Disconnect`します。|このアクションでは、結合や Telnet などの動詞を使用しないでください。|
|[切断](/dotnet/api/System.Management.Automation.VerbsCommunications.Disconnect)(dc)|ソースと変換先の間のリンクを解除します。 この動詞を組み合わせて`Connect`します。|このアクションでは、中断やログオフなどの動詞を使用しないでください。|
|[読み取り](/dotnet/api/System.Management.Automation.VerbsCommunications.Read)(rd)|ソースからの情報を取得します。 この動詞を組み合わせて`Write`します。|このアクションでは、プロンプトでは、取得などの動詞を使用およびありませんを取得します。|
|[受信](/dotnet/api/System.Management.Automation.VerbsCommunications.Receive)(rc)|ソースから送信される情報を受け取ります。 この動詞を組み合わせて`Send`します。|このアクションでは、使用読み、同意などの動詞またはピーク。|
|[送信](/dotnet/api/System.Management.Automation.VerbsCommunications.Send)(sd)|先の情報を提供します。 この動詞を組み合わせて`Receive`します。|このアクションでは、Put、ブロードキャスト、メール、Fax などの動詞を使用しないでください。|
|[書き込み](/dotnet/api/System.Management.Automation.VerbsCommunications.Write)(wr)|ターゲットの情報を追加します。 この動詞を組み合わせて`Read`します。|このアクションでは、Put、または印刷などの動詞を使用しないでください。|

## <a name="data-verbs"></a>データの動詞

PowerShell を使用して、 [System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData)データ処理に適用されるアクションを定義するクラス。
次の表では、ほとんど定義されている動詞の一覧表示します。

|動詞名 (エイリアス)|操作|備考|
|-------------------------|------------|--------------|
|[バックアップ](/dotnet/api/System.Management.Automation.VerbsData.Backup)(ba)|複製することにより、データを格納します。|このアクションでは、保存、Burn、複製、または同期などの動詞を使用しないでください。|
|[チェックポイント](/dotnet/api/System.Management.Automation.VerbsData.Checkpoint)(ch)|データの場合、またはその構成の現在の状態のスナップショットを作成します。|このアクションは使用しないでください相違などの動詞|
|[比較](/dotnet/api/System.Management.Automation.VerbsData.Compare)(cr)|別のリソースからのデータに対して 1 つのリソースからデータを評価します。|このアクションは使用しないでください相違などの動詞|
|[圧縮](/dotnet/api/System.Management.Automation.VerbsData.Compress)(cm)|リソースのデータが圧縮されます。 ペアリング`Expand`します。|このアクションでは、最適化など、動詞を使用しないでください。|
|[変換](/dotnet/api/System.Management.Automation.VerbsData.Convert)(cv)|コマンドレットは、双方向の変換をサポートしている場合、または、コマンドレットは、複数のデータ型間の変換をサポートしている場合に別に 1 つの表現からのデータを変更します。|このアクションでは、使用の変更、サイズ変更などの動詞または Resample。|
|[ConvertFrom](/dotnet/api/System.Management.Automation.VerbsData.ConvertFrom) (cf)|1 つまたは複数のサポートされている出力の種類 (コマンドレットの名詞は、入力を示します) 入力の 1 つの主要な型に変換します。|このアクションでは、エクスポート、出力、またはアウトなどの動詞を使用しないでください。|
|[ConvertTo](/dotnet/api/System.Management.Automation.VerbsData.ConvertTo) (ct)|(コマンドレットの名詞は、出力の種類を示します) のプライマリ出力の型への入力の 1 つまたは複数の型から変換します。|このアクションを使用しないで、インポートなどの動詞入力、または。|
|[マウント解除](/dotnet/api/System.Management.Automation.VerbsData.Dismount)(dm)|名前付きの場所からエンティティをデタッチします。 この動詞を組み合わせて`Mount`します。|このアクションでは、マウント解除またはリンク解除などの動詞を使用しないでください。|
|[編集](/dotnet/api/System.Management.Automation.VerbsData.Edit)(ed)|追加またはコンテンツを削除して、既存のデータを変更します。|このアクションでは、変更、更新、または変更などの動詞を使用しないでください。|
|[展開](/dotnet/api/System.Management.Automation.VerbsData.Expand)(en)|圧縮されたリソースのデータを元の状態に復元します。 この動詞を組み合わせて`Compress`します。|このアクションでは、分解または圧縮解除などの動詞を使用しないでください。|
|[エクスポート](/dotnet/api/System.Management.Automation.VerbsData.Export)(ep)|または、インターチェンジの形式に、ファイルなどの永続的なデータ ストアには、主な入力をカプセル化します。 この動詞を組み合わせて`Import`します。|このアクションでは、抽出やバックアップなどの動詞を使用しないでください。|
|[グループ](/dotnet/api/System.Management.Automation.VerbsData.Group)(gp)|配置するか、または 1 つまたは複数のリソースを関連付けます。|このアクションでは、集計、並べ替え、関連付けなどの動詞を使用して、およびはありませんを関連付けます。|
|[インポート](/dotnet/api/System.Management.Automation.VerbsData.Import)(ip)|(ファイル) などの永続的なデータ ストアまたはインターチェンジの形式で格納されているデータからリソースを作成します。 たとえば、`Import-CSV`コマンドレットは、他のコマンドレットで使用できるオブジェクトをコンマ区切り値 (CSV) ファイルからデータをインポートします。 この動詞を組み合わせて`Export`します。|このアクションでは、一括読み込みまたは負荷などの動詞を使用しないでください。|
|[初期化](/dotnet/api/System.Management.Automation.VerbsData.Initialize)(in)|使用して、リソースを準備し、既定の状態に設定します。|このアクションでは、消去、Init、更新、再構築、再初期化、またはセットアップなどの動詞を使用しないでください。|
|[制限](/dotnet/api/System.Management.Automation.VerbsData.Limit)(l)|リソースに制約を適用します。|このアクションでは、クォータなどの動詞を使用しないでください。|
|[マージ](/dotnet/api/System.Management.Automation.VerbsData.Merge)(mg)|複数のリソースから 1 つのリソースを作成します。|このアクションでは、結合または結合などの動詞を使用しないでください。|
|[マウント](/dotnet/api/System.Management.Automation.VerbsData.Mount)(mt)|場所には、名前付きエンティティをアタッチします。 この動詞を組み合わせて`Dismount`します。|このアクションでは、動詞の接続を使用しないでください。|
|[Out](/dotnet/api/System.Management.Automation.VerbsData.Out) (o)|環境からデータを送信します。 たとえば、`Out-Printer`コマンドレットは、プリンターにデータを送信します。||
|[発行](/dotnet/api/System.Management.Automation.VerbsData.Publish)(pb)|他のユーザーにリソースを使用可能です。 この動詞を組み合わせて`Unpublish`します。|このアクションでは、展開、リリースなどの動詞を使用して、およびはありませんインストール。|
|[復元](/dotnet/api/System.Management.Automation.VerbsData.Restore)(rr)|設定される状態などの定義済みの状態をリソースに設定`Checkpoint`します。 たとえば、`Restore-Computer`コマンドレットは、ローカル コンピューターのシステムの復元を開始します。|このアクションでは、修復、返された場合、元に戻す、または修正プログラムなどの動詞を使用しないでください。|
|[保存](/dotnet/api/System.Management.Automation.VerbsData.Save)(sv)|損失を回避するためにデータを保持します。||
|[同期](/dotnet/api/System.Management.Automation.VerbsData.Sync)(sy)|2 つ以上のリソースが同じ状態のことを保証します。|このアクションでは、Replicate の場合、強制などの動詞を使用して、およびありませんと一致。|
|[発行の取り消し](/dotnet/api/System.Management.Automation.VerbsData.Unpublish)(ub)|リソースは、他のユーザーにできなくなります。 この動詞を組み合わせて`Publish`します。|このアクションでは、アンインストールを元に戻すなどの動詞を使用して、およびはありません非表示にします。|
|[Update](/dotnet/api/System.Management.Automation.VerbsData.Update) (ud)|リソースの状態、精度への準拠、またはコンプライアンスを維持するために最新の状態が表示されます。 たとえば、`Update-FormatData`コマンドレットを更新し、現在の PowerShell コンソールに書式設定ファイルを追加します。|このアクションでは、更新、更新、再計算などの動詞を使用して、およびありませんインデックスを再作成。|

## <a name="diagnostic-verbs"></a>診断の動詞

PowerShell を使用して、 [System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)診断に適用されるアクションを定義するクラス。
次の表では、ほとんど定義されている動詞の一覧表示します。

|動詞 (エイリアス)|操作|備考|
|--------------------|------------|--------------|
|[デバッグ](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Debug)(db)|運用上の問題を診断するリソースを調べます。|このアクションでは、診断などの動詞を使用しないでください。|
|[メジャー](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Measure) (ミリ秒)|指定された演算によって消費されるリソースまたはリソースに関する統計情報を取得します。|このアクションでは、Calculate、決定する、または分析などの動詞を使用しないでください。|
|[Ping](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Ping) (pi)|使用して、`Test`動詞。||
|[修復](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Repair)(rp)|リソースを使用可能な状態に復元します。|このアクションでは、修正プログラムや復元などの動詞を使用しないでください。|
|[解決](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Resolve)(rv)|リソースの省略表現をより完全な表現にマップします。|このアクションでは、展開または決定するなどの動詞を使用しないでください。|
|[テスト](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Test)(t)|操作またはリソースの整合性を確認します。|このアクションでは、診断、分析、復旧、または検証などの動詞を使用しないでください。|
|[トレース](/dotnet/api/System.Management.Automation.VerbsDiagnostic.Trace)(tr)|リソースのアクティビティを追跡します。|このアクションでは、追跡、フォロー、検査などの動詞を使用して、およびはありません学習。|

## <a name="lifecycle-verbs"></a>動詞のライフ サイクル

PowerShell を使用して、 [System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)リソースのライフ サイクルに適用されるアクションを定義するクラス。
次の表では、ほとんど定義されている動詞の一覧表示します。

|動詞 (エイリアス)|操作|備考|
|--------------------|------------|--------------|
|[承認](/dotnet/api/System.Management.Automation.VerbsLifecycle.Approve)(ap)|確認します。 または、リソースやプロセスの状態にすることに同意します。||
|[アサート](/dotnet/api/System.Management.Automation.VerbsLifecycle.Assert)(として)|リソースの状態ものとみなされます。|このアクションでは、Certify などの動詞を使用しないでください。|
|[ビルド](/dotnet/api/System.Management.Automation.VerbsLifecycle.Build)(bd)|入力ファイル (通常はソース コードまたは宣言型のドキュメント) の中からいくつか成果物 (通常はバイナリまたはドキュメント) を作成します。|この動詞は、PowerShell v6 で追加されました|
|[完全な](/dotnet/api/system.management.automation.host.buffercelltype?view=powershellsdk-1.1.0)(cp)|操作は終了です。||
|[確認](/dotnet/api/System.Management.Automation.VerbsLifecycle.Confirm)(cn)|確認、検証、またはリソースやプロセスの状態を検証します。|このアクションでは、確認、同意、Certify、検証、または確認などの動詞を使用しないでください。|
|[拒否](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deny)(dn)|拒否、オブジェクト、ブロック、またはリソースやプロセスの状態に反すます。|このアクションではないブロック、オブジェクト、拒否するなどの動詞を使用して、または拒否します。|
|[デプロイ](/dotnet/api/System.Management.Automation.VerbsLifecycle.Deploy)(dp)|アプリケーション、web サイト、またはソリューションをそのソリューションのコンシューマーにアクセスできること、デプロイが完了したらこのような方法で [s] リモート ターゲットに送信します|この動詞は、PowerShell v6 で追加されました|
|[無効にする](/dotnet/api/System.Management.Automation.VerbsLifecycle.Disable)(d)|リソースが利用できない、または非アクティブな状態を構成します。 たとえば、`Disable-PSBreakpoint`コマンドレットにより、ブレークポイントがアクティブでないです。 この動詞を組み合わせて`Enable`します。|このアクションでは、停止、または非表示にするなどの動詞を使用しないでください。|
|[有効にする](/dotnet/api/System.Management.Automation.VerbsLifecycle.Enable)(e)|使用可能なまたはアクティブな状態にリソースを構成します。 たとえば、`Enable-PSBreakpoint`コマンドレットにより、ブレークポイントがアクティブです。 この動詞を組み合わせて`Disable`します。|このアクションでは、開始や開始などの動詞を使用しないでください。|
|[インストール](/dotnet/api/System.Management.Automation.VerbsLifecycle.Install)(です)|場所にリソースを配置し、必要に応じてそれを初期化します。 この動詞を組み合わせて`Uninstall`します。|このアクションでは、セットアップなど使用動詞ではない操作を実行します。|
|[呼び出す](/dotnet/api/System.Management.Automation.VerbsLifecycle.Invoke)(i)|コマンドまたはメソッドを実行しているなどの操作を実行します。|このアクションの実行や開始などの動詞を使用しないでください。|
|[登録](/dotnet/api/System.Management.Automation.VerbsLifecycle.Register)(rg)|データベースなどのリポジトリには、リソースのエントリを作成します。 この動詞を組み合わせて`Unregister`します。||
|[要求](/dotnet/api/System.Management.Automation.VerbsLifecycle.Request)(rq)|リソースを要求したり、アクセス許可を要求したりします。||
|[再起動](/dotnet/api/System.Management.Automation.VerbsLifecycle.Restart)(rt)|操作を停止し、もう一度開始します。 たとえば、`Restart-Service`コマンドレットを停止して、サービスを起動します。|このアクションでは、リサイクルなどの動詞を使用しないでください。|
|[再開](/dotnet/api/System.Management.Automation.VerbsLifecycle.Resume)(ru)|中断された操作を開始します。 たとえば、`Resume-Service`コマンドレットは、中断されたサービスを開始します。 この動詞を組み合わせて`Suspend`します。||
|[開始](/dotnet/api/System.Management.Automation.VerbsLifecycle.Start)(sa)|操作を開始します。 たとえば、`Start-Service`コマンドレットは、サービスを開始します。 この動詞を組み合わせて`Stop`します。|このアクションでは、起動、開始、またはブートなどの動詞を使用しないでください。|
|[停止](/dotnet/api/System.Management.Automation.VerbsLifecycle.Stop)(sp)|アクティビティを中断します。 この動詞を組み合わせて`Start`します。|このアクションでは、最後に、Kill、Terminate などの動詞を使用しておよびありませんキャンセル。|
|[送信](/dotnet/api/System.Management.Automation.VerbsLifecycle.Submit)(sb)|承認のためのリソースを表示します。|このアクションでは、Post などの動詞を使用しないでください。|
|[中断](/dotnet/api/System.Management.Automation.VerbsLifecycle.Suspend)(ss)|アクティビティを一時停止します。 たとえば、`Suspend-Service`コマンドレットは、サービスを一時停止します。 この動詞を組み合わせて`Resume`します。|このアクションでは、一時停止などの動詞を使用しないでください。|
|[アンインストール](/dotnet/api/System.Management.Automation.VerbsLifecycle.Uninstall)(米国)|指定された場所からリソースを削除します。 この動詞を組み合わせて`Install`します。||
|[登録を解除](/dotnet/api/System.Management.Automation.VerbsLifecycle.Unregister)(、)|リポジトリからリソースのエントリを削除します。 この動詞を組み合わせて`Register`します。|このアクションでは、削除などの動詞を使用しないでください。|
|[待機](/dotnet/api/System.Management.Automation.VerbsLifecycle.Wait)(w)|指定したイベントが発生するまでは、操作を一時停止します。 たとえば、`Wait-Job`コマンドレットは、1 つまでの操作を一時停止しますまたは、複数のバック グラウンド ジョブが完了します。|このアクションでは、スリープ状態または一時停止などの動詞を使用しないでください。|

## <a name="security-verbs"></a>セキュリティの動詞

PowerShell を使用して、 [System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)セキュリティに適用されるアクションを定義するクラス。
次の表では、ほとんど定義されている動詞の一覧表示します。

|動詞 (エイリアス)|操作|備考|
|--------------------|------------|--------------|
|[ブロック](/dotnet/api/System.Management.Automation.VerbsSecurity.Block)(bl)|リソースへのアクセスを制限します。 この動詞を組み合わせて`Unblock`します。|この処理をできないようにする、制限、または Deny などの動詞を使用しないでください。|
|[Grant](/dotnet/api/System.Management.Automation.VerbsSecurity.Grant) (gr)|リソースにアクセスをできます。 この動詞を組み合わせて`Revoke`します。|この操作を許可] または [有効にするなどの動詞を使用しないでください。|
|[保護](/dotnet/api/System.Management.Automation.VerbsSecurity.Protect)(pt)|リソース攻撃や損失から保護されます。 この動詞を組み合わせて`Unprotect`します。|このアクションでは、暗号化、保護、または封印などの動詞を使用しないでください。|
|[取り消す](/dotnet/api/System.Management.Automation.VerbsSecurity.Revoke)(rk)|リソースへのアクセスを許可しないアクションを指定します。 この動詞を組み合わせて`Grant`します。|このアクションでは、削除または無効にするなどの動詞を使用しないでください。|
|[ブロック解除](/dotnet/api/System.Management.Automation.VerbsSecurity.Unblock)(ul)|リソースへの制限を削除します。 この動詞を組み合わせて`Block`します。|このアクションでは、クリアまたは許可するなどの動詞を使用しないでください。|
|[保護の解除](/dotnet/api/System.Management.Automation.VerbsSecurity.Unprotect)(最大)|攻撃や損失からこれを防ぐために追加されたリソースからの保護を削除します。 この動詞を組み合わせて`Protect`します。|このアクションでは、復号化または Unseal などの動詞を使用しないでください。|

## <a name="other-verbs"></a>その他の動詞

PowerShell を使用して、 [System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)など、一般的な通信、データのライフ サイクルの特定の動詞名カテゴリに分類されない正規動詞名またはセキュリティ動詞名を定義するクラス動詞。

|動詞 (エイリアス)|操作|備考|
|--------------------|------------|--------------|
|[使用](/dotnet/api/System.Management.Automation.VerbsOther.Use)(u)|作業を行うリソースが含まれていますか。||

## <a name="see-also"></a>参照

[System.Management.Automation.VerbsCommon](/dotnet/api/System.Management.Automation.VerbsCommon)

[System.Management.Automation.VerbsCommunications](/dotnet/api/System.Management.Automation.VerbsCommunications)

[System.Management.Automation.VerbsData](/dotnet/api/System.Management.Automation.VerbsData)

[System.Management.Automation.VerbsDiagnostic](/dotnet/api/System.Management.Automation.VerbsDiagnostic)

[System.Management.Automation.VerbsLifeCycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle)

[System.Management.Automation.VerbsSecurity](/dotnet/api/System.Management.Automation.VerbsSecurity)

[System.Management.Automation.VerbsOther](/dotnet/api/System.Management.Automation.VerbsOther)

[コマンドレットの宣言](./cmdlet-class-declaration.md)

[Windows PowerShell プログラマー ガイド](../prog-guide/windows-powershell-programmer-s-guide.md)

[Windows PowerShell Shell SDK](../windows-powershell-reference.md)
