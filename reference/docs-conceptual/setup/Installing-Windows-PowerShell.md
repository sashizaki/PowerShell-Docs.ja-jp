---
ms.date: 2017-08-09
keywords: "powershell, コマンドレット, ダウンロード, インストール, セットアップ, windows 10, windows 8.1, windows 8.0, windows 7"
title: "Windows PowerShell のインストール"
ms.openlocfilehash: 7ccbee66d01dd8e0e6e6ab09c6c8a399bee59ce8
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="installing-windows-powershell"></a>Windows PowerShell のインストール

既定では、PowerShell は、Windows 7 SP1 および Windows Server 2008 R2 SP1 以降のすべての Windows にインストールされています。

**PowerShell 6** (ベータ) をインストールする Linux、macOS、および Windows のユーザーは、自分のマシンで次の操作を行う必要があります。

1. [GitHub](https://github.com/powershell/powershell#get-powershell) から特定の OS とバージョン用の PowerShell を取得します
1. インストール手順に従って操作します
  - [Linux](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md)
  - [macOS](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/linux.md#macos-1012)
  - [Windows](https://github.com/PowerShell/PowerShell/blob/master/docs/installation/windows.md#msi)

PowerShell 6 は、Docker でも利用できます。[Docker のインストール](https://github.com/PowerShell/PowerShell/tree/master/docker)手順を参照してください。

## <a name="finding-powershell-in-windows-10-81-80-and-7"></a>Windows 10、8.1、8.0、7 で PowerShell を見つける

Windows で PowerShell コンソールや ISE (Integrated Scripting Environment) を見つけるのは、その場所が Windows のあるバージョンから次のバージョンへ移動するため、難しい場合があります。

次の表は、使用している Windows のバージョンで PowerShell を見つけるのに役立ちます。
ここに一覧されているバージョンはすべて、リリース時の元のバージョンです。更新プログラムは含まれていません。

### <a name="for-console"></a>コンソールの場合

バージョン | インストール先
-- | --
Windows 10 | 左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます
Windows 8.1、8.0 | スタート画面で、「PowerShell」と入力し始めます。<br/>デスクトップ上の場合は、左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます
Windows 7 SP1 | 左下隅にある Windows アイコンをクリックして、検索ボックスに「PowerShell」と入力し始めます

### <a name="for-ise"></a>ISE の場合

バージョン | インストール先
-- | --
Windows 10 | 左下隅にある Windows アイコンをクリックして、「ISE」と入力し始めます
Windows 8.1、8.0 | スタート画面で、「**PowerShell ISE**」と入力します。<br/>デスクトップで、左下隅にある Windows アイコンをクリックして、「**PowerShell ISE**」と入力します
Windows 7 SP1 | 左下隅にある Windows アイコンをクリックして、検索ボックスに「PowerShell」と入力し始めます

## <a name="finding-powershell-in-windows-server-versions"></a>Windows Server バージョンで PowerShell を見つける

Windows Server 2008 R2 以降では、グラフィカル ユーザー インターフェイス (GUI) を含めずに、Windows オペレーティング システムをインストールできます。
GUI なしの Windows Server のエディションは **Core** エディションという名前で、GUI ありのエディションは **Desktop** という名前です。

### <a name="windows-server-core-editions"></a>Windows Server Core エディション

すべての Core エディションで、サーバーにログインすると、Windows コマンド プロンプト ウィンドウが表示されます。

「`powerhell`」と入力して **Enter** キーを押し、コマンド プロンプト セッション内で PowerShell を開始します。 「`exit`」と入力して PowerShell セッションを終了し、コマンド プロンプトに戻ります。

### <a name="windows-server-desktop-editions"></a>Windows Server Desktop エディション

すべての Desktop エディションで、左下隅にある Windows アイコンをクリックして、「PowerShell」と入力し始めます。
コンソールと ISE のオプションが両方表示されます。

上記のルールの例外は、Windows Server 2008 R2 SP1 の ISE のみです。この場合は、左下隅にある Windows アイコンをクリックして、「PowerShell ISE」と入力します。

## <a name="how-to-check-the-version-of-powershell"></a>PowerShell のバージョンを確認する方法

インストールした PowerShell のバージョンを確認するには、PowerShell コンソール (または ISE) を起動し、「`$PSVersionTable`」と入力して **Enter** キーを押します。

## <a name="upgrading-existing-windows-powershell"></a>既存の Windows PowerShell をアップグレードする

PowerShell のインストール パッケージは、WMF インストーラー内に含まれています。
WMF インストーラーのバージョンは、PowerShell のバージョンに一致します。Windows PowerShell に、スタンドアロンのインストーラーはありません。

PowerShell の既存のバージョンを更新する場合、Windows では、以下の表を使って、更新する PowerShell のバージョン用のインストーラーを見つけます。

Windows | PS 3.0 | PS 4.0 | PS 5.0 | PS 5.1 |
--|--|--|--|--|
Windows 10 (注 1 を参照してください)<br/>Windows Server 2016 | - | - | - | インストール済み
Windows 8.1<br/>Windows Server 2012 R2 | - | インストール済み | [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [WMF 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
Windows 8<br/>Windows Server 2012 | インストール済み | [WMF 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [WMF 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616)
Windows 7 SP1<br/>Windows Server 2008 R2 SP1 | [WMF 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) | [WMF 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) | [WMF 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) | [WMF 5.1](https://www.microsoft.com/en-us/download/details.aspx?id=54616)

> **注 1**:
  >>
  >> 自動更新を有効にしている Windows 10 の最初のリリースでは、PowerShell はバージョン 5.0 から 5.1 に更新されます。
  >>
  >> 元のバージョンの Windows 10 が Windows Update によって更新されない場合、PowerShell のバージョンは 5.0 です。

## <a name="need-azure-powershell"></a>Azure PowerShell が必要な場合

**Azure PowerShell** を探している場合は、「[Overview of Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure)」 (Azure PowerShell の概要) から開始することができます。

その他にも、[Azure PowerShell のインストールと構成](https://docs.microsoft.com/en-us/powershell/azure/install-azurerm-ps)が必要な場合があります

## <a name="see-also"></a>参照

- [Windows PowerShell のシステム要件](Windows-PowerShell-System-Requirements.md)
- [Windows PowerShell の開始](Starting-Windows-PowerShell.md)
