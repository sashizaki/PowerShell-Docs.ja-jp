---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell の開始
ms.assetid: 59b649a2-c90c-4cf4-bf95-a740c59148e7
ms.openlocfilehash: 9184e8b0e508610e7f4775f1032f3a69c93bb8c1
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058354"
---
# <a name="starting-windows-powershell"></a>Windows PowerShell の開始
PowerShell は、複数のホストに埋め込まれているスクリプト エンジン dll です。  開始するホストとして最も一般的なものは、対話型コマンド ラインの PowerShell.exe および対話型スクリプト環境の PowerShell_ISE.exe です。

Windows Server® 2012 R2、Windows® 8.1、Windows Server 2012、Windows 8 で Windows PowerShell® を開始するには、「[一般的な管理タスクとナビゲーション](https://technet.microsoft.com/library/hh831491.aspx)」を参照してください。

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a>以前のバージョンの Windows で Windows PowerShell を開始する方法

このセクションでは、Windows® 7、Windows Server® 2008 R2、Windows Server® 2008 で、Windows PowerShell と Windows PowerShell Integrated Scripting Environment (ISE) を開始する方法について説明します。 Windows Server® 2008 R2 と Windows Server® 2008 で、Windows PowerShell 2.0 の Windows PowerShell ISE のオプション機能を有効にする方法についても説明します。

次のいずれかの方法で、必要に応じて、Windows PowerShell 3.0 または Windows PowerShell 4.0 のインストールされたバージョンを開始します。

#### <a name="from-the-start-menu"></a>[スタート] メニューからの場合

- **[スタート]** をクリックし、「**PowerShell**」と入力して **[Windows PowerShell]** をクリックします。
- **[スタート]** メニューから、**[スタート]**、**[すべてのプログラム]**、**[アクセサリ]**、**[Windows PowerShell]** フォルダー、**[Windows PowerShell]** の順にクリックします。

#### <a name="at-the-command-prompt"></a>コマンド プロンプトでの場合

Cmd.exe、Windows PowerShell、または Windows PowerShell ISE で Windows PowerShell を開始するには、次のように入力します。

```
PowerShell
```

また、PowerShell.exe プログラムのパラメーターを使って、セッションをカスタマイズできます。 詳しくは、「[PowerShell.exe コマンドラインのヘルプ](../core-powershell/console/PowerShell.exe-Command-Line-Help.md)」をご覧ください。

#### <a name="with-administrative-privileges-run-as-administrator"></a>管理特権を使う場合 ("管理者として実行")

**[スタート]** をクリックし、「**PowerShell**」と入力し、**[Windows PowerShell]** を右クリックして、**[管理者として実行]** をクリックします。

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a>以前のリリースの Windows で Windows PowerShell ISE を開始する方法

次のいずれかの方法で Windows PowerShell ISE を開始します。

#### <a name="from-the-start-menu"></a>[スタート] メニューからの場合

- **[スタート]** をクリックし、「**ISE**」と入力して **[Windows PowerShell ISE]** をクリックします。
- **[スタート]** メニューから、**[スタート]**、**[すべてのプログラム]**、**[アクセサリ]**、**[Windows PowerShell]** フォルダー、**[Windows PowerShell ISE]** の順にクリックします。

#### <a name="at-the-command-prompt"></a>コマンド プロンプトでの場合

Cmd.exe、Windows PowerShell、または Windows PowerShell ISE で Windows PowerShell を開始するには、次のように入力します。

```
PowerShell_ISE
```

または

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a>管理特権を使う場合 ("管理者として実行")

**[スタート]** をクリックし、「**ISE**」と入力し、**[Windows PowerShell ISE]** を右クリックして、**[管理者として実行]** をクリックします。

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a>以前のリリースの Windows で Windows PowerShell ISE を有効にする方法

Windows PowerShell 4.0 および Windows PowerShell 3.0 では、Windows PowerShell ISE は既定ではすべてのバージョンの Windows で有効になっています。 まだ有効になっていない場合、Windows Management Framework 4.0 または Windows Management Framework 3.0 により有効になります。

Windows PowerShell 2.0 では、Windows PowerShell ISE は既定では Windows 7 で有効になっています。 ただし、Windows Server 2008 R2 および Windows Server 2008 では省略可能な機能です。

Windows Server 2008 R2 または Windows Server 2008 で Windows PowerShell 2.0 の Windows PowerShell ISE を有効にするには、次の手順に従います。

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a>Windows PowerShell Integrated Scripting Environment (ISE) を有効にするには

1. サーバー マネージャーを起動します。
2. **[機能]**、**[機能の追加]** の順にクリックします。
3. [機能の選択]で、[Windows PowerShell Integrated Scripting Environment (ISE)] をクリックします。

## <a name="starting-the-32-bit-version-of-windows-powershell"></a>32 ビット版の Windows PowerShell を起動する

64 ビット コンピューターに Windows PowerShell をインストールする場合、64 ビット版に加えて、**Windows PowerShell (x86)**、つまり Windows PowerShell の 32 ビット版もインストールされます。 Windows PowerShell を実行すると、既定では 64 ビット版が実行されます。

ただし、32 ビット版を必要とするモジュールを使用するときや、32 ビットのコンピューターにリモートで接続しているときなど、**Windows PowerShell (x86)** の実行を必要とすることもときどきあります。

Windows PowerShell の 32 ビット版を起動するには、次の手順のいずれかを使用します。

#### <a name="in-windows-server-2012-r2"></a>Windows Server® 2012 R2 の場合

- **[スタート]** 画面で、「**Windows PowerShell (x86)**」と入力します。 **[Windows PowerShell x86]** タイルをクリックします。
- **サーバー マネージャー**の **[ツール]** メニューから、**[Windows PowerShell (x86)]** を選択します。
- デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell x86**」と入力し、**[Windows PowerShell (x86)]** をクリックします。
- コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`

#### <a name="in-windows-server-2012"></a>Windows Server® 2012 の場合

- **[スタート]** 画面で、「**PowerShell**」と入力して **[Windows PowerShell (x86)]** をクリックします。
- **サーバー マネージャー**の **[ツール]** メニューから、**[Windows PowerShell (x86)]** を選択します。
- デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell**」と入力し、**[Windows PowerShell (x86)]** をクリックします。
- コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`

#### <a name="in-windows-81"></a>Windows® 8.1 の場合

- **[スタート]** 画面で、「**Windows PowerShell (x86)**」と入力します。 **[Windows PowerShell x86]** タイルをクリックします。
- Windows 8.1 の[リモート サーバー管理ツール](https://go.microsoft.com/fwlink/?LinkID=304145)を実行している場合、**[サーバー管理ツール]** メニューから [Windows PowerShell x86] を開くこともできます。
  **[Windows PowerShell (x86)]** を選択します。
- デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell x86**」と入力し、**[Windows PowerShell (x86)]** をクリックします。
- コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`

#### <a name="in-windows-8"></a>In Windows® 8 の場合

- **[スタート]** 画面で、右上隅にカーソルを移動し、**[設定]** をクリックし、**[タイル]** をクリックします。そして、**[管理ツールを表示する]** スライダーを [はい] に移動させます。 次に「**PowerShell**」と入力し、**[Windows PowerShell(x86)]** をクリックします。
- Windows 8 の[リモート サーバー管理ツール](https://www.microsoft.com/download/details.aspx?id=28972)を実行している場合、**[サーバー管理ツール]** メニューから [Windows PowerShell x86] を開くこともできます。 **[Windows PowerShell (x86)]** を選択します。
- **[スタート]** 画面またはデスクトップで、「**PowerShell (x86)**」と入力し、**[Windows PowerShell (x86)]** をクリックします。
- コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`