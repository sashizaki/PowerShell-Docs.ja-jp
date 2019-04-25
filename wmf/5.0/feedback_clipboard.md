---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: d5ec95abb1d3160afc4179cff991cb5ef72d85fe
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057300"
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
