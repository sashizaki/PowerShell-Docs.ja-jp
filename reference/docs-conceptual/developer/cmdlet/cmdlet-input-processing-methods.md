---
title: コマンドレットの入力処理方法 |Microsoft Docs
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
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72369871"
---
# <a name="cmdlet-input-processing-methods"></a><span data-ttu-id="8132e-102">コマンドレットの入力処理メソッド</span><span class="sxs-lookup"><span data-stu-id="8132e-102">Cmdlet Input Processing Methods</span></span>

<span data-ttu-id="8132e-103">コマンドレットは、このトピックで説明されている1つ以上の入力処理方法をオーバーライドして作業を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8132e-103">Cmdlets must override one or more of the input processing methods described in this topic to perform their work.</span></span>
<span data-ttu-id="8132e-104">これらのメソッドを使用すると、コマンドレットは、前処理、入力処理、および後処理の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8132e-104">These methods allow the cmdlet to perform operations of pre-processing, input processing, and post-processing.</span></span>
<span data-ttu-id="8132e-105">これらのメソッドを使用すると、コマンドレットの処理を停止することもできます。</span><span class="sxs-lookup"><span data-stu-id="8132e-105">These methods also allow you to stop cmdlet processing.</span></span>
<span data-ttu-id="8132e-106">これらのメソッドの使用方法の詳細な例については、「 [Selectstr チュートリアル](selectstr-tutorial.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8132e-106">For a more detailed example of how to use these methods, see [SelectStr Tutorial](selectstr-tutorial.md).</span></span>

## <a name="pre-processing-operations"></a><span data-ttu-id="8132e-107">処理前の操作</span><span class="sxs-lookup"><span data-stu-id="8132e-107">Pre-Processing Operations</span></span>

<span data-ttu-id="8132e-108">コマンドレットは、後でコマンドレットによって処理されるすべてのレコードに対して有効なすべての前処理操作を追加するように、[このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)オーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8132e-108">Cmdlets should override the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) method to add any preprocessing operations that are valid for all the records that will be processed later by the cmdlet.</span></span>
<span data-ttu-id="8132e-109">PowerShell がコマンドパイプラインを処理するとき、PowerShell は、パイプラインのコマンドレットの各インスタンスに対してこのメソッドを1回呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8132e-109">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="8132e-110">PowerShell がコマンドパイプラインを呼び出す方法の詳細については、「コマンド[レット処理のライフサイクル](/previous-versions/ms714429(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8132e-110">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="8132e-111">次のコードは、BeginProcessing メソッドの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="8132e-111">The following code shows an implementation of the BeginProcessing method.</span></span>

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a><span data-ttu-id="8132e-112">入力処理操作</span><span class="sxs-lookup"><span data-stu-id="8132e-112">Input Processing Operations</span></span>

<span data-ttu-id="8132e-113">コマンドレットでは[、コマンド](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)レットに送信される入力を処理するために、コマンドレットをオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="8132e-113">Cmdlets can override the [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) method to process the input that is sent to the cmdlet.</span></span>
<span data-ttu-id="8132e-114">PowerShell はコマンドパイプラインを処理するときに、コマンドレットによって処理される各入力レコードに対してこのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8132e-114">When PowerShell processes a command pipeline, PowerShell calls this method for each input record that is processed by the cmdlet.</span></span>
<span data-ttu-id="8132e-115">PowerShell がコマンドパイプラインを呼び出す方法の詳細については、「コマンド[レット処理のライフサイクル](/previous-versions/ms714429(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8132e-115">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="8132e-116">次のコードは、ProcessRecord メソッドの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="8132e-116">The following code shows an implementation of the ProcessRecord method.</span></span>

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a><span data-ttu-id="8132e-117">処理後の操作</span><span class="sxs-lookup"><span data-stu-id="8132e-117">Post-Processing Operations</span></span>

<span data-ttu-id="8132e-118">コマンドレットは、コマンドレットによって処理されたすべてのレコードに対して有効なすべての後処理操作を追加するように、[このメソッドを](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)オーバーライドする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8132e-118">Cmdlets should override the [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) method to add any post-processing operations that are valid for all the records that were processed by the cmdlet.</span></span>
<span data-ttu-id="8132e-119">たとえば、処理が完了した後に、コマンドレットでオブジェクト変数のクリーンアップが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8132e-119">For example, your cmdlet might have to clean up object variables after it is finished processing.</span></span>

<span data-ttu-id="8132e-120">PowerShell がコマンドパイプラインを処理するとき、PowerShell は、パイプラインのコマンドレットの各インスタンスに対してこのメソッドを1回呼び出します。</span><span class="sxs-lookup"><span data-stu-id="8132e-120">When PowerShell processes a command pipeline, PowerShell calls this method once for each instance of the cmdlet in the pipeline.</span></span>
<span data-ttu-id="8132e-121">ただし、コマンドレットが入力処理の途中で取り消された場合、またはコマンドレットのいずれかの部分で終了エラーが発生した場合は、PowerShell ランタイムが EndProcessing メソッドを呼び出さないことに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8132e-121">However, it is important to remember that the PowerShell runtime will not call the EndProcessing method if the cmdlet is canceled midway through its input processing or if a terminating error occurs in any part of the cmdlet.</span></span>
<span data-ttu-id="8132e-122">このため、オブジェクトのクリーンアップを必要とするコマンドレットは、ファイナライザーを含む完全な[IDisposable](/dotnet/api/System.IDisposable)パターンを実装する必要があります。これにより、処理の終了時にランタイムが EndProcessing メソッドと[system.servicemodel メソッドの両方を呼び](/dotnet/api/System.IDisposable.Dispose)出すことができるようになります。</span><span class="sxs-lookup"><span data-stu-id="8132e-122">For this reason, a cmdlet that requires object cleanup should implement the complete [System.IDisposable](/dotnet/api/System.IDisposable) pattern, including a finalizer, so that the runtime can call both the EndProcessing and [System.IDisposable.Dispose](/dotnet/api/System.IDisposable.Dispose) methods at the end of processing.</span></span>
<span data-ttu-id="8132e-123">PowerShell がコマンドパイプラインを呼び出す方法の詳細については、「コマンド[レット処理のライフサイクル](/previous-versions/ms714429(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8132e-123">For more information about how PowerShell invokes the command pipeline, see [Cmdlet Processing Lifecycle](/previous-versions/ms714429(v=vs.85)).</span></span>

<span data-ttu-id="8132e-124">次のコードは、EndProcessing メソッドの実装を示しています。</span><span class="sxs-lookup"><span data-stu-id="8132e-124">The following code shows an implementation of the EndProcessing method.</span></span>

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a><span data-ttu-id="8132e-125">参照</span><span class="sxs-lookup"><span data-stu-id="8132e-125">See Also</span></span>

[<span data-ttu-id="8132e-126">システムの管理... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8132e-126">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="8132e-127">システムの管理....................</span><span class="sxs-lookup"><span data-stu-id="8132e-127">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="8132e-128">システムの管理... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="8132e-128">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="8132e-129">SelectStr チュートリアル</span><span class="sxs-lookup"><span data-stu-id="8132e-129">SelectStr Tutorial</span></span>](selectstr-tutorial.md)

[<span data-ttu-id="8132e-130">System.IDisposable</span><span class="sxs-lookup"><span data-stu-id="8132e-130">System.IDisposable</span></span>](/dotnet/api/System.IDisposable)

[<span data-ttu-id="8132e-131">Windows PowerShell Shell SDK</span><span class="sxs-lookup"><span data-stu-id="8132e-131">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
