---
title: "WMF 5.1 リリース ノート"
ms.date: 2016-07-27
keywords: PowerShell, DSC, WMF
description: 
ms.topic: article
author: jkeithb
manager: dongill
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: 15de6aca52624134998b2d08fcfff9e1bcc1af7b
ms.sourcegitcommit: f75fc25411ce6a768596d3438e385c43c4f0bf71
translationtype: HT
---
# <a name="windows-management-framework-wmf-51-release-notes"></a>Windows Management Framework (WMF) 5.1 リリース ノート #

WMF 5.1 には、Windows Server 2016 でリリースされる PowerShell、WMI、WinRM、ソフトウェア インベントリおよびライセンス (SIL) のコンポーネントが含まれています。 WMF 5.1 は、Windows 7、Windows 8.1、Windows Server 2008 R2、Windows Server 2012、および Windows Server 2012 R2 にインストールすることができ、WMF 5.0 RTM と比較すると次のような機能が強化されています。

- 新しいコマンドレット: ローカル ユーザーとグループ、Get-ComputerInfo
- PowerShellGet では、署名付きモジュールの適用や JEA モジュールのインストールなどの機能強化が行われています。
- PackageManagement では、コンテナー、CBS セットアップ、EXE ベースのセットアップ、CAB パッケージをサポートするようになりました。
- DSC および PowerShell クラスにおけるデバッグ機能の強化
- セキュリティの機能強化としては、プル サーバーからもたらされるカタログ署名付きモジュールの適用、PowerShellGet コマンドレットを使用するタイミングなどが挙げられます。
- さまざまなユーザー要求と問題への対応

**重要な注意事項:**

- **WMF 5.1 には .NET Framework 4.5 が必要です**。 .NET 4.5 がインストールされていない場合、インストールは成功しますが、主な機能は失敗します。 手順については、トピック「[WMF 5.1 のインストールと構成](https://msdn.microsoft.com/en-us/powershell/wmf/5.1/install-configure)」を参照してください。 
- WMF 5.1 RTM をインストールする前に、WMF 5.1 プレビューをアンインストールする必要があります。
- WMF 5.1 は、WMF 5.0 または WMF 4.0 の上に直接インストールできます。
- Windows 7 および Windows Server 2008 R2 の上に WMF 5.1 をインストールする前に、WMF 4.0 をインストールする__必要はありません__。 これは WMF 5.1 プレビュー リリースでの問題でしたが、解決されました。  


