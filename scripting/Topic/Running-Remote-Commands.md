---
title: リモート コマンドの実行
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: d6938b56-7dc8-44ba-b4d4-cd7b169fd74d
---
# リモート コマンドの実行
1 つの Windows PowerShell コマンドを使用し、1 台から数百台のコンピューターでコマンドを実行できます。 Windows PowerShell は、WMI、RPC、WS-Management など、さまざまなテクノロジを使用してリモート コンピューティングをサポートします。

## 設定をしないリモート処理
多くの Windows PowerShell コマンドレットは、1 台以上のリモート コンピューターのデータの収集や設定の変更が可能な ComputerName パラメーターを持っています。 Windows PowerShell がサポートするすべての Windows オペレーティング システムのさまざまな通信テクノロジや多くの作業を、特別な構成なしで利用します。

これらのコマンドレットには、次のものがあります。

-   [Restart-Computer](assetId:///bd52bcf6-80ee-4866-9320-04ee1d1dca4a)

-   [Test-Connection](assetId:///87d293e5-10e2-489b-b0a9-922d77c05f3f)

-   [Clear-EventLog](assetId:///05d0de31-3c9d-4cd6-8e1a-dac19835464c)

-   [Get-EventLog [m2]](assetId:///a4372a60-b7d9-4b1c-a268-aa5240300141)

-   [Get-Hotfix](assetId:///e1ef636f-5170-4675-b564-199d9ef6f101)

-   [Get-Process [m2]](assetId:///27a05dbd-4b69-48a3-8d55-b295f6225f15)

-   [Get-Service [m2]](assetId:///0a09cb22-0a1c-4a79-9851-4e53075f9cf6)

-   [Set-Service [m2]](assetId:///b71e29ed-372b-4e32-a4b7-5eb6216e56c3)

-   [Get-WinEvent](assetId:///e1ef636f-5170-4675-b564-199d9ef6f101)

-   [Get-WmiObject [m2]](assetId:///a4c499fa-deec-4c4b-b3fb-6e195d48a396)

通常、特別な構成なしでリモート処理をサポートするコマンドレットは、ComputerName パラメーターを指定し、Session パラメーター必要はありません。 セッションでこれらのコマンドレットを見つけるには、次のように入力します。

```
get-command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## Windows PowerShell のリモート処理
Windows PowerShell のリモート処理では、WS-Management プロトコルを使用し、1 台以上のリモート コンピューターで Windows PowerShell コマンドを実行できます。 これにより、永続的な接続の確立、1:1 対話型のセッションの開始、および複数のコンピューターでのスクリプトの実行が可能になります。

Windows PowerShell のリモート処理を使用するには、リモート管理のためにリモート コンピューターを構成する必要があります。 手順を含む詳細については、「[about_Remote_Requirements](assetId:///da213949-134c-4741-b307-81f4492ba1bd)」を参照してください。

Windows PowerShell のリモート処理を構成した後は、多くのリモート処理の戦略が使用可能になります。 このドキュメントの残りの部分では、その一部だけを取り上げます。 詳細については、「[about_Remote](assetId:///9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)」と「[about_Remote_FAQ](assetId:///e23702fd-9415-4a98-9975-390a4d3adc42)」を参照してください。

### 対話型セッションの開始
1 台のリモート コンピューターとの対話型セッションを開始するには、[Enter-PSSession](assetId:///f4fd89b4-80e9-434e-bd46-952aa8d40d4c) コマンドレットを使用します。 たとえば、Server01 リモート コンピューターと対話型セッションを開始するには、次のように入力します。

```
enter-pssession Server01
```

コマンド プロンプトが、接続しているコンピューターの名前を表示するよう変更されます。 これ以降、プロンプトで入力したコマンドはリモート コンピューターで実行され、結果はローカル コンピューターに表示されます。

対話型セッションを終了するには、次のように入力します。

```
exit-pssession
```

Enter-PSSession コマンドレットと Exit-PSSession コマンドレットの詳細については、「[Enter-PSSession](assetId:///f4fd89b4-80e9-434e-bd46-952aa8d40d4c)」と「[Exit-PSSession](assetId:///b6daa1ce-48a5-41a3-ac4b-b64dbe03465d)」を参照してください。

### リモート コマンドの実行
1 台以上のリモート コンピューターでいずれかのコマンドを実行するには、[Invoke-Command](assetId:///22fd98ba-1874-492e-95a5-c069467b8462) コマンドレットを使用します。 たとえば、[Get-UICulture [m2]](assetId:///99175c2e-e856-4208-970e-3dd2f6bac5b8) コマンドをリモート コンピューター Server01 と Server02 で実行するには、次のように入力します。

```
invoke-command -computername Server01, Server02 {get-UICulture}
```

コンピューターに出力が返されます。

```
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```

Invoke-Command コマンドレットの詳細については、「[Invoke-Command](assetId:///22fd98ba-1874-492e-95a5-c069467b8462)」を参照してください。

### スクリプトの実行
1 台以上のリモート コンピューターでスクリプトを実行するには、Invoke-Command コマンドレットの FilePath パラメーターを使用します。 スクリプトがローカル コンピューターでアクセス可能でなければなりません。 結果はローカル コンピューターに返されます。

たとえば、次のコマンドは、リモート コンピューター Server01 と Server02 で DiskCollect.ps1 スクリプトを実行します。

```
invoke-command -computername Server01, Server02 -filepath c:\Scripts\DiskCollect.ps1
```

Invoke-Command コマンドレットの詳細については、「[Invoke-Command](assetId:///22fd98ba-1874-492e-95a5-c069467b8462)」を参照してください。

### 永続的な接続の確立
データを共有する一連の関連コマンドを実行するには、リモート コンピューターでセッションを作成し、Invoke-Command コマンドレットを使用して作成したセッションでコマンドを実行します。 リモート セッションを作成するには、New-PSSession コマンドレットを使用します。

たとえば、次のコマンドは、コンピューター Server01 でリモート セッションを作成し、コンピューター Server02 で別のリモート セッションを作成します。 セッション オブジェクトは $s 変数に保存されます。

```
$s = new-pssession -computername Server01, Server02
```

セッションが確立されたので、それらで任意のコマンドを実行できます。 また、セッションは永続的であるため、1 つのコマンドでデータを収集し、後続のコマンドで利用することができます。

たとえば、次のコマンドは $s 変数のセッションで Get-Hotfix コマンドを実行し、結果を $h 変数に保存します。 $h 変数は $s のそれぞれのセッションで作成されますが、ローカル セッションには存在しません。

```
invoke-command -session $s {$h = get-hotfix}
```

これで、次のように、後続のコマンドで $h 変数のデータを使用できます。 結果はローカル コンピューターに表示されます。

```
invoke-command -session $s {$h | where {$_.installedby -ne "NTAUTHORITY\SYSTEM"
```

### 高度なリモート処理
Windows PowerShell のリモート管理はこれだけではありません。 Windows PowerShell と共にインストールされるコマンドレットを使用して、ローカルとリモートの両側からのリモート セッションの確立と構成、カスタマイズおよび制限されたセッションの作成、リモート セッションで実際に暗黙的に実行されるコマンドのリモート セッションからのユーザーによるインポート、リモート セッションのセキュリティの構成など、さまざまな処理を実行できます。

リモートの構成を容易にするために、Windows PowerShell には WSMan プロバイダーが含まれます。 プロバイダーが作成する WSMAN: ドライブでは、ローカル コンピューターとリモート コンピューターの構成設定の階層内を移動できます。 WSMan プロバイダーの詳細については、「[WSMan プロバイダー](assetId:///66fe1241-e08f-49ca-832f-a84c33ca8735)」と「[about_WS-Management_Cmdlets](assetId:///6ed3370a-ea10-45a5-9493-696aeace27ed)」を参照するか、Windows PowerShell コンソールで "get-help wsman" と入力してください。

詳細については、「[about_Remote_FAQ](assetId:///e23702fd-9415-4a98-9975-390a4d3adc42)」、「[Register-PSSessionConfiguration](assetId:///af68867a-d201-4b19-a1de-594015ed8a25)」および「[Import-PSSession](assetId:///048c115e-a6fb-4e0d-8cea-c5ca24630c9d)」を参照してください。 リモート処理のエラーに関するヘルプは、「[about_Remote_Troubleshooting](assetId:///2f890148-8578-49ed-85ea-79a489dd6317)」を参照してください。

## 参照
[about_Remote に関するページ](assetId:///9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)
[about_Remote_FAQ](assetId:///e23702fd-9415-4a98-9975-390a4d3adc42)
[about_Remote_Requirements](assetId:///da213949-134c-4741-b307-81f4492ba1bd)
[about_Remote_Troubleshooting](assetId:///2f890148-8578-49ed-85ea-79a489dd6317)
[about_PSSessions](assetId:///7a9b4e0e-fa1b-47b0-92f6-6e2995d70acb)
[about_WS-Management_Cmdlets](assetId:///6ed3370a-ea10-45a5-9493-696aeace27ed)
[Invoke-Command](assetId:///22fd98ba-1874-492e-95a5-c069467b8462)
[Import-PSSession](assetId:///048c115e-a6fb-4e0d-8cea-c5ca24630c9d)
[New-PSSession](assetId:///59452f12-a11d-4558-99ea-e6ca6ad5ffd3)
[Register-PSSessionConfiguration](assetId:///af68867a-d201-4b19-a1de-594015ed8a25)
[WSMan プロバイダー](assetId:///66fe1241-e08f-49ca-832f-a84c33ca8735)



<!--HONumber=Apr16_HO1-->


