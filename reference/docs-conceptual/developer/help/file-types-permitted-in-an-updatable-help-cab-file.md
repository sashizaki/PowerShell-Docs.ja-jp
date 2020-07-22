---
title: 更新可能なヘルプ CAB ファイルで許可されるファイルの種類
ms.date: 03/22/2012
ms.openlocfilehash: 2a8e97edf8daaed915ea1a3e04565d996a2e15fd
ms.sourcegitcommit: de59ff77c6535fc772c1e327b3c823295eaed6ea
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2020
ms.locfileid: "86893137"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="23da4-102">更新可能なヘルプ CAB ファイルで許可されるファイルの種類</span><span class="sxs-lookup"><span data-stu-id="23da4-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="23da4-103">圧縮されていない CAB ファイルの内容は、既定で 1 GB に制限されています。</span><span class="sxs-lookup"><span data-stu-id="23da4-103">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="23da4-104">この[制限を回避](/powershell/module/Microsoft.PowerShell.Core/Save-Help)するには、ユーザー[は update-help コマンドレットと help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットの**Force**パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23da4-104">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="23da4-105">インターネットからダウンロードされたヘルプファイルのセキュリティを確保するために、更新可能なヘルプ CAB ファイルには、以下に示すファイルの種類のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="23da4-105">To assure the security of help files that are downloaded from the internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="23da4-106">Update-help[コマンドレット](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、ヘルプトピックスキーマに対してすべてのファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="23da4-106">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="23da4-107">`Update-Help`コマンドレットで、無効なファイルや許可されていない種類のファイルが検出された場合、無効なファイルはインストールされず、ユーザーのコンピューター上の CAB からのファイルのインストールは停止します。</span><span class="sxs-lookup"><span data-stu-id="23da4-107">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="23da4-108">コマンドレットの XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="23da4-108">XML-based help topics for cmdlets.</span></span>
- <span data-ttu-id="23da4-109">スクリプトと関数の XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="23da4-109">XML-based help topics for scripts and functions.</span></span>
- <span data-ttu-id="23da4-110">PowerShell プロバイダーの XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="23da4-110">XML-based help topics for PowerShell providers.</span></span>
- <span data-ttu-id="23da4-111">トピックの概要などのテキストベースのヘルプトピック。</span><span class="sxs-lookup"><span data-stu-id="23da4-111">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="23da4-112">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、cab をアンパックするときに cab の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="23da4-112">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="23da4-113">は `Update-Help` 、更新可能なヘルプ CAB ファイルで準拠していないファイルの種類を検出すると、終了エラーを生成し、操作を停止します。</span><span class="sxs-lookup"><span data-stu-id="23da4-113">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="23da4-114">準拠しているファイルの種類であっても、CAB からはヘルプファイルはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="23da4-114">It does not install any help files from the CAB, even those of compliant file types.</span></span>
