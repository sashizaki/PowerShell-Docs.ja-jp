---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: db9c630bcb8e9e0da423c779976739f1ae76f13e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057436"
---
# <a name="archive-cmdlets"></a><span data-ttu-id="81bc8-102">アーカイブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="81bc8-102">Archive cmdlets</span></span>

<span data-ttu-id="81bc8-103">2 つの新しいコマンドレット **Compress-Archive** および **Expand-Archive** では、ZIP ファイルの圧縮と展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="81bc8-103">Two new cmdlets, **Compress-Archive** and **Expand-Archive**, let you compress and expand ZIP files.</span></span>

## <a name="compress-archive"></a><span data-ttu-id="81bc8-104">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="81bc8-104">Compress-Archive</span></span>
<span data-ttu-id="81bc8-105">**Compress-Archive** コマンドレットでは、指定したファイルから新しいアーカイブ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="81bc8-105">The **Compress-Archive** cmdlet creates a new archive file from specified files.</span></span> <span data-ttu-id="81bc8-106">アーカイブ ファイルを使うと、複数のファイルを 1 つのファイルにパッケージ化し、必要に応じて圧縮できるため、取り扱いと保存が容易になります。</span><span class="sxs-lookup"><span data-stu-id="81bc8-106">An archive file allows multiple files to be packaged and optionally compressed into a single file for easier handling and storage.</span></span> <span data-ttu-id="81bc8-107">アーカイブ ファイルは、**-CompressionLevel** パラメーターに指定した圧縮アルゴリズムを使って圧縮することができます。</span><span class="sxs-lookup"><span data-stu-id="81bc8-107">An archive file can be compressed by using a compression algorithm specified in the **-CompressionLevel** parameter.</span></span>
```powershell
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>]
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>]
```

## <a name="expand-archive"></a><span data-ttu-id="81bc8-108">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="81bc8-108">Expand-Archive</span></span>
<span data-ttu-id="81bc8-109">**Expand-Archive** コマンドレットでは、指定したアーカイブ ファイルからファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="81bc8-109">The **Expand-Archive** cmdlet extracts files from a specified archive file.</span></span> <span data-ttu-id="81bc8-110">アーカイブ ファイルを使うと、複数のファイルを 1 つのファイルにパッケージ化し、必要に応じて圧縮できるため、取り扱いと保存が容易になります。</span><span class="sxs-lookup"><span data-stu-id="81bc8-110">An archive file allows multiple files to be packaged and optionally compressed into a single file for easier handling and storage.</span></span>
```powershell
Expand-Archive -LiteralPath <String> [-DestinationPath] <String>
Expand-Archive [-Path] <String> [-DestinationPath] <String>
```
