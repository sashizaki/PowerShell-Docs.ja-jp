---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: PowerShell ギャラリー
ms.openlocfilehash: 9519b8bcca9f43419a33db380c3b852e9bb354ac
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="the-powershell-gallery"></a>PowerShell ギャラリー

PowerShell ギャラリーは、PowerShell コンテンツの中央リポジトリです。 ギャラリーには、新しい PowerShell コマンドや Desired State Configuration (DSC) リソースがあります。

## <a name="powershellget-overview"></a>PowerShellGet 概要

PowerShellGet モジュールには、[PowerShell ギャラリー](https://www.PowerShellGallery.com)やその他のプライベート リポジトリでモジュール、DSC リソース、ロール機能、スクリプトなどの PowerShell アーティファクトを検索、インストール、更新、公開するためのコマンドレットが含まれています。

## <a name="getting-started-with-the-gallery"></a>ギャラリーをお使いになる前に

ギャラリーからアイテムをインストールするには、PowerShellGet の最新版が必要です。これは、Windows 10、Windows Management Framework (WMF) 5.0、MSI ベースのインストーラー (PowerShell 3 と 4) で利用できます。

- [**Windows 10 を入手する**](http://go.microsoft.com/fwlink/?LinkID=624830&clcid=0x409)、
- [**WMF 5.0 を入手する**](http://go.microsoft.com/fwlink/?LinkId=398175)、
- [**MSI インストーラーを入手する**](http://go.microsoft.com/fwlink/?LinkID=746217&clcid=0x409)

最新の [PowerShellGet](http://go.microsoft.com/fwlink/?LinkID=760387&clcid=0x409) モジュールで次の操作が可能になります。

-   [Find-Module](https://go.microsoft.com/fwlink/?LinkId=821658) と [Find-Script](https://go.microsoft.com/fwlink/?LinkId=822322) でギャラリー内のアイテムを検索する
-   [Save-Module](https://go.microsoft.com/fwlink/?LinkId=821669) と [Save-Script](https://go.microsoft.com/fwlink/?LinkId=822334) でギャラリーのアイテムをシステムに保存する
-   [Install-Module](https://go.microsoft.com/fwlink/?LinkId=821663) と [Install-Script](https://go.microsoft.com/fwlink/?LinkId=822327) でギャラリーからアイテムをインストールする
-   [Publish-Module](https://go.microsoft.com/fwlink/?LinkId=821666) と [Publish-Script](https://go.microsoft.com/fwlink/?LinkId=822331) でギャラリーにアイテムをアップロードする
-   [Register-PSRepository](https://go.microsoft.com/fwlink/?LinkId=821668) で独自のリポジトリを追加する

ギャラリーで PowerShellGet コマンドを使用する方法については、[[はじめに]](psgallery/psgallery_gettingstarted.md) ページを参照してください。 *Update-Help -Module PowerShellGet* を実行し、コマンドのローカル ヘルプをインストールすることもできます。

## <a name="supported-operating-systems"></a>サポートされるオペレーティング システム

**PowerShellGet** モジュールは **PowerShell 3.0 以降**を必要とします。

そのため、**PowerShellGet** は次のいずれかのオペレーティング システムを必要とします。

- Windows 10
- Windows 8.1 Pro
- Windows 8.1 Enterprise
- Windows 7 SP1
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2008 R2 SP1

**PowerShellGet** には、.NET Framework 4.5 以降も必要です。 .NET Framework 4.5 以降を[ここ](https://msdn.microsoft.com/library/5a4x27ek.aspx)からインストールできます。


## <a name="got-a-question-have-feedback"></a>ご質問または フィードバックがある場合は、

PowerShell ギャラリーと PowerShellGet の詳細を [[はじめに]](psgallery/psgallery_gettingstarted.md) ページで確認できます。 [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell) でご意見とご感想をお寄せください。問題がございましたら、ご報告ください。