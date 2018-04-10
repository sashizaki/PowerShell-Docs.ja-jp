---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: d34a267bae7e48afe4442256d7f112da3a97eb7d
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="clipboard-cmdlets"></a>クリップボードのコマンドレット
**Get-Clipboard** と **Set-Clipboard** を使うと、Windows PowerShell セッションとの間でコンテンツを容易に転送できるようになります。 たとえば、エクスプローラーを使用して 3 つのファイルをクリップボードにコピーすると (ファイルを選択して `ctrl-c` を押すなど)、そのクリップボードの内容はファイルの一覧として簡単にアクセスできます。

```powershell
PS C:\\&gt; Get-Clipboard -Format FileDropList

Directory: C:\\Users\\slee\\Downloads\\Example

Mode LastWriteTime Length Name

---- ------------- ------ ----

-a---- 4/14/2015 1:19 PM 0 File2.txt

-a---- 4/14/2015 1:19 PM 0 File3.txt

-a---- 4/14/2015 1:19 PM 0 File1.txt
```


クリップボードのコマンドレットは、画像、オーディオ ファイル、ファイルのリスト、およびテキストをサポートします。