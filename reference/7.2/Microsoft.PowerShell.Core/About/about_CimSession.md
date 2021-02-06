---
description: '**CimSession** オブジェクトと、CIM セッションと PowerShell セッションの違いについて説明します。'
Locale: en-US
ms.date: 05/13/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_cimsession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_CimSession
ms.openlocfilehash: 556c3db21ea5e410b28f5546cdd8a433e0bc3e50
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599316"
---
# <a name="about-cimsession"></a><span data-ttu-id="e279f-103">CimSession について</span><span class="sxs-lookup"><span data-stu-id="e279f-103">About CimSession</span></span>

## <a name="short-description"></a><span data-ttu-id="e279f-104">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="e279f-104">Short description</span></span>
<span data-ttu-id="e279f-105">**CimSession** オブジェクトと、CIM セッションと PowerShell セッションの違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e279f-105">Describes a **CimSession** object and the difference between CIM sessions and PowerShell sessions.</span></span>

## <a name="long-description"></a><span data-ttu-id="e279f-106">長い説明</span><span class="sxs-lookup"><span data-stu-id="e279f-106">Long description</span></span>

<span data-ttu-id="e279f-107">Common Information Model (CIM) セッションは、ローカルコンピューターまたはリモートコンピューターへの接続を表すクライアント側オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e279f-107">A Common Information Model (CIM) session is a client-side object that represents a connection to a local computer or a remote computer.</span></span> <span data-ttu-id="e279f-108">CIM セッションは、PowerShell セッション (PSSessions) の代わりに使用できます。</span><span class="sxs-lookup"><span data-stu-id="e279f-108">You can use CIM sessions as an alternative to PowerShell sessions (PSSessions).</span></span> <span data-ttu-id="e279f-109">どちらの方法にも利点があります。</span><span class="sxs-lookup"><span data-stu-id="e279f-109">Both approaches have advantages.</span></span>

<span data-ttu-id="e279f-110">コマンドレットを使用して、 `New-CimSession` 接続に関する情報 (コンピューター名、接続に使用されるプロトコル、セッション id、インスタンス id など) を含む CIM セッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e279f-110">You can use the `New-CimSession` cmdlet to create a CIM session that contains information about a connection, such as computer name, the protocol used for the connection, session ID, and instance ID.</span></span>

<span data-ttu-id="e279f-111">接続を確立するために必要な情報を指定する **CimSession** オブジェクトを作成した後、PowerShell は接続をすぐには確立しません。</span><span class="sxs-lookup"><span data-stu-id="e279f-111">After you create a **CimSession** object that specifies information required to establish a connection, PowerShell does not establish the connection immediately.</span></span> <span data-ttu-id="e279f-112">コマンドレットで CIM セッションを使用すると、PowerShell は指定されたコンピューターに接続し、コマンドレットが完了すると接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="e279f-112">When a cmdlet uses the CIM session, PowerShell connects to the specified computer, and then, when the cmdlet finishes, PowerShell terminates the connection.</span></span>

<span data-ttu-id="e279f-113">CIM セッションを使用する代わりに **PSSession** を作成した場合は、PowerShell によって接続設定が検証され、接続が確立され、維持されます。</span><span class="sxs-lookup"><span data-stu-id="e279f-113">If you create a **PSSession** instead of using a CIM session, PowerShell validates connection settings, and then establishes and maintains the connection.</span></span> <span data-ttu-id="e279f-114">CIM セッションを使用する場合、PowerShell は必要になるまでネットワーク接続を開いていません。</span><span class="sxs-lookup"><span data-stu-id="e279f-114">If you use CIM sessions, PowerShell does not open a network connection until needed.</span></span> <span data-ttu-id="e279f-115">PowerShell セッションの詳細については、「 [about_PSSessions](about_PSSessions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e279f-115">For more information about PowerShell sessions, see [about_PSSessions](about_PSSessions.md).</span></span>

## <a name="when-to-use-a-cim-session"></a><span data-ttu-id="e279f-116">CIM セッションを使用する場合</span><span class="sxs-lookup"><span data-stu-id="e279f-116">When to use a CIM session</span></span>

<span data-ttu-id="e279f-117">CIM セッションを受け入れる WS-Man、Windows Management Instrumentation (WMI) プロバイダーまたは CIM を使用して操作するコマンドレットだけが使用できます。</span><span class="sxs-lookup"><span data-stu-id="e279f-117">Only cmdlets that work with a Windows Management Instrumentation (WMI) provider or CIM over WS-Man accept CIM sessions.</span></span> <span data-ttu-id="e279f-118">他のコマンドレットの場合は、 **Pssessions** を使用します。</span><span class="sxs-lookup"><span data-stu-id="e279f-118">For other cmdlets, use **PSSessions**.</span></span>

<span data-ttu-id="e279f-119">CIM セッションを使用すると、PowerShell はローカルクライアントでコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e279f-119">When you use a CIM session, PowerShell runs the cmdlet on the local client.</span></span> <span data-ttu-id="e279f-120">CIM セッションを使用して WMI プロバイダーに接続します。</span><span class="sxs-lookup"><span data-stu-id="e279f-120">It connects to the WMI provider using the CIM session.</span></span> <span data-ttu-id="e279f-121">ターゲットコンピューターには、PowerShell、または Windows オペレーティングシステムの任意のバージョンが必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="e279f-121">The target computer does not require PowerShell, or even any version of the Windows operating system.</span></span>

<span data-ttu-id="e279f-122">これに対して、コマンドレットは、 **PSSession** を使用してターゲットコンピューター上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="e279f-122">In contrast, a cmdlet run using a **PSSession** runs on the target computer.</span></span>
<span data-ttu-id="e279f-123">ターゲットシステムに PowerShell が必要です。</span><span class="sxs-lookup"><span data-stu-id="e279f-123">It requires PowerShell on the target system.</span></span> <span data-ttu-id="e279f-124">さらに、コマンドレットは、ローカルコンピューターにデータを送り返します。</span><span class="sxs-lookup"><span data-stu-id="e279f-124">Furthermore, the cmdlet sends data back to the local computer.</span></span> <span data-ttu-id="e279f-125">PowerShell は、接続を介して送信されるデータを管理し、Windows リモート管理 (WinRM) によって設定された制限内でサイズを保持します。</span><span class="sxs-lookup"><span data-stu-id="e279f-125">PowerShell manages the data sent over the connection, and keeps the size within the limits set by Windows Remote Management (WinRM).</span></span> <span data-ttu-id="e279f-126">CIM セッションでは、WinRM の制限は課せられません。</span><span class="sxs-lookup"><span data-stu-id="e279f-126">CIM sessions do not impose the WinRM limits.</span></span>

## <a name="using-cdxml-cmdlets"></a><span data-ttu-id="e279f-127">CDXML コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="e279f-127">Using CDXML cmdlets</span></span>

<span data-ttu-id="e279f-128">CIM ベースのコマンドレット定義 XML (CDXML) コマンドレットは、任意の WMI プロバイダーを使用するように記述できます。</span><span class="sxs-lookup"><span data-stu-id="e279f-128">CIM-based Cmdlet Definition XML (CDXML) cmdlets can be written to use any WMI Provider.</span></span> <span data-ttu-id="e279f-129">すべての WMI プロバイダーは、 **CimSession** オブジェクトを使用します。</span><span class="sxs-lookup"><span data-stu-id="e279f-129">All WMI providers use **CimSession** objects.</span></span> <span data-ttu-id="e279f-130">CDXML の詳細については、「 [cdxml の定義と用語](/previous-versions/windows/desktop/wmi_v2/cdxml-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e279f-130">For more information about CDXML, see [CDXML definition and terms](/previous-versions/windows/desktop/wmi_v2/cdxml-overview).</span></span>

<span data-ttu-id="e279f-131">CDXML コマンドレットには、 **CimSession** オブジェクトの配列を受け取ることができる自動 **CimSession** パラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="e279f-131">CDXML cmdlets have an automatic **CimSession** parameter that can take an array of **CimSession** objects.</span></span> <span data-ttu-id="e279f-132">既定では、PowerShell は、同時に実行される CIM 接続の数を15に制限します。</span><span class="sxs-lookup"><span data-stu-id="e279f-132">By default, PowerShell limits number of concurrent CIM Connections to 15.</span></span> <span data-ttu-id="e279f-133">この制限は、 **ThrottleLimit** を実装する CDXML コマンドレットでオーバーライドできます。</span><span class="sxs-lookup"><span data-stu-id="e279f-133">This limit can be overridden by CDXML cmdlets that implement the **ThrottleLimit**.</span></span> <span data-ttu-id="e279f-134">**ThrottleLimit** を理解するには、個々のコマンドレットのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e279f-134">See the individual cmdlet documentation to understand the **ThrottleLimit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e279f-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="e279f-135">SEE ALSO</span></span>

[<span data-ttu-id="e279f-136">New-CimSession</span><span class="sxs-lookup"><span data-stu-id="e279f-136">New-CimSession</span></span>](xref:CimCmdlets.New-CimSession)

[<span data-ttu-id="e279f-137">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="e279f-137">about_PSSessions</span></span>](about_PSSessions.md)

