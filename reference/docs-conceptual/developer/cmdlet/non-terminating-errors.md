---
title: 終了しないエラー |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: d74c248e6ef54151400b8060d76524e89d87352c
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87786562"
---
# <a name="non-terminating-errors"></a><span data-ttu-id="9ceed-102">終了しないエラー</span><span class="sxs-lookup"><span data-stu-id="9ceed-102">Non-Terminating Errors</span></span>

<span data-ttu-id="9ceed-103">このトピックでは、終了しないエラーの報告に使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9ceed-103">This topic discusses the method used to report non-terminating errors.</span></span> <span data-ttu-id="9ceed-104">また、コマンドレット内からメソッドを呼び出す方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="9ceed-104">It also discusses how to call the method from within the cmdlet.</span></span>

<span data-ttu-id="9ceed-105">終了しないエラーが発生した場合、コマンドレットは[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出してこのエラーを報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9ceed-105">When a non-terminating error occurs, the cmdlet should report this error by calling the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method.</span></span> <span data-ttu-id="9ceed-106">コマンドレットが終了しないエラーを報告した場合、コマンドレットはこの入力オブジェクトおよびさらに受信パイプラインオブジェクトに対して引き続き操作できます。</span><span class="sxs-lookup"><span data-stu-id="9ceed-106">When the cmdlet reports a non-terminating error, the cmdlet can continue to operate on this input object and on further incoming pipeline objects.</span></span> <span data-ttu-id="9ceed-107">コマンドレットで[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)メソッドを呼び出すと、コマンドレットは、終了しないエラーの原因となった状態を説明するエラーレコードを書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="9ceed-107">If the cmdlet calls the [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) method, the cmdlet can write an error record that describes the condition that caused the non-terminating error.</span></span> <span data-ttu-id="9ceed-108">エラーレコードの詳細については、「 [Windows PowerShell エラーレコード](./windows-powershell-error-records.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9ceed-108">For more information about error records, see [Windows PowerShell Error Records](./windows-powershell-error-records.md).</span></span>

<span data-ttu-id="9ceed-109">コマンドレットは、入力処理メソッド内から必要に応じて[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="9ceed-109">Cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) as necessary from within their input processing methods.</span></span> <span data-ttu-id="9ceed-110">ただし、コマンドレットは[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出すことができます。このために[は、コマンド](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)[レットを呼び出し](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)たスレッド[、または system.](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) ................................... コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9ceed-110">However, cmdlets can call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) only from the thread that called the [System.Management.Automation.Cmdlet.BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), or [System.Management.Automation.Cmdlet.EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) input processing method.</span></span> <span data-ttu-id="9ceed-111">別のスレッドから[WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)を呼び出さないでください。</span><span class="sxs-lookup"><span data-stu-id="9ceed-111">Do not call [System.Management.Automation.Cmdlet.WriteError](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) from another thread.</span></span> <span data-ttu-id="9ceed-112">代わりに、エラーをメインスレッドに送り返します。</span><span class="sxs-lookup"><span data-stu-id="9ceed-112">Instead, communicate errors back to the main thread.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ceed-113">参照</span><span class="sxs-lookup"><span data-stu-id="9ceed-113">See Also</span></span>

[<span data-ttu-id="9ceed-114">WriteError (システム管理)</span><span class="sxs-lookup"><span data-stu-id="9ceed-114">System.Management.Automation.Cmdlet.WriteError</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[<span data-ttu-id="9ceed-115">システムの管理... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="9ceed-115">System.Management.Automation.Cmdlet.BeginProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[<span data-ttu-id="9ceed-116">システムの管理....................</span><span class="sxs-lookup"><span data-stu-id="9ceed-116">System.Management.Automation.Cmdlet.ProcessRecord</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[<span data-ttu-id="9ceed-117">システムの管理... コマンドレット</span><span class="sxs-lookup"><span data-stu-id="9ceed-117">System.Management.Automation.Cmdlet.EndProcessing</span></span>](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[<span data-ttu-id="9ceed-118">Windows PowerShell エラー レコード</span><span class="sxs-lookup"><span data-stu-id="9ceed-118">Windows PowerShell Error Records</span></span>](./windows-powershell-error-records.md)

[<span data-ttu-id="9ceed-119">Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)</span><span class="sxs-lookup"><span data-stu-id="9ceed-119">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
