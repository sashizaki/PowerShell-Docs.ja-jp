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
ms.openlocfilehash: 9d5c9b16fc5daf3d2f753eeeeedb0db925551a67
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56853778"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="7d489-102">終了しないエラー</span><span class="sxs-lookup"><span data-stu-id="7d489-102">Non-Terminating Errors</span></span>

<span data-ttu-id="7d489-103">このトピックでは、未終了エラーをレポートに使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7d489-103">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="7d489-104">コマンドレットは、内からメソッドを呼び出す方法も説明します。</span><span class="sxs-lookup"><span data-stu-id="7d489-104">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="7d489-105">コマンドレットが呼び出すことによってこのエラーを報告する必要があります、未終了エラーが発生したときに、 [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッド。</span><span class="sxs-lookup"><span data-stu-id="7d489-105">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="7d489-106">コマンドレットが、この入力オブジェクトとそれ以上の受信の動作を続行できますコマンドレットは、未終了エラーを報告、ときにオブジェクトをパイプラインします。</span><span class="sxs-lookup"><span data-stu-id="7d489-106">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="7d489-107">コマンドレットを呼び出す場合、 [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドでは、コマンドレットは、未終了エラーの原因となった状態を説明するエラー レコードを記述できます。</span><span class="sxs-lookup"><span data-stu-id="7d489-107">If the cmdlet calls the [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="7d489-108">エラー レコードの詳細については、次を参照してください。 [Windows PowerShell のエラー レコード](./windows-powershell-error-records.md)します。</span><span class="sxs-lookup"><span data-stu-id="7d489-108">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="7d489-109">コマンドレットを呼び出すことができます[System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)処理メソッドの入力の中から必要です。</span><span class="sxs-lookup"><span data-stu-id="7d489-109">Cmdlets can call [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="7d489-110">ただし、コマンドレットを呼び出すことができます[System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出したスレッドからのみ、 [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)、 [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)、または[System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)処理方法を入力します。</span><span class="sxs-lookup"><span data-stu-id="7d489-110">However, cmdlets can call [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.Beginprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.Processrecord\*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.Endprocessing\*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="7d489-111">呼び出さない[System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)別のスレッドから。</span><span class="sxs-lookup"><span data-stu-id="7d489-111">Do not call [System.Management.Automation.Cmdlet.Writeerror\*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="7d489-112">代わりに、メイン スレッドへのエラーを通知します。</span><span class="sxs-lookup"><span data-stu-id="7d489-112">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d489-113">参照</span><span class="sxs-lookup"><span data-stu-id="7d489-113">See Also</span></span>

[<span data-ttu-id="7d489-114">System.Management.Automation.Cmdlet.Writeerror\*</span><span class="sxs-lookup"><span data-stu-id="7d489-114">System.Management.Automation.Cmdlet.Writeerror\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="7d489-115">System.Management.Automation.Cmdlet.Beginprocessing\*</span><span class="sxs-lookup"><span data-stu-id="7d489-115">System.Management.Automation.Cmdlet.Beginprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="7d489-116">System.Management.Automation.Cmdlet.Processrecord\*</span><span class="sxs-lookup"><span data-stu-id="7d489-116">System.Management.Automation.Cmdlet.Processrecord\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="7d489-117">System.Management.Automation.Cmdlet.Endprocessing\*</span><span class="sxs-lookup"><span data-stu-id="7d489-117">System.Management.Automation.Cmdlet.Endprocessing\*</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="7d489-118">Windows PowerShell のエラー レコード</span><span class="sxs-lookup"><span data-stu-id="7d489-118">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="7d489-119">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="7d489-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
