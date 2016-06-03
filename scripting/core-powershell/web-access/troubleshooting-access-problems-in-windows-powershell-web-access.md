#  Windows PowerShell Web Access でのアクセスに関する問題のトラブルシューティング

最終更新日 : 2013 年 6 月 24 日

適用対象: Windows Server 2012 R2、Windows Server 2012

<a href="" id="BKMK_trouble"></a>

------------------------------------------------------------------------

Windows PowerShell Web Access を使ったリモート コンピューターへの接続を試行する場合に発生する可能性がある一般的な問題と、問題解決のための推奨事項を次の表に示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>問題</p></th>
<th><p>考えられる原因と解決策</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>サインイン エラー</p></td>
<td><p>エラー発生の原因として以下が考えられます。</p>
<ul>
<li><p>コンピューターまたはリモート コンピューターの特定のセッション構成に対するユーザー アクセスを許可する承認規則が存在しない。 Windows PowerShell Web Access では制限的なセキュリティを採用しているため、承認規則を使ってリモート コンピューターへのアクセス権をユーザーに明示的に付与する必要があります。 承認規則の作成の詳細については、「<a href="https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx">Windows PowerShell Web Access の承認規則とセキュリティ機能</a>」を参照してください。</p></li>
<li><p>ユーザーによる対象コンピューターへのアクセスが承認されていない。 これはアクセス制御リスト (ACL) によって決定されます。 詳細については、「<a href="https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx">Web ベースの Windows PowerShell コンソールの使用</a>」の「Windows PowerShell Web Access へのサインイン」または <a href="https://msdn.microsoft.com/library/windows/desktop/ee706585.aspx">Windows PowerShell チームのブログを参照してください。</a>.</p>
<ul>
<li><p>Windows PowerShell のリモート管理が対象コンピューター上で有効になっていない。 ユーザーが接続しようとしているコンピューターでリモート管理が有効になっていることを確認してください。 詳細については、Windows PowerShell の About ヘルプ トピックの「<a href="https://technet.microsoft.com/library/dd315349.aspx">about_Remote_Requirements</a>」にある、「リモート処理用にコンピューターを構成する方法」を参照してください。</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td><p>ユーザーが Internet Explorer ウィンドウで Windows PowerShell Web Access にサインインしようとすると、<strong>[内部サーバー エラー]</strong> ページが表示されるか、Internet Explorer が応答しなくなる。 この問題は Internet Explorer に限られている。</p></td>
<td><p>この問題は、ユーザーがサインイン時に指定したドメイン名に漢字が含まれていた場合や、ゲートウェイ サーバー名に 1 つ以上の漢字が含まれている場合に発生します。 ユーザーがこの問題に対処するには、<a href="http://ie.microsoft.com/testdrive/info/downloads/Default.html">Internet Explorer 10 をインストールおよび実行</a>し、次の手順を行う必要があります。</p>
<ol>
<li><p>Internet Explorer の <strong>[ドキュメント モード]</strong> 設定を <strong>[IE10 標準] に変更します。</strong>.</p>
<ol>
<li><p><strong>F12</strong> キーを押して開発者ツール コンソールを開きます。</p></li>
<li><p>Internet Explorer 10 で、<strong>[ブラウザー モード]</strong> をクリックし、<strong>[Internet Explorer 10] をクリックします。</strong>.</p></li>
<li><p><strong>[ドキュメント モード]</strong>、<strong>[IE10 標準] の順にクリックします。</strong>.</p></li>
<li><p>もう一度 <strong>F12</strong> キーを押して開発者ツール コンソールを閉じます。</p></li>
</ol></li>
<li><p>自動プロキシ構成を無効にします。</p>
<ol>
<li><p>Internet Explorer 10 で、<strong>[ツール]</strong>、<strong>[インターネット オプション] の順にクリックします。</strong>.</p></li>
<li><p><strong>[インターネット オプション]</strong> ダイアログ ボックスの <strong>[接続]</strong> タブで、<strong>[LAN の設定] をクリックします。</strong>.</p></li>
<li><p><strong>[設定を自動的に検出する]</strong> チェック ボックスをオフにします。 <strong>[OK]</strong> をクリックし、もう一度 <strong>[OK]</strong> をクリックして、<strong>[インターネット オプション]</strong> ダイアログ ボックスを閉じます。</p></li>
</ol></li>
</ol></td>
</tr>
<tr class="odd">
<td><p>リモートのワークグループ コンピューターに接続できない</p></td>
<td><p>対象のコンピューターがワークグループ メンバーである場合、次の構文を使ってユーザー名を入力し、コンピューターにサインインします: &lt;<em>workgroup_name</em>&gt;\&lt;<em>user_name。</em>&gt;</p></td>
</tr>
<tr class="even">
<td><p>ロールがインストールされているにもかかわらず Web サーバー (IIS) 管理ツールが見つからない</p></td>
<td><p><span class="code">Install-windowsfeature</span> コマンドレットを使用して Windows PowerShell Web Access をインストールした場合、 <span class="code">IncludeManagementTools</span> パラメーターをコマンドレットに追加しない限り、管理ツールはインストールされません。 例については、「<a href="https://technet.microsoft.com/en-us/library/hh831611(v=ws.11).aspx">Windows PowerShell Web Access のインストールと使用</a>」の「Windows PowerShell コマンドレットを使って Windows PowerShell Web Access をインストールするには」を参照してください。 ゲートウェイ サーバーを対象とする役割と機能の追加ウィザードのセッションでツールを選択することで、IIS マネージャー コンソールとその他の必要な IIS 管理ツールを追加できます。 役割および機能の追加ウィザードは、サーバー マネージャー内で開きます。</p></td>
</tr>
<tr class="odd">
<td><p>Windows PowerShell Web Access Web サイトにアクセスできない</p></td>
<td><p>Internet Explorer セキュリティ強化の構成 (IE ESC) を有効にして、信頼済みサイトの一覧に Windows PowerShell Web Access Web サイトを追加するか、IE ESC を無効にします。 IE ESC は、サーバー マネージャーの <strong>[ローカル サーバー]</strong> ページの <strong>[プロパティ]</strong> タイルで無効にすることができます。</p></td>
</tr>
<tr class="even">
<td><p>ゲートウェイ サーバーが対象のコンピューターであり、ワークグループ内にある場合に、接続しようとすると次のエラー メッセージが表示される: <strong>"承認エラーが発生しました。 対象のコンピューターに接続する権限が与えられているかどうかを確認してください。"</strong></p></td>
<td><p>ゲートウェイ サーバーが対象のサーバーでもあり、ワークグループ内にある場合は、次の表に示されているようにユーザー名、コンピューター名、およびユーザー グループ名を指定します。 ドット (.) を単体で使用してコンピューター名を表すことはできません。</p>
<div>
<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th><p>シナリオ</p></th>
<th><p>UserName パラメーター</p></th>
<th><p>UserGroup パラメーター</p></th>
<th><p>ComputerName パラメーター</p></th>
<th><p>ComputerGroup パラメーター</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ゲートウェイ サーバーがドメイン内にある場合</p></td>
<td><p><em>Server_name</em>\<em>user_name</em>、Localhost\<em>user_name</em>、または .\<em>user_name</em></p></td>
<td><p><em>Server_name</em>\<em>user_group</em>、Localhost\<em>user_group</em>、または .\<em>user_group</em></p></td>
<td><p>ゲートウェイ サーバーの完全修飾名または Localhost</p></td>
<td><p><em>Server_name</em>\<em>computer_group</em>、Localhost\<em>computer_group</em>、または .\<em>computer_group</em></p></td>
</tr>
<tr class="even">
<td><p>ゲートウェイ サーバーがワークグループ内にある場合</p></td>
<td><p><em>Server_name</em>\<em>user_name</em>、Localhost\<em>user_name</em>、または .\<em>user_name</em></p></td>
<td><p><em>Server_name</em>\<em>user_group</em>、Localhost\<em>user_group</em>、または .\<em>user_group</em></p></td>
<td><p>サーバー名</p></td>
<td><p><em>Server_name</em>\<em>computer_group</em>、Localhost\<em>computer_group</em>、または .\<em>computer_group</em></p></td>
</tr>
</tbody>
</table>
</div>
<p>次のいずれかの形式の資格情報を使用して、対象コンピューターとしてゲートウェイ サーバーにサインインします。</p>
<ul>
<li><p><em>Server_name</em>\<em>user_name</em></p></li>
<li><p>Localhost\<em>user_name</em></p></li>
<li><p>.\<em>user_name</em></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>承認規則内に、構文 <em>user_name</em>/<em>computer_name ではなくセキュリティ識別子 (SID) が表示される</em> </p></td>
<td><p>規則が有効ではなくなっているか、Active Directory ドメイン サービスのクエリが失敗しています。 以前はワークグループ内にあったゲートウェイ サーバーが後でドメインに参加した場合は通常、承認規則は有効ではありません。</p></td>
</tr>
<tr class="even">
<td><p>ドメインを伴う IPv6 アドレスとして承認規則内で指定されている対象コンピューターにサインインできない。</p></td>
<td><p>承認規則では、ドメイン名形式の IPv6 アドレスがサポートされていません。 IPv6 アドレスを使用して対象コンピューターを指定するには、承認規則内で元の (コロンを含む) IPv6 アドレスを使用します。 Windows PowerShell Web Access のサインイン ページでは、ドメイン名形式の IPv6 アドレスも数値形式の (コロンを含む) IPv6 アドレスも対象コンピューター名としてサポートされていますが、承認規則内では異なります。 IPv6 アドレスの詳細については、<a href="https://technet.microsoft.com/library/cc781672.aspx">IPv6 の動作のしくみに関するページを参照してください。</a>.</p></td>
</tr>
</tbody>
</table>

<a href="javascript:void(0)" class="LW_CollapsibleArea_TitleAhref" title="Collapse"><span class="cl_CollapsibleArea_expanding LW_CollapsibleArea_Img"></span><span class="LW_CollapsibleArea_Title">参照</span></a>
<a href="/en-us/library/dn282395(v=ws.11).aspx#Anchor_1" class="LW_CollapsibleArea_Anchor_Img" title="Right-click to copy and share the link for this section"></a>

------------------------------------------------------------------------

[Windows PowerShell Web Access の承認規則とセキュリティ機能](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx)
[Web ベースの Windows PowerShell コンソールの使用](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx)
[about\_Remote\_Requirements](https://technet.microsoft.com/library/dd315349.aspx)

<span>表示:</span> 保護されている継承

<span class="stdr-votetitle">このページは役に立ちましたか。</span>
はい
いいえ

その他にご意見はありますか。

<span class="stdr-count"><span class="stdr-charcnt">残り 1500</span> 文字</span>
送信
スキップする

<span class="stdr-thankyou">ありがとうございました。</span> <span class="stdr-appreciate">貴重なご意見をお寄せいただき心より感謝いたします。</span>

[プロファイル (個人情報) の管理](https://social.technet.microsoft.com/profile)

|

<a href="javascript:void(0)" id="SiteFeedbackLinkOpener"><span id="FeedbackButton" class="FeedbackButton clip20x21"> <img src="https://i-technet.sec.s-msft.com/Areas/Epx/Content/Images/ImageSprite.png?v=635975720914499532" alt="Site Feedback" id="feedBackImg" class="cl_footer_feedback_icon" /> </span> サイトのフィードバック</a>
サイトのフィードバック

<a href="javascript:void(0)" id="SiteFeedbackLinkCloser">x</a>

お客様のご体験をお聞かせください。

ページはすばやく表示されましたか?

<span> はい<span> </span></span> <span> いいえ<span> </span></span>

ページのデザインは気に入りましたか?

<span> はい<span> </span></span> <span> いいえ<span> </span></span>

詳しくお聞かせください。

-   [Flash ニュースレター](https://technet.microsoft.com/cc543196.aspx)
-   |
-   [お問い合わせ先](https://technet.microsoft.com/cc512759.aspx)
-   |
-   [プライバシーに関する声明](https://privacy.microsoft.com/privacystatement)
-   |
-   [使用条件](https://technet.microsoft.com/cc300389.aspx)
-   |
-   [商標](https://www.microsoft.com/en-us/legal/intellectualproperty/Trademarks/)
-   |

© 2016 Microsoft

© 2016 Microsoft

サードパーティのスクリプトやコード、サードパーティから本 Web サイトへのリンク、あるいは本サイトからサードパーティへのリンクは、マイクロソフトではなく、そのようなコードの所有者によってお客様にライセンス供与されています。 ASP.NET Ajax CDN の使用条件 - http://www.asp.net/ajaxlibrary/CDN.ashx
<img src="https://m.webtrends.com/dcsjwb9vb00000c932fd0rjc7_5p3t/njs.gif?dcsuri=/nojavascript&amp;WT.js=No" alt="DCSIMG" id="Img1" width="1" height="1" />


<!--HONumber=May16_HO2-->


