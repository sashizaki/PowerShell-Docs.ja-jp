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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72364441"
---
# <a name="getproc-tutorial"></a><span data-ttu-id="3264d-102">GetProc チュートリアル</span><span class="sxs-lookup"><span data-stu-id="3264d-102">GetProc Tutorial</span></span>

<span data-ttu-id="3264d-103">このセクションでは、Windows PowerShell によって提供される[Get Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process)コマンドレットによく似た get Proc コマンドレットを作成するためのチュートリアルを提供します。</span><span class="sxs-lookup"><span data-stu-id="3264d-103">This section provides a tutorial for creating a Get-Proc cmdlet that is very similar to the [Get-Process](/powershell/module/Microsoft.PowerShell.Management/Get-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="3264d-104">このチュートリアルでは、コマンドレットの実装方法とコードの説明を示すコードのフラグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="3264d-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="3264d-105">このチュートリアルのトピック</span><span class="sxs-lookup"><span data-stu-id="3264d-105">Topics in this Tutorial</span></span>

<span data-ttu-id="3264d-106">このチュートリアルのトピックは、前のトピックで説明した内容を各トピックで作成することで、順番に読むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3264d-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="3264d-107">[パラメーターを指定せずにコマンドレットを作成する](./creating-a-cmdlet-without-parameters.md)このセクションでは、パラメーターを使用せずにローカルコンピューターから情報を取得するコマンドレットを作成し、その情報をパイプラインに書き込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3264d-107">[Creating a Cmdlet without Parameters](./creating-a-cmdlet-without-parameters.md) This section describes how to create a cmdlet that retrieves information from the local computer without the use of parameters, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="3264d-108">[コマンドライン入力を処理するパラメーターの追加](./adding-parameters-that-process-command-line-input.md)このセクションでは、コマンドレットに渡された明示的なオブジェクトに基づいて入力を処理できるように、Get Proc コマンドレットにパラメーターを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3264d-108">[Adding Parameters that Process Command-Line Input](./adding-parameters-that-process-command-line-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process input based on explicit objects passed to the cmdlet.</span></span> <span data-ttu-id="3264d-109">ここで説明する実装では、名前に基づいてプロセスを取得し、その情報をパイプラインに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="3264d-109">The implementation described here retrieves processes based on their name, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="3264d-110">[パイプライン入力を処理するパラメーターの追加](./adding-parameters-that-process-pipeline-input.md)このセクションでは、コマンドレットがパイプラインを介して渡されたオブジェクトを処理できるように、Get Proc コマンドレットにパラメーターを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3264d-110">[Adding Parameters that Process Pipeline Input](./adding-parameters-that-process-pipeline-input.md) This section describes how to add a parameter to the Get-Proc cmdlet so that the cmdlet can process objects passed to it through the pipeline.</span></span> <span data-ttu-id="3264d-111">ここで説明する実装コマンドレットは、コマンドレットに渡されたオブジェクトに基づいてプロセスを取得し、その情報をパイプラインに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="3264d-111">The implementation cmdlet described here retrieves processes based on objects passed to the cmdlet, and then writes the information to the pipeline.</span></span>

<span data-ttu-id="3264d-112">[コマンドレットに終了しないエラー報告を追加して](./adding-non-terminating-error-reporting-to-your-cmdlet.md)いますこのセクションでは、終了しないエラー報告をコマンドレットに追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3264d-112">[Adding Nonterminating Error Reporting to Your Cmdlet](./adding-non-terminating-error-reporting-to-your-cmdlet.md) This section describes how to add nonterminating error reporting to a cmdlet.</span></span> <span data-ttu-id="3264d-113">ここで説明する実装では、入力を処理するときに発生する終了しないエラーを検出し、エラーレコードをエラーストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="3264d-113">The implementation described here detects nonterminating errors that occur when processing input, and writes an error record to the error stream.</span></span>

## <a name="see-also"></a><span data-ttu-id="3264d-114">参照</span><span class="sxs-lookup"><span data-stu-id="3264d-114">See Also</span></span>

[<span data-ttu-id="3264d-115">パラメーターを指定せずにコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="3264d-115">Creating a Cmdlet without Parameters</span></span>](./creating-a-cmdlet-without-parameters.md)

[<span data-ttu-id="3264d-116">コマンドライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="3264d-116">Adding Parameters that Process Command-Line Input</span></span>](./adding-parameters-that-process-command-line-input.md)

[<span data-ttu-id="3264d-117">パイプライン入力を処理するパラメーターの追加</span><span class="sxs-lookup"><span data-stu-id="3264d-117">Adding Parameters that Process Pipeline Input</span></span>](./adding-parameters-that-process-pipeline-input.md)

[<span data-ttu-id="3264d-118">コマンドレットに終了しないエラー報告を追加しています</span><span class="sxs-lookup"><span data-stu-id="3264d-118">Adding Nonterminating Error Reporting to Your Cmdlet</span></span>](./adding-non-terminating-error-reporting-to-your-cmdlet.md)

[<span data-ttu-id="3264d-119">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="3264d-119">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
