---
title: 未終了エラー |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 468dabd6-bfeb-448d-8e09-0996db516edd
caps.latest.revision: 8
ms.openlocfilehash: 5f804756e0e3e867832f15f50967fd6987f160a5
ms.sourcegitcommit: caac7d098a448232304c9d6728e7340ec7517a71
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2019
ms.locfileid: "58054359"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="c7210-102">終了しないエラー</span><span class="sxs-lookup"><span data-stu-id="c7210-102">Non-Terminating Errors</span></span>

<span data-ttu-id="c7210-103">このトピックでは、未終了エラーをレポートに使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7210-103">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="c7210-104">コマンドレットは、内からメソッドを呼び出す方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="c7210-104">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="c7210-105">コマンドレットが呼び出すことによってこのエラーを報告する必要があります、未終了エラーが発生したときに、 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッド。</span><span class="sxs-lookup"><span data-stu-id="c7210-105">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="c7210-106">コマンドレットが、この入力オブジェクトとそれ以上の受信の動作を続行できますコマンドレットは、未終了エラーを報告、ときにオブジェクトをパイプラインします。</span><span class="sxs-lookup"><span data-stu-id="c7210-106">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="c7210-107">コマンドレットを呼び出す場合、 [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドでは、コマンドレットは、未終了エラーの原因となった状態を説明するエラー レコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="c7210-107">If the cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="c7210-108">エラー レコードの詳細については、[Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7210-108">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="c7210-109">コマンドレットを呼び出すことができます[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)処理メソッドの入力の中から必要です。</span><span class="sxs-lookup"><span data-stu-id="c7210-109">Cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="c7210-110">ただし、コマンドレットを呼び出すことができます[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出したスレッドからのみ、 [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、 [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、または[System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)処理方法を入力します。</span><span class="sxs-lookup"><span data-stu-id="c7210-110">However, cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="c7210-111">呼び出さない[System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)別のスレッドから。</span><span class="sxs-lookup"><span data-stu-id="c7210-111">Do not call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="c7210-112">代わりに、メイン スレッドへのエラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="c7210-112">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7210-113">参照</span><span class="sxs-lookup"><span data-stu-id="c7210-113">See Also</span></span>

[<span data-ttu-id="c7210-114">System.Management.Automation.Cmdlet.WriteError</span><span class="sxs-lookup"><span data-stu-id="c7210-114">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="c7210-115">System.Management.Automation.Cmdlet.BeginProcessing</span><span class="sxs-lookup"><span data-stu-id="c7210-115">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="c7210-116">System.Management.Automation.Cmdlet.ProcessRecord</span><span class="sxs-lookup"><span data-stu-id="c7210-116">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="c7210-117">System.Management.Automation.Cmdlet.EndProcessing</span><span class="sxs-lookup"><span data-stu-id="c7210-117">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="c7210-118">Windows PowerShell のエラー レコード</span><span class="sxs-lookup"><span data-stu-id="c7210-118">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="c7210-119">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="c7210-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
