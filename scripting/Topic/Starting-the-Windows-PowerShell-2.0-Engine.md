---
title: Windows PowerShell 2.0 エンジンの開始
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: edafc2fa-7576-49c2-bbba-9336f4bcfc28
---
# Windows PowerShell 2.0 エンジンの開始
このセクションでは、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンが組み込まれている [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)]、[!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)]、[!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)]、[!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] で、および [!INCLUDE[psversion2](../Token/psversion2_md.md)]、[!INCLUDE[psversion3](../Token/psversion3_md.md)]、[!INCLUDE[psversion4](../Token/psversion4_md.md)] がインストールされている他のシステムで、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを起動する方法を説明します。

[!INCLUDE[psversion4](../Token/psversion4_md.md)] と [!INCLUDE[psversion3](../Token/psversion3_md.md)] は、[!INCLUDE[psversion2](../Token/psversion2_md.md)] と下位互換性を保つように設計されています。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] 用に記述されたコマンドレット、プロバイダー、スナップイン、モジュール、スクリプトは、未変更のまま [!INCLUDE[psversion4](../Token/psversion4_md.md)] と [!INCLUDE[psversion3](../Token/psversion3_md.md)] で実行できます。 ただし、Microsoft .NET Framework 4 のランタイムのアクティブ化ポリシーの変更のため、[!INCLUDE[psversion2](../Token/psversion2_md.md)] 用に作成され共通言語ランタイム (CLR) 2.0 でコンパイルされた [!INCLUDE[wps_2](../Token/wps_2_md.md)] ホスト プログラムは、変更を加えなければ [!INCLUDE[psversion3](../Token/psversion3_md.md)] または [!INCLUDE[psversion4](../Token/psversion4_md.md)] (CLR 4.0 でコンパイル) で実行できません。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンは、既存のスクリプトまたはホスト プログラムが [!INCLUDE[psversion4](../Token/psversion4_md.md)]、[!INCLUDE[psversion3](../Token/psversion3_md.md)]、Microsoft .NET Framework 4 との互換性がないために実行できない場合に限り使用することを意図しています。 そのようなケースはまれと考えられます。

[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを必要とする多くのプログラムは、エンジンを自動的に起動します。 次の手順は、エンジンを手動で起動する必要のあるまれな状況のためのものです。

## 必要なプログラムのインストールと有効化
[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを起動する前に、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンと Microsoft .NET Framework 3.5 Service Pack 1 を有効にします。 方法については、「[Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md)」をご覧ください。

[Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkID=293881) または [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] がインストールされているシステムには、すべての必要なコンポーネントが揃っています。 これ以上の構成は必要ありません。 [Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkID=293881) または [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] のインストール方法の詳細については、「[Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md)」をご覧ください。

## [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの起動方法
[!INCLUDE[mshshort](../Token/mshshort_md.md)] を起動すると、既定で最新バージョンが起動します。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンで [!INCLUDE[mshshort](../Token/mshshort_md.md)] を起動するには、PowerShell.exe の Version パラメーターを使用します。 コマンドは、Windows PowerShell と Cmd.exe を含む任意のコマンド プロンプトで実行できます。

```
PowerShell.exe -Version 2
```

## [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを使ったリモート セッションの開始方法
リモート セッションで [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを実行するには、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを読み込むリモート コンピューターでセッション構成 ("エンドポイント" とも呼ばれる) を作成します。 セッション構成は、リモート コンピューターに保存され、許可されているユーザーは誰でもそれを使って [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを使用するセッションを作成できます。

これは、通常システム管理者によって実行される高度なタスクです。

次の手順では、[Register-PSSessionConfiguration](assetId:///e9152ae2-bd6d-4056-9bc7-dc1893aa29ea) コマンドレットの **PSVersion** パラメーターを使用して、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを使用するセッション構成を作成します。 [New-PSSessionConfigurationFile](assetId:///5f3e3633-6e90-479c-aea9-ba45a1954866) コマンドレットの **PowerShellVersion** パラメーターを使用して、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを読み込むセッションのセッション構成ファイルを作成することも、[Set-PSSessionConfiguration](assetId:///b21fbad3-1759-4260-b206-dcb8431cd6ea) パラメーターの **PSVersion** パラメーターを使用して、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを使用するようにセッション構成を変更することもできます。

セッション構成ファイルの詳細については、「[about_Session_Configuration_Files](assetId:///c7217447-1ebf-477b-a8ef-4dbe9a1473b8)」をご覧ください。セットアップとセキュリティを含むセッション構成の詳細については、「[about_Session_Configurations [v4]](assetId:///a2fbe12a-350c-4d04-be50-24102824e3ab)」をご覧ください。

#### リモート [!INCLUDE[psversion2](../Token/psversion2_md.md)] セッションを開始するには

1.  [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを必要とするセッション構成を作成するには、**PSVersion** パラメーターに値 "2.0" を指定して [Register-PSSessionConfiguration](assetId:///e9152ae2-bd6d-4056-9bc7-dc1893aa29ea) コマンドレットを使用します。 接続の "サーバー側" (受信側) にあるコンピューターでこのコマンドを実行します。

    次のサンプル コマンドは、Server01 コンピューター上に PS2 セッション構成を作成します。 このコマンドを実行するには、**[管理者として実行]** オプションを使用して [!INCLUDE[psversion4](../Token/psversion4_md.md)] または [!INCLUDE[psversion3](../Token/psversion3_md.md)] を起動します。

    ```
    Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
    ```

2.  PS2 セッション構成を使用する Server01 コンピューターでセッションを作成するには、リモート セッションを作成するコマンドレット ([New-PSSession](assetId:///76f6628c-054c-4eda-ba7a-a6f28daaa26f) コマンドレットなど) の **ConfigurationName** パラメーターを使用します。

    セッション構成を使用するセッションを開始すると、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンが自動的にセッションに読み込まれます。

    次のコマンドは、PS2 セッション構成を使用する Server01 コンピューターでセッションを開始します。 このコマンドは、セッションを $s 変数に保存します。

    ```
    $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
    ```

## [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを使ってバックグラウンド ジョブを開始する方法
[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを使ってバックグラウンド ジョブを開始するには、[Start-Job](assetId:///2bc04935-0deb-4ec0-b856-d7290cca6442) コマンドレットの **PSVersion** パラメーターを使用します。

次のコマンドは、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンを使ってバックグラウンド ジョブを開始します。

```
Start-Job {Get-Process} -PSVersion 2.0
```

バックグラウンド ジョブの詳細については、「[about_Jobs [v4]](assetId:///7362512a-8a4e-4575-b2ea-a740e5c4f002)」をご覧ください。



<!--HONumber=Apr16_HO1-->


