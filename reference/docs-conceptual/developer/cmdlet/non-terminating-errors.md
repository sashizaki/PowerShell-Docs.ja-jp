---
ms.date: 09/13/2016
ms.topic: reference
title: 終了しないエラー
description: 終了しないエラー
ms.openlocfilehash: d23642103e005c6d3a6168b317b11f40001b6bbe
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655734"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="2e2e2-103">終了しないエラー</span><span class="sxs-lookup"><span data-stu-id="2e2e2-103">Non-Terminating Errors</span></span>

<span data-ttu-id="2e2e2-104">このトピックでは、終了しないエラーの報告に使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-104">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="2e2e2-105">また、コマンドレット内からメソッドを呼び出す方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-105">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="2e2e2-106">終了しないエラーが発生した場合、コマンドレットは [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) メソッドを呼び出してこのエラーを報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-106">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="2e2e2-107">コマンドレットが終了しないエラーを報告した場合、コマンドレットはこの入力オブジェクトおよびさらに受信パイプラインオブジェクトに対して引き続き操作できます。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-107">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="2e2e2-108">コマンドレットで [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) メソッドを呼び出すと、コマンドレットは、終了しないエラーの原因となった状態を説明するエラーレコードを書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-108">If the cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="2e2e2-109">エラーレコードの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-109">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="2e2e2-110">コマンドレットは、入力処理メソッド内から必要に応じて [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-110">Cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="2e2e2-111">ただし、コマンドレットは[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出すことができます。このために[は、コマンド](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)[レットを呼び出し](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)たスレッド[、または system.](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) ................................... コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-111">However, cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="2e2e2-112">別のスレッドから [WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) を呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-112">Do not call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="2e2e2-113">代わりに、エラーをメインスレッドに送り返します。</span><span class="sxs-lookup"><span data-stu-id="2e2e2-113">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e2e2-114">参照</span><span class="sxs-lookup"><span data-stu-id="2e2e2-114">See Also</span></span>

[<span data-ttu-id="2e2e2-115">WriteError (システム管理)</span><span class="sxs-lookup"><span data-stu-id="2e2e2-115">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="2e2e2-116">システムの管理... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="2e2e2-116">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="2e2e2-117">システムの管理....................</span><span class="sxs-lookup"><span data-stu-id="2e2e2-117">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="2e2e2-118">システムの管理... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="2e2e2-118">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="2e2e2-119">Windows PowerShell エラー レコード</span><span class="sxs-lookup"><span data-stu-id="2e2e2-119">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="2e2e2-120">Windows PowerShell コマンドレットの記述</span><span class="sxs-lookup"><span data-stu-id="2e2e2-120">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
