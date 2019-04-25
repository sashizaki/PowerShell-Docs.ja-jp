---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 22a027ebc97e15075980bc77ce272d8ecdae0b5f
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058665"
---
# <a name="improvements-in-powershell-script-debugging"></a>PowerShell スクリプト デバッグの強化

デバッガーの動作を向上させるため、PowerShell 5.0 では多くの点が強化されています。

## <a name="break-all"></a>すべて中断

PowerShell コンソールと Windows PowerShell ISE では、実行中のスクリプトに対してデバッガー中断が可能になりました。 これは、ローカルとリモートの両方のセッションに適用されます。

コンソールでは、**Ctrl+Break** を押します。

ISE では、**Ctrl+B** を押すか、**[デバッグ] -> [すべて中断]** メニュー コマンドを使います。

## <a name="remote-debugging-and-remote-file-editing-in-windows-powershell-ise"></a>Windows PowerShell ISE でのリモートによるデバッグとファイル編集

Windows PowerShell ISE では、PSEdit コマンドを実行することにより、リモート セッションでファイルを開いて編集できるようになりました。
たとえば、次のように、リモート セッションでコマンド ラインからファイルを開いて編集できます。

```powershell
[RemoteComputer1]: PS C:\> PSEdit C:\DebugDemoScripts\Test-GetMutex.ps1
```

また、ブレークポイントにヒットしたときに、Windows PowerShell ISE で自動的に開くリモート ファイルを編集して変更を保存できるようになりました。
今後は、リモート コンピューターで実行しているスクリプト ファイルをデバッグし、エラー修正のためにファイルを編集し、変更したスクリプトを再実行することができます。

## <a name="advanced-script-debugging"></a>高度なスクリプトのデバッグ

新しい高度なデバッグ機能では、Windows PowerShell を読み込んだローカル コンピューターのプロセスにアタッチし、そのプロセス内の任意の実行空間をデバッグできます。

### <a name="runspace-debugging"></a>実行空間のデバッグ

プロセス内の現在の実行空間を一覧表示し、その実行空間に Windows PowerShell コンソールや ISE デバッガーをアタッチしてスクリプト デバッグを実行するための、新しいコマンドレットが追加されました。

-   Get-Runspace
-   Debug-Runspace
-   Enable-RunspaceDebug
-   Disable-RunspaceDebug
-   Get-RunspaceDebug

### <a name="attach-to-process-hosting-powershell"></a>PowerShell をホストしているプロセスにアタッチする

Windows PowerShell が読み込まれているすべてのコンピューター プロセスにアタッチできるようになりました。 これを行うには、プロセスを使って対話型セッションに入ります。これは、Enter-PSSession コマンドレットを実行して、対話型リモート セッションに入る方法と似ています。

-   Enter-PSHostProcess
-   Exit-PSHostProcess
