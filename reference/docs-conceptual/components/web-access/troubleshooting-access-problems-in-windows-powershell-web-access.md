---
ms.date: 08/23/2017
keywords: powershell,コマンドレット
title: Windows PowerShell Web Access でのアクセスに関する問題のトラブルシューティング
ms.openlocfilehash: 818beffaf7df55ae36a154b7b751f9201c5b4299
ms.sourcegitcommit: d97b200e7a49315ce6608cd619e3e2fd99193edd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "75870185"
---
# <a name="troubleshooting-access-problems-in-windows-powershell-web-access"></a>Windows PowerShell Web Access でのアクセスに関する問題のトラブルシューティング

更新:2013 年 6 月 24 日 (改訂: 2017 年 8 月 23 日)

適用先:Windows Server 2012 R2、Windows Server 2012

次のセクションでは、Windows PowerShell Web Access を利用したリモート コンピューターへの接続で発生する可能性がある一般的な問題とその問題の解決案を提示します。

## <a name="sign-in-failure"></a>サインイン エラー

エラー発生の原因として以下が考えられます。

- コンピューターまたはリモート コンピューターの特定のセッション構成に対するユーザー アクセスを許可する承認規則が存在しない。

  Windows PowerShell Web Access では制限的なセキュリティを採用しているため、承認規則を使ってリモート コンピューターへのアクセス権をユーザーに明示的に付与する必要があります。

  承認規則の作成の詳細については、「[Windows PowerShell Web Access の承認規則とセキュリティ機能](authorization-rules-and-security-features-of-windows-powershell-web-access.md)」を参照してください。

- ユーザーによる対象コンピューターへのアクセスが承認されていない。 これはアクセス制御リスト (ACL) によって決定されます。

  詳細については、「[Windows PowerShell Web Access へのサインイン](use-the-web-based-windows-powershell-console.md#signing-in-to-windows-powershell-web-access)」か Windows PowerShell チーム ブログを参照してください。

- Windows PowerShell のリモート管理が対象コンピューター上で有効になっていない。

  ユーザーが接続しようとしているコンピューターでリモート管理が有効になっていることを確認してください。

  詳細については、「[リモート処理用にコンピューターを構成する方法](/powershell/module/microsoft.powershell.core/about/about_remote_requirements#how-to-configure-your-computer-for-remoting)」を参照してください。

## <a name="internal-server-error"></a>内部サーバー エラー

ユーザーが Internet Explorer ウィンドウで Windows PowerShell Web Access にサインインしようとすると、 **[内部サーバー エラー]** ページが表示されるか、*Internet Explorer* が応答しなくなる。

この問題は Internet Explorer に限られている。

### <a name="possible-cause"></a>考えられる原因

この問題は、ユーザーがサインイン時に指定したドメイン名に漢字が含まれていた場合や、ゲートウェイ サーバー名に 1 つ以上の漢字が含まれている場合に発生します。

#### <a name="workaround"></a>回避策

1. Internet Explorer 10 をインストールし、実行します。
1. Internet Explorer の **[ドキュメント モード]** 設定を *[IE10 標準]* に変更します。
   1. **F12** キーを押して開発者ツール コンソールを開きます。
   1. Internet Explorer 10 で、 **[ブラウザー モード]** をクリックし、 *[Internet Explorer 10]* をクリックします。
   1. **[ドキュメント モード]** 、 *[IE10 標準]* の順にクリックします。
   1. もう一度 **F12** キーを押して開発者ツール コンソールを閉じます。
1. Internet Explorer 10 の自動プロキシ構成を無効にします。
   1. **[ツール]** をクリックした後、 **[インターネット オプション]** をクリックします。
   1. **[インターネット オプション]** ダイアログ ボックスの **[接続]** タブで、 **[LAN の設定]** をクリックします。
   1. **[設定を自動的に検出する]** チェック ボックスをオフにします。 **[OK]** をクリックし、もう一度 **[OK]** をクリックして、 *[インターネット オプション]* ダイアログ ボックスを閉じます。

## <a name="cannot-connect-to-a-remote-workgroup-computer"></a>リモートのワークグループ コンピューターに接続できない

対象のコンピューターがワークグループ メンバーである場合、次の構文を使ってユーザー名を入力し、コンピューターにサインインします: `<workgroup_name>\<user_name>`

## <a name="cannot-find-web-server-iis-management-tools-even-though-the-role-was-installed"></a>ロールがインストールされているにもかかわらず Web サーバー (IIS) 管理ツールが見つからない

`Install-WindowsFeature` コマンドレットを使用して Windows PowerShell Web Access をインストールした場合、**IncludeManagementTools** パラメーターをコマンドレットに追加しない限り、管理ツールはインストールされません。

例については、「[Windows PowerShell コマンドレットを使って Windows PowerShell Web Access をインストールするには](install-and-use-windows-powershell-web-access.md#to-install-windows-powershell-web-access-by-using-windows-powershell-cmdlets)」を参照してください。

ゲートウェイ サーバーを対象とする**役割と機能の追加ウィザード**のセッションでツールを選択することで、IIS マネージャー コンソールとその他の必要な IIS 管理ツールを追加できます。 役割および機能の追加ウィザードは、サーバー マネージャー内で開きます。

## <a name="windows-powershell-web-access-website-is-not-accessible"></a>Windows PowerShell Web Access Web サイトにアクセスできない

Internet Explorer セキュリティ強化の構成 (IE ESC) を有効にして、信頼済みサイトの一覧に Windows PowerShell Web Access Web サイトを追加できます。

セキュリティ上の理由からお勧めはできませんが、IE ESC を無効にするという方法もあります。 IE ESC は、サーバー マネージャーの [ローカル サーバー] ページの [プロパティ] タイルで無効にすることができます。

## <a name="an-authorization-failure-occurred-verify-that-you-are-authorized-to-connect-to-the-destination-computer"></a>"承認エラーが発生しました。 対象のコンピューターに接続する権限が与えられているかどうかを確認してください。"

ゲートウェイ サーバーが対象のコンピューターであり、ワークグループ内にある場合に、接続しようとすると上記のエラー メッセージが表示される。

ゲートウェイ サーバーが対象のサーバーでもあり、ワークグループ内にある場合は、ユーザー名、コンピューター名、ユーザー グループ名を指定します。 ドット (.) を単体で使用してコンピューター名を表すことはできません。

### <a name="scenarios-and-proper-values"></a>シナリオと適切な値

#### <a name="all-cases"></a>すべてのケース

  パラメーター   |                                        値
------------- | -----------------------------------------------------------------------------------
UserName      | `Server_name\user_name`<br/>`Localhost\user_name`<br/>`.\user_name`
UserGroup     | `Server_name\user_group`<br/>`Localhost\user_group`<br/>`.\user_group`
ComputerGroup | `Server_name\computer_group`<br/>`Localhost\computer_group`<br/>`.\computer_group`

#### <a name="gateway-server-is-in-a-domain"></a>ゲートウェイ サーバーがドメイン内にある場合

 パラメーター   |                        値
------------ | ----------------------------------------------------
[ComputerName] | ゲートウェイ サーバーの完全修飾名または Localhost

#### <a name="gateway-server-is-in-a-workgroup"></a>ゲートウェイ サーバーがワークグループ内にある場合

 パラメーター   |    値
------------ | -----------
[ComputerName] | サーバー名

### <a name="gateway-credentials"></a>ゲートウェイの資格情報

次のいずれかの形式の資格情報を使用して、ターゲット コンピューターとしてゲートウェイ サーバーにサインインします。

- `Server_name\user_name`
- `Localhost\user_name`
- `.\user_name`

## <a name="a-security-identifier-sid-is-displayed-in-an-authorization-rule"></a>セキュリティ識別子 (SID) が認証規則に表示される

承認規則内に、構文 `user_name/computer_name` ではなくセキュリティ識別子 (SID) が表示されます。

規則が有効ではなくなっているか、Active Directory Domain Services のクエリが失敗しています。 以前はワークグループ内にあったゲートウェイ サーバーが後でドメインに参加した場合は通常、承認規則は有効ではありません。

## <a name="cannot-sign-in-with-rule-as-an-ipv6-address-with-a-domain"></a>規則の IPv6 アドレスにドメインが含まれるとき、サインインできない

ドメインを含む IPv6 アドレスとして承認規則内で指定されているターゲット コンピューターにサインインできません。

承認規則では、ドメイン名形式の IPv6 アドレスがサポートされていません。

IPv6 アドレスを使用して対象コンピューターを指定するには、承認規則内で元の (コロンを含む) IPv6 アドレスを使用します。 Windows PowerShell Web Access のサインイン ページでは、ドメイン名形式の IPv6 アドレスも数値形式の (コロンを含む) IPv6 アドレスもターゲット コンピューター名としてサポートされていますが、承認規則内では異なります。

IPv6 アドレスの詳細については、[IPv6 の動作のしくみに関するページ](/previous-versions/windows/it-pro/windows-server-2003/cc781672(v=ws.10))を参照してください。

## <a name="see-also"></a>参照

- [Windows PowerShell Web Access の承認規則とセキュリティ機能](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn282394(v=ws.11))
- [Web ベースの Windows PowerShell コンソールの使用](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831417(v=ws.11))
- [about_Remote_Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements)
