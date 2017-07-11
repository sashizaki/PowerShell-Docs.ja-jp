---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 3392db954c22030bb64ae5093619d23952e1fcdb
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="uninstallation-instructions" class="xliff"></a>

# アンインストール手順

<a id="using-command-prompt" class="xliff"></a>

## コマンド プロンプトを使用
1.  **コマンド プロンプト**を開きます。
2.  [Windows Update スタンドアロン ランチャー](https://support.microsoft.com/en-us/kb/934307)を次のように実行します。

Windows Server 2012 R2 および Windows 8.1:
```powershell
wusa /uninstall /kb:3134758
```
Windows Server 2012:
```powershell
wusa /uninstall /kb:3134759
```
Windows Server 2008 R2 SP1 および Windows 7 SP1:
```powershell
wusa /uninstall /kb:3134760
```

<a id="using-control-panel" class="xliff"></a>

## コントロール パネルを使用
1.  **[コントロール パネル]** を開きます。
2.  **[プログラム]** を開き、**[プログラムのアンインストール]** を開きます。
3.  **[インストールされた更新プログラムを表示]** をクリックします。
4.  インストールされた更新プログラムの一覧から **[Windows Management Framework 5.0]** を選択します。 これは *KB3134758*、*KB3134759*、または *KB3134760* に対応しています。 **[アンインストール]** をクリックします。

