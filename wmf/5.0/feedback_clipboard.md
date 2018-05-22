---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: e6b54519d878ab572662075709beb4cf4454b0c6
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/16/2018
---
# <a name="clipboard-cmdlets"></a><span data-ttu-id="f2639-102">クリップボードのコマンドレット</span><span class="sxs-lookup"><span data-stu-id="f2639-102">Clipboard cmdlets</span></span>
<span data-ttu-id="f2639-103">**Get-Clipboard** と **Set-Clipboard** を使うと、Windows PowerShell セッションとの間でコンテンツを容易に転送できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f2639-103">**Get-Clipboard** and **Set-Clipboard** make it easier for you to transfer content to and from a Windows PowerShell session.</span></span> <span data-ttu-id="f2639-104">たとえば、エクスプローラーを使用して 3 つのファイルをクリップボードにコピーすると (ファイルを選択して `ctrl-c` を押すなど)、そのクリップボードの内容はファイルの一覧として簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f2639-104">For example, if you use Windows Explorer to copy three files to the clipboard (by selecting them and pressing `ctrl-c`, for example), you can then easily access the contents of the clipboard as a list of files:</span></span>

```powershell
PS C:\\&gt; Get-Clipboard -Format FileDropList

Directory: C:\\Users\\slee\\Downloads\\Example

Mode LastWriteTime Length Name

---- ------------- ------ ----

-a---- 4/14/2015 1:19 PM 0 File2.txt

-a---- 4/14/2015 1:19 PM 0 File3.txt

-a---- 4/14/2015 1:19 PM 0 File1.txt
```


<span data-ttu-id="f2639-105">クリップボードのコマンドレットは、画像、オーディオ ファイル、ファイルのリスト、およびテキストをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2639-105">The Clipboard cmdlets support images, audio files, file lists, and text.</span></span>
