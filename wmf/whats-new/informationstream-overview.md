---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: 情報ストリーム
ms.openlocfilehash: c54603cf0dd4f0b69f8147620130f9f29bc3e5ec
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855747"
---
# <a name="information-stream"></a>情報ストリーム

PowerShell 5.0 に、スクリプトとそのホストの間で構造化データを転送する新しい構造化された**情報**ストリームが追加されました。 `Write-Host` も更新され、**情報**ストリームに送った出力をキャプチャしたり、サイレント状態にしたりできるようになりました。 新しい `Write-Information` コマンドレットを **InformationVariable** および **InformationAction** 共通パラメーターと一緒に使うと、柔軟性と機能が向上します。

次の関数では、新しい**情報**ストリームを利用するコマンドレットを使用します。

```powershell
function OutputGusher {
  [CmdletBinding()]
  param()
  Write-Host -ForegroundColor Green 'Preparing to give you output!'
  Write-Host '============================='
  Write-Host 'I ' -ForegroundColor White -NoNewline
  Write-Host '<3 ' -ForegroundColor Red -NoNewline
  Write-Host 'Output' -ForegroundColor White
  Write-Host '============================='

  $p = Get-Process -id $pid
  $p

  Write-Information $p -Tag Process
  Write-Information 'Some spammy logging information' -Tag LogLow
  Write-Information 'Some important logging information' -Tag LogHigh

  Write-Host
  Write-Host -ForegroundColor Green 'SCRIPT COMPLETE!!'
}
```

この関数の実行結果は、次の例のとおりです。

```powershell
$r = c:\temp\OutputGusher
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================

SCRIPT COMPLETE!!
```

`$r` 変数がスクリプト変数 `$p` の処理情報をキャプチャしました。

```powershell
$r.Id
4008
```

`Write-Information` の **InformationVariable** パラメーターを使用すると、`Write-Host` コマンドレットとは異なり、出力を変数にキャプチャできます。 **タグ**を使用すると、**情報**ストリームに送信されたメッセージのチャネルを分けることができます。

```powershell
$r = OutputGusher -InformationVariable iv
$ivOutput = $iv | Group-Object -AsHash { $_.Tags[0] } -AsString
$ivOutput
```

```Output
Preparing to give you output!
=============================
I <3 Output
=============================
SCRIPT COMPLETE!!

Name                 Value
----                 -----
LogLow               {Some spammy logging information}
LogHigh              {Some important logging information}
Process              {System.Diagnostics.Process (powershell)}
PSHOST               {Preparing to give you output!, =============================, I , <3 ...}
```

タグを使用して**情報**ストリームにメッセージを送ると、そのメッセージはホスト アプリケーションには表示されず、タグ名を使用して取得されるようになります。 たとえば、次のように入力します。

```powershell
$iv | where Tags -eq 'LogHigh'
```

```Output
Some important logging information
```