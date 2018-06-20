---
ms.date: 08/23/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell Web Access でのアクセスに関する問題のトラブルシューティング
ms.openlocfilehash: ef476d8e386e5380cb2c9dda69180dfce8748bf4
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
ms.locfileid: "30953448"
---
# <a name="troubleshooting-access-problems-in-windows-powershell-web-access"></a>Windows PowerShell Web Access でのアクセスに関する問題のトラブルシューティング

更新: 2013 年 6 月 24 日 (改訂: 2017 年 8 月 23 日)

適用対象: Windows Server 2012 R2、Windows Server 2012

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

  詳細については、「[リモート処理用にコンピューターを構成する方法](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements#how-to-configure-your-computer-for-remoting)」を参照してください。

## <a name="internal-server-error"></a>内部サーバー エラー

ユーザーが Internet Explorer ウィンドウで Windows PowerShell Web Access にサインインしようとすると、**[内部サーバー エラー]** ページが表示されるか、*Internet Explorer* が応答しなくなる。

この問題は Internet Explorer に限られている。

### <a name="possible-cause"></a>考えられる原因

この問題は、ユーザーがサインイン時に指定したドメイン名に漢字が含まれていた場合や、ゲートウェイ サーバー名に 1 つ以上の漢字が含まれている場合に発生します。

#### <a name="workaround"></a>回避策

1. [Internet Explorer 10 をインストールし、実行します](http://ie.microsoft.com/testdrive/info/downloads/Default.html)。
1. Internet Explorer の **[ドキュメント モード]** 設定を *[IE10 標準]* に変更します。
   1. **F12** キーを押して開発者ツール コンソールを開きます。
   1. Internet Explorer 10 で、**[ブラウザー モード]** をクリックし、*[Internet Explorer 10]* をクリックします。
   1. **[ドキュメント モード]**、*[IE10 標準]* の順にクリックします。
   1. もう一度 **F12** キーを押して開発者ツール コンソールを閉じます。
1. Internet Explorer 10 の自動プロキシ構成を無効にします。
   1. **[ツール]**、 **[インターネット オプション]** の順にクリックします。
   1. **[インターネット オプション]** ダイアログ ボックスの **[接続]** タブで、**[LAN の設定]** をクリックします。
   1. **[設定を自動的に検出する]** チェック ボックスをオフにします。 **[OK]** をクリックし、もう一度 **[OK]** をクリックして、*[インターネット オプション]* ダイアログ ボックスを閉じます。

## <a name="cannot-connect-to-a-remote-workgroup-computer"></a>リモートのワークグループ コンピューターに接続できない

対象のコンピューターがワークグループ メンバーである場合、次の構文を使ってユーザー名を入力し、コンピューターにサインインします: `<workgroup_name>\<user_name>`

## <a name="cannot-find-web-server-iis-management-tools-even-though-the-role-was-installed"></a>ロールがインストールされているにもかかわらず Web サーバー (IIS) 管理ツールが見つからない

`Install-WindowsFeature` コマンドレットを使って Windows PowerShell Web Access をインストールした場合、コマンドレットに `-IncludeManagementTools` パラメーターを追加しない限り管理ツールはインストールされません。

例については、「[Windows PowerShell コマンドレットを使って Windows PowerShell Web Access をインストールするには](install-and-use-windows-powershell-web-access.md#to-install-windows-powershell-web-access-by-using-windows-powershell-cmdlets)」を参照してください。

ゲートウェイ サーバーを対象とする**役割と機能の追加ウィザード**のセッションでツールを選択することで、IIS マネージャー コンソールとその他の必要な IIS 管理ツールを追加できます。
役割および機能の追加ウィザードは、サーバー マネージャー内で開きます。

## <a name="windows-powershell-web-access-website-is-not-accessible"></a>Windows PowerShell Web Access Web サイトにアクセスできない

Internet Explorer セキュリティ強化の構成 (IE ESC) を有効にして、信頼済みサイトの一覧に Windows PowerShell Web Access Web サイトを追加できます。

セキュリティ上の理由からお勧めはできませんが、IE ESC を無効にするという方法もあります。
IE ESC は、サーバー マネージャーの [ローカル サーバー] ページの [プロパティ] タイルで無効にすることができます。

## <a name="an-authorization-failure-occurred-verify-that-you-are-authorized-to-connect-to-the-destination-computer"></a>"承認エラーが発生しました。 対象のコンピューターに接続する権限が与えられているかどうかを確認してください。"

ゲートウェイ サーバーが対象のコンピューターであり、ワークグループ内にある場合に、接続しようとすると上記のエラー メッセージが表示される。

ゲートウェイ サーバーが対象のサーバーでもあり、ワークグループ内にある場合は、ユーザー名、コンピューター名、ユーザー グループ名を指定します。
ドット (.) を単体で使用してコンピューター名を表すことはできません。

### <a name="scenarios-and-proper-values"></a>シナリオと適切な値

#### <a name="all-cases"></a>すべてのケース

パラメーター | 値
-- | --
UserName | Server\_name\\user\_name<br/>Localhost\\user\_name<br/>.\\user\_name
UserGroup | Server\_name\\user\_group<br/>Localhost\\user\_group<br/>.\\user\_group
ComputerGroup | Server\_name\\computer\_group<br/>Localhost\\computer\_group<br/>.\\computer\_group

#### <a name="gateway-server-is-in-a-domain"></a>ゲートウェイ サーバーがドメイン内にある場合

パラメーター | 値
-- | --
ComputerName | ゲートウェイ サーバーの完全修飾名または Localhost

#### <a name="gateway-server-is-in-a-workgroup"></a>ゲートウェイ サーバーがワークグループ内にある場合

パラメーター | 値
-- | --
ComputerName | サーバー名

### <a name="gateway-credentials"></a>ゲートウェイの資格情報

次のいずれかの形式の資格情報を使用して、対象コンピューターとしてゲートウェイ サーバーにサインインします。

- Server\_name\\user\_name
- Localhost\\user\_name
- .\\user\_name

## <a name="a-security-identifier-sid-is-displayed-in-an-authorization-rule"></a>セキュリティ識別子 (SID) が認証規則に表示される

承認規則内に、構文 user\_name/computer\_name ではなくセキュリティ識別子 (SID) が表示される

規則が有効ではなくなっているか、Active Directory Domain Services のクエリが失敗しています。
以前はワークグループ内にあったゲートウェイ サーバーが後でドメインに参加した場合は通常、承認規則は有効ではありません。

## <a name="cannot-sign-in-with-rule-as-an-ipv6-address-with-a-domain"></a>規則の IPv6 アドレスにドメインが含まれるとき、サインインできない

ドメインを伴う IPv6 アドレスとして承認規則内で指定されている対象コンピューターにサインインできない。

承認規則では、ドメイン名形式の IPv6 アドレスがサポートされていません。

IPv6 アドレスを使用して対象コンピューターを指定するには、承認規則内で元の (コロンを含む) IPv6 アドレスを使用します。
Windows PowerShell Web Access のサインイン ページでは、ドメイン名形式の IPv6 アドレスも数値形式の (コロンを含む) IPv6 アドレスも対象コンピューター名としてサポートされていますが、承認規則内では異なります。

IPv6 アドレスの詳細については、[IPv6 の動作のしくみに関するページ](https://technet.microsoft.com/library/cc781672(v=ws.10).aspx)を参照してください。

## <a name="see-also"></a>参照

- [Windows PowerShell Web Access の承認規則とセキュリティ機能](https://technet.microsoft.com/en-us/library/dn282394(v=ws.11).aspx)
- [Web ベースの Windows PowerShell コンソールの使用](https://technet.microsoft.com/en-us/library/hh831417(v=ws.11).aspx)
- [about_Remote_Requirements](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_requirements)