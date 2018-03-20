---
ms.date: 2017-06-12
author: rpsqrd
ms.topic: conceptual
keywords: "JEA, PowerShell, セキュリティ"
title: "JEA の前提条件"
ms.openlocfilehash: e6ee16e34eb9f1f0b2f3601c1aa9e90ab4f785f1
ms.sourcegitcommit: 99227f62dcf827354770eb2c3e95c5cf6a3118b4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2018
---
# <a name="prerequisites"></a>前提条件

> 適用先: Windows PowerShell 5.0

Just Enough Administration は、Windows PowerShell 5.0 以降に含まれる機能です。
このトピックでは、JEA の使用を開始するために満たす必要のある前提条件について説明します。

## <a name="install-jea"></a>JEA のインストール

JEA は Windows PowerShell 5.0 以降で利用できますが、完全な機能のためには、システムで使用できる最新バージョンの PowerShell をインストールすることをお勧めします。
次の表は、Windows Server での JEA の可用性を示します。

サーバーのオペレーティング システム   | JEA の可用性
--------------------------|--------------------------------
Windows Server 2016       | プレインストール済み
Windows Server 2012 R2    | WMF 5.1 のすべての機能
Windows Server 2012       | WMF 5.1 のすべての機能
Windows Server 2008 R2    | WMF 5.1 の制限された機能<sup>1</sup>

JEA は、自宅または会社のコンピューターでも使用できます。

クライアントのオペレーティング システム   | JEA の可用性
--------------------------|-----------------------------------------------------
Windows 10 1607 以降          | プレインストール済み
Windows 10 1603、1511     | 制限された機能でプレインストール済み<sup>2</sup>
Windows 10 1507           | 不可
Windows 8、8.1            | WMF 5.1 のすべての機能
Windows 7                 | WMF 5.1 の制限された機能<sup>1</sup>

<sup>1</sup> Windows Server 2008 R2 または Windows 7 で、グループが管理するサービス アカウントを使用するように JEA を構成することはできません。
仮想アカウントと他の JEA 機能はサポートされています*。*

<sup>2</sup> Windows 10 のバージョン 1511 と 1603 では、JEA の次の機能はサポートされません。グループ管理されたサービス アカウントとしての実行、セッション構成での条件付きアクセス規則、ユーザー ドライブ、ローカル ユーザー アカウントへのアクセスの許可。
これらの機能を使うには、Windows をバージョン 1607 (Anniversary Update) 以降に更新します。

### <a name="check-which-version-of-powershell-is-installed"></a>インストールされている PowerShell のバージョンを確認する

システムにインストールされている PowerShell のバージョンを確認するには、Windows PowerShell プロンプトで `$PSVersionTable` 変数を調べます。

```powershell
PS C:\> $PSVersionTable.PSVersion

Major  Minor  Build  Revision
-----  -----  -----  --------
5      1      14393  1000
```

*メジャー* バージョンが **5** 以上の場合、JEA を使用できます。
エクスペリエンスを最善にし、すべての最新機能にアクセスするには、可能な場合は PowerShell バージョン **5.1** にアップグレードすることをお勧めします。

### <a name="install-windows-management-framework"></a>Windows Management Framework をインストールする

古いバージョンの PowerShell を実行している場合、最新の Windows Management Framework (WMF) 更新プログラムにシステムを更新する必要があります。
更新パッケージおよび最新の WMF リリース ノートへのリンクは、[ダウンロード センター](https://aka.ms/WMF5)にあります。

すべてのサーバーをアップグレードする前に、WMF とのワークロードの互換性をテストすることを強くお勧めします。

Windows 10 のユーザーは、現在のバージョンの Windows PowerShell を取得するには、最新の機能更新をインストールする必要があります。

## <a name="enable-powershell-remoting"></a>PowerShell リモート処理を有効にする

PowerShell リモート処理は、JEA 構築の基盤を提供します。
したがって、JEA を使用する前に、システムで PowerShell リモート処理を有効にし、[適切にセキュリティ保護する](https://msdn.microsoft.com/powershell/scripting/setup/winrmsecurity)必要があります。

Windows Server 2012、2012 R2、2016 では、PowerShell リモート処理は既定で有効になります。
管理者特権の PowerShell ウィンドウで次のコマンドを実行することにより、PowerShell リモート処理を有効にできます。

```powershell
Enable-PSRemoting
```

## <a name="enable-powershell-module-and-script-block-logging-optional"></a>PowerShell モジュールおよびスクリプト ブロック ログを有効にする (省略可能)

次の手順で、システム上のすべての PowerShell 操作のログを有効にします。
PowerShell モジュール ログは JEA には必要ありませんが、ユーザーが実行するコマンドが中央の場所に記録されるように有効にすることを強くお勧めします。

グループ ポリシーを使って、PowerShell モジュール ログ ポリシーを構成できます。

1. ワークステーションでローカル グループ ポリシー エディターを開くか、Active Directory ドメイン コントローラーのグループ ポリシー管理コンソールでグループ ポリシー オブジェクトを開きます
2. **[コンピューターの構成]\\[管理用テンプレート]\\[Windows コンポーネント]\\[Windows PowerShell]** に移動します。
3. **[モジュール ログを有効にする]** をダブルクリックします。
4. **[有効]** をクリックします。
5. [オプション] セクションで、モジュール名の横にある **[表示]** をクリックします。
6. ポップアップ ウィンドウに「**\***」と入力します。 これは、すべてのモジュールのコマンドを記録するよう PowerShell に指示します。
7. **[OK]** をクリックしてポリシーを設定します。
8. **[PowerShell スクリプト ブロックのログ記録を有効にする]** をダブルクリックします。
9. **[有効]** をクリックします。
10. **[OK]** をクリックしてポリシーを設定します。
11. (ドメインに参加しているコンピューターのみ) **gpupdate** を実行するか、グループ ポリシーが更新されたポリシーを処理して設定を適用するのを待ちます

グループ ポリシーを通してシステム全体の PowerShell トランスクリプトを有効にすることもできます。

## <a name="next-steps"></a>次の手順

- [ロール機能ファイルを作成する](role-capabilities.md)
- [セッション構成ファイルを作成する](session-configurations.md)

## <a name="see-also"></a>関連項目

- [PowerShell リモート処理と WinRM セキュリティに関する追加情報](https://msdn.microsoft.com/powershell/scripting/setup/winrmsecurity)
- [*PowerShell ♥ the Blue Team* のセキュリティに関するブログ投稿](https://blogs.msdn.microsoft.com/powershell/2015/06/09/powershell-the-blue-team/)

