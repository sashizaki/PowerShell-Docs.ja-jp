---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリーの FileList 機能
ms.openlocfilehash: 83273cfca0627cb9906ca6474092f9be9a120e4d
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2018
---
# <a name="filelist-feature-in-the-gallery"></a><span data-ttu-id="97c8b-103">ギャラリーの FileList 機能</span><span class="sxs-lookup"><span data-stu-id="97c8b-103">FileList feature in the Gallery</span></span>

<span data-ttu-id="97c8b-104">ギャラリーで公開されているすべてのアイテムの内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="97c8b-104">You are able to view the contents in all items published in the gallery.</span></span>

<span data-ttu-id="97c8b-105">この機能は 2 部構成になっています。アイテム内のファイルを一覧表示し、サポートされているファイルの種類を対象にファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="97c8b-105">This feature includes two parts: listing the files within the item, and displaying file contents for supported file types.</span></span> <span data-ttu-id="97c8b-106">現在のところ、.ps1、.psm1、.psd1、.ps1xml、.xml、.txt をファイル拡張子に持つコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="97c8b-106">Currently we support displaying the contents of the following file extensions: .ps1, .psm1, .psd1, .ps1xml, .xml and .txt.</span></span> <span data-ttu-id="97c8b-107">次のリリースではサポートされるファイル拡張子の数が増える予定です。</span><span class="sxs-lookup"><span data-stu-id="97c8b-107">We will be supporting more file extensions in the next releases.</span></span>

## <a name="where-to-find-filelist"></a><span data-ttu-id="97c8b-108">FileList の見つけ方</span><span class="sxs-lookup"><span data-stu-id="97c8b-108">Where to Find FileList</span></span>

<span data-ttu-id="97c8b-109">個々のアイテムのページに、FileList セクションと **[表示]** リンクがあります。</span><span class="sxs-lookup"><span data-stu-id="97c8b-109">On each individual item page, you will be able to find FileList section and a **Show** link.</span></span> <span data-ttu-id="97c8b-110">[表示] をクリックすると、アイテムに含まれているアイテムの完全リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="97c8b-110">Click on the Show and you will find a complete list of items contained in the item.</span></span>

<span data-ttu-id="97c8b-111">サポートされているファイルの種類はハイパーリンクとして表示されます。ハイパーリンクをクリックすると、新しいページが開き、ファイル コンテンツが表示されます。PowerShell 構文が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="97c8b-111">Each supported file type is displayed as a hyperlink, and clicking it will take you to a new page with file contents displayed in PowerShell syntax highlighting.</span></span> <span data-ttu-id="97c8b-112">画面の上部にあるアイテムのタイトルまたはバージョンをクリックすると、アイテム詳細ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="97c8b-112">Clicking on the title or the version of the item, which is displayed at the top of the screen, will bring you back to item detail page.</span></span>