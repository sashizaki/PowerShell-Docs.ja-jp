---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: ada4fcc0beb3eb74b099f221762341abbf2c3b4c
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="new-temporaryfile"></a>New-TemporaryFile
スクリプトでは、ときおり、一時ファイルを作成する必要があります。 **New-TemporaryFile** コマンドレットを使うと、簡単に作成できます。

PS C:\\&gt; $tempFile = New-TemporaryFile

PS C:\\&gt; $tempFile.FullName

C:\\Users\\slee\\AppData\\Local\\Temp\\tmp375.tmp