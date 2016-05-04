---
title: 以前のバージョンの Windows で Windows PowerShell を開始する
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 57125436-3d1e-4e7f-b5c4-8f0ecb49d642
---
# 以前のバージョンの Windows で Windows PowerShell を開始する
このセクションでは、[!INCLUDE[wps_2](../Token/wps_2_md.md)] と [!INCLUDE[mshgraphicalhost](../Token/mshgraphicalhost_md.md)] を [!INCLUDE[win7_client_firstref](../Token/win7_client_firstref_md.md)]、[!INCLUDE[win7_server_firstref](../Token/win7_server_firstref_md.md)]、[!INCLUDE[lserver](../Token/lserver_md.md)] で開始する方法について説明します。 また、[!INCLUDE[psversion2](../Token/psversion2_md.md)] 内の [!INCLUDE[mshgraphicalhostshort](../Token/mshgraphicalhostshort_md.md)] のオプション機能を [!INCLUDE[win7_server_firstref](../Token/win7_server_firstref_md.md)] と [!INCLUDE[lserver](../Token/lserver_md.md)] で有効にする方法について説明します。

サポートされるシステムで [!INCLUDE[psversion4](../Token/psversion4_md.md)] をインストールするには、[Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkID=293881) をダウンロードしてインストールします。 詳しくは、「[Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md)」をご覧ください。

サポートされるシステムで [!INCLUDE[psversion3](../Token/psversion3_md.md)] をインストールするには、[Windows Management Framework 3.0](http://go.microsoft.com/fwlink/?LinkID=240290) をダウンロードしてインストールします。 詳しくは、「[Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md)」をご覧ください。

## 以前のバージョンの Windows で [!INCLUDE[mshshort](../Token/mshshort_md.md)] を開始する方法
次のいずれかの方法で、必要に応じて、[!INCLUDE[psversion3](../Token/psversion3_md.md)] や [!INCLUDE[psversion4](../Token/psversion4_md.md)] のインストールされたバージョンを開始します。

#### [スタート] メニューからの場合

-   **[スタート]** をクリックし、「**PowerShell**」と入力して **[Windows PowerShell]** をクリックします。

-   **[スタート]** メニューから、**[スタート]**、**[すべてのプログラム]**、**[アクセサリ]**、**[Windows PowerShell]** フォルダー、**[Windows PowerShell]** の順にクリックします。

#### コマンド プロンプトでの場合

-   Cmd.exe、[!INCLUDE[wps_2](../Token/wps_2_md.md)]、[!INCLUDE[wps_2](../Token/wps_2_md.md)] ISE で [!INCLUDE[wps_2](../Token/wps_2_md.md)] を開始するには、以下のように入力します。

    ```
    PowerShell
    ```

    また、PowerShell.exe プログラムのパラメーターを使って、セッションをカスタマイズできます。 詳しくは、「[PowerShell.exe コマンドラインのヘルプ](../Topic/PowerShell.exe-Command-Line-Help.md)」をご覧ください。

#### 管理特権を使う場合 ("管理者として実行")

1.  **[スタート]** をクリックし、「**PowerShell**」と入力し、**[Windows PowerShell]** を右クリックして、**[管理者として実行]** をクリックします。

## 以前のリリースの Windows で [!INCLUDE[mshgraphicalhostshort](../Token/mshgraphicalhostshort_md.md)] を開始する方法
次のいずれかの方法を使って、[!INCLUDE[mshgraphicalhostshort](../Token/mshgraphicalhostshort_md.md)] を開始します。

#### [スタート] メニューからの場合

-   **[スタート]** をクリックし、「**ISE**」と入力して **[Windows PowerShell ISE]** をクリックします。

-   **[スタート]** メニューから、**[スタート]**、**[すべてのプログラム]**、**[アクセサリ]**、**[Windows PowerShell]** フォルダー、**[Windows PowerShell ISE]** の順にクリックします。

#### コマンド プロンプトでの場合

-   Cmd.exe、[!INCLUDE[wps_2](../Token/wps_2_md.md)]、[!INCLUDE[wps_2](../Token/wps_2_md.md)] ISE で [!INCLUDE[wps_2](../Token/wps_2_md.md)] を開始するには、以下のように入力します。

    ```
    PowerShell_ISE
    ```

    または

    ```
    ISE
    ```

#### 管理特権を使う場合 ("管理者として実行")

1.  **[スタート]** をクリックし、「**ISE**」と入力し、**[Windows PowerShell ISE]** を右クリックして、**[管理者として実行]** をクリックします。

## 以前のリリースの Windows で [!INCLUDE[mshgraphicalhostshort](../Token/mshgraphicalhostshort_md.md)] を有効にする方法
[!INCLUDE[psversion4](../Token/psversion4_md.md)] と [!INCLUDE[psversion3](../Token/psversion3_md.md)] で、[!INCLUDE[mshgraphicalhostshort](../Token/mshgraphicalhostshort_md.md)] は既定ではすべてのバージョンの Windows で有効になっています。 まだ有効になっていない場合、Windows Management Framework 4.0 や [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] により有効になります。

[!INCLUDE[psversion2](../Token/psversion2_md.md)] で、[!INCLUDE[mshgraphicalhostshort](../Token/mshgraphicalhostshort_md.md)] は既定では [!INCLUDE[win7_client_secondref](../Token/win7_client_secondref_md.md)] で有効になっています。 ただし、[!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)] と [!INCLUDE[lserver](../Token/lserver_md.md)] 上では省略可能な機能です。

[!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)] や [!INCLUDE[lserver](../Token/lserver_md.md)] 上で [!INCLUDE[psversion2](../Token/psversion2_md.md)] 内の [!INCLUDE[mshgraphicalhostshort](../Token/mshgraphicalhostshort_md.md)] を有効にするには、次の手順に従います。

#### [!INCLUDE[mshgraphicalhost](../Token/mshgraphicalhost_md.md)] を有効にする方法

1.  サーバー マネージャーを起動します。

2.  **[機能]**、**[機能の追加]** の順にクリックします。

3.  [機能の選択] で、[!INCLUDE[mshgraphicalhost](../Token/mshgraphicalhost_md.md)] をクリックします。



<!--HONumber=Apr16_HO1-->


