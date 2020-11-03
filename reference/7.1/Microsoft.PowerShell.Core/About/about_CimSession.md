---
description: '**CimSession** オブジェクトと、CIM セッションと PowerShell セッションの違いについて説明します。'
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_cimsession?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CimSession
ms.openlocfilehash: d0d926efb3f534705f2cf3840e72408ac80b75c7
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93224131"
---
# <a name="about-cimsession"></a><span data-ttu-id="f6f70-104">CimSession について</span><span class="sxs-lookup"><span data-stu-id="f6f70-104">About CimSession</span></span>

## <a name="short-description"></a><span data-ttu-id="f6f70-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="f6f70-105">Short description</span></span>
<span data-ttu-id="f6f70-106">**CimSession** オブジェクトと、CIM セッションと PowerShell セッションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-106">Describes a **CimSession** object and the difference between CIM sessions and PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="f6f70-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="f6f70-107">Long description</span></span>

<span data-ttu-id="f6f70-108">Common Information Model (CIM) セッションは、ローカルコンピューターまたはリモートコンピューターへの接続を表すクライアント側オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f6f70-108">A Common Information Model (CIM) session is a client-side object that represents a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="f6f70-109">CIM セッションは、PowerShell セッション (PSSessions) の代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6f70-109">You can use CIM sessions as an alternative to PowerShell sessions (PSSessions).</span></span> <span data-ttu-id="f6f70-110">どちらの方法にも利点があります。</span><span class="sxs-lookup"><span data-stu-id="f6f70-110">Both approaches have advantages.</span></span>

<span data-ttu-id="f6f70-111">コマンドレットを使用して、 `New-CimSession` 接続に関する情報 (コンピューター名、接続に使用されるプロトコル、セッション id、インスタンス id など) を含む CIM セッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="f6f70-111">You can use the `New-CimSession` cmdlet to create a CIM session that contains information about a connection, such as computer name, the protocol used for the connection, session ID, and instance ID.</span></span>

<span data-ttu-id="f6f70-112">接続を確立するために必要な情報を指定する **CimSession** オブジェクトを作成した後、PowerShell は接続をすぐには確立しません。</span><span class="sxs-lookup"><span data-stu-id="f6f70-112">After you create a **CimSession** object that specifies information required to establish a connection, PowerShell does not establish the connection immediately.</span></span> <span data-ttu-id="f6f70-113">コマンドレットで CIM セッションを使用すると、PowerShell は指定されたコンピューターに接続し、コマンドレットが完了すると接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-113">When a cmdlet uses the CIM session, PowerShell connects to the specified computer, and then, when the cmdlet finishes, PowerShell terminates the connection.</span></span>

<span data-ttu-id="f6f70-114">CIM セッションを使用する代わりに **PSSession** を作成した場合は、PowerShell によって接続設定が検証され、接続が確立され、維持されます。</span><span class="sxs-lookup"><span data-stu-id="f6f70-114">If you create a **PSSession** instead of using a CIM session, PowerShell validates connection settings, and then establishes and maintains the connection.</span></span> <span data-ttu-id="f6f70-115">CIM セッションを使用する場合、PowerShell は必要になるまでネットワーク接続を開いていません。</span><span class="sxs-lookup"><span data-stu-id="f6f70-115">If you use CIM sessions, PowerShell does not open a network connection until needed.</span></span> <span data-ttu-id="f6f70-116">PowerShell セッションの詳細については、「 [about_PSSessions](about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f70-116">For more information about PowerShell sessions, see [about_PSSessions](about_PSSessions.md).</span></span>

## <a name="when-to-use-a-cim-session"></a><span data-ttu-id="f6f70-117">CIM セッションを使用する場合</span><span class="sxs-lookup"><span data-stu-id="f6f70-117">When to use a CIM session</span></span>

<span data-ttu-id="f6f70-118">CIM セッションを受け入れる WS-Man、Windows Management Instrumentation (WMI) プロバイダーまたは CIM を使用して操作するコマンドレットだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="f6f70-118">Only cmdlets that work with a Windows Management Instrumentation (WMI) provider or CIM over WS-Man accept CIM sessions.</span></span> <span data-ttu-id="f6f70-119">他のコマンドレットの場合は、 **Pssessions** を使用します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-119">For other cmdlets, use **PSSessions**.</span></span>

<span data-ttu-id="f6f70-120">CIM セッションを使用すると、PowerShell はローカルクライアントでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-120">When you use a CIM session, PowerShell runs the cmdlet on the local client.</span></span> <span data-ttu-id="f6f70-121">CIM セッションを使用して WMI プロバイダーに接続します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-121">It connects to the WMI provider using the CIM session.</span></span> <span data-ttu-id="f6f70-122">ターゲットコンピューターには、PowerShell、または Windows オペレーティングシステムの任意のバージョンが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="f6f70-122">The target computer does not require PowerShell, or even any version of the Windows operating system.</span></span>

<span data-ttu-id="f6f70-123">これに対して、コマンドレットは、 **PSSession** を使用してターゲットコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="f6f70-123">In contrast, a cmdlet run using a **PSSession** runs on the target computer.</span></span>
<span data-ttu-id="f6f70-124">ターゲットシステムに PowerShell が必要です。</span><span class="sxs-lookup"><span data-stu-id="f6f70-124">It requires PowerShell on the target system.</span></span> <span data-ttu-id="f6f70-125">さらに、コマンドレットは、ローカルコンピューターにデータを送り返します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-125">Furthermore, the cmdlet sends data back to the local computer.</span></span> <span data-ttu-id="f6f70-126">PowerShell は、接続を介して送信されるデータを管理し、Windows リモート管理 (WinRM) によって設定された制限内でサイズを保持します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-126">PowerShell manages the data sent over the connection, and keeps the size within the limits set by Windows Remote Management (WinRM).</span></span> <span data-ttu-id="f6f70-127">CIM セッションでは、WinRM の制限は課せられません。</span><span class="sxs-lookup"><span data-stu-id="f6f70-127">CIM sessions do not impose the WinRM limits.</span></span>

## <a name="using-cdxml-cmdlets"></a><span data-ttu-id="f6f70-128">CDXML コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="f6f70-128">Using CDXML cmdlets</span></span>

<span data-ttu-id="f6f70-129">CIM ベースのコマンドレット定義 XML (CDXML) コマンドレットは、任意の WMI プロバイダーを使用するように記述できます。</span><span class="sxs-lookup"><span data-stu-id="f6f70-129">CIM-based Cmdlet Definition XML (CDXML) cmdlets can be written to use any WMI Provider.</span></span> <span data-ttu-id="f6f70-130">すべての WMI プロバイダーは、 **CimSession** オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-130">All WMI providers use **CimSession** objects.</span></span> <span data-ttu-id="f6f70-131">CDXML の詳細については、「 [cdxml の定義と用語](/previous-versions/windows/desktop/wmi_v2/cdxml-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f70-131">For more information about CDXML, see [CDXML definition and terms](/previous-versions/windows/desktop/wmi_v2/cdxml-overview).</span></span>

<span data-ttu-id="f6f70-132">CDXML コマンドレットには、 **CimSession** オブジェクトの配列を受け取ることができる自動 **CimSession** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="f6f70-132">CDXML cmdlets have an automatic **CimSession** parameter that can take an array of **CimSession** objects.</span></span> <span data-ttu-id="f6f70-133">既定では、PowerShell は、同時に実行される CIM 接続の数を15に制限します。</span><span class="sxs-lookup"><span data-stu-id="f6f70-133">By default, PowerShell limits number of concurrent CIM Connections to 15.</span></span> <span data-ttu-id="f6f70-134">この制限は、 **ThrottleLimit** を実装する CDXML コマンドレットでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="f6f70-134">This limit can be overridden by CDXML cmdlets that implement the **ThrottleLimit**.</span></span> <span data-ttu-id="f6f70-135">**ThrottleLimit** を理解するには、個々のコマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6f70-135">See the individual cmdlet documentation to understand the **ThrottleLimit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6f70-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="f6f70-136">SEE ALSO</span></span>

[<span data-ttu-id="f6f70-137">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="f6f70-137">New-CimSession</span></span>](xref:CimCmdlets.New-CimSession)

[<span data-ttu-id="f6f70-138">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="f6f70-138">about_PSSessions</span></span>](about_PSSessions.md)

