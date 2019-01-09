---
ms.date: 08/23/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell Web Access のアンインストール
ms.openlocfilehash: 22c874d766445dccedd8494097daf16c30fa66ff
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403229"
---
# <a name="uninstall-windows-powershell-web-access"></a>Windows PowerShell Web Access をアンインストールする

更新:2013 年 6 月 24 日

適用先:Windows Server 2012 R2、Windows Server 2012

このトピックの手順で、Windows PowerShell Web Access Web サイトと該当アプリケーションがインストール先のゲートウェイ サーバーから削除されます。

## <a name="notify-users"></a>ユーザーに通知

開始する前に、Web サイトを削除することを Web ベース コンソールのユーザーに通知してください。

Windows PowerShell Web Access の実行に必要なため、Windows PowerShell Web Access をアンインストールしても、自動インストールされた IIS その他の機能はアンインストールされません。
アンインストール プロセスでは、Windows PowerShell Web Access が依存する機能はそのまま残されるため、必要に応じて手動でアンインストールしてください。

## <a name="recommended-quick-uninstallation"></a>推奨の (クイック) アンインストール

このセクションの手順では、Windows PowerShell コマンドレットを利用し、

- Windows PowerShell Web Access Web アプリケーション
- と Windows PowerShell Web Access 機能

の両方をアンインストールできます。

### <a name="step-1-delete-the-web-application-using-cmdlets"></a>手順 1:コマンドレットを使用して web アプリケーションを削除します。

1. 次のいずれかを実行して Windows PowerShell セッションを開きます。

    -   Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックします。

    -   Windows の**スタート**画面で、**[Windows PowerShell]** をクリックします。

2. 「`Uninstall-PswaWebApplication`」と入力し、**Enter** キーを押します。
   1. 独自のカスタム Web サイト名を指定した場合は、コマンドに `-WebsiteName` パラメーターを追加し、Web サイト名を指定します。

        `Uninstall-PswaWebApplication -WebsiteName <web-site-name>`
   1. (既定のアプリケーション **pswa** ではなく) カスタム Web アプリケーションを使用している場合は、コマンドに `-WebApplicationName` パラメーターを追加し、Web アプリケーションの名前を指定します。

        `Uninstall-PswaWebApplication -WebApplicationName <web-application-name>`
   1. テスト証明書使っている場合、次の例のように `DeleteTestCertificate` パラメーターをコマンドレットに追加します。

        `Uninstall-PswaWebApplication -DeleteTestCertificate`

### <a name="step-2-uninstall-windows-powershell-web-access-using-cmdlets"></a>手順 2:コマンドレットを使用して Windows PowerShell Web Access をアンインストールします。

1. 次のいずれかを実行して、管理者特権を使って Windows PowerShell セッションを開きます。 セッションを既に開いている場合は、次の手順に進んでください。

    -   Windows デスクトップで、タスク バーの **[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。

    -   Windows の**スタート**画面で、**[Windows PowerShell]** を右クリックし、**[管理者として実行]** をクリックします。

1. 次のように入力して **Enter** キーを押します。*computer_name* は、Windows PowerShell Web Access を削除するリモート サーバーです。 `-Restart` パラメーターによって、対象サーバーが自動的に再起動されます (削除で必要な場合)。

        Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -ComputerName <computer_name> -Restart

    オフライン VHD から役割と機能を削除するには、 `-ComputerName` パラメーターと `-VHD` パラメーターの両方を追加する必要があります。 `-ComputerName` パラメーターには VHD のマウント先のサーバー名が格納され、 `-VHD` パラメーターには指定したサーバー上の VHD ファイルへのパスが格納されます。

        Uninstall-WindowsFeature -Name WindowsPowerShellWebAccess -VHD <path> -ComputerName <computer_name> -Restart

1. 削除が完了したら、Windows PowerShell Web Access が削除されていることを確認します。これには、サーバー マネージャーの **[すべてのサーバー]** ページを開き、機能を削除したサーバーを選択して、選択したサーバーのページで **[役割と機能]** タイルを表示します。

    また、選択したサーバーを対象として `Get-WindowsFeature` コマンドレット (Get-WindowsFeature -ComputerName &lt;*computer_name*&gt;) を実行し、サーバーにインストールされている役割と機能の一覧を表示することもできます。

## <a name="custom-uninstallation"></a>カスタム アンインストール

このセクションの手順では、サーバー マネージャーの役割と機能の削除ウィザード、および IIS マネージャー コンソールを使用して Windows PowerShell Web Access の Web アプリケーションと Windows PowerShell Web Access 機能の両方をアンインストールできます。

### <a name="step-1-delete-the-web-application-using-iis-manager"></a>手順 1:IIS マネージャーを使用して web アプリケーションを削除します。


1. 次のいずれかの方法で IIS マネージャー コンソールを開きます。 既に開いている場合は、次の手順に進んでください。

    -   Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。 [サーバー マネージャー] の **[ツール]** メニューで **[インターネット インフォメーション サービス (IIS) マネージャー]** をクリックします。

    -   Windows の**スタート**画面で、**インターネット インフォメーション サービス (IIS) マネージャー**という名前の任意の一部を入力します。 **[アプリ]** の結果に表示されたショートカットをクリックします。

1. IIS マネージャーのツリー ウィンドウで、Windows PowerShell Web Access Web アプリケーションを実行している Web サイトを選択します。

1. **[操作]** ウィンドウの **[Web サイトの管理]** で **[停止]** をクリックします。

1. ツリー ウィンドウで、Windows PowerShell Web Access Web アプリケーションを実行している Web サイトの Web アプリケーションを右クリックして、**[削除]** をクリックします。

1. ツリー ウィンドウで **[アプリケーション プール]** を選択し、Windows PowerShell Web Access アプリケーション プールのフォルダーを選択して、**[操作]** ウィンドウの **[停止]** をクリックし、コンテンツ ウィンドウの **[削除]** をクリックします。

1. IIS マネージャーを閉じます。

> ![警告](images/SecurityNote.jpeg)**注**:
>
> アンインストールでは証明書は削除されません。
>
> 自己署名証明書を作成している場合、または使用したテスト証明書を削除する場合は、IIS マネージャーで証明書を削除できます。

### <a name="step-2-uninstall-windows-powershell-web-access-using-the-remove-roles-and-features-wizard"></a>手順 2:役割の削除と機能のウィザードを使用して Windows PowerShell Web Access のアンインストールします。

1. サーバー マネージャーを既に開いている場合は、次の手順に進んでください。 サーバー マネージャーをまだ開いていない場合は、次のいずれかの方法で開きます。

    -   Windows デスクトップで、Windows タスク バーの **[サーバー マネージャー]** をクリックし、サーバー マネージャーを開始します。

    -   Windows の**スタート**画面で、**[サーバー マネージャー]** をクリックします。

1. **[管理]** メニューの **[役割と機能の削除]** をクリックします。

1. **[対象サーバーの選択]** ページで、削除対象の機能を備えているサーバーまたはオフライン VHD を選択します。 オフライン VHD を選択するには、最初に VHD マウント先のサーバーを選択してから、VHD ファイルを選択します。 対象サーバーを選択したら、**[次へ]** をクリックします。

1. もう一度 **[次へ]** をクリックして **[機能の削除]** ページにスキップします。

1. **[Windows PowerShell Web Access]** のチェック ボックスをすべてオフにして、**[次へ]** をクリックします。

1. **[削除オプションの確認]** ページで、**[削除]** をクリックします。

## <a name="see-also"></a>参照

- [Windows PowerShell Web Access のインストールと使用](install-and-use-windows-powershell-web-access.md)
- [IIS マネージャー 7.0 ヘルプ](https://technet.microsoft.com/library/cc732664.aspx)