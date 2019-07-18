---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery, PsGet
title: PowerShell ギャラリー
ms.openlocfilehash: d3e3b9d8bb3d6cefd3a3bfe79b012bb1dc1d8a2d
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62076023"
---
# <a name="the-powershell-gallery"></a>PowerShell ギャラリー

PowerShell ギャラリーは、PowerShell コンテンツの中央リポジトリです。 ここには、PowerShell コマンドと Desired State Configuration (DSC) リソースを含む、便利な PowerShell モジュールがあります。
また、PowerShell スクリプトもあり、その一部には一連のタスクとそのタスクの順序の概要を示す PowerShell ワークフローが含まれています。 このパッケージの一部は Microsoft によって作成されており、その他は PowerShell コミュニティによって作成されています。

## <a name="powershellget-overview"></a>PowerShellGet 概要

PowerShellGet モジュールには、[PowerShell ギャラリー](https://www.PowerShellGallery.com)やその他のプライベート リポジトリでモジュール、DSC リソース、ロール機能、スクリプトなどのアーティファクトを含む PowerShell パッケージを検索、インストール、更新、公開するためのコマンドレットが含まれています。

## <a name="getting-started-with-the-gallery"></a>ギャラリーをお使いになる前に

ギャラリーからパッケージをインストールするには、最新バージョンの PowerShellGet モジュールが必要です。
完全な手順については、「[PowerShellGet のインストール](installing-psget.md)」を参照してください。

ギャラリーで PowerShellGet コマンドを使用する方法については、[[はじめに]](getting-started.md) ページを参照してください。 *Update-Help -Module PowerShellGet* を実行し、コマンドのローカル ヘルプをインストールすることもできます。

## <a name="supported-operating-systems"></a>サポートされるオペレーティング システム

**PowerShellGet** モジュールは、**Windows PowerShell 3.0 以降**、または **PowerShell Core 6.0 以降**を必要とします。

**Windows PowerShell** の適切なバージョンは、次のオペレーティング システムに対して利用できます。

- Windows 10
- Windows 8.1 Pro
- Windows 8.1 Enterprise
- Windows 7 SP1
- Windows Server 2019
- Windows Server 2016
- Windows Server 2012 R2
- Windows Server 2008 R2 SP1

**PowerShellGet** には、.NET Framework 4.5 以降が必要です。 .NET Framework 4.5 以降を[ここ](https://msdn.microsoft.com/library/5a4x27ek.aspx)からインストールできます。

**PowerShell Core** はクロス プラットフォームであるため、Windows、Linux、MacOS で動作し、**PowerShellGet** をこれらのシステムで使用することもできます。 **PowerShell Core** でサポートされるシステムの完全な一覧については、[PowerShell のインストール](/powershell/scripting/setup/installing-powershell)に関するページを参照してください。

ギャラリーでホストされているモジュールの多くは、さまざまな OS をサポートしており、追加の要件があります。 詳細については、モジュールのドキュメントをご覧ください。

## <a name="got-a-question-have-feedback"></a>ご質問または フィードバックがある場合は、

PowerShell ギャラリーと PowerShellGet の詳細を [[はじめに]](getting-started.md) ページで確認できます。 [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell) でご意見とご感想をお寄せください。問題がございましたら、ご報告ください。
