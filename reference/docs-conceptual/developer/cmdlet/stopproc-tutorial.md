---
ms.date: 09/13/2016
ms.topic: reference
title: StopProc チュートリアル
description: StopProc チュートリアル
ms.openlocfilehash: 95229ee3c4905d295bd6991fe8ccf8c9840c3cdd
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646447"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="f0f3d-103">StopProc チュートリアル</span><span class="sxs-lookup"><span data-stu-id="f0f3d-103">StopProc Tutorial</span></span>

<span data-ttu-id="f0f3d-104">このセクションでは、Stop-Proc コマンドレットを作成するためのチュートリアルを提供します。これは、Windows PowerShell によって提供される [Stop Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) コマンドレットによく似ています。</span><span class="sxs-lookup"><span data-stu-id="f0f3d-104">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="f0f3d-105">このチュートリアルでは、コマンドレットの実装方法とコードの説明を示すコードのフラグメントを示します。</span><span class="sxs-lookup"><span data-stu-id="f0f3d-105">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="f0f3d-106">このチュートリアルのトピック</span><span class="sxs-lookup"><span data-stu-id="f0f3d-106">Topics in this Tutorial</span></span>

<span data-ttu-id="f0f3d-107">このチュートリアルのトピックは、前のトピックで説明した内容を各トピックで作成することで、順番に読むように設計されています。</span><span class="sxs-lookup"><span data-stu-id="f0f3d-107">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="f0f3d-108">[システムを変更するコマンドレットを作成](./creating-a-cmdlet-that-modifies-the-system.md) するこのセクションでは、コンピューター上で実行されているプロセスの停止など、システムの変更をサポートするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0f3d-108">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="f0f3d-109">[コマンドレットにユーザーメッセージを追加](./adding-user-messages-to-your-cmdlet.md) するこのセクションでは、ユーザーメッセージ、デバッグメッセージ、警告メッセージ、および進行状況に関する情報をコマンドレットに書き込む機能を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0f3d-109">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="f0f3d-110">[エイリアス、ワイルドカードの展開、およびコマンドレットパラメーターへのヘルプの追加](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) このセクションでは、パラメーターのエイリアス、ヘルプ、およびワイルドカードの展開をサポートするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0f3d-110">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="f0f3d-111">[コマンドレットへのパラメーターセットの追加](./adding-parameter-sets-to-a-cmdlet.md) ここでは、コマンドレットにパラメーターセットを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f0f3d-111">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="f0f3d-112">パラメーターセットを使用すると、ユーザーが指定したパラメーターに基づいて、コマンドレットの動作を変えることができます。</span><span class="sxs-lookup"><span data-stu-id="f0f3d-112">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0f3d-113">参照</span><span class="sxs-lookup"><span data-stu-id="f0f3d-113">See Also</span></span>

[<span data-ttu-id="f0f3d-114">システムを変更するコマンドレットを作成する</span><span class="sxs-lookup"><span data-stu-id="f0f3d-114">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="f0f3d-115">コマンドレットにユーザー メッセージを追加する</span><span class="sxs-lookup"><span data-stu-id="f0f3d-115">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="f0f3d-116">エイリアス、ワイルドカード展開、ヘルプをコマンドレット パラメーターに追加する</span><span class="sxs-lookup"><span data-stu-id="f0f3d-116">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="f0f3d-117">コマンドレットへのパラメーターセットの追加</span><span class="sxs-lookup"><span data-stu-id="f0f3d-117">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="f0f3d-118">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="f0f3d-118">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
