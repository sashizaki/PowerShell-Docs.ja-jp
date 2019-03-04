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
ms.openlocfilehash: 931383858c0b83f0a9a66026c215e16481b89e9e
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56862838"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="d9ef7-102">更新可能なヘルプ CAB ファイルで許可されるファイルの種類</span><span class="sxs-lookup"><span data-stu-id="d9ef7-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="d9ef7-103">このトピックでは、一覧し、ヘルプの更新可能な CAB ファイルのコンテンツの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-103">This topics lists and describes the content requirements for Updatable Help CAB files.</span></span>

## <a name="updatable-help-cab-file-requirements"></a><span data-ttu-id="d9ef7-104">更新可能なヘルプの CAB ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="d9ef7-104">Updatable Help CAB File Requirements</span></span>

<span data-ttu-id="d9ef7-105">圧縮されていない CAB ファイルの内容は、既定では、1 GB に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-105">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="d9ef7-106">この制限をバイパスする、ユーザーが使用する必要、 **Force**のパラメーター、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-106">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>
<span data-ttu-id="d9ef7-107">圧縮されていない CAB ファイルの内容は、既定では、1 GB に制限されます。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-107">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="d9ef7-108">この制限をバイパスする、ユーザーが使用する必要、 **Force**のパラメーター、 [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレット。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-108">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="d9ef7-109">インターネットからダウンロードしたヘルプ ファイルのセキュリティを確保するために、ヘルプの更新可能な CAB ファイルは、以下に示すファイルの種類のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-109">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="d9ef7-110">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレット ヘルプ トピックのスキーマに対してすべてのファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-110">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="d9ef7-111">場合、`Update-Help`コマンドレットには、正しくないか許可されている型ではないファイルが検出すると、無効なファイルはインストールされませんし、ユーザーのコンピューターに cab ファイルからファイルのインストールを停止します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-111">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>
<span data-ttu-id="d9ef7-112">インターネットからダウンロードしたヘルプ ファイルのセキュリティを確保するために、ヘルプの更新可能な CAB ファイルは、以下に示すファイルの種類のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-112">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="d9ef7-113">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレット ヘルプ トピックのスキーマに対してすべてのファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-113">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="d9ef7-114">場合、`Update-Help`コマンドレットには、正しくないか許可されている型ではないファイルが検出すると、無効なファイルはインストールされませんし、ユーザーのコンピューターに cab ファイルからファイルのインストールを停止します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-114">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="d9ef7-115">XML ベースのコマンドレットのヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-115">XML-based help topics for cmdlets.</span></span>

- <span data-ttu-id="d9ef7-116">XML ベースのスクリプトや関数のトピックをヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-116">XML-based help topics for scripts and functions.</span></span>

- <span data-ttu-id="d9ef7-117">XML ベースの Windows PowerShell プロバイダーのヘルプ。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-117">XML-based help topics for Windows PowerShell providers.</span></span>

- <span data-ttu-id="d9ef7-118">テキスト ベースのトピックに関するヘルプ トピックについてをなどです。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-118">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="d9ef7-119">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cab ファイルをアンパックする場合は、CAB の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-119">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="d9ef7-120">場合`Update-Help`ヘルプの更新可能な CAB ファイルに非準拠のファイルの種類、終了エラーを生成し、操作を停止を検索します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-120">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="d9ef7-121">準拠しているファイルの種類のものも含め cab ファイルからヘルプ ファイルはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-121">It does not install any help files from the CAB, even those of compliant file types.</span></span>
<span data-ttu-id="d9ef7-122">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cab ファイルをアンパックする場合は、CAB の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-122">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="d9ef7-123">場合`Update-Help`ヘルプの更新可能な CAB ファイルに非準拠のファイルの種類、終了エラーを生成し、操作を停止を検索します。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-123">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="d9ef7-124">準拠しているファイルの種類のものも含め cab ファイルからヘルプ ファイルはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="d9ef7-124">It does not install any help files from the CAB, even those of compliant file types.</span></span>