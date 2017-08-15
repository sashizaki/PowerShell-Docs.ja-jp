---
ms.date: 2017-06-12T00:00:00.000Z
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 7ad4a00f7beba0de70696d88cd5448c7c638c50c
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2017
---
# <a name="archive-cmdlets"></a>アーカイブのコマンドレット

2 つの新しいコマンドレット **Compress-Archive** および **Expand-Archive** では、ZIP ファイルの圧縮と展開を実行します。

## <a name="compress-archive"></a>Compress-Archive
**Compress-Archive** コマンドレットでは、指定したファイルから新しいアーカイブ ファイルを作成します。 アーカイブ ファイルを使うと、複数のファイルを 1 つのファイルにパッケージ化し、必要に応じて圧縮できるため、取り扱いと保存が容易になります。 アーカイブ ファイルは、**-CompressionLevel** パラメーターに指定した圧縮アルゴリズムを使って圧縮することができます。
```powershell
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>] 
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>]
```

## <a name="expand-archive"></a>Expand-Archive
**Expand-Archive** コマンドレットでは、指定したアーカイブ ファイルからファイルを抽出します。 アーカイブ ファイルを使うと、複数のファイルを 1 つのファイルにパッケージ化し、必要に応じて圧縮できるため、取り扱いと保存が容易になります。
```powershell
Expand-Archive -LiteralPath <String> [-DestinationPath] <String>
Expand-Archive [-Path] <String> [-DestinationPath] <String>
```

