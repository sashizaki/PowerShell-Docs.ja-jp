---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 7ad4a00f7beba0de70696d88cd5448c7c638c50c
ms.sourcegitcommit: a5c0795ca6ec9332967bff9c151a8572feb1a53a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2017
---
# <a name="archive-cmdlets"></a><span data-ttu-id="4efad-102">アーカイブのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="4efad-102">Archive cmdlets</span></span>

<span data-ttu-id="4efad-103">2 つの新しいコマンドレット **Compress-Archive** および **Expand-Archive** では、ZIP ファイルの圧縮と展開を実行します。</span><span class="sxs-lookup"><span data-stu-id="4efad-103">Two new cmdlets, **Compress-Archive** and **Expand-Archive**, let you compress and expand ZIP files.</span></span>

## <a name="compress-archive"></a><span data-ttu-id="4efad-104">Compress-Archive</span><span class="sxs-lookup"><span data-stu-id="4efad-104">Compress-Archive</span></span>
<span data-ttu-id="4efad-105">**Compress-Archive** コマンドレットでは、指定したファイルから新しいアーカイブ ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4efad-105">The **Compress-Archive** cmdlet creates a new archive file from specified files.</span></span> <span data-ttu-id="4efad-106">アーカイブ ファイルを使うと、複数のファイルを 1 つのファイルにパッケージ化し、必要に応じて圧縮できるため、取り扱いと保存が容易になります。</span><span class="sxs-lookup"><span data-stu-id="4efad-106">An archive file allows multiple files to be packaged and optionally compressed into a single file for easier handling and storage.</span></span> <span data-ttu-id="4efad-107">アーカイブ ファイルは、**-CompressionLevel** パラメーターに指定した圧縮アルゴリズムを使って圧縮することができます。</span><span class="sxs-lookup"><span data-stu-id="4efad-107">An archive file can be compressed by using a compression algorithm specified in the **-CompressionLevel** parameter.</span></span>
```powershell
Compress-Archive -LiteralPath <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>] 
Compress-Archive [-Path] <String[]> [-DestinationPath] <String> [-Update] [-CompressionLevel <Microsoft.PowerShell.Commands.CompressionLevel>]
```

## <a name="expand-archive"></a><span data-ttu-id="4efad-108">Expand-Archive</span><span class="sxs-lookup"><span data-stu-id="4efad-108">Expand-Archive</span></span>
<span data-ttu-id="4efad-109">**Expand-Archive** コマンドレットでは、指定したアーカイブ ファイルからファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="4efad-109">The **Expand-Archive** cmdlet extracts files from a specified archive file.</span></span> <span data-ttu-id="4efad-110">アーカイブ ファイルを使うと、複数のファイルを 1 つのファイルにパッケージ化し、必要に応じて圧縮できるため、取り扱いと保存が容易になります。</span><span class="sxs-lookup"><span data-stu-id="4efad-110">An archive file allows multiple files to be packaged and optionally compressed into a single file for easier handling and storage.</span></span>
```powershell
Expand-Archive -LiteralPath <String> [-DestinationPath] <String>
Expand-Archive [-Path] <String> [-DestinationPath] <String>
```

