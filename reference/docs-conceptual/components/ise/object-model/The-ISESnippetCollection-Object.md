---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: ISESnippetCollection オブジェクト
ms.openlocfilehash: 6c392c08767fba004f63155d5a469777856a0b59
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "67030503"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="4b38c-103">ISESnippetCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="4b38c-103">The ISESnippetCollection Object</span></span>

<span data-ttu-id="4b38c-104">**ISESnippetCollection** オブジェクトは、**ISESnippet** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="4b38c-104">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="4b38c-105">**PowerShellTab** オブジェクトに関連付けられているファイル コレクションは、このクラスのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="4b38c-105">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="4b38c-106">例としては、 **$psISE.CurrentPowerShellTab.Files** コレクションです。</span><span class="sxs-lookup"><span data-stu-id="4b38c-106">An example is the **$psISE.CurrentPowerShellTab.Files** collection.</span></span>

## <a name="methods"></a><span data-ttu-id="4b38c-107">メソッド</span><span class="sxs-lookup"><span data-stu-id="4b38c-107">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="4b38c-108">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="4b38c-108">Load\( FilePathName \)</span></span>

<span data-ttu-id="4b38c-109">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="4b38c-109">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="4b38c-110">ユーザー定義のスニペットを含む .snippets.ps1xml ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="4b38c-110">Loads a .snippets.ps1xml file that contains user-defined snippets.</span></span> <span data-ttu-id="4b38c-111">スニペットを作成する最も簡単な方法は、New-IseSnippet コマンドレットを使用することです。このコマンドレットでは、Windows PowerShell ISE を開始するたびにスニペットがロードされるように、自動的にスニペットをプロファイル フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="4b38c-111">The easiest way to create snippets is to use the New-IseSnippet cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="4b38c-112">**FilePathName** - スニペット定義を含む .snippets.ps1xml ファイルへのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="4b38c-112">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="4b38c-113">参照</span><span class="sxs-lookup"><span data-stu-id="4b38c-113">See Also</span></span>

- [<span data-ttu-id="4b38c-114">ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="4b38c-114">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="4b38c-115">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="4b38c-115">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="4b38c-116">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="4b38c-116">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
