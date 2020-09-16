---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
title: WMF 5.0 のアンインストール
ms.openlocfilehash: fa76bacb4b62025d0d2350b9a0e072068ca83ab1
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236307"
---
# <a name="uninstallation-instructions"></a>アンインストール手順

## <a name="using-command-prompt"></a>コマンド プロンプトを使用

1. **コマンド プロンプト**を開きます。
2. [Windows Update スタンドアロン ランチャー](https://support.microsoft.com/kb/934307)を次のように実行します。

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

## <a name="using-control-panel"></a>コントロール パネルを使用

1. **[コントロール パネル]** を開きます。
2. **[プログラム]** を開き、 **[プログラムのアンインストール]** を開きます。
3. **[インストールされた更新プログラムを表示]** をクリックします。
4. インストールされた更新プログラムの一覧から **[Windows Management Framework 5.0]** を選択します。 これは *KB3134758*、*KB3134759*、または *KB3134760* に対応しています。 **[アンインストール]** をクリックします。
