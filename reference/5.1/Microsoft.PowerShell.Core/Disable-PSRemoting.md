---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 01/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/disable-psremoting?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-PSRemoting
ms.openlocfilehash: 3a281786f99b2a46d0aeb9785480f02b35b2b433
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212104"
---
# Disable-PSRemoting

## 概要
PowerShell エンドポイントがリモート接続を受信できないようにします。

## SYNTAX

```
Disable-PSRemoting [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## Description

この `Disable-PSRemoting` コマンドレットは、ローカルコンピューター上のすべての Windows PowerShell セッションエンドポイント構成へのリモートアクセスをブロックします。 これには、PowerShell 6 以降で作成されたすべてのエンドポイントが含まれます。

すべてのセッション構成へのリモートアクセスを再度有効にするには、コマンドレットを使用し `Enable-PSRemoting` ます。 これには、PowerShell 6 以降で作成されたすべてのエンドポイントが含まれます。 選択したセッション構成へのリモートアクセスを有効にするには、コマンドレットの **Accessmode** パラメーターを使用し `Set-PSSessionConfiguration` ます。
また、 `Enable-PSSessionConfiguration` `Disable-PSSessionConfiguration` コマンドレットとコマンドレットを使用して、すべてのユーザーのセッション構成を有効または無効にすることもできます。 セッション構成の詳細については、「 [about_Session_Configurations](About/about_Session_Configurations.md)」を参照してください。

> [!NOTE]
> を実行した後も、 `Disable-PSRemoting` ローカルコンピューターでループバック接続を行うことができます。 ループバック接続は、から発信され、同じローカルコンピューターに接続する PowerShell リモートセッションです。 外部ソースからのリモートセッションはブロックされたままになります。 ループバック接続の場合は、 **EnableNetworkAccess** パラメーターに従って暗黙的な資格情報を使用する必要があります。 ループバック接続の詳細については、「 [新規-PSSession](New-PSSession.md)」を参照してください。

このコマンドレットを実行するには、[ **管理者として実行** ] オプションを使用して Windows PowerShell を起動します。

## 例

### 例 1: すべてのセッション構成へのリモートアクセスを禁止する

この例では、コンピューター上のすべての PowerShell セッションエンドポイント構成にリモートアクセスできないようにします。

```powershell
Disable-PSRemoting
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### 例 2: 確認メッセージを表示せずにすべてのセッション構成へのリモートアクセスを禁止する

この例では、メッセージを表示せずに、コンピューター上のすべての PowerShell セッションエンドポイント構成をリモートアクセスできないようにします。

```powershell
Disable-PSRemoting -Force
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these
 steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.
```

### 例 3: このコマンドレットを実行した場合の影響

この例は、コマンドレットを使用した場合の効果を示して `Disable-PSRemoting` います。 このコマンドシーケンスを実行するには、[ **管理者として実行** ] オプションを使用して PowerShell を起動します。

セッション構成を無効にすると、 `New-PSSession` コマンドレットはローカルコンピューター ("ループバック" とも呼ばれます) へのリモートセッションを作成しようとします。 リモートアクセスはローカルコンピューターで無効になっているため、コマンドは失敗します。

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error
 message : Access is denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost -ConfigurationName PowerShell.6
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : OpenError: (System.Management.A\u2026tion.RemoteRunspace:RemoteRunspace)
 [New-PSSession], PSRemotingTransportException
+ FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed
```

### 例 4: このコマンドレットと Enable-PSRemoting を実行した場合の影響

この例では、 `Disable-PSRemoting` コマンドレットとコマンドレットを使用して、のセッション構成への影響を示し `Enable-PSRemoting` ます。

`Disable-PSRemoting` は、すべての PowerShell セッションエンドポイント構成へのリモートアクセスを無効にするために使用されます。 **Force** パラメーターにより、すべてのユーザー メッセージが表示されなくなります。 `Get-PSSessionConfiguration` `Format-Table` コマンドレットおよびコマンドレットは、コンピューター上のセッション構成を表示します。

出力には、ネットワークトークンを持つすべてのリモートユーザーが、エンドポイント構成へのアクセスを拒否されていることが示されています。 ローカルコンピューター上の Administrators グループは、ローカル (ループバックとも呼ばれます) で暗黙的な資格情報を使用して接続されている限り、エンドポイント構成へのアクセスが許可されます。

```powershell
Disable-PSRemoting -force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Enable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow BUILTIN\Administrators AccessAllowed
microsoft.powershell32        BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   BUILTIN\Administrators AccessAllowed
```

この `Enable-PSRemoting` コマンドレットは、コンピューター上のすべての PowerShell セッションエンドポイント構成へのリモートアクセスを再度有効にします。 **Force** パラメーターを指定すると、すべてのユーザープロンプトが表示されなくなり、プロンプトなしで WinRM サービスが再起動されます。 新しい出力は、 **Accessdenied** セキュリティ記述子がすべてのセッション構成から削除されたことを示しています。

### 例 5: 無効なセッションエンドポイント構成を使用したループバック接続

この例では、エンドポイントの構成を無効にする方法を示し、無効になっているエンドポイントへのループバック接続を成功させる方法を示します。 `Disable-PSRemoting` すべての PowerShell セッションエンドポイント構成を無効にします。

```powershell
Disable-PSRemoting -Force
New-PSSession -ComputerName localhost
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

New-PSSession : [localhost] Connecting to remote server localhost failed with the following error message : Access is
denied. For more information, see the about_Remote_Troubleshooting Help topic.
At line:1 char:1
+ New-PSSession -ComputerName localhost
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [New-PSSession], PSRemotin
   gTransportException
    + FullyQualifiedErrorId : AccessDenied,PSSessionOpenFailed

```

```powershell
New-PSSession -ComputerName localhost -EnableNetworkAccess
```

```Output
 Id Name       Transport ComputerName  ComputerType   State   ConfigurationName   Availability
 -- ----       --------- ------------  ------------   -----   -----------------   ------------
 1  Runspace1  WSMan     localhost     RemoteMachine  Opened  powershell.6           Available
```

を初めて使用する場合は、 `New-PSSession` ローカルコンピューターへのリモートセッションの作成が試行されます。 この種類の接続はネットワークスタックを経由し、ループバックではありません。 その結果、無効なエンドポイントへの接続は失敗し、" **アクセスが拒否されまし** た" というエラーが表示されます。

2つ目の使用では、 `New-PSSession` ローカルコンピューターへのリモートセッションの作成も試行します。
この場合、ネットワークスタックをバイパスするループバック接続であるため、成功します。

次の条件が満たされると、ループバック接続が作成されます。

- 接続先のコンピューター名は ' localhost ' です。
- 資格情報は渡されません。 現在ログインしているユーザー (暗黙的な資格情報) は、接続に使用されます。
- **EnableNetworkAccess** スイッチパラメーターが使用されます。

ループバック接続の詳細については、「 [新しい PSSession](New-PSSession.md) ドキュメント」を参照してください。

### 例 6: カスタムセキュリティ記述子を持つセッション構成へのリモートアクセスを禁止する

この例では、 `Disable-PSRemoting` コマンドレットを使用して、カスタムセキュリティ記述子を持つセッション構成を含むすべてのセッション構成へのリモートアクセスを無効にする方法を示します。

`Register-PSSessionConfiguration`**テスト** セッション構成を作成します。 **FilePath** パラメーターでは、セッションをカスタマイズするセッション構成ファイルを指定します。 **Showsecurity記述子 ui** パラメーターを使用すると、セッション構成のアクセス許可を設定するダイアログボックスが表示されます。 [アクセス許可] ダイアログボックスで、指定されたユーザーに対してカスタムのフルアクセス許可を作成します。

`Get-PSSessionConfiguration`およびコマンドレットでは、 `Format-Table` セッション構成とそのプロパティが表示されます。 出力には、 **テスト** セッション構成で、指定されたユーザーに対する対話型アクセスと特殊なアクセス許可が許可されていることが示されています。

`Disable-PSRemoting` すべてのセッション構成へのリモートアクセスを無効にします。

```powershell
Register-PSSessionConfiguration -Name Test -FilePath .\TestEndpoint.pssc -ShowSecurityDescriptorUI -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap

Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Wrap
New-PSSession -ComputerName localhost -ConfigurationName Test
```

```Output
Name                          Permission
----                          ----------
microsoft.powershell          BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\INTERACTIVE AccessAllowed, BUILTIN\Administrators AccessAllowed,
DOMAIN01\User01 AccessAllowed

WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
Test                          NT AUTHORITY\NETWORK AccessDenied, NTAUTHORITY\INTERACTIVE AccessAllowed,
BUILTIN\Administrators AccessAllowed, DOMAIN01\User01 AccessAllowed


[Server01] Connecting to remote server failed with the following error message : Access is denied. For more information, see the about_Rem
ote_Troubleshooting Help topic.
+ CategoryInfo          : OpenError: (System.Manageme....RemoteRunspace:RemoteRunspace) [], PSRemotingTransportException
+ FullyQualifiedErrorId : PSSessionOpenFailed
```

ここで `Get-PSSessionConfiguration` 、 `Format-Table` コマンドレットとコマンドレットは、すべてのネットワークユーザーに対する **accessdenied** セキュリティ記述子が、 **テスト** セッション構成を含むすべてのセッション構成に追加されることを示しています。 他のセキュリティ記述子は変更されませんが、"network_deny_all" セキュリティ記述子が優先されます。 これは、 `New-PSSession` **テスト** セッション構成に接続するためにを使用した場合に示されます。

### 例 7: 選択したセッション構成へのリモートアクセスを再度有効にする

この例では、選択したセッション構成にのみリモート アクセスを再度有効にする方法を示します。 すべてのセッション構成を無効にした後、特定のセッションを再び有効にします。

`Set-PSSessionConfiguration`コマンドレットは、microsoft を変更するために使用され **ます。ServerManager** セッション構成。 **Accessmode** パラメーターの値を **remote** に設定すると、構成へのリモートアクセスが有効になります。

```powershell
Disable-PSRemoting -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto

Set-PSSessionConfiguration -Name Microsoft.ServerManager -AccessMode Remote -Force
Get-PSSessionConfiguration | Format-Table -Property Name, Permission -Auto
```

```Output
WARNING: Disabling the session configurations does not undo all the changes made by the Enable-PSRemoting
 or Enable-PSSessionConfiguration cmdlet. You might have to manually undo the changes by following these steps:
    1. Stop and disable the WinRM service.
    2. Delete the listener that accepts requests on any IP address.
    3. Disable the firewall exceptions for WS-Management communications.
    4. Restore the value of the LocalAccountTokenFilterPolicy to 0, which restricts remote access to
       members of the Administrators group on the computer.

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed

Name                          Permission
----                          ----------
microsoft.powershell          NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell.workflow NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.powershell32        NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
microsoft.ServerManager       BUILTIN\Administrators AccessAllowed
WithProfile                   NT AUTHORITY\NETWORK AccessDenied, BUILTIN\Administrators AccessAllowed
```

## PARAMETERS

### -Confirm

コマンドレットの実行前に確認を求めるメッセージが表示されます。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
ユーザーに確認せずに、直ちにコマンドを実行します。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

コマンドレットの実行時に発生する内容を示します。 このコマンドレットは実行されません。

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### 共通パラメーター

このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。 詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。

## 入力

### なし

パイプを使用してこのコマンドレットにオブジェクトを送ることはできません。

## 出力

### なし

このコマンドレットは出力を生成しません。

## 注

- セッション構成を無効にしても、 `Enable-PSRemoting` またはコマンドレットによって行われたすべての変更が元に戻されるわけではありません `Enable-PSSessionConfiguration` 。 場合によっては次の変更を手動で元に戻す必要があります。

  1. WinRM サービスを停止して無効にする。
  2. 任意の IP アドレスで要求を受け入れるリスナーを削除する。
  3. WS-Management 通信用のファイアウォールの例外を無効にする。
  4. LocalAccountTokenFilterPolicy の値を 0 に復元して、リモート アクセスをコンピューターの Administrators グループのメンバーに制限する。

  セッション構成は、セッションの環境を定義する設定のグループです。 コンピューターに接続するすべてのセッションは、コンピューターに登録されているセッション構成のいずれかを使用する必要があります。 すべてのセッション構成へのリモート アクセスを拒否することにより、リモート ユーザーがコンピューターに接続するセッションを確立するのを効果的に防止できます。

  Windows PowerShell 2.0 では、は、 `Disable-PSRemoting` すべてのセッション構成のセキュリティ記述子に Deny_All エントリを追加します。 この設定は、すべてのユーザーがローカルコンピューターに対してユーザー管理セッションを作成できないようにします。 Windows PowerShell 3.0 では、は、 `Disable-PSRemoting` すべてのセッション構成のセキュリティ記述子に Network_Deny_All エントリを追加します。 この設定は、他のコンピューター上のユーザーがローカルコンピューター上にユーザー管理セッションを作成できないようにしますが、ローカルコンピューターのユーザーがユーザー管理のループバックセッションを作成することを許可します。

  Windows PowerShell 2.0 で `Disable-PSRemoting` は、はと同じです `Disable-PSSessionConfiguration -Name *` 。 Windows PowerShell 3.0 以降のリリースで `Disable-PSRemoting` は、はに相当します。 `Set-PSSessionConfiguration -Name \<Configuration name\> -AccessMode Local`

## 関連リンク

[Disable-PSSessionConfiguration](Disable-PSSessionConfiguration.md)

[Enable-PSRemoting](Enable-PSRemoting.md)

[Get-PSSessionConfiguration](Get-PSSessionConfiguration.md)

[New-PSSession](New-PSSession.md)

[Register-PSSessionConfiguration](Register-PSSessionConfiguration.md)

[Set-PSSessionConfiguration](Set-PSSessionConfiguration.md)

[Unregister-PSSessionConfiguration](Unregister-PSSessionConfiguration.md)

[WSMan プロバイダー](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)
