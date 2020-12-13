---
ms.date: 03/22/2012
ms.topic: reference
title: 更新可能なヘルプ CAB ファイルで許可されるファイルの種類
description: 更新可能なヘルプ CAB ファイルで許可されるファイルの種類
ms.openlocfilehash: bb69b8b89a9a3a5c8c00059ec404a4d41a5db9a5
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92654740"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="8e8fa-103">更新可能なヘルプ CAB ファイルで許可されるファイルの種類</span><span class="sxs-lookup"><span data-stu-id="8e8fa-103">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="8e8fa-104">圧縮されていない CAB ファイルの内容は、既定で 1 GB に制限されています。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-104">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="8e8fa-105">この [制限を回避](/powershell/module/Microsoft.PowerShell.Core/Save-Help)するには、ユーザー [は update-help コマンドレットと help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットの **Force** パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-105">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="8e8fa-106">インターネットからダウンロードされたヘルプファイルのセキュリティを確保するために、更新可能なヘルプ CAB ファイルには、以下に示すファイルの種類のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-106">To assure the security of help files that are downloaded from the internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="8e8fa-107">Update-help [コマンドレット](/powershell/module/Microsoft.PowerShell.Core/Update-Help) は、ヘルプトピックスキーマに対してすべてのファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-107">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="8e8fa-108">`Update-Help`コマンドレットで、無効なファイルや許可されていない種類のファイルが検出された場合、無効なファイルはインストールされず、ユーザーのコンピューター上の CAB からのファイルのインストールは停止します。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-108">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="8e8fa-109">コマンドレットの XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-109">XML-based help topics for cmdlets.</span></span>
- <span data-ttu-id="8e8fa-110">スクリプトと関数の XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-110">XML-based help topics for scripts and functions.</span></span>
- <span data-ttu-id="8e8fa-111">PowerShell プロバイダーの XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-111">XML-based help topics for PowerShell providers.</span></span>
- <span data-ttu-id="8e8fa-112">トピックの概要などのテキストベースのヘルプトピック。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-112">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="8e8fa-113">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、cab をアンパックするときに cab の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-113">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="8e8fa-114">は `Update-Help` 、更新可能なヘルプ CAB ファイルで準拠していないファイルの種類を検出すると、終了エラーを生成し、操作を停止します。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-114">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="8e8fa-115">準拠しているファイルの種類であっても、CAB からはヘルプファイルはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="8e8fa-115">It does not install any help files from the CAB, even those of compliant file types.</span></span>
