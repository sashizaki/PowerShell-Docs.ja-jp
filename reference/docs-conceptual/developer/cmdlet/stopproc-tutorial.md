---
title: StopProc チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a142aeb6-9c11-44a0-b34f-1f9470fa347b
caps.latest.revision: 5
ms.openlocfilehash: 27c8e2c7525aba38e69e50b2b7fd3b18b8e54989
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369411"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="e0d38-102">StopProc チュートリアル</span><span class="sxs-lookup"><span data-stu-id="e0d38-102">StopProc Tutorial</span></span>

<span data-ttu-id="e0d38-103">このセクションでは、Stop Proc コマンドレットを作成するためのチュートリアルを提供します。これは、Windows PowerShell によって提供される[Stop Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)コマンドレットによく似ています。</span><span class="sxs-lookup"><span data-stu-id="e0d38-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="e0d38-104">このチュートリアルでは、コマンドレットの実装方法とコードの説明を示すコードのフラグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="e0d38-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="e0d38-105">このチュートリアルのトピック</span><span class="sxs-lookup"><span data-stu-id="e0d38-105">Topics in this Tutorial</span></span>

<span data-ttu-id="e0d38-106">このチュートリアルのトピックは、前のトピックで説明した内容を各トピックで作成することで、順番に読むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e0d38-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="e0d38-107">[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md)するこのセクションでは、コンピューター上で実行されているプロセスの停止など、システムの変更をサポートするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0d38-107">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="e0d38-108">[コマンドレットにユーザーメッセージを追加](./adding-user-messages-to-your-cmdlet.md)するこのセクションでは、ユーザーメッセージ、デバッグメッセージ、警告メッセージ、および進行状況に関する情報をコマンドレットに書き込む機能を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0d38-108">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="e0d38-109">[エイリアス、ワイルドカードの展開、およびコマンドレットパラメーターへのヘルプの追加](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)このセクションでは、パラメーターのエイリアス、ヘルプ、およびワイルドカードの展開をサポートするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0d38-109">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="e0d38-110">[コマンドレットへのパラメーターセットの追加](./adding-parameter-sets-to-a-cmdlet.md)ここでは、コマンドレットにパラメーターセットを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0d38-110">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="e0d38-111">パラメーターセットを使用すると、ユーザーが指定したパラメーターに基づいて、コマンドレットの動作を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="e0d38-111">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0d38-112">参照</span><span class="sxs-lookup"><span data-stu-id="e0d38-112">See Also</span></span>

[<span data-ttu-id="e0d38-113">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="e0d38-113">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="e0d38-114">コマンドレットにユーザーメッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="e0d38-114">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="e0d38-115">エイリアス、ワイルドカードの展開、およびコマンドレットパラメーターへのヘルプの追加</span><span class="sxs-lookup"><span data-stu-id="e0d38-115">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="e0d38-116">コマンドレットへのパラメーターセットの追加</span><span class="sxs-lookup"><span data-stu-id="e0d38-116">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="e0d38-117">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="e0d38-117">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
