---
title: Docker での PowerShell の使用
description: Docker イメージにプレインストールされている PowerShell の使用方法。
ms.devlang: powershell
ms.topic: conceptual
ms.date: 03/03/2020
ms.openlocfilehash: 771214c719ef01fe2c8bc56a4b26c629fcad3856
ms.sourcegitcommit: 01c60c0c97542dbad48ae34339cddbd813f1353b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78279659"
---
# <a name="using-powershell-in-docker"></a>Docker での PowerShell の使用

PowerShell がプレインストールされた Docker イメージが公開されています。 この記事では、Docker コンテナーで PowerShell の使用を開始する方法を説明します。

## <a name="finding-available-images"></a>使用可能なイメージの検索

リリースされたイメージを使用するには、Docker 17.05 以降が必要です。 また、`sudo` またはローカル管理者権限なしで Docker を実行できる必要があります。 `docker` を正しくインストールするには、Docker の公式な[手順][install]に従ってください。

リリースされているコンテナーは、`centos:7` などの公式のディストリビューション イメージから派生し、依存関係をインストールした後、最後に PowerShell パッケージがインストールされた状態となっています。

これらのコンテナーは [hub.docker.com/r/microsoft/powershell][docker-release] にあります。

これらの Docker イメージの詳細については、GitHub の [PowerShell-Docker][PowerShell-Docker] リポジトリを参照してください。

## <a name="using-powershell-in-a-container"></a>コンテナーでの PowerShell の使用

次の手順は、イメージをダウンロードし、対話型 PowerShell セッションを開始するのに必要な Docker コマンドを示しています。

```console
docker run -it mcr.microsoft.com/powershell
```

### <a name="remove-the-image-when-no-longer-needed"></a>不要になったイメージを削除する

次のコマンドは、不要になった Docker コンテナーを削除するときに使用します。

```console
docker rmi mcr.microsoft.com/powershell
```

## <a name="legal-and-licensing"></a>法律およびライセンス

PowerShell は、[MIT ライセンス][] に基づき使用が許諾されています。

### <a name="windows-docker-file-and-image-licenses"></a>Windows Docker ファイルとイメージのライセンス

Windows コンテナー用のコンテナー OS イメージを入手して使用する場合、Docker Hub 上で参照可能な追加ライセンス条項を確認して理解し、同意する必要があります。

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
