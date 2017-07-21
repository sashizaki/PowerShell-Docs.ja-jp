---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: Save-Script
ms.openlocfilehash: 7b692d33e3f86a89505b8d37c0da4177f3dff2c2
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="save-script"></a><span data-ttu-id="04d28-103">Save-Script</span><span class="sxs-lookup"><span data-stu-id="04d28-103">Save-Script</span></span>

<span data-ttu-id="04d28-104">Save-Script コマンドレットでは、指定した場所に保存することによって、スクリプト ファイルを確認できます。</span><span class="sxs-lookup"><span data-stu-id="04d28-104">Save-Script cmdlet lets you to review the script file by saving it to a specified location.</span></span>

## <a name="description"></a><span data-ttu-id="04d28-105">説明</span><span class="sxs-lookup"><span data-stu-id="04d28-105">Description</span></span>

<span data-ttu-id="04d28-106">Save-Script コマンドレットは指定したスクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="04d28-106">The Save-Script cmdlet saves the specified script.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="04d28-107">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="04d28-107">Cmdlet syntax</span></span>

```powershell
Get-Command -Name Save-Script -Module PowerShellGet -Syntax
```
## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="04d28-108">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="04d28-108">Cmdlet online help reference</span></span>

[<span data-ttu-id="04d28-109">Save-Script</span><span class="sxs-lookup"><span data-stu-id="04d28-109">Save-Script</span></span>](http://go.microsoft.com/fwlink/?LinkId=619786)

## <a name="example-commands"></a><span data-ttu-id="04d28-110">コマンド例</span><span class="sxs-lookup"><span data-stu-id="04d28-110">Example commands</span></span>

### <a name="example-1-save-a-script-from-a-repository"></a><span data-ttu-id="04d28-111">例 1: リポジトリからスクリプトを保存する</span><span class="sxs-lookup"><span data-stu-id="04d28-111">Example 1: Save a script from a repository</span></span>
<span data-ttu-id="04d28-112">このコマンドは、最新バージョンのスクリプト Fabrikam-ClientScript を GalleryINT リポジトリからローカル フォルダー C:\ScriptSharingDemo に保存します</span><span class="sxs-lookup"><span data-stu-id="04d28-112">This command saves the latest version of the script Fabrikam-ClientScript from GalleryINT repository to the local folder C:\ScriptSharingDemo</span></span>

```powershell
Save-Script -Name Fabrikam-ClientScript -Repository GalleryINT -Path C:\ScriptSharingDemo
```

### <a name="example-2-save-a-version-of-a-script-by-piping-from-the-find-script-cmdlet"></a><span data-ttu-id="04d28-113">例 2: Find-Script コマンドレットからパイプして、スクリプトのバージョンを保存する</span><span class="sxs-lookup"><span data-stu-id="04d28-113">Example 2: Save a version of a script by piping from the Find-Script cmdlet</span></span>

<span data-ttu-id="04d28-114">最初のコマンドで、リポジトリ GalleryINT からバージョン 1.5 の Fabrikam-ClientScript を検索して、フォルダー C:\ScriptSharingDemo に保存します</span><span class="sxs-lookup"><span data-stu-id="04d28-114">The first command finds version 1.5 of Fabrikam-ClientScript from the repository GalleryINT and saves it to the folder C:\ScriptSharingDemo</span></span>

<span data-ttu-id="04d28-115">2 番目のコマンドで、保存したスクリプト メタデータを検証します。</span><span class="sxs-lookup"><span data-stu-id="04d28-115">The second command validates the saved script metadata.</span></span>

```powershell
Find-Script -Name Fabrikam-ClientScript -Repository GalleryINT -RequiredVersion 1.5 | Save-Script -Path C:\\ScriptSharingDemo
Test-ScriptFileInfo C:\\ScriptSharingDemo\\Fabrikam-ClientScript.ps1

Version Name Author Description
------- ---- ------ -----------
1.5 Fabrikam-ClientScript manikb Description for the Fabrikam-ClientScript script
```

