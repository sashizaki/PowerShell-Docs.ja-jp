---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 0c450d765531c18c0b73c5c64262e9895f92068a
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
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