---
ms.date: 08/12/2017
ms.topic: conceptual
keywords: WMF, PowerShell, セットアップ
title: WMF 5.1 リリース ノート
ms.openlocfilehash: 3081d200f0c6aac6074719bb1c204900aabf96c2
ms.sourcegitcommit: e46b868f56f359909ff7c8230b1d1770935cce0e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/13/2018
ms.locfileid: "45522907"
---
# <a name="windows-management-framework-wmf-51"></a>Windows Management Framework (WMF) 5.1 #

WMF は、既存の Windows システムを、Windows Server 2016 でリリースされた PowerShell、WMI、WinRM、およびソフトウェア インベントリ ログ (SIL) のコンポーネントのバージョンに更新する機能を提供します。

WMF 5.1 は、Windows 7、Windows 8.1、Windows Server 2008 R2、Windows Server 2012、および Windows Server 2012 R2 にインストールすることができ、WMF 5.0 RTM と比較すると次のような機能が強化されています。

- 新しいコマンドレット: ローカル ユーザーとグループ、Get-ComputerInfo
- PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。
- PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。
- DSC および PowerShell クラスにおけるデバッグ機能の強化
- セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。
- さまざまなユーザー要求と問題への対応

このリリースの新機能については、「[新しいシナリオと機能](https://docs.microsoft.com/powershell/wmf/5.1/scenarios-features)」の下の各トピックを参照してください。

「[インストールと構成](https://docs.microsoft.com/powershell/wmf/5.1/install-configure)」トピックは要件を一覧表示し、WMF のインストール手順について説明します。

「[互換性](https://docs.microsoft.com/powershell/wmf/5.1/compatibility)」トピックは、どのWindows リリースにどの WMF のバージョンがインストールされているのかを一覧表示します。

「[製品の互換性](https://docs.microsoft.com/powershell/wmf/5.1/productincompat)」は、現時点で WMF 5.1 を承認していない Microsoft アプリケーションを一覧表示します。

WMF の各コンポーネントの詳細については、MSDN のドキュメントに記載されています。

- [PowerShell 5.1](https://docs.microsoft.com/powershell/)
- [WMI](https://msdn.microsoft.com/library/jj152383(v=vs.85).aspx)
- [WinRM](https://msdn.microsoft.com/library/aa384426(v=vs.85).aspx)
- [ソフトウェア インベントリ ログ](https://technet.microsoft.com/library/dn383584(v=ws.11).aspx)
