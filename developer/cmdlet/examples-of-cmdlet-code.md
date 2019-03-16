---
title: コマンドレット コードの例 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fed2f68-ce6d-4a8f-bf21-f94f27a155c2
caps.latest.revision: 9
ms.openlocfilehash: 936728d64f30a08fb9e2fa9ccef103683594aa3e
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58056262"
---
# <a name="examples-of-cmdlet-code"></a><span data-ttu-id="1c7b8-102">コマンドレット コードの例</span><span class="sxs-lookup"><span data-stu-id="1c7b8-102">Examples of Cmdlet Code</span></span>

<span data-ttu-id="1c7b8-103">このセクションでは、独自のコマンドレットの記述を開始するために使用できるコマンドレットのコードの例を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-103">This section contains examples of cmdlet code that you can use to start writing your own cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c7b8-104">コマンドレットを作成する手順を実行する場合に、「[コマンドレットの記述に関するチュートリアル](./tutorials-for-writing-cmdlets.md)します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-104">If you want step-by-step instructions for writing cmdlets, see [Tutorials for Writing Cmdlets](./tutorials-for-writing-cmdlets.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="1c7b8-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="1c7b8-105">In This Section</span></span>

<span data-ttu-id="1c7b8-106">[単純なコマンドレットの記述方法](./how-to-write-a-simple-cmdlet.md)コマンドレット コードの基本構造を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-106">[How to Write a Simple Cmdlet](./how-to-write-a-simple-cmdlet.md) This example shows the basic structure of cmdlet code.</span></span>

<span data-ttu-id="1c7b8-107">[コマンドレットのパラメーターを宣言する方法](./how-to-declare-cmdlet-parameters.md)この例は、異なる型のパラメーターを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-107">[How to Declare Cmdlet Parameters](./how-to-declare-cmdlet-parameters.md) This example shows how to declare the different types of parameters.</span></span>

<span data-ttu-id="1c7b8-108">[パラメーターの設定の宣言方法](./how-to-declare-parameter-sets.md)コマンドレットを実行するアクションを変更できるパラメーターのセットを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-108">[How to Declare Parameter Sets](./how-to-declare-parameter-sets.md) This example shows how to declare sets of parameters that can change the action a cmdlet performs.</span></span>

<span data-ttu-id="1c7b8-109">[パラメーターの入力の検証方法](./how-to-validate-parameter-input.md)これらの例は、パラメーターの入力を検証する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-109">[How to Validate Parameter Input](./how-to-validate-parameter-input.md) These examples show how to validate parameter input.</span></span>

<span data-ttu-id="1c7b8-110">[動的パラメーターを宣言する方法](./how-to-declare-dynamic-parameters.md)この例は、実行時に追加されるパラメーターを宣言する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-110">[How to Declare Dynamic Parameters](./how-to-declare-dynamic-parameters.md) This example shows how to declare a parameter that is added at runtime.</span></span>

<span data-ttu-id="1c7b8-111">[コマンドレット内でスクリプトを呼び出す方法](./how-to-invoke-scripts-within-a-cmdlet.md)コマンドレットに指定されているスクリプトを起動する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-111">[How to Invoke Scripts Within a Cmdlet](./how-to-invoke-scripts-within-a-cmdlet.md) This example shows how to invoke a script that is supplied to a cmdlet.</span></span>

<span data-ttu-id="1c7b8-112">[入力処理メソッドをオーバーライドする方法](./how-to-override-input-processing-methods.md)これらの例は、BeginProcessing、ProcessRecord、EndProcessing メソッドをオーバーライドするために使用する基本的な構造を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-112">[How To Override Input Processing Methods](./how-to-override-input-processing-methods.md) These examples show the basic structure used to override the BeginProcessing, ProcessRecord, and EndProcessing methods.</span></span>

<span data-ttu-id="1c7b8-113">[ShouldProcess の呼び出しをサポートする方法](./how-to-request-confirmations.md)この例では、どのように[System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)と[System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)メソッドは、コマンドレット内からを呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-113">[How to Support ShouldProcess Calls](./how-to-request-confirmations.md) This example shows how the [System.Management.Automation.Cmdlet.ShouldProcess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) and [System.Management.Automation.Cmdlet.ShouldContinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) methods should be called from within a cmdlet.</span></span>

<span data-ttu-id="1c7b8-114">[トランザクションをサポートする方法](./how-to-support-transactions.md)コマンドレットは、トランザクションをサポートしているを指定する方法と、トランザクション内でコマンドレットを使用する場合に実行するアクションを実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-114">[How to Support Transactions](./how-to-support-transactions.md) This example shows how to indicate that the cmdlet supports transactions and how to implement the action that is taken when the cmdlet is used within a transaction.</span></span>

<span data-ttu-id="1c7b8-115">[ジョブのサポート方法](./how-to-support-jobs.md)コマンドレットを記述するときにジョブをサポートする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-115">[How to Support Jobs](./how-to-support-jobs.md) This example shows how to support jobs when you write cmdlets.</span></span>

<span data-ttu-id="1c7b8-116">[コマンドレットからのコマンドレットを呼び出す方法](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md)この例は、別のコマンドレットが呼び出されたコマンドレットの機能を開発しているコマンドレットに追加することができます内からコマンドレットを呼び出す方法を示します。</span><span class="sxs-lookup"><span data-stu-id="1c7b8-116">[How to Invoke a Cmdlet From Within a Cmdlet](./how-to-invoke-a-cmdlet-from-within-a-cmdlet.md) This example shows how to invoke a cmdlet from within another cmdlet, which allows you to add the functionality of the invoked cmdlet to the cmdlet you are developing.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c7b8-117">参照</span><span class="sxs-lookup"><span data-stu-id="1c7b8-117">See Also</span></span>

[<span data-ttu-id="1c7b8-118">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="1c7b8-118">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
