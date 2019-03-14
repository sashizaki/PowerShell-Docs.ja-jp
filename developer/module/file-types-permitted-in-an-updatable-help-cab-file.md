---
title: ヘルプ CAB ファイルの更新可能なで許可されているファイルの種類 |Microsoft Docs
ms.custom: ''
ms.date: 03/22/2012
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Windows PowerShell 3.0
ms.assetid: acabdb93-c41a-4b8d-acbe-45cdab91e198
caps.latest.revision: 10
ms.openlocfilehash: 3562804157ebdfca561445a8671d726b55cc4efd
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794248"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="22368-102">更新可能なヘルプ CAB ファイルで許可されるファイルの種類</span><span class="sxs-lookup"><span data-stu-id="22368-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="22368-103">このトピックでは、一覧し、ヘルプの更新可能な CAB ファイルのコンテンツの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="22368-103">This topics lists and describes the content requirements for Updatable Help CAB files.</span></span>

## <a name="updatable-help-cab-file-requirements"></a><span data-ttu-id="22368-104">更新可能なヘルプの CAB ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="22368-104">Updatable Help CAB File Requirements</span></span>

<span data-ttu-id="22368-105">圧縮されていない CAB ファイルの内容は、既定では、1 GB に制限されます。</span><span class="sxs-lookup"><span data-stu-id="22368-105">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="22368-106">この制限をバイパスする、ユーザーが使用する必要、 **Force**のパラメーター、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="22368-106">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="22368-107">インターネットからダウンロードしたヘルプ ファイルのセキュリティを確保するために、ヘルプの更新可能な CAB ファイルは、以下に示すファイルの種類のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="22368-107">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="22368-108">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレット ヘルプ トピックのスキーマに対してすべてのファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="22368-108">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="22368-109">場合、`Update-Help`コマンドレットには、正しくないか許可されている型ではないファイルが検出すると、無効なファイルはインストールされませんし、ユーザーのコンピューターに cab ファイルからファイルのインストールを停止します。</span><span class="sxs-lookup"><span data-stu-id="22368-109">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="22368-110">XML ベースのコマンドレットのヘルプ。</span><span class="sxs-lookup"><span data-stu-id="22368-110">XML-based help topics for cmdlets.</span></span>

- <span data-ttu-id="22368-111">XML ベースのスクリプトや関数のトピックをヘルプ。</span><span class="sxs-lookup"><span data-stu-id="22368-111">XML-based help topics for scripts and functions.</span></span>

- <span data-ttu-id="22368-112">XML ベースの Windows PowerShell プロバイダーのヘルプ。</span><span class="sxs-lookup"><span data-stu-id="22368-112">XML-based help topics for Windows PowerShell providers.</span></span>

- <span data-ttu-id="22368-113">テキスト ベースのトピックに関するヘルプ トピックについてをなどです。</span><span class="sxs-lookup"><span data-stu-id="22368-113">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="22368-114">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cab ファイルをアンパックする場合は、CAB の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="22368-114">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="22368-115">場合`Update-Help`ヘルプの更新可能な CAB ファイルに非準拠のファイルの種類、終了エラーを生成し、操作を停止を検索します。</span><span class="sxs-lookup"><span data-stu-id="22368-115">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="22368-116">準拠しているファイルの種類のものも含め cab ファイルからヘルプ ファイルはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="22368-116">It does not install any help files from the CAB, even those of compliant file types.</span></span>