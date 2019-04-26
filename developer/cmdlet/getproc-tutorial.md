---
title: GetProc チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4663905f-560a-4e39-9b03-6db2c315c322
caps.latest.revision: 6
ms.openlocfilehash: bbd07a0d0abd30742b7e02482adedae3af43aca4
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068098"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="57c04-102">GetProc チュートリアル</span><span class="sxs-lookup"><span data-stu-id="57c04-102">GetProc Tutorial</span></span>

<span data-ttu-id="57c04-103">このセクションによく似ていますが、Get-proc コマンドレットを作成する方法についてのチュートリアルを提供します、 [Get-process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットの Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="57c04-103">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="57c04-104">このチュートリアルでは、コマンドレットの実装方法を示すコードのフラグメントとコードの説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="57c04-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="57c04-105">このチュートリアルのトピック</span><span class="sxs-lookup"><span data-stu-id="57c04-105">Topics in this Tutorial</span></span>

<span data-ttu-id="57c04-106">このチュートリアルのトピックは、前のトピックで説明した内容に基づき、各トピックで、順番に読み取ることが設計されています。</span><span class="sxs-lookup"><span data-stu-id="57c04-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="57c04-107">[パラメーターを指定しないでコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)パラメーターを使用せず、ローカル コンピューターから情報を取得し、パイプラインに情報を書き込みますコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57c04-107">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="57c04-108">[そのプロセス コマンド ライン入力パラメーターを追加する](./adding-parameters-that-process-command-line-input.md)コマンドレットは、コマンドレットに渡される明示的なオブジェクトに基づく入力を処理できるように、Get-proc コマンドレットにパラメーターを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57c04-108">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="57c04-109">説明されている実装では、ここで、名前に基づいてプロセスを取得し、パイプラインに情報を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="57c04-109">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="57c04-110">[そのプロセス パイプラインの入力パラメーターを追加する](./adding-parameters-that-process-pipeline-input.md)コマンドレットは、パイプラインを介して渡されたオブジェクトを処理できるように、Get-proc コマンドレットにパラメーターを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57c04-110">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="57c04-111">説明されている実装コマンドレットは、ここで、コマンドレットに渡されたオブジェクトに基づいて、プロセスを取得し、パイプラインに情報を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="57c04-111">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="57c04-112">[終了しないエラーの報告を追加、コマンドレットに](./adding-non-terminating-error-reporting-to-your-cmdlet.md)終了しないエラーがレポートをコマンドレットに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="57c04-112">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="57c04-113">ここで説明されている実装では、入力を処理するときに発生してエラー レコードをエラー ストリームに書き込みを終了しないエラーを検出します。</span><span class="sxs-lookup"><span data-stu-id="57c04-113">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="57c04-114">参照</span><span class="sxs-lookup"><span data-stu-id="57c04-114">See Also</span></span>

[<span data-ttu-id="57c04-115">パラメーターを指定しないでコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="57c04-115">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="57c04-116">コマンドライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="57c04-116">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="57c04-117">プロセス パイプラインの入力パラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="57c04-117">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="57c04-118">終了しないエラーが報告、コマンドレットを追加します。</span><span class="sxs-lookup"><span data-stu-id="57c04-118">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="57c04-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="57c04-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
