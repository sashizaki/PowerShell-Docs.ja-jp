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
ms.openlocfilehash: 7f8d25e03707052b1d5b62e245caae360da11d0b
ms.sourcegitcommit: 5990f04b8042ef2d8e571bec6d5b051e64c9921c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2019
ms.locfileid: "57794945"
---
# <a name="cmdlet-input-processing-methods"></a><span data-ttu-id="be37b-102">コマンドレットの入力処理メソッド</span><span class="sxs-lookup"><span data-stu-id="be37b-102">Cmdlet Input Processing Methods</span></span>

<span data-ttu-id="be37b-103">コマンドレットは、1 つ以上の入力処理メソッドが作業を実行するには、このトピックで説明をオーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be37b-103">Cmdlets must override one or more of the input processing methods described in this topic to perform their work.</span></span> <span data-ttu-id="be37b-104">これらのメソッドは、処理前の操作、入力処理操作、および処理後の操作を実行するコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="be37b-104">These methods allow the cmdlet to perform pre-processing operations, input processing operations, and post-processing operations.</span></span> <span data-ttu-id="be37b-105">これらのメソッドでは、コマンドレットの処理を停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="be37b-105">These methods also allow you to stop cmdlet processing.</span></span>

## <a name="pre-processing-tasks"></a><span data-ttu-id="be37b-106">処理前のタスク</span><span class="sxs-lookup"><span data-stu-id="be37b-106">Pre-Processing Tasks</span></span>

<span data-ttu-id="be37b-107">コマンドレットをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.Beginprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)コマンドレットによって後で処理されるすべてのレコードの有効な前処理の操作を追加します。</span><span class="sxs-lookup"><span data-stu-id="be37b-107">Cmdlets should override the [System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) method to add any preprocessing operations that are valid for all the records that will be processed later by the cmdlet.</span></span> <span data-ttu-id="be37b-108">Windows PowerShell コマンドのパイプラインを処理するとき Windows PowerShell はこのメソッド 1 回パイプラインでのコマンドレットの各インスタンスについて、</span><span class="sxs-lookup"><span data-stu-id="be37b-108">When Windows PowerShell processes a command pipeline, Windows PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span> <span data-ttu-id="be37b-109">Windows PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5)します。</span><span class="sxs-lookup"><span data-stu-id="be37b-109">For more information about how Windows PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span></span>

<span data-ttu-id="be37b-110">次のコードの実装を示します、 [System.Management.Automation.Cmdlet.Beginprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)メソッド。</span><span class="sxs-lookup"><span data-stu-id="be37b-110">The following code shows an implementation of the [System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) method.</span></span>

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the BeginProcessing template."
  WriteObject("This is a test of the BeginProcessing template.");
}
```

<span data-ttu-id="be37b-111">使用する方法の詳細な例については、 [System.Management.Automation.Cmdlet.Beginprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)メソッドを参照してください[SelectStr チュートリアル](./selectstr-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="be37b-111">For a more detailed example of how to use the [System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) method, see [SelectStr Tutorial](./selectstr-tutorial.md).</span></span> <span data-ttu-id="be37b-112">このチュートリアルで、**選択 Str**コマンドレットを使用して、 [System.Management.Automation.Cmdlet.Beginprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)検索入力レコードの処理に使用される正規表現を生成します。</span><span class="sxs-lookup"><span data-stu-id="be37b-112">In this tutorial, the **Select-Str** cmdlet uses the [System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0) method to generate the regular expression that is used to search the input processing records.</span></span>

## <a name="input-processing-tasks"></a><span data-ttu-id="be37b-113">処理タスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="be37b-113">Input Processing Tasks</span></span>

<span data-ttu-id="be37b-114">コマンドレットをオーバーライドできます、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)コマンドレットに送信される入力を処理するメソッド。</span><span class="sxs-lookup"><span data-stu-id="be37b-114">Cmdlets can override the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method to process the input that is sent to the cmdlet.</span></span> <span data-ttu-id="be37b-115">Windows PowerShell コマンドのパイプラインを処理するとき、Windows PowerShell は、コマンドレットによって処理される各入力レコードのこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="be37b-115">When Windows PowerShell processes a command pipeline, Windows PowerShell calls this method for each input record that is processed by the cmdlet.</span></span> <span data-ttu-id="be37b-116">Windows PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5)します。</span><span class="sxs-lookup"><span data-stu-id="be37b-116">For more information about how Windows PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span></span>

<span data-ttu-id="be37b-117">次のコードの実装を示します、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)メソッド。</span><span class="sxs-lookup"><span data-stu-id="be37b-117">The following code shows an implementation of the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the ProcessRecord template."
  WriteObject("This is a test of the ProcessRecord template.");
}
```

<span data-ttu-id="be37b-118">使用する方法の詳細な例については、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)メソッドを参照してください[SelectStr チュートリアル](./selectstr-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="be37b-118">For a more detailed example of how to use the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method, see [SelectStr Tutorial](./selectstr-tutorial.md).</span></span>

## <a name="post-processing-tasks"></a><span data-ttu-id="be37b-119">処理後のタスク</span><span class="sxs-lookup"><span data-stu-id="be37b-119">Post-Processing Tasks</span></span>

<span data-ttu-id="be37b-120">コマンドレットをオーバーライドする必要があります、 [System.Management.Automation.Cmdlet.Endprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)コマンドレットによって処理されたすべてのレコードの有効な任意の後処理操作を追加するメソッド。</span><span class="sxs-lookup"><span data-stu-id="be37b-120">Cmdlets should override the [System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) method to add any post-processing operations that are valid for all the records that were processed by the cmdlet.</span></span> <span data-ttu-id="be37b-121">コマンドレットが完了したら、オブジェクト変数をクリーンアップする必要がありますなどを処理します。</span><span class="sxs-lookup"><span data-stu-id="be37b-121">For example, your cmdlet might have to clean up object variables after it is finished processing.</span></span>

<span data-ttu-id="be37b-122">Windows PowerShell コマンドのパイプラインを処理するとき Windows PowerShell はこのメソッド 1 回パイプラインでのコマンドレットの各インスタンスについて、</span><span class="sxs-lookup"><span data-stu-id="be37b-122">When Windows PowerShell processes a command pipeline, Windows PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span> <span data-ttu-id="be37b-123">ただし、それは、Windows PowerShell ランタイムを呼び出さないことに注意してください、 [System.Management.Automation.Cmdlet.Endprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)メソッドの場合、コマンドレットは、その入力の処理によって途中キャンセルまたは終端コマンドレットのすべての部分で、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="be37b-123">However, it is important to remember that the Windows PowerShell runtime will not call the [System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) method if the cmdlet is canceled midway through its input processing or if a terminating error occurs in any part of the cmdlet.</span></span> <span data-ttu-id="be37b-124">このため、オブジェクトのクリーンアップが必要なコマンドレットの完全な実装する必要があります[System.Idisposable](/dotnet/api/System.IDisposable)パターン、ファイナライザーをなど、ランタイムは、両方を呼び出すことができます、 [System.Management.Automation.Cmdlet.Endprocessing%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)と[System.Idisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose)処理の終了メソッド。</span><span class="sxs-lookup"><span data-stu-id="be37b-124">For this reason, a cmdlet that requires object cleanup should implement the complete [System.Idisposable](/dotnet/api/System.IDisposable) pattern, including a finalizer, so that the runtime can call both the [System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0) and [System.Idisposable.Dispose\*](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span> <span data-ttu-id="be37b-125">Windows PowerShell がコマンドのパイプラインを呼び出す方法の詳細については、次を参照してください。[コマンドレットの処理ライフ サイクル](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5)します。</span><span class="sxs-lookup"><span data-stu-id="be37b-125">For more information about how Windows PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](https://msdn.microsoft.com/en-us/3202f55c-314d-4ac3-ad78-4c7ca72253c5).</span></span>

<span data-ttu-id="be37b-126">次のコードの実装を示します、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)メソッド。</span><span class="sxs-lookup"><span data-stu-id="be37b-126">The following code shows an implementation of the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method.</span></span>

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required
  // by your cmdlet. It is used here to generate the following
  // output:
  // "This is a test of the EndProcessing template."
  WriteObject("This is a test of the EndProcessing template.");
}
```

<span data-ttu-id="be37b-127">使用する方法の詳細な例については、 [System.Management.Automation.Cmdlet.Processrecord%2A でしょうか。Displayproperty = Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)メソッドを参照してください[SelectStr チュートリアル](./selectstr-tutorial.md)します。</span><span class="sxs-lookup"><span data-stu-id="be37b-127">For a more detailed example of how to use the [System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0) method, see [SelectStr Tutorial](./selectstr-tutorial.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="be37b-128">参照</span><span class="sxs-lookup"><span data-stu-id="be37b-128">See Also</span></span>

[<span data-ttu-id="be37b-129">System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname</span><span class="sxs-lookup"><span data-stu-id="be37b-129">System.Management.Automation.Cmdlet.Beginprocessing%2A?Displayproperty=Fullname</span></span>](/dotnet/api/system.management.automation.cmdlet.beginprocessing?view=powershellsdk-1.1.0)

[<span data-ttu-id="be37b-130">System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname</span><span class="sxs-lookup"><span data-stu-id="be37b-130">System.Management.Automation.Cmdlet.Processrecord%2A?Displayproperty=Fullname</span></span>](/dotnet/api/system.management.automation.cmdlet.processrecord?view=powershellsdk-1.1.0)

[<span data-ttu-id="be37b-131">System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname</span><span class="sxs-lookup"><span data-stu-id="be37b-131">System.Management.Automation.Cmdlet.Endprocessing%2A?Displayproperty=Fullname</span></span>](/dotnet/api/system.management.automation.cmdlet.endprocessing?view=powershellsdk-1.1.0)

[<span data-ttu-id="be37b-132">System.Idisposable</span><span class="sxs-lookup"><span data-stu-id="be37b-132">System.Idisposable</span></span>](/dotnet/api/System.IDisposable)

[<span data-ttu-id="be37b-133">Windows PowerShell シェル SDK</span><span class="sxs-lookup"><span data-stu-id="be37b-133">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
