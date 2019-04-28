---
title: コマンドレットの入力処理メソッド |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual methods (PowerShell SDK]
ms.assetid: b0bb8172-c9fa-454b-9f1b-57c3fe60671b
caps.latest.revision: 12
ms.openlocfilehash: a28c8d3df19bc72bf338d6abc4e02768c5097209
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62068489"
---
# <a name="cmdlet-input-processing-methods"></a><span data-ttu-id="0ce6a-102">コマンドレットの入力処理メソッド</span><span class="sxs-lookup"><span data-stu-id="0ce6a-102">Cmdlet Input Processing Methods</span></span>

<span data-ttu-id="0ce6a-103">コマンドレットは、1 つ以上の入力処理メソッドが作業を実行するには、このトピックで説明をオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-103">Cmdlets must override one or more of the input processing methods described in this topic to perform their work.</span></span>
<span data-ttu-id="0ce6a-104">これらのメソッドは、事前処理、入力の処理、および処理後の操作を実行するコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-104">These methods allow the cmdlet to perform operations of pre-processing, input processing, and post-processing.</span></span>
<span data-ttu-id="0ce6a-105">これらのメソッドでは、コマンドレットの処理を停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-105">These methods also allow you to stop cmdlet processing.</span></span>
<span data-ttu-id="0ce6a-106">これらのメソッドを使用する方法の詳細な例を参照してください。 [SelectStr チュートリアル](selectstr-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-106">For a more detailed example of how to use these methods, see [SelectStr Tutorial](selectstr-tutorial.md).</span></span>

## <a name="pre-processing-operations"></a><span data-ttu-id="0ce6a-107">処理前の操作</span><span class="sxs-lookup"><span data-stu-id="0ce6a-107">Pre-Processing Operations</span></span>

<span data-ttu-id="0ce6a-108">コマンドレットをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)コマンドレットによって後で処理されるすべてのレコードの有効な前処理の操作を追加します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-108">Cmdlets should override the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to add any preprocessing operations that are valid for all the records that will be processed later by the cmdlet.</span></span>
<span data-ttu-id="0ce6a-109">PowerShell コマンドのパイプラインを処理するとき PowerShell メソッドを呼び出しますこの 1 回パイプラインでのコマンドレットの各インスタンスについて。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-109">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="0ce6a-110">PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](/previous-versions/ms714429(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-110">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="0ce6a-111">次のコードでは、BeginProcessing メソッドの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-111">The following code shows an implementation of the BeginProcessing method.</span></span>

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a><span data-ttu-id="0ce6a-112">処理操作の入力</span><span class="sxs-lookup"><span data-stu-id="0ce6a-112">Input Processing Operations</span></span>

<span data-ttu-id="0ce6a-113">コマンドレットをオーバーライドできます、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)コマンドレットに送信される入力を処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-113">Cmdlets can override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the input that is sent to the cmdlet.</span></span>
<span data-ttu-id="0ce6a-114">PowerShell コマンドのパイプラインを処理するとき、PowerShell は、コマンドレットによって処理される各入力レコードのこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-114">When PowerShell processes a command pipeline, PowerShell calls this method for each input record that is processed by the cmdlet.</span></span>
<span data-ttu-id="0ce6a-115">PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](/previous-versions/ms714429(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-115">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="0ce6a-116">次のコードでは、ProcessRecord メソッドの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-116">The following code shows an implementation of the ProcessRecord method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a><span data-ttu-id="0ce6a-117">処理後の操作</span><span class="sxs-lookup"><span data-stu-id="0ce6a-117">Post-Processing Operations</span></span>

<span data-ttu-id="0ce6a-118">コマンドレットをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)コマンドレットによって処理されたすべてのレコードの有効な任意の後処理操作を追加するメソッド。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-118">Cmdlets should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method to add any post-processing operations that are valid for all the records that were processed by the cmdlet.</span></span>
<span data-ttu-id="0ce6a-119">コマンドレットが完了したら、オブジェクト変数をクリーンアップする必要がありますなどを処理します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-119">For example, your cmdlet might have to clean up object variables after it is finished processing.</span></span>

<span data-ttu-id="0ce6a-120">PowerShell コマンドのパイプラインを処理するとき PowerShell メソッドを呼び出しますこの 1 回パイプラインでのコマンドレットの各インスタンスについて。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-120">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="0ce6a-121">ただしは、PowerShell 実行時は呼び出さないこと、EndProcessing メソッド、コマンドレットがその入力の処理によって途中取り消された場合、または、コマンドレットのすべての部分では終了エラーが発生した場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-121">However, it is important to remember that the PowerShell runtime will not call the EndProcessing method if the cmdlet is canceled midway through its input processing or if a terminating error occurs in any part of the cmdlet.</span></span>
<span data-ttu-id="0ce6a-122">このため、オブジェクトのクリーンアップが必要なコマンドレットの完全な実装する必要があります[System.IDisposable](/dotnet/api/System.IDisposable)パターン、ファイナライザーをなど、ランタイムは両方、EndProcessing を呼び出すことができますと[System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose)処理の終了メソッド。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-122">For this reason, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including a finalizer, so that the runtime can call both the EndProcessing and [System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span>
<span data-ttu-id="0ce6a-123">PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](/previous-versions/ms714429(v=vs.85))します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-123">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="0ce6a-124">次のコードでは、EndProcessing メソッドの実装を示します。</span><span class="sxs-lookup"><span data-stu-id="0ce6a-124">The following code shows an implementation of the EndProcessing method.</span></span>

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a><span data-ttu-id="0ce6a-125">参照</span><span class="sxs-lookup"><span data-stu-id="0ce6a-125">See Also</span></span>

[<span data-ttu-id="0ce6a-126">System.Management.Automation.Cmdlet.BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="0ce6a-126">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="0ce6a-127">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="0ce6a-127">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="0ce6a-128">System.Management.Automation.Cmdlet.EndProcessing</span><span class="sxs-lookup"><span data-stu-id="0ce6a-128">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="0ce6a-129">SelectStr チュートリアル</span><span class="sxs-lookup"><span data-stu-id="0ce6a-129">SelectStr Tutorial</span></span>](selectstr-tutorial.md)

[<span data-ttu-id="0ce6a-130">System.IDisposable</span><span class="sxs-lookup"><span data-stu-id="0ce6a-130">System.IDisposable</span></span>](/dotnet/api/System.IDisposable)

[<span data-ttu-id="0ce6a-131">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="0ce6a-131">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
