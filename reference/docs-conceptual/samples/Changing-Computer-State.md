---
ms.date: 12/23/2019
keywords: powershell,コマンドレット
title: コンピューターの状態を変更する
ms.openlocfilehash: 9278df55ba027134a61c8ed4e89b5b839d460b29
ms.sourcegitcommit: 058a6e86eac1b27ca57a11687019df98709ed709
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2020
ms.locfileid: "75736915"
---
# <a name="changing-computer-state"></a>コンピューターの状態を変更する

PowerShell でコンピューターをリセットするには、標準のコマンド ライン ツール、WMI、または CIM クラスのいずれかを使用します。
PowerShell は単にツールを実行するために使用するだけですが、PowerShell でコンピューターの電力状態を変更する手順には、PowerShell での外部ツールの使用方法に関する重要な詳細も含まれています。

## <a name="locking-a-computer"></a>コンピューターをロックする

一般的に入手可能なツールを使ってコンピューターを直接ロックする唯一の方法は、**user32.dll** の **LockWorkstation()** 関数を呼び出すことです。

```powershell
rundll32.exe user32.dll,LockWorkStation
```

このコマンドを実行すると、ワークステーションが直ちにロックされます。 このコマンドでは、**rundll32.exe** を使用して Windows DLL を実行 (および、繰り返し使用できるようにそれらのライブラリを保存) することにより、Windows の管理関数のライブラリである `user32.dll` を実行します。

Windows XP の場合など、ユーザーの簡易切り替えが有効なときにワークステーションをロックすると、コンピューターでは、現在のユーザーのスクリーン セーバーが起動するのではなく、ユーザーのログオン画面が表示されます。

ターミナル サーバーで特定のセッションをシャットダウンするには、**tsshutdn.exe** コマンド ライン ツールを使用します。

## <a name="logging-off-the-current-session"></a>現在のセッションからログオフする

ローカル システム上でセッションからログオフする場合、いくつかの方法が考えられます。 最も簡単な方法は、リモート デスクトップ/ターミナル サービスのコマンドライン ツールである **logoff.exe** を使用することです (詳細については、PowerShell プロンプトで「`logoff /?`」と入力してください)。 現在アクティブなセッションからログオフするには、引数を付けずに「`logoff`」と入力します。

また、**shutdown.exe** ツールにログオフのオプションを指定することもできます。

```powershell
shutdown.exe -l
```

他に、WMI を使用するというオプションがあります。 **Win32_OperatingSystem** クラスには、**Shutdown** メソッドがあります。
このメソッドに 0 フラグを指定して呼び出すと、ログオフが開始されます。

**Shutdown** メソッドの詳細については、「[Win32_OperatingSystem クラスの Shutdown メソッド](/windows/win32/cimwin32prov/shutdown-method-in-class-win32-operatingsystem)」を参照してください。

```powershell
Get-CimInstance -Classname Win32_OperatingSystem | Invoke-CimMethod -MethodName Shutdown
```

## <a name="shutting-down-or-restarting-a-computer"></a>コンピューターをシャットダウンまたは再起動する

通常、コンピューターのシャットダウンと再起動は同じ種類に属するタスクです。 コンピューターをシャットダウンできるツールであれば、コンピューターを再起動することもできます。逆にコンピューターを再起動できるツールであれば、コンピューターをシャットダウンすることもできます。 PowerShell からコンピューターを簡単に再起動する方法としては、2 とおりの方法があります。 **tsshutdn.exe** または **shutdown.exe** に適切な引数を指定して実行することです。 詳しい使用方法は、`tsshutdn.exe /?` または `shutdown.exe /?` で参照できます。

シャットダウン操作と再起動操作は、PowerShell から直接実行することもできます。

コンピューターをシャットダウンするには、Stop-Computer コマンドを使用します

```powershell
Stop-Computer
```

オペレーティング システムを再起動するには、Restart-Computer コマンドを使用します

```powershell
Restart-Computer
```

コンピューターを強制的に直ちに再起動するには、-Force パラメーターを使用します。

```powershell
Restart-Computer -Force
```
