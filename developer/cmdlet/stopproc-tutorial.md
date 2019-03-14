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
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794401"
---
# <a name="stopproc-tutorial"></a><span data-ttu-id="8685e-102">StopProc チュートリアル</span><span class="sxs-lookup"><span data-stu-id="8685e-102">StopProc Tutorial</span></span>

<span data-ttu-id="8685e-103">このセクションによく似ていますが、停止 Proc コマンドレットを作成するためのチュートリアルを提供する、 [Stop-process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process)コマンドレットの Windows PowerShell によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="8685e-103">This section provides a tutorial for creating the Stop-Proc cmdlet, which is very similar to the [Stop-Process](/powershell/module/Microsoft.PowerShell.Management/Stop-Process) cmdlet provided by Windows PowerShell.</span></span> <span data-ttu-id="8685e-104">このチュートリアルでは、コマンドレットの実装方法を示すコードのフラグメントとコードの説明を提供します。</span><span class="sxs-lookup"><span data-stu-id="8685e-104">This tutorial provides fragments of code that illustrate how cmdlets are implemented, and an explanation of the code.</span></span>

## <a name="topics-in-this-tutorial"></a><span data-ttu-id="8685e-105">このチュートリアルのトピック</span><span class="sxs-lookup"><span data-stu-id="8685e-105">Topics in this Tutorial</span></span>

<span data-ttu-id="8685e-106">このチュートリアルのトピックは、前のトピックで説明した内容に基づき、各トピックで、順番に読み取ることが設計されています。</span><span class="sxs-lookup"><span data-stu-id="8685e-106">The topics in this tutorial are designed to be read sequentially, with each topic building on what was discussed in the previous topic.</span></span>

<span data-ttu-id="8685e-107">[システムを変更するコマンドレットを作成する](./creating-a-cmdlet-that-modifies-the-system.md)コンピューターで実行されているプロセスを停止するなど、システムの変更をサポートするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8685e-107">[Creating a Cmdlet that Modifies the System](./creating-a-cmdlet-that-modifies-the-system.md) This section describes how to create a cmdlet that supports system modifications, such as stopping a process running on the computer.</span></span>

<span data-ttu-id="8685e-108">[ユーザー メッセージのコマンドレットに追加](./adding-user-messages-to-your-cmdlet.md)コマンドレットに、ユーザー メッセージ、デバッグ メッセージ、警告メッセージ、および進行状況に関する情報を記述する機能を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8685e-108">[Adding User Messages to Your Cmdlet](./adding-user-messages-to-your-cmdlet.md) This section describes how to add the ability to write user messages, debug messages, warning messages, and progress information to your cmdlet.</span></span>

<span data-ttu-id="8685e-109">[ワイルドカードの展開のエイリアスを追加し、コマンドレット パラメーター](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)パラメーターのエイリアス、ヘルプ、およびワイルドカードの展開をサポートするコマンドレットを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8685e-109">[Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md) This section describes how to create a cmdlet that supports parameter aliases, Help, and wildcard expansion.</span></span>

<span data-ttu-id="8685e-110">[コマンドレットにパラメーターの設定を追加する](./adding-parameter-sets-to-a-cmdlet.md)コマンドレットにパラメーターの設定を追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8685e-110">[Adding Parameter Sets to Cmdlets](./adding-parameter-sets-to-a-cmdlet.md) This section describes how to add parameter sets to a cmdlet.</span></span> <span data-ttu-id="8685e-111">パラメーター セットは、に応じて異なるパラメーターがユーザーによって指定された動作するコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8685e-111">Parameter sets allow the cmdlet to operate differently based on what parameters are specified by the user.</span></span>

## <a name="see-also"></a><span data-ttu-id="8685e-112">参照</span><span class="sxs-lookup"><span data-stu-id="8685e-112">See Also</span></span>

[<span data-ttu-id="8685e-113">システムを変更するコマンドレットを作成します。</span><span class="sxs-lookup"><span data-stu-id="8685e-113">Creating a Cmdlet that Modifies the System</span></span>](./creating-a-cmdlet-that-modifies-the-system.md)

[<span data-ttu-id="8685e-114">ユーザー メッセージをコマンドレットに追加します。</span><span class="sxs-lookup"><span data-stu-id="8685e-114">Adding User Messages to Your Cmdlet</span></span>](./adding-user-messages-to-your-cmdlet.md)

[<span data-ttu-id="8685e-115">ワイルドカードの展開のエイリアスを追加し、コマンドレットのパラメーター</span><span class="sxs-lookup"><span data-stu-id="8685e-115">Adding Aliases, Wildcard Expansion, and Help to Cmdlet Parameters</span></span>](./adding-aliases-wildcard-expansion-and-help-to-cmdlet-parameters.md)

[<span data-ttu-id="8685e-116">コマンドレットにパラメーターを追加すると設定します。</span><span class="sxs-lookup"><span data-stu-id="8685e-116">Adding Parameter Sets to Cmdlets</span></span>](./adding-parameter-sets-to-a-cmdlet.md)

[<span data-ttu-id="8685e-117">Windows PowerShell SDK</span><span class="sxs-lookup"><span data-stu-id="8685e-117">Windows PowerShell SDK</span></span>](../windows-powershell-reference.md)
