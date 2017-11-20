---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "Windows PowerShell を使用する準備を行う"
ms.assetid: 6dc7052d-cc5a-4220-950f-98f963a2b587
ms.openlocfilehash: de09c74e938f11a130864b1620d6c169006a27be
ms.sourcegitcommit: 4807ab554d55fdee499980835bcc279368b1df68
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="getting-ready-to-use-windows-powershell"></a>Windows PowerShell を使用する準備を行う
Windows PowerShell をインストールして起動したら、次のセットアップ オプションを実行することを検討してください。 これらのタスクは、いつでも実行できます。

- **ヘルプ ファイルをインストールします。** Windows PowerShell 3.0 に含まれているコマンドレットには、ヘルプ ファイルが付属していません。 ただし、[Update-Help](/powershell/module/microsoft.powershell.core/update-help) コマンドレットを使うと、最新のヘルプ ファイルをダウンロードしてコンピューターにインストールできます。 ファイルをインストールしたら、[Get-Help](/powershell/module/microsoft.powershell.core/get-help) コマンドレットを使ってコマンド ラインに表示します。 詳しくは、「[about_Updatable_Help](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」をご覧ください。

    ヘルプ ファイルをインストールしない場合でも、ヘルプ トピックをオンラインで読むことができます。 特定のコマンドレットのオンライン バージョンのヘルプ トピックを見つけるには、「`Get-Help <CmdletName> -Online`」と入力します。 Windows PowerShell のヘルプ トピックを参照する場合は、[PowerShell のドキュメント](/powershell/scripting)を参照してください。

- **スクリプトを実行します。** Windows PowerShell のセキュリティを維持するために、Windows PowerShell の既定の実行ポリシーは **制限あり** になっています。 このポリシーによると、コマンドレットは実行できますが、スクリプトは実行できません。 スクリプトを実行するには、[Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) コマンドレットを使用して、実行ポリシーを **AllSigned** または **RemoteSigned** に変更します。 コンピューターの Administrators グループのメンバーだけが、このコマンドレットを実行できます。 詳細については、「[about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies)」を参照してください。

- **リモート処理を有効にします。** システムは、他のコンピューターでリモート コマンドを実行できるように既に構成されています。 Windows Server 2012 R2 と Windows Server 2012 では、システムはリモート コマンドを受信できるようにも構成されています。つまり、他のコンピューターがローカル コンピューターでリモート コマンドを実行できるようになっています。 Windows の他のバージョンを実行しているコンピューターがリモート コマンドを受信できるようにするには、リモートから管理するコンピューター上で [Enable-PSRemoting](/powershell/module/microsoft.powershell.core/enable-psremoting) コマンドレットを実行します。 コンピューターの Administrators グループのメンバーだけが、このコマンドレットを実行できます。 詳しくは、「[about_Remote](/powershell/module/microsoft.powershell.core/about/about_remote)」をご覧ください。

    注: Windows PowerShell 2.0 を実行しているコンピューターでリモート処理が有効になっている場合は、Windows Management Framework 3.0 をインストールした後も、リモート処理は引き続き有効のままです。 ただし、Windows Server 2008 (Windows Server 2008 R2 ではない) では、Windows Management Framework 3.0 をインストールした後に re-enable のリモート処理が必要です。

## <a name="see-also"></a>参照
- [Windows PowerShell のインストール](../setup/Installing-Windows-PowerShell.md)
- [Windows PowerShell の開始](/powershell/scripting/setup/starting-windows-powershell)

