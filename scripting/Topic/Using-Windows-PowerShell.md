---
title: Windows PowerShell を使用する
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: cf06f1e5-3945-47e4-98be-412f5a1f43fe
---
# Windows PowerShell を使用する
[!INCLUDE[wps_1](../Token/wps_1_md.md)] は、特にシステム管理用に設計された、タスク ベースのコマンド ライン シェルおよびスクリプト言語です。 .NET Framework 上に構築された [!INCLUDE[wps_2](../Token/wps_2_md.md)] は、IT 技術者およびパワー ユーザーが Windows オペレーティング システムと Windows 上で実行するアプリケーションの管理の自動化を制御する際に役立ちます。

このセクションのリソースは、[!INCLUDE[wps_2](../Token/wps_2_md.md)] に付属する [!INCLUDE[wps_2](../Token/wps_2_md.md)] の機能と、グラフィカルな [!INCLUDE[wps_2](../Token/wps_2_md.md)] エディターである [!INCLUDE[wps_2](../Token/wps_2_md.md)] Integrated Scripting Environment について学ぶ際に役立ちます。

## このセクションの内容
このセクションの内容は、[!INCLUDE[wps_2](../Token/wps_2_md.md)] についての詳細、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の使用方法、および最新のリリースにおける [!INCLUDE[wps_2](../Token/wps_2_md.md)] の新機能を確認する際に役立ちます。

-   [Windows PowerShell の新機能](../Topic/What-s-New-in-Windows-PowerShell.md)。 このトピックでは、[!INCLUDE[wps_2](../Token/wps_2_md.md)] 3.0 および [!INCLUDE[wps_2](../Token/wps_2_md.md)] 4.0 の変更点について説明しています。

-   [Windows PowerShell ファースト ステップ ガイド](../Topic/Getting-Started-with-Windows-PowerShell.md)。 サポートするすべてのオペレーティング システムに [!INCLUDE[wps_2](../Token/wps_2_md.md)] をインストールし、起動するためのシステム要件と使用説明を含む概要とチュートリアルです。

-   [Windows PowerShell ユーザー ガイド](../Topic/Windows-PowerShell-User-s-Guide.md)。 使用を開始するための実際のスクリプトとシナリオを含む詳しい概要です。

-   [Windows PowerShell Integrated Scripting Environment (ISE)](../Topic/Windows-PowerShell-Integrated-Scripting-Environment--ISE-.md)。 グラフィカルな [!INCLUDE[wps_2](../Token/wps_2_md.md)] のスクリプト エディターとコンソールである [!INCLUDE[wps_2](../Token/wps_2_md.md)] ISE のドキュメントです。

-   [Windows PowerShell Desired State Configuration (DSC) の概要](assetId:///04c9e716-822c-40f0-8fdf-f2dda8abd888)。 [!INCLUDE[wps_2](../Token/wps_2_md.md)] 4.0、Windows PowerShell Desired State Configuration (DSC) の新機能の概要です。 DSC は、管理者が Windows 環境、およびネットワーク スイッチなどのデバイスで一貫した構成を実現する際に役立ちます。

-   [PowerShell.exe コマンドラインのヘルプ](../Topic/PowerShell.exe-Command-Line-Help.md)。 Windows のコマンド プロンプトから [!INCLUDE[wps_2](../Token/wps_2_md.md)] を起動し、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の基本的なコマンドを実行する方法です。

-   [Windows PowerShell 用語集](../Topic/Windows-PowerShell-Glossary.md)。 [!INCLUDE[wps_2](../Token/wps_2_md.md)] とそのドキュメントで使用する一般的な用語について説明しています。

## 関連テクノロジ
[!INCLUDE[wps_2](../Token/wps_2_md.md)] は、Windows ベースのコンピューターのリモート管理の自動化に役立つ関連するスクリプト テクノロジのファミリーの一部です。 これらのテクノロジに関する詳細情報へのリンクがここにあります。

-   [Windows PowerShell ワークフロー](http://technet.microsoft.com/library/jj134242.aspx)。 [!INCLUDE[psversion3](../Token/psversion3_md.md)] で初めて導入された、[!INCLUDE[wps_2](../Token/wps_2_md.md)] ワークフローを使用すると、IT 技術者と開発者は、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の自動化機能と使いやすさにより、[Windows Workflow Foundation](http://msdn.microsoft.com/library/ee342461.aspx) の利点を活用できます。

-   [Windows PowerShell Web Access](http://technet.microsoft.com/library/hh831611.aspx)。 [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] で初めて導入された [!INCLUDE[wps_2](../Token/wps_2_md.md)] Web Access は、[!INCLUDE[wps_2](../Token/wps_2_md.md)] ゲートウェイとして機能し、リモート コンピューターを対象とした Web ベースの [!INCLUDE[wps_2](../Token/wps_2_md.md)] コンソールを提供します。 これにより、IT 技術者は [!INCLUDE[wps_2](../Token/wps_2_md.md)] のコマンドとスクリプトを Web ブラウザーの [!INCLUDE[wps_2](../Token/wps_2_md.md)] コンソールから実行できます。クライアント デバイスに [!INCLUDE[wps_2](../Token/wps_2_md.md)]、リモート管理ソフトウェア、またはブラウザーのプラグインをインストールする必要はありません。

-   [Windows PowerShell Web サービス (Management OData IIS 拡張機能)](http://msdn.microsoft.com/library/windows/desktop/hh880865.aspx)。 [!INCLUDE[wps_2](../Token/wps_2_md.md)] Web サービスは、Web サーバー (IIS) で実行している OData ベースの Web サービスを介して簡単に [!INCLUDE[wps_2](../Token/wps_2_md.md)] コマンドレットを公開できるフレームワークです。

-   [Windows PowerShell Desired State Configuration ファースト ステップ ガイド](assetId:///c134aa32-b085-4656-9a89-955d8ff768d0)。 [!INCLUDE[wps_2](../Token/wps_2_md.md)] Desired State Configuration (DSC) は、[!INCLUDE[psversion4](../Token/psversion4_md.md)] で導入された、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の新しい管理プラットフォームであり、ソフトウェア サービスとそれらの実行環境向けに構成データの展開と管理を実行できます。 DSC は、ソフトウェア環境の状態をどのように構成するかを宣言によって指定するために使用する、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の言語拡張機能、新しいコマンドレット、およびリソースのセットです。

-   [Windows Management Framework 4.0 プレビュー](http://go.microsoft.com/fwlink/?LinkID=293881)には、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の更新プログラム、[!INCLUDE[wps_2](../Token/wps_2_md.md)] ISE、[!INCLUDE[wps_2](../Token/wps_2_md.md)] Web サービス (Management OData IIS 拡張機能)、Windows リモート管理 (WinRM)、Windows Management Infrastructure (WMI)、サーバー マネージャーの WMI プロバイダー、および 4.0 の新機能である [!INCLUDE[wps_2](../Token/wps_2_md.md)] Desired State Configuration (DSC) などがあります。 Windows Management Framework 4.0 プレビューを使用すると、[!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)]、[!INCLUDE[win7_client_firstref](../Token/win7_client_firstref_md.md)] SP1、および [!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)] SP1 を実行するコンピューターにこれらのテクノロジをインストールして使用できます。

-   [Windows Management Framework 3.0](http://www.microsoft.com/download/details.aspx?id=34595) には、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の更新プログラム、[!INCLUDE[wps_2](../Token/wps_2_md.md)] ISE、[!INCLUDE[wps_2](../Token/wps_2_md.md)] Web サービス (Management OData IIS の拡張機能)、Windows リモート管理 (WinRM)、Windows Management Infrastructure (WMI)、およびサーバー マネージャーの WMI プロバイダーが含まれています。 Windows Management Framework 3.0 を使用すると、[!INCLUDE[win7_client_firstref](../Token/win7_client_firstref_md.md)] SP1、Windows Server 2008 SP2、および [!INCLUDE[win7_server_secondref](../Token/win7_server_secondref_md.md)] SP1 を実行するコンピューターにこれらのテクノロジをインストールして使用できます。

## Windows PowerShell について学習する
[!INCLUDE[wps_2](../Token/wps_2_md.md)] の学習を開始するには、まず次のリソースを使用してください。

-   [Microsoft Virtual Academy: PowerShell 3.0 ファースト ステップ ガイド ジャンプ スタート](http://www.microsoftvirtualacademy.com/training-courses/advanced-tools-scripting-with-powershell-3-0-jump-start)。 このジャンプ スタートは、忙しい IT 技術者、管理者、およびヘルプ デスクのスタッフが、[!INCLUDE[wps_2](../Token/wps_2_md.md)] を使用して管理機能を向上させ、冗長なタスクを自動化し、環境の規模を管理する方法を学べるように作られています。 [!INCLUDE[wps_2](../Token/wps_2_md.md)] の動作および [!INCLUDE[wps_2](../Token/wps_2_md.md)] を動作させる方法を、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の発明者 Jeffrey Snover 氏、Concentrated Technology のシニア テクノロジスト Jason Helmick 氏などの専門家から学びます。

-   [Microsoft Virtual Academy: PowerShell 3.0 の高度なツールとスクリプトのジャンプ スタート](http://www.microsoftvirtualacademy.com/training-courses/getting-started-with-powershell-3-0-jump-start)。 IT 技術者は、この [!INCLUDE[wps_2](../Token/wps_2_md.md)] の上級コースを受講して、リアルタイム管理と自動化スクリプトを便利で再利用可能なツールとコマンドレットに変える方法を見つけてください。 ツールのビルドとメンテナンスの最適なパターンとベスト プラクティスを学習するとともに、至るところで [!INCLUDE[wps_2](../Token/wps_2_md.md)] の事業計画担当者兼発明者である上級エンジニア Jeffrey Snover 氏および IT 技術者 Jason Helmick 氏からの特別なヒントとトリックを修得することができます。

-   [Windows PowerShell ファースト ステップ ガイド](../Topic/Getting-Started-with-Windows-PowerShell.md)。 サポートするすべてのオペレーティング システムに [!INCLUDE[wps_2](../Token/wps_2_md.md)] をインストールし、起動するためのシステム要件と使用説明を含む概要とチュートリアルです。

-   [Windows PowerShell ユーザー ガイド](../Topic/Windows-PowerShell-User-s-Guide.md)。 使用を開始するための実際のスクリプトとシナリオを含む詳しい概要です。

-   [Windows PowerShell コア モジュールの参照](http://technet.microsoft.com/library/hh847741(v=wps.630).aspx) [!INCLUDE[wps_2](../Token/wps_2_md.md)] エンジンの一部として含まれる言語機能とコマンドレットのヘルプ トピックをアルファベット順にした一覧です。

-   [Windows PowerShell を使用した Windows および Windows Server の自動化](http://technet.microsoft.com/library/dn249523.aspx)。 Windows Server および Windows クライアントに搭載された機能またはサーバーの役割の一部として含まれる [!INCLUDE[wps_2](../Token/wps_2_md.md)] モジュールのヘルプ トピックをアルファベット順にした一覧です。

-   [Windows PowerShell を使用した System Center の自動化 ](https://technet.microsoft.com/en-us/library/mt156962.aspx)。 Microsoft System Center のコンポーネントに付属する [!INCLUDE[wps_2](../Token/wps_2_md.md)] モジュールのヘルプ トピックをアルファベット順にした一覧です。

## Windows PowerShell のヘルプをダウンロードおよび更新する
以下のトピックは、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の最新のヘルプを取得し、[!INCLUDE[wps_2](../Token/wps_2_md.md)] のコマンド プロンプトで表示する方法について説明しています。

-   [Update-Help](http://technet.microsoft.com/library/hh849720.aspx) コマンドレット。 ご使用のコンピューターに [!INCLUDE[wps_2](../Token/wps_2_md.md)] モジュールのヘルプ トピックの最新バージョンをダウンロードし、インストールする [!INCLUDE[wps_2](../Token/wps_2_md.md)] コマンドレットです。

    ネットワークから分離されたコンピューターに更新可能なヘルプをインストールする方法を含む、[!INCLUDE[wps_2](../Token/wps_2_md.md)] の更新可能なヘルプ システムの詳細については、「[about_Updatable_Help](http://technet.microsoft.com/library/hh847735.aspx)」、「[Save-Help](http://technet.microsoft.com/library/hh849724.aspx)」、および「[更新可能なヘルプをサポートする](http://msdn.microsoft.com/library/hh852754.aspx)」を参照してください。

-   [Get-Help](http://technet.microsoft.com/library/hh849696(v=wps.630).aspx) コマンドレット。 システムにインストールされているコマンドレットとプロバイダーについて確認するために使用する [!INCLUDE[wps_2](../Token/wps_2_md.md)] コマンドレットです。

-   公開されたヘルプ ファイルの更新に関する通知を受け取るには、次の RSS フィードを購読してください。[http://sxp.microsoft.com/feeds/msdntn/PowerShellHelpVersions](http://sxp.microsoft.com/feeds/msdntn/PowerShellHelpVersions)



<!--HONumber=Apr16_HO1-->


