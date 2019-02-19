---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: PowerShell リモート処理での次ホップの実行
ms.openlocfilehash: 1b6e5ad53346324adc7be2d013e154c8600afa4f
ms.sourcegitcommit: 6ae5b50a4b3ffcd649de1525c3ce6f15d3669082
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "56265588"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a>PowerShell リモート処理での次ホップの実行

"次ホップの問題" とは次のような状況のことです。

1. _ServerA_ にログインしています。
2. _ServerA_ からリモート PowerShell セッションを開始して _ServerB_ に接続します。
3. PowerShell リモート処理セッションを介して _ServerB_ で実行するコマンドは、_ServerC_ 上のリソースにアクセスを試みます。
4. PowerShell リモート処理セッションの作成に使った資格情報は _ServerB_ から _ServerC_ に渡されないため、_ServerC_ 上のリソースへのアクセスは拒否されます。

この問題に対処する方法はいくつかあります。 このトピックでは、次ホップの問題に対する最も一般的な解決方法をいくつか紹介します。

## <a name="credssp"></a>CredSSP

認証に[資格情報のセキュリティ サポート プロバイダー (CredSSP)](https://msdn.microsoft.com/library/windows/desktop/bb931352.aspx) を使用できます。 CredSSP はリモート サーバー (_ServerB_) に資格情報をキャッシュするため、これを使用すると資格情報の盗難攻撃にさらされます。 リモート コンピューターが侵害されると、攻撃者はユーザーの資格情報にアクセスできます。 CredSSP は、既定では、クライアント コンピューターとサーバー コンピューターの両方で無効になっています。 CredSSP は、最も信頼性の高い環境でのみ有効にしてください。 たとえば、ドメイン コントローラーは信頼性が高いため、ドメイン コントローラーに接続しているドメイン管理者が有効にすることをお勧めします。

PowerShell リモート処理で CredSSP を使用する場合のセキュリティに関する注意事項の詳細については、「[Accidental Sabotage: Beware of CredSSP (予想外の妨害行為: CredSSP に関する注意事項)](https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp)」を参照してください。

資格情報の盗難攻撃の詳細については、「[Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft (Pass-the-Hash (PtH) 攻撃とその他の資格情報の盗難の抑制)](https://www.microsoft.com/en-us/download/details.aspx?id=36036)」を参照してください。

PowerShell リモート処理用に CredSSP を有効にして使う方法の例については、「[Using CredSSP to solve the second-hop problem](https://blogs.technet.microsoft.com/heyscriptingguy/2012/11/14/enable-powershell-second-hop-functionality-with-credssp/)」 (次ホップ問題の解決に CredSSP を使う) をご覧ください。

### <a name="pros"></a>長所

- Windows Server 2008 以降のすべてのサーバーで機能します。

### <a name="cons"></a>短所

- セキュリティの脆弱性があります。
- クライアント ロールとサーバー ロールの両方の構成が必要です。

## <a name="kerberos-delegation-unconstrained"></a>Kerberos の委任 (無制限)

Kerberos の無制限の委任を使って、次ホップを実行することもできます。 ただし、この方法では、委任された資格情報が使われる場所を制御することはできません。

>**注:** **[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。 詳しくは、「[Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts](https://blogs.technet.microsoft.com/poshchap/2015/05/01/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts/)」 (セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析) および「[Kerberos Authentication Tools and Settings](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx)」 (Kerberos 認証のツールと設定) をご覧ください。

### <a name="pros"></a>長所

- 特別なコーディングが必要ありません。

### <a name="cons"></a>短所

- WinRM の次ホップはサポートされません。
- 資格情報が使われる場所を制御できず、セキュリティの脆弱性が発生します。

## <a name="kerberos-constrained-delegation"></a>Kerberos の制約付き委任

従来の (リソースに基づかない) 制約付き委任を使って、次ホップを実行できます。 「任意の認証プロトコルを使用して、」オプションを使用して Kerberos の制約付き委任を構成するプロトコル遷移を許可します。

> [!NOTE]
> **[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。 詳しくは、「[Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts](https://blogs.technet.microsoft.com/poshchap/2015/05/01/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts/)」 (セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析) および「[Kerberos Authentication Tools and Settings](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx)」 (Kerberos 認証のツールと設定) をご覧ください。

### <a name="pros"></a>長所

- 特別なコーディングが必要ありません。

### <a name="cons"></a>短所

- WinRM の次ホップはサポートされません。
- リモート サーバー (_ServerB_) の Active Directory オブジェクトで構成する必要があります。
- 1 つのドメインに制限されます。 複数のドメインまたはフォレストにまたがることはできません。
- オブジェクトとサービス プリンシパル名 (SPN) を更新する権限が必要です。

## <a name="resource-based-kerberos-constrained-delegation"></a>リソースに基づく Kerberos の制約付き委任

リソースに基づく Kerberos の制約付き委任 (Windows Server 2012 で導入) を使って、リソースが存在するサーバー オブジェクトでの資格情報の委任を構成します。
上で説明した次ホップのシナリオでは、_ServerC_ を構成して、受け入れる委任された資格情報の委任元を指定します。

>**注:** **[アカウントは重要なので委任できない]** プロパティが設定されている Active Directory アカウントは委任できません。 詳しくは、「[Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts](https://blogs.technet.microsoft.com/poshchap/2015/05/01/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts/)」 (セキュリティ フォーカス: 特権アカウントに対する "アカウントは重要なので委任できない" の分析) および「[Kerberos Authentication Tools and Settings](https://technet.microsoft.com/library/cc738673(v=ws.10).aspx)」 (Kerberos 認証のツールと設定) をご覧ください。

### <a name="pros"></a>長所

- 資格情報が保存されません。
- PowerShell コマンドレットを使った構成が比較的簡単です。特別なコーディングは必要ありません。
- 特別なドメイン アクセスは必要ありません。
- 複数のドメインおよびフォレストをまたいで動作します。
- PowerShell のコード。

### <a name="cons"></a>短所

- Windows Server 2012 以降が必要です。
- WinRM の次ホップはサポートされません。
- オブジェクトとサービス プリンシパル名 (SPN) を更新する権限が必要です。

### <a name="example"></a>例

_ServerB_ からの委任された資格情報を許可するように _ServerC_ でリソースに基づく制約付き委任を構成する PowerShell の例を示します。
この例では、すべてのサーバーが Windows Server 2012 以降を実行しており、いずれかのサーバーが属している各ドメインに少なくとも 1 つの Windows Server 2012 ドメイン コントローラーがあるものとします。

制約付き委任を構成する前に、`RSAT-AD-PowerShell` 機能を追加して Active Directory PowerShell モジュールをインストールした後、そのモジュールをセッションにインポートする必要があります。

```powershell
PS C:\> Add-WindowsFeature RSAT-AD-PowerShell

PS C:\> Import-Module ActiveDirectory
```
使用できる複数のコマンドレットに、**PrincipalsAllowedToDelegateToAccount** パラメーターが追加されています。

```powershell
PS C:\> Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount

CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

**PrincipalsAllowedToDelegateToAccount** パラメーターは、Active Directory オブジェクトの **msDS-AllowedToActOnBehalfOfOtherIdentity** 属性を設定します。この属性には、関連付けられたアカウント (この例では、_Server_ のコンピューター アカウント) に資格情報を委任する権限を持つアカウントを指定するアクセス制御リスト (ACL) が含まれます。

サーバーを表すために使用する変数を設定します。

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

WinRM (したがって PowerShell リモート処理) は、既定でコンピューター アカウントとして実行します。 これは、`winrm` サービスの **StartName** プロパティを見て確認できます。

```powershell
PS C:\> Get-WmiObject win32_service -filter 'name="winrm"' | Format-List StartName

StartName : NT AUTHORITY\NetworkService
```

_ServerC_ で _ServerB_ の PowerShell リモート処理セッションからの委任を許可するため、_ServerC_ の **PrincipalsAllowedToDelegateToAccount** パラメーターを _ServerB_ のコンピューター オブジェクトに設定することによって、アクセスを許可します。

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

Kerberos の[キー配布センター (KDC)](https://msdn.microsoft.com/library/windows/desktop/aa378170(v=vs.85).aspx) は、拒否されたアクセス試行を 15 分間キャッシュします (ネガティブ キャッシュ)。 _ServerB_ が以前に _ServerC_ にアクセスしようとした場合、次のコマンドを呼び出すことによって _ServerB_ 上のキャッシュをクリアする必要があります。

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

キャッシュを消去するには、コンピューターを再起動するか、15 分以上待つのでもかまいません。

キャッシュをクリアした後は、_ServerA_ から _ServerB_ を経由して _ServerC_ にコードを正常に実行できます。

```powershell
# Capture a credential
$cred = Get-Credential Contoso\Alice

# Test kerberos double hop
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    Test-Path \\$($using:ServerC.Name)\C$
    Get-Process lsass -ComputerName $($using:ServerC.Name)
    Get-EventLog -LogName System -Newest 3 -ComputerName $($using:ServerC.Name)
}
```

この例では、_ServerB_ が `$ServerC` 変数を認識できるようにするため、`$using` 変数を使用しています。 `$using` 変数については、「[About Remote Variables](https://technet.microsoft.com/library/jj149005.aspx)」 (リモート変数について) を参照してください。

複数のサーバーが _ServerC_ に資格情報を委任できるようにするには、_ServerC_ で **PrincipalsAllowedToDelegateToAccount** パラメーターの値に配列を設定します。

```powershell
# Set up variables for each server
$ServerB1 = Get-ADComputer -Identity ServerB1
$ServerB2 = Get-ADComputer -Identity ServerB2
$ServerB3 = Get-ADComputer -Identity ServerB3
$ServerC  = Get-ADComputer -Identity ServerC

# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC `
    -PrincipalsAllowedToDelegateToAccount @($ServerB1,$ServerB2,$ServerB3)
```

ドメインをまたいで次ホップを実行する場合は、_ServerB_ が属するドメインのドメイン コントローラーの完全修飾ドメイン名 (FQDN) を追加します。

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

ServerC に資格情報を委任する機能を削除するには、_ServerC_ の **PrincipalsAllowedToDelegateToAccount** パラメーターの値に `$null` を設定します。

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a>リソースに基づく Kerberos の制約付き委任についての情報

- [Kerberos 認証の新機能](https://technet.microsoft.com/library/hh831747.aspx)
- [Windows Server 2012 による Kerberos の制約付き委任の処理方法、第 1 部](https://windowsitpro.com/security/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1)
- [Windows Server 2012 による Kerberos の制約付き委任の処理方法、第 2 部](https://windowsitpro.com/security/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2)
- [統合 Windows 認証での Azure Active Directory アプリケーション プロキシ展開に対する Kerberos の制約付き委任の概要](https://aka.ms/kcdpaper)
- [[MS-ADA2]: Active Directory スキーマ属性 M2.210 Attribute msDS-AllowedToActOnBehalfOfOtherIdentity](https://msdn.microsoft.com/library/hh554126.aspx)
- [[MS-SFU]: Kerberos プロトコル拡張: Service for User および制約付き委任プロトコルの 1.3.2 S4U2proxy](https://msdn.microsoft.com/library/cc246079.aspx)
- [リソースに基づく Kerberos の制約付き委任](https://blog.kloud.com.au/2013/07/11/kerberos-constrained-delegation/)
- [PrincipalsAllowedToDelegateToAccount を使用した制約付き委任を使用しないリモート管理](https://blogs.msdn.microsoft.com/taylorb/2012/11/06/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount/)

## <a name="pssessionconfiguration-using-runas"></a>RunAs を使用する PSSessionConfiguration

_ServerB_ にセッション構成を作成し、その **RunAsCredential** パラメーターを設定できます。

PSSessionConfiguration と RunAs を使って次ホップの問題を解決する方法については、「[Another solution to multi-hop PowerShell remoting](https://blogs.msdn.microsoft.com/sergey_babkins_blog/2015/03/18/another-solution-to-multi-hop-powershell-remoting/)」 (マルチホップ PowerShell リモート処理に対する別の解決策) をご覧ください。

### <a name="pros"></a>長所

- WMF 3.0 以降のすべてのサーバーで機能します。

### <a name="cons"></a>短所

- すべての中間サーバー (_ServerB_) で **PSSessionConfiguration** と **RunAs** を構成する必要があります。
- ドメインの **RunAs** アカウントを使うときは、パスワードの管理が必要です。

## <a name="just-enough-administration-jea"></a>Just Enough Administration (JEA)

JEA では、PowerShell セッションの間に管理者が実行できるコマンドを制限できます。 これを使って、次ホップの問題を解決できます。

JEA については、「[Just Enough Administration](https://docs.microsoft.com/powershell/jea/overview)」をご覧ください。

### <a name="pros"></a>長所

- 仮想アカウントを使う場合にパスワードの管理が不要です。

### <a name="cons"></a>短所

- WMF 5.0 以降が必要です。
- すべての中間サーバー (_ServerB_) の構成が必要です。

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a>Invoke-Command スクリプト ブロックの内部で資格情報を渡す

[Invoke-Command](https://msdn.microsoft.com/powershell/reference/5.1/microsoft.powershell.core/invoke-command) コマンドレットを呼び出すときに **ScriptBlock** パラメーターの内部で資格情報を渡すことができます。

### <a name="pros"></a>長所

- 特別なサーバー構成は必要ありません。
- WMF 2.0 以降を実行する任意のサーバーで動作します。

### <a name="cons"></a>短所

- 面倒なコード技法が必要です。
- WMF 2.0 を実行している場合は、リモート セッションに引数を渡すために異なる構文が必要です。

### <a name="example"></a>例

**Invoke-Command** スクリプト ブロックで資格情報を渡す方法の例を次に示します。

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a>関連項目

[PowerShell リモート処理のセキュリティに関する考慮事項](WinRMSecurity.md)
