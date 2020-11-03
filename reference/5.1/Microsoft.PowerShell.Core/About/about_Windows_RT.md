---
description: Windows RT 8.1 上の Windows PowerShell 4.0 の制限事項について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_windows_rt?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Windows_RT
ms.openlocfilehash: 323f06a7a0d8253417510503c1011ac02c20179f
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222435"
---
# <a name="about-windows-rt"></a><span data-ttu-id="40679-104">Windows RT について</span><span class="sxs-lookup"><span data-stu-id="40679-104">About Windows RT</span></span>

## <a name="short-description"></a><span data-ttu-id="40679-105">概要</span><span class="sxs-lookup"><span data-stu-id="40679-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="40679-106">Windows RT 8.1 上の Windows PowerShell 4.0 の制限事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="40679-106">Explains limitations of  Windows PowerShell 4.0 on Windows RT 8.1.</span></span>

## <a name="long-description"></a><span data-ttu-id="40679-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="40679-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="40679-108">Windows RT 8.1 オペレーティングシステムは、Advanced RISC Machine (ARM) プロセッサを使用するコンピューターとデバイス (Microsoft Surface 2 など、コンピューターに付属しているオペレーティングシステム) にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="40679-108">The Windows RT 8.1 operating system is installed on computers and devices (such as Microsoft Surface 2, on which it is the operating system that ships with the computer) that use Advanced RISC Machine (ARM) processors.</span></span>

<span data-ttu-id="40679-109">Windows PowerShell 4.0 は Windows RT 8.1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="40679-109">Windows PowerShell 4.0 is included in Windows RT 8.1.</span></span> <span data-ttu-id="40679-110">すべてのコマンドレット、プロバイダー、およびモジュール、および Windows PowerShell 2.0 以降のリリース向けに設計されたほとんどのスクリプトは、変更せずに Windows RT 8.1 上で動作します。</span><span class="sxs-lookup"><span data-stu-id="40679-110">All cmdlets, providers, and modules, and most scripts designed for Windows PowerShell 2.0 and later releases run on Windows RT 8.1 without changes.</span></span>

<span data-ttu-id="40679-111">Windows RT 8.1 には一部の Windows 機能が含まれていないため、windows PowerShell の一部の機能が異なる動作をしたり、Windows RT ベースのデバイスで動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="40679-111">Because Windows RT 8.1 does not include all Windows features, some Windows PowerShell features work differently or do not work on Windows RT-based devices.</span></span> <span data-ttu-id="40679-112">次の一覧では、その違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="40679-112">The following list explains the differences.</span></span>

- <span data-ttu-id="40679-113">Windows PowerShell ISE はに含まれておらず、Windows RT 8.1 で実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="40679-113">Windows PowerShell ISE is not included in and cannot run on Windows RT 8.1.</span></span>
  <span data-ttu-id="40679-114">Windows PowerShell ISE には Windows Presentation Foundation が必要ですが、Windows RT 8.1 には含まれていません。</span><span class="sxs-lookup"><span data-stu-id="40679-114">Windows PowerShell ISE requires Windows Presentation Foundation, which is not included in Windows RT 8.1.</span></span>

- <span data-ttu-id="40679-115">既定では、Windows PowerShell リモート処理と WinRM サービスは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="40679-115">Windows PowerShell remoting and the WinRM service are disabled by default.</span></span>
  <span data-ttu-id="40679-116">リモート処理を有効にするには、Enable-PSRemoting コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="40679-116">To enable remoting, run the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="40679-117">また、Set-Service コマンドレットを実行して、WinRM サービスのスタートアップの種類を [自動] または [自動 (遅延開始)] に設定します。</span><span class="sxs-lookup"><span data-stu-id="40679-117">Also, run the Set-Service cmdlet to set the startup type of the WinRM service to Automatic, or Automatic (Delayed Start).</span></span>

  <span data-ttu-id="40679-118">リモート処理が無効になっている場合は、Windows PowerShell リモート処理を使用して他のコンピューターでコマンドを実行できますが、Windows RT デバイスでコマンドを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="40679-118">While remoting is disabled, you can use Windows PowerShell remoting to run commands on other computers, but other computers cannot run commands on the Windows RT device.</span></span> <span data-ttu-id="40679-119">また、暗黙的なリモート処理 (つまり、コマンドレットまたはスクリプトに組み込まれていて、追加されたパラメーターで明示的に要求されていないリモート処理)</span><span class="sxs-lookup"><span data-stu-id="40679-119">Also, implicit remoting - that is, remoting that is built in to a cmdlet or script, and not explicitly requested with added parameters</span></span>
  - <span data-ttu-id="40679-120">Windows RT 8.1 で実行されている Windows PowerShell では機能しません。</span><span class="sxs-lookup"><span data-stu-id="40679-120">does not work in Windows PowerShell running on Windows RT 8.1.</span></span>

- <span data-ttu-id="40679-121">ドメインに参加しているコンピューティングと Kerberos 認証は、Windows RT 8.1 ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40679-121">Domain-joined computing and Kerberos authentication are not supported on Windows RT 8.1.</span></span> <span data-ttu-id="40679-122">Windows PowerShell を使用してこれらの機能を追加または管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="40679-122">You cannot use Windows PowerShell to add or manage these features.</span></span>

- <span data-ttu-id="40679-123">Windows RT 8.1 でサポートされていない Microsoft .NET Framework クラスは、windows RT 8.1 の Windows PowerShell でもサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40679-123">Microsoft .NET Framework classes that are not supported on Windows RT 8.1 are also not supported by Windows PowerShell on Windows RT 8.1.</span></span>

- <span data-ttu-id="40679-124">Windows RT 8.1 ではトランザクションが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="40679-124">Transactions are not enabled on Windows RT 8.1.</span></span> <span data-ttu-id="40679-125">トランザクションのコマンドレット (UseTransaction など) が正常に動作しない場合は、トランザクションのコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="40679-125">Transaction cmdlets, such as Start-Transaction, and transaction parameters, such as UseTransaction, do not work properly.</span></span>

- <span data-ttu-id="40679-126">Windows RT 8.1 デバイス上のすべての Windows PowerShell セッションでは、ConstrainedLanguage 言語モードが使用されます。</span><span class="sxs-lookup"><span data-stu-id="40679-126">All Windows PowerShell sessions on Windows RT 8.1 devices use the ConstrainedLanguage language mode.</span></span> <span data-ttu-id="40679-127">ConstrainedLanguage 言語モードは、ユーザーモードコードの整合性 (UMCI) に関連しています。</span><span class="sxs-lookup"><span data-stu-id="40679-127">ConstrainedLanguage language mode is a companion to User Mode Code Integrity (UMCI).</span></span> <span data-ttu-id="40679-128">すべての Windows コマンドレットと Windows PowerShell 言語要素が許可されますが、ユーザーが Windows PowerShell を使用して UMCI 保護を回避または違反しないように、型を制限します。</span><span class="sxs-lookup"><span data-stu-id="40679-128">It permits all Windows cmdlets and Windows PowerShell language elements, but restricts types to ensure that users cannot use Windows PowerShell to circumvent or violate the UMCI protections.</span></span>

<span data-ttu-id="40679-129">ConstrainedLanguage language モードの詳細については、「 [about_Language_Modes](about_Language_Modes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40679-129">For more information about ConstrainedLanguage language mode, see [about_Language_Modes](about_Language_Modes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="40679-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="40679-130">SEE ALSO</span></span>

[<span data-ttu-id="40679-131">about_Language_Modes</span><span class="sxs-lookup"><span data-stu-id="40679-131">about_Language_Modes</span></span>](about_Language_Modes.md)

[<span data-ttu-id="40679-132">about_Remote</span><span class="sxs-lookup"><span data-stu-id="40679-132">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="40679-133">about_Windows_PowerShell_ISE</span><span class="sxs-lookup"><span data-stu-id="40679-133">about_Windows_PowerShell_ISE</span></span>](about_Windows_PowerShell_ISE.md)
