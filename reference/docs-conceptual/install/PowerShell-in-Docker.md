---
title: Docker での PowerShell の使用
description: Docker イメージにプレインストールされている PowerShell の使用方法。
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/03/2020
ms.openlocfilehash: b16a31a04ca863ab55c7c9718b1a1a973e61ee46
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "80646369"
---
# <a name="using-powershell-in-docker"></a>Docker での PowerShell の使用

PowerShell がプレインストールされた Docker イメージを発行します。 この記事では、Docker コンテナーで PowerShell の使用を開始する方法を説明します。

## <a name="finding-available-images"></a>使用可能なイメージの検索

リリースされたイメージには、Docker 17.05 以降が必要です。 また、`sudo` またはローカル管理者権限なしで Docker を実行できる必要もあります。 `docker` を正しくインストールするには、Docker の公式な[手順][install]に従ってください。

リリース コンテナーは、`centos:7` などの公式のディストリビューション イメージから派生し、依存関係をインストールしてから、最後に PowerShell パッケージをインストールします。

これらのコンテナーは [hub.docker.com/r/microsoft/powershell][docker-release] にあります。

これらの Docker イメージの詳細については、GitHub の [PowerShell-Docker][PowerShell-Docker] リポジトリを参照してください。

## <a name="using-powershell-in-a-container"></a>コンテナーでの PowerShell の使用

次の手順は、イメージをダウンロードし、対話型 PowerShell セッションを開始するのに必要な Docker コマンドを示しています。

```console
docker run -it mcr.microsoft.com/powershell
```

### <a name="remove-the-image-when-no-longer-needed"></a>不要になったイメージを削除する

次のコマンドは、不要になった Docker イメージを削除するときに使用します。

```console
docker rmi mcr.microsoft.com/powershell
```

## <a name="legal-and-licensing"></a>法律およびライセンス

PowerShell は、[MIT ライセンス][] に基づき使用が許諾されています。

### <a name="windows-docker-file-and-image-licenses"></a>Windows Docker ファイルとイメージのライセンス

Windows コンテナー用のコンテナー OS イメージを要求して使用することで、Docker Hub で利用可能な追加ライセンス条項を確認して理解し、同意することができます。

- [Window Server Core][Window Server Core]
- [Nano Server][Nano Server]

### <a name="telemetry"></a>テレメトリ

既定では、PowerShell は、個人を特定できる情報が含まれない限られたテレメトリを収集し、将来のバージョンの PowerShell 開発に利用します。 テレメトリを送信しないようにするには、インストール先から PowerShell を起動する前に、`POWERSHELL_TELEMETRY_OPTOUT` という環境変数を作成して値を `1` に設定します。 収集するテレメトリは、[Microsoft プライバシー ステートメント][privacy]に記載されています。

<!-- link references -->
[install]: https://docs.docker.com/engine/installation/
[docker-release]: https://hub.docker.com/r/microsoft/powershell/
[appinsights]: https://azure.microsoft.com/services/application-insights/
[MIT ライセンス]: https://github.com/PowerShell/PowerShell/tree/master/LICENSE.txt
[PowerShell-Docker]: https://github.com/PowerShell/PowerShell-Docker
[Window Server Core]: https://hub.docker.com/r/microsoft/windowsservercore/
[Nano Server]: https://hub.docker.com/r/microsoft/nanoserver/
[privacy]: https://privacy.microsoft.com/privacystatement/
