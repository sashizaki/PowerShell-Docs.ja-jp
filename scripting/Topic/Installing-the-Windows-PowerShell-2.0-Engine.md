---
title: Windows PowerShell 2.0 エンジンのインストール
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 82928f2b-f96a-4ae6-a0d0-6e7b181da308
---
# Windows PowerShell 2.0 エンジンのインストール
このトピックでは、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンをインストールする方法について説明します。

[!INCLUDE[psversion3](../Token/psversion3_md.md)] は、[!INCLUDE[psversion2](../Token/psversion2_md.md)] との下位互換性を保つように設計されています。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] 用に記述されたコマンドレット、プロバイダー、スナップイン、モジュール、およびスクリプトは、未変更のまま [!INCLUDE[psversion3](../Token/psversion3_md.md)] と [!INCLUDE[psversion4](../Token/psversion4_md.md)] で実行できます。 ただし、Microsoft .NET Framework 4 でランタイムのアクティブ化ポリシーが変更されたため、[!INCLUDE[psversion2](../Token/psversion2_md.md)] 用に作成され、共通言語ランタイム (CLR) 2.0 でコンパイルされた Windows PowerShell ホスト プログラムは、変更を加えなければ新しいリリースの [!INCLUDE[wps_2](../Token/wps_2_md.md)] (CLR 4.0 でコンパイルされたもの) で実行できません。

これらの変更の影響を受けるコマンドやホスト プログラムとの下位互換性を維持するため、[!INCLUDE[psversion2](../Token/psversion2_md.md)]、[!INCLUDE[psversion3](../Token/psversion3_md.md)]、および [!INCLUDE[psversion4](../Token/psversion4_md.md)] のエンジンは、side-by-side で実行できるように設計されています。 さらに、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンは、[!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)]、[!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)]、[!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)]、[!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)]、および [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] にも組み込まれています。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンは、[!INCLUDE[psversion3](../Token/psversion3_md.md)]、[!INCLUDE[psversion4](../Token/psversion4_md.md)]、または Microsoft .NET Framework 4 との互換性がないために既存のスクリプトまたはホスト プログラムを実行できない場合にのみ使用することを目的としています。 そのようなケースはまれであると思われます。

[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンは、[!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)]、[!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)]、[!INCLUDE[win8_client_1](../Token/win8_client_1_md.md)]、および [!INCLUDE[win8_server_1](../Token/win8_server_1_md.md)] のオプション機能です。 以前のバージョンの Windows に [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] をインストールすると、[!INCLUDE[wps_2](../Token/wps_2_md.md)] インストール ディレクトリ内で [!INCLUDE[psversion2](../Token/psversion2_md.md)] インストールが [!INCLUDE[psversion3](../Token/psversion3_md.md)] インストールによって完全に置き換えられます。 ただし、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンは保持されます。

[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの開始に関する情報については、「[Windows PowerShell 2.0 エンジンの開始](../Topic/Starting-the-Windows-PowerShell-2.0-Engine.md)」をご覧ください。

## [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] と [!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)] の場合
この [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] と [!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)] では、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの機能が既定でオンになっています。 ただし、この機能を使うには、この機能に必要な Microsoft .NET Framework 3.5 オプションをオンにする必要があります。 このセクションでは、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの機能をオンまたはオフにする方法についても説明します。

#### .NET Framework 3.5 をオンにするには

1.  **[スタート]** 画面で、「**Windows の機能**」と入力します。

2.  **アプリ** バーで、**[設定]** をクリックしてから、**[Windows の機能の有効化または無効化]** をクリックします。

3.  **[Windows の機能]** ボックスで、**[.NET Framework 3.5 (.NET 2.0 および 3.0 を含む)]** をオンにします。

    **[.NET Framework 3.5 (.NET 2.0 および 3.0 を含む)]** を選択すると、ボックスが塗りつぶされて、機能の一部のみが選択された状態になります。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの場合は、この状態で十分です。

#### [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンをオンまたはオフにするには

1.  **[スタート]** 画面で、「**Windows の機能**」と入力します。

2.  **アプリ** バーで、**[設定]** をクリックしてから、**[Windows の機能の有効化または無効化]** をクリックします。

3.  **[Windows の機能]** ボックスで、**[[!INCLUDE[psversion2](../Token/psversion2_md.md)]]** ノードを展開し、**[[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジン]** ボックスをクリックして、オンまたはオフにします。

## [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)] と [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] の場合
次の手順を実行して、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンと Microsoft .NET Framework 3.5 の機能を追加します。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンには最低でも Microsoft .NET Framework 2.0.50727 が必要です。 この要件は Microsoft .NET Framework 3.5 で満たされます。

#### .NET Framework 3.5 の機能を追加するには

1.  **サーバー マネージャー**で、**[管理]** メニューから **[役割と機能の追加]** を選びます。

    または、**サーバー マネージャー**で、**[すべてのサーバー]** をクリックし、サーバー名を右クリックしてから、**[役割と機能の追加]** を選びます。

2.  **[インストールの種類]** ページで **[役割ベースまたは機能ベースのインストール]** を選びます。

3.  **[機能]** ページで、**[.NET 3.5 Framework 機能]** ノードを展開し、**[.NET Framework 3.5 (.NET 2.0 および 3.0 を含む)]** を選びます。

    このノードの下にあるその他のオプションは、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンには必要ありません。

#### [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの機能を追加するには

-   **サーバー マネージャー**で、**[管理]** メニューから **[役割と機能の追加]** を選びます。

    または、**サーバー マネージャー**で、**[すべてのサーバー]** をクリックし、サーバー名を右クリックしてから、**[役割と機能の追加]** を選びます。

-   **[インストールの種類]** ページで **[役割ベースまたは機能ベースのインストール]** を選びます。

-   **[機能]** ページで、**[[!INCLUDE[mshshort](../Token/mshshort_md.md)] (インストール済み)]** ノードを展開し、**[[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジン]** を選びます。

[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンの開始に関する情報については、「[Windows PowerShell 2.0 エンジンの開始](../Topic/Starting-the-Windows-PowerShell-2.0-Engine.md)」をご覧ください。

## 以前のシステムの場合
[!INCLUDE[psversion4](../Token/psversion4_md.md)] を [!INCLUDE[win7_client_secondref](../Token/win7_client_secondref_md.md)]、[!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)]、および [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] にインストールする [Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkID=293881) パッケージに、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンが組み込まれています。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンは有効になっており、使用準備が整っていますので、追加のインストールや、セットアップ、構成は必要ありません。

[!INCLUDE[psversion3](../Token/psversion3_md.md)] を [!INCLUDE[win7_client_secondref](../Token/win7_client_secondref_md.md)]、[!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)]、および [!INCLUDE[lserver](../Token/lserver_md.md)] にインストールする [!INCLUDE[ps_wmf_3.0](../Token/ps_wmf_3.0_md.md)] パッケージに、[!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンが組み込まれています。 [!INCLUDE[psversion2](../Token/psversion2_md.md)] エンジンは有効になっており、使用準備が整っていますので、追加のインストールや、セットアップ、構成は必要ありません。

## 参照
[Windows PowerShell のシステム要件](../Topic/Windows-PowerShell-System-Requirements.md)
[Windows PowerShell のインストール](../Topic/Installing-Windows-PowerShell.md)
[Windows PowerShell [ps] の開始](assetId:///8ec8c2d7-8e7c-4722-a3d2-498fe5739a8e)
[Windows PowerShell 2.0 エンジンを開始する](../Topic/Starting-the-Windows-PowerShell-2.0-Engine.md)



<!--HONumber=Apr16_HO1-->


