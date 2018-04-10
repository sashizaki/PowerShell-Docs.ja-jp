---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 814b1172505e1bac59a75fee494e9741f7d1f820
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="enhanced-transcription-options"></a><span data-ttu-id="94c21-102">強化されたトランスクリプション オプション</span><span class="sxs-lookup"><span data-stu-id="94c21-102">Enhanced Transcription Options</span></span>

<span data-ttu-id="94c21-103">Windows PowerShell トランスクリプションが強化され、コンソール ホスト (powershell.exe) だけでなく、すべてのホスト アプリケーション (Windows PowerShell ISE など) に適用されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="94c21-103">Windows PowerShell transcription has been improved to apply to all hosting applications (such as Windows PowerShell ISE) rather than just the console host (powershell.exe).</span></span>

<span data-ttu-id="94c21-104">トランスクリプトを強化するだけでなく、トランスクリプトの任意のネスト、結果として得られるトランスクリプト ヘッダーの追加メタデータ、および (一元化されたログの収集をサポートするために) トランスクリプション出力ディレクトリの設定をサポートするようにトランスクリプト機能自体が更新されました。</span><span class="sxs-lookup"><span data-stu-id="94c21-104">In addition to extending for transcripting, the transcripting functionality itself has been updated to support arbitrary nesting of transcripts, additional metadata in the resulting transcript header, and setting a transcription output directory (to support centralized log collection).</span></span>

<span data-ttu-id="94c21-105">トランスクリプション オプション (システム全体のトランスクリプトの有効化を含む) は、**[PowerShell トランスクリプションを有効にする]** グループ ポリシー設定 ([管理用テンプレート] -> [Windows コンポーネント] -> [Windows PowerShell]) で設定できます。</span><span class="sxs-lookup"><span data-stu-id="94c21-105">Transcription options (including enabling a system-wide transcript) can be configured with the **Turn on PowerShell Transcription** Group Policy setting (in Administrative Templates -> Windows Components -> Windows PowerShell).</span></span>