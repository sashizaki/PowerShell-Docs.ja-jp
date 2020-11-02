---
ms.date: 12/31/2019
title: ISESnippetCollection オブジェクト
description: ISESnippetCollection オブジェクトは、ISESnippet オブジェクトのコレクションです。 PowerShellTab オブジェクトに関連付けられているファイル コレクションは、このクラスのメンバーです。
ms.openlocfilehash: e6170ddf72d5ead840aa3015d4de1dcb21dbfeff
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92655973"
---
# <a name="the-isesnippetcollection-object"></a><span data-ttu-id="8867b-104">ISESnippetCollection オブジェクト</span><span class="sxs-lookup"><span data-stu-id="8867b-104">The ISESnippetCollection Object</span></span>

<span data-ttu-id="8867b-105">**ISESnippetCollection** オブジェクトは、 **ISESnippet** オブジェクトのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="8867b-105">The **ISESnippetCollection** object is a collection of **ISESnippet** objects.</span></span> <span data-ttu-id="8867b-106">**PowerShellTab** オブジェクトに関連付けられているファイル コレクションは、このクラスのメンバーです。</span><span class="sxs-lookup"><span data-stu-id="8867b-106">The files collection that is associated with a **PowerShellTab** object is a member of this class.</span></span> <span data-ttu-id="8867b-107">例は、`$psISE.CurrentPowerShellTab.Files` コレクションです。</span><span class="sxs-lookup"><span data-stu-id="8867b-107">An example is the `$psISE.CurrentPowerShellTab.Files` collection.</span></span>

## <a name="methods"></a><span data-ttu-id="8867b-108">メソッド</span><span class="sxs-lookup"><span data-stu-id="8867b-108">Methods</span></span>

### <a name="load-filepathname-"></a><span data-ttu-id="8867b-109">Load\( FilePathName \)</span><span class="sxs-lookup"><span data-stu-id="8867b-109">Load\( FilePathName \)</span></span>

<span data-ttu-id="8867b-110">Windows PowerShell ISE 3.0 以降でサポートされており、それよりも前のバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="8867b-110">Supported in Windows PowerShell ISE 3.0 and later, and not present in earlier versions.</span></span>

<span data-ttu-id="8867b-111">ユーザー定義のスニペットが含まれる `.snippets.ps1xml` ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="8867b-111">Loads a `.snippets.ps1xml` file that contains user-defined snippets.</span></span> <span data-ttu-id="8867b-112">スニペットを作成する最も簡単な方法は、`New-IseSnippet` コマンドレットを使用することです。このコマンドレットを使うと、Windows PowerShell ISE を開始するたびにスニペットがロードされるように、スニペットがプロファイル フォルダーに自動的に保存されます。</span><span class="sxs-lookup"><span data-stu-id="8867b-112">The easiest way to create snippets is to use the `New-IseSnippet` cmdlet, which automatically stores them in your profile folder so that they are loaded every time that you start Windows PowerShell ISE.</span></span>

<span data-ttu-id="8867b-113">**FilePathName** - スニペット定義を含む .snippets.ps1xml ファイルへのパスとファイル名。</span><span class="sxs-lookup"><span data-stu-id="8867b-113">**FilePathName** - String The path and file name to a .snippets.ps1xml file that contains snippet definitions.</span></span>

```powershell
# Loads a custom snippet file into the current PowerShell tab.
$SnipFile = Join-Path ( Split-Path $profile) 'Snippets\MySnips.snippets.ps1xml' $psISE.CurrentPowerShellTab.Snippets.Add($SnipPath)
```

## <a name="see-also"></a><span data-ttu-id="8867b-114">参照</span><span class="sxs-lookup"><span data-stu-id="8867b-114">See Also</span></span>

- [<span data-ttu-id="8867b-115">ISESnippetObject</span><span class="sxs-lookup"><span data-stu-id="8867b-115">The ISESnippetObject</span></span>](The-ISESnippetObject.md)
- [<span data-ttu-id="8867b-116">Windows PowerShell ISE スクリプト オブジェクト モデルの目的</span><span class="sxs-lookup"><span data-stu-id="8867b-116">Purpose of the Windows PowerShell ISE Scripting Object Model</span></span>](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [<span data-ttu-id="8867b-117">ISE オブジェクト モデルの階層</span><span class="sxs-lookup"><span data-stu-id="8867b-117">The ISE Object Model Hierarchy</span></span>](The-ISE-Object-Model-Hierarchy.md)
