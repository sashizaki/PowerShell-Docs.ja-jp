---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
title: "WMF 5.1 リリース ノート"
ms.openlocfilehash: f80c1ec5886578e3e43f2c96981f40152db000d1
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="windows-management-framework-wmf-51-release-notes" class="xliff"></a>

# Windows Management Framework (WMF) 5.1 リリース ノート #

WMF 5.1 には、Windows Server 2016 でリリースされた PowerShell、WMI、WinRM、ソフトウェア インベントリおよびライセンス (SIL) のコンポーネントが含まれています。
WMF 5.1 は、Windows 7、Windows 8.1、Windows Server 2008 R2、Windows Server 2012、および Windows Server 2012 R2 にインストールすることができ、WMF 5.0 RTM と比較すると次のような機能が強化されています。

- 新しいコマンドレット: ローカル ユーザーとグループ、Get-ComputerInfo
- PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。
- PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。
- DSC および PowerShell クラスにおけるデバッグ機能の強化
- セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。
- さまざまなユーザー要求と問題への対応

**重要な注意事項:**

- **WMF 5.1 には .NET Framework 4.5.2 が必要です**。 .NET 4.5.2 がインストールされていない場合、インストールは成功しますが、主な機能は失敗します。 手順については、トピック「[WMF 5.1 のインストールと構成](https://msdn.microsoft.com/en-us/powershell/wmf/5.1/install-configure)」を参照してください。
- WMF 5.1 RTM をインストールする前に、WMF 5.1 プレビューをアンインストールする必要があります。
- WMF 5.1 は、WMF 5.0 または WMF 4.0 の上に直接インストールできます。
- Windows 7 および Windows Server 2008 R2 の上に WMF 5.1 をインストールする前に、WMF 4.0 をインストールする__必要はありません__。 これは WMF 5.1 プレビュー リリースでの問題でしたが、解決されました。  


