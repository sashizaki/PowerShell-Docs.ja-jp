---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISESnippetCollection オブジェクト
ms.assetid: ae974955-4282-4cbc-8c42-0fff1904ef32
ms.openlocfilehash: bd5ed4a1f15e0a398b7c6a17f0071cad889be4a7
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 12/14/2018
ms.locfileid: "53403434"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="1bb94-103">ISESnippetCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="1bb94-103">The ISESnippetCollection Object</span></span>

<span data-ttu-id="1bb94-104">**ISESnippetCollection** オブジェクトは、**ISESnippet** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="1bb94-104">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="1bb94-105">**PowerShellTab** オブジェクトに関連付けられているファイル コレクションは、このクラスのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="1bb94-105">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="1bb94-106">例としては、**$psISE.CurrentPowerShellTab.Files** コレクションです。</span><span class="sxs-lookup"><span data-stu-id="1bb94-106">An example is the **$psISE.CurrentPowerShellTab.Files** collection.</span></span>

## <a name="methods"></a><span data-ttu-id="1bb94-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="1bb94-107">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="1bb94-108">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="1bb94-108">Load\( FilePathName \)</span></span>

<span data-ttu-id="1bb94-109">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="1bb94-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="1bb94-110">ユーザー定義のスニペットを含む .snippets.ps1xml ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1bb94-110">Loads a .snippets.ps1xml file that contains user-defined snippets.</span></span> <span data-ttu-id="1bb94-111">スニペットを作成する最も簡単な方法は、New-IseSnippet コマンドレットを使用することです。このコマンドレットでは、Windows PowerShell ISE を開始するたびにスニペットがロードされるように、自動的にスニペットをプロファイル フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="1bb94-111">The easiest way to create snippets is to use the New-IseSnippet cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="1bb94-112">**FilePathName** - スニペット定義を含む .snippets.ps1xml ファイルへのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="1bb94-112">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="1bb94-113">参照</span><span class="sxs-lookup"><span data-stu-id="1bb94-113">See Also</span></span>

- [<span data-ttu-id="1bb94-114">ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="1bb94-114">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="1bb94-115">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="1bb94-115">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="1bb94-116">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="1bb94-116">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)