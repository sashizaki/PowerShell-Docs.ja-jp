---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: ギャラリーの FileList 機能
ms.openlocfilehash: 5f372c943c73fa8e1014657394e40eaedef5d045
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003798"
---
# <a name="filelist-feature-in-the-gallery"></a><span data-ttu-id="cf596-103">ギャラリーの FileList 機能</span><span class="sxs-lookup"><span data-stu-id="cf596-103">FileList feature in the Gallery</span></span>

<span data-ttu-id="cf596-104">ギャラリーで公開されているすべてのパッケージの内容を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cf596-104">You are able to view the contents in all packages published in the gallery.</span></span>

<span data-ttu-id="cf596-105">この機能は 2 部構成になっています。パッケージ内のファイルを一覧表示し、サポートされているファイルの種類を対象にファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="cf596-105">This feature includes two parts: listing the files within the package, and displaying file contents for supported file types.</span></span> <span data-ttu-id="cf596-106">現在のところ、.ps1、.psm1、.psd1、.ps1xml、.xml、.txt をファイル拡張子に持つコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="cf596-106">Currently we support displaying the contents of the following file extensions: .ps1, .psm1, .psd1, .ps1xml, .xml and .txt.</span></span> <span data-ttu-id="cf596-107">次のリリースではサポートされるファイル拡張子の数が増える予定です。</span><span class="sxs-lookup"><span data-stu-id="cf596-107">We will be supporting more file extensions in the next releases.</span></span>

## <a name="where-to-find-filelist"></a><span data-ttu-id="cf596-108">FileList の見つけ方</span><span class="sxs-lookup"><span data-stu-id="cf596-108">Where to Find FileList</span></span>

<span data-ttu-id="cf596-109">個々のパッケージのページに、FileList セクションと **[表示]** リンクがあります。</span><span class="sxs-lookup"><span data-stu-id="cf596-109">On each individual package page, you will be able to find FileList section and a **Show** link.</span></span> <span data-ttu-id="cf596-110">[表示] をクリックすると、パッケージに含まれているパッケージの完全リストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf596-110">Click on the Show and you will find a complete list of items contained in the package.</span></span>

<span data-ttu-id="cf596-111">サポートされているファイルの種類はハイパーリンクとして表示されます。ハイパーリンクをクリックすると、新しいページが開き、ファイル コンテンツが表示されます。PowerShell 構文が強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf596-111">Each supported file type is displayed as a hyperlink, and clicking it will take you to a new page with file contents displayed in PowerShell syntax highlighting.</span></span> <span data-ttu-id="cf596-112">画面の上部にあるパッケージのタイトルまたはバージョンをクリックすると、パッケージ詳細ページに戻ります。</span><span class="sxs-lookup"><span data-stu-id="cf596-112">Clicking on the title or the version of the package, which is displayed at the top of the screen, will bring you back to package detail page.</span></span>
