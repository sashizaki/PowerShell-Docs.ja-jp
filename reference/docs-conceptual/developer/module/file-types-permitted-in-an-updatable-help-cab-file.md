---
title: 更新可能なヘルプ CAB ファイルで許可されているファイルの種類 |Microsoft Docs
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
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72367261"
---
# <a name="file-types-permitted-in-an-updatable-help-cab-file"></a><span data-ttu-id="bf66a-102">更新可能なヘルプ CAB ファイルで許可されるファイルの種類</span><span class="sxs-lookup"><span data-stu-id="bf66a-102">File Types Permitted in an Updatable Help CAB File</span></span>

<span data-ttu-id="bf66a-103">このトピックでは、更新可能なヘルプ CAB ファイルのコンテンツ要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="bf66a-103">This topics lists and describes the content requirements for Updatable Help CAB files.</span></span>

## <a name="updatable-help-cab-file-requirements"></a><span data-ttu-id="bf66a-104">更新可能なヘルプ CAB ファイルの要件</span><span class="sxs-lookup"><span data-stu-id="bf66a-104">Updatable Help CAB File Requirements</span></span>

<span data-ttu-id="bf66a-105">圧縮されていない CAB ファイルの内容は、既定で 1 GB に制限されています。</span><span class="sxs-lookup"><span data-stu-id="bf66a-105">Uncompressed CAB file content is limited to 1 GB by default.</span></span> <span data-ttu-id="bf66a-106">この[制限を回避](/powershell/module/Microsoft.PowerShell.Core/Save-Help)するには、ユーザー[は update-help コマンドレットと help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)コマンドレットの**Force**パラメーターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf66a-106">To bypass this limit, users have to use the **Force** parameter of the [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) and [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Save-Help) cmdlets.</span></span>

<span data-ttu-id="bf66a-107">インターネットからダウンロードされたヘルプファイルのセキュリティを確保するために、更新可能なヘルプ CAB ファイルには、以下に示すファイルの種類のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="bf66a-107">To assure the security of help files that are downloaded from the Internet, an Updatable Help CAB file can include only the file types listed below.</span></span> <span data-ttu-id="bf66a-108">Update-help[コマンドレット](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、ヘルプトピックスキーマに対してすべてのファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="bf66a-108">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) cmdlet validates all files against the help topic schemas.</span></span> <span data-ttu-id="bf66a-109">@No__t 0 のコマンドレットが、無効なファイルや許可されていない種類のファイルを検出した場合、無効なファイルはインストールされず、ユーザーのコンピューター上の CAB からのファイルのインストールが停止します。</span><span class="sxs-lookup"><span data-stu-id="bf66a-109">If the `Update-Help` cmdlet encounters a file that is invalid or is not a permitted type, it does not install the invalid file and stops installing files from the CAB on the user's computer.</span></span>

- <span data-ttu-id="bf66a-110">コマンドレットの XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="bf66a-110">XML-based help topics for cmdlets.</span></span>

- <span data-ttu-id="bf66a-111">スクリプトと関数の XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="bf66a-111">XML-based help topics for scripts and functions.</span></span>

- <span data-ttu-id="bf66a-112">Windows PowerShell プロバイダーの XML ベースのヘルプトピックです。</span><span class="sxs-lookup"><span data-stu-id="bf66a-112">XML-based help topics for Windows PowerShell providers.</span></span>

- <span data-ttu-id="bf66a-113">トピックの概要などのテキストベースのヘルプトピック。</span><span class="sxs-lookup"><span data-stu-id="bf66a-113">Text-based help topics, such as About topics.</span></span>

<span data-ttu-id="bf66a-114">[Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)は、cab をアンパックするときに cab の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="bf66a-114">The [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) verifies the CAB contents when it unpacks the CAB.</span></span> <span data-ttu-id="bf66a-115">@No__t-0 の場合、更新可能なヘルプ CAB ファイルで非対応のファイルの種類が検出されると、終了エラーが生成され、操作が停止されます。</span><span class="sxs-lookup"><span data-stu-id="bf66a-115">If `Update-Help` finds non-compliant file types in an Updatable Help CAB file, it generates a terminating error and stops the operation.</span></span> <span data-ttu-id="bf66a-116">準拠しているファイルの種類であっても、CAB からはヘルプファイルはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="bf66a-116">It does not install any help files from the CAB, even those of compliant file types.</span></span>