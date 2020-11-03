---
description: "\"PowerShell で実行\" 機能を使用して、ファイルシステムドライブからスクリプトを実行する方法について説明します。"
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_run_with_powershell?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Run_With_PowerShell
ms.openlocfilehash: c5b1ca5d924c6eddd6371a269f694a5304510b25
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93223728"
---
# <a name="about-run-with-powershell"></a><span data-ttu-id="8b0f9-104">PowerShell を使用した実行について</span><span class="sxs-lookup"><span data-stu-id="8b0f9-104">About Run With PowerShell</span></span>

## <a name="short-description"></a><span data-ttu-id="8b0f9-105">概要</span><span class="sxs-lookup"><span data-stu-id="8b0f9-105">SHORT DESCRIPTION</span></span>
<span data-ttu-id="8b0f9-106">"PowerShell で実行" 機能を使用して、ファイルシステムドライブからスクリプトを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-106">Explains how to use the "Run with PowerShell" feature to run a script from a file system drive.</span></span>

## <a name="long-description"></a><span data-ttu-id="8b0f9-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="8b0f9-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="8b0f9-108">Windows PowerShell 3.0 以降では、"PowerShell で実行" 機能を使用して、Windows 8 および Windows Server 2012 のエクスプローラーと、以前のバージョンの Windows のエクスプローラーからスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-108">Beginning in Windows PowerShell 3.0, you can use the "Run with PowerShell" feature to run scripts from File Explorer in Windows 8 and Windows Server 2012 and from Windows Explorer in earlier versions of Windows.</span></span>

<span data-ttu-id="8b0f9-109">"PowerShell を使用して実行" 機能は、必要なパラメーターを持たず、コマンドプロンプトに出力を返さないスクリプトを実行するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-109">The "Run with PowerShell" feature is designed to run scripts that do not have required parameters and do not return output to the command prompt.</span></span>

<span data-ttu-id="8b0f9-110">"PowerShell を使用して実行" 機能を使用すると、PowerShell コンソールウィンドウが少しだけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-110">When you use the "Run with PowerShell" feature, the PowerShell console window appears only briefly, if at all.</span></span> <span data-ttu-id="8b0f9-111">これと対話することはできません。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-111">You cannot interact with it.</span></span>

<span data-ttu-id="8b0f9-112">"PowerShell で実行" 機能を使用するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-112">To use the "Run with PowerShell" feature:</span></span>

<span data-ttu-id="8b0f9-113">エクスプローラー (または Windows エクスプローラー) で、スクリプトファイルの名前を右クリックし、[PowerShell で実行] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-113">In File Explorer (or Windows Explorer), right-click the script file name and then select "Run with PowerShell".</span></span>

<span data-ttu-id="8b0f9-114">"PowerShell を使用して実行" 機能は、実行ポリシーがバイパスの PowerShell セッションを開始し、スクリプトを実行して、セッションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-114">The "Run with PowerShell" feature starts a PowerShell session that has an execution policy of Bypass, runs the script, and closes the session.</span></span>

<span data-ttu-id="8b0f9-115">次の形式のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-115">It runs a command that has the following format:</span></span>

```
PowerShell.exe -File <FileName> -ExecutionPolicy Bypass
```

<span data-ttu-id="8b0f9-116">"PowerShell で実行" は、スクリプトが実行されるセッション (PowerShell プロセスの現在のインスタンス) に対してのみバイパス実行ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-116">"Run with PowerShell" sets the Bypass execution policy only for the session (the current instance of the PowerShell process) in which the script runs.</span></span>
<span data-ttu-id="8b0f9-117">この機能では、コンピューターまたはユーザーの実行ポリシーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-117">This feature does not change the execution policy for the computer or the user.</span></span>

<span data-ttu-id="8b0f9-118">"PowerShell を使用して実行" 機能は、AllSigned 実行ポリシーによってのみ影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-118">The "Run with PowerShell" feature is affected only by the AllSigned execution policy.</span></span> <span data-ttu-id="8b0f9-119">コンピューターまたはユーザーに対して AllSigned 実行ポリシーが有効な場合は、"PowerShell で実行" は署名されたスクリプトのみを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-119">If the AllSigned execution policy is effective for the computer or the user, "Run with PowerShell" runs only signed scripts.</span></span> <span data-ttu-id="8b0f9-120">"PowerShell で実行" は、他の実行ポリシーの影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-120">"Run with PowerShell" is not affected by any other execution policy.</span></span> <span data-ttu-id="8b0f9-121">詳細については、「[about_Execution_Policies](about_Execution_Policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-121">For more information, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="8b0f9-122">トラブルシューティングに関する注意: PowerShell コマンドを使用して実行すると、実行ポリシーの変更を確認するメッセージが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8b0f9-122">Troubleshooting Note: Run with PowerShell command might prompt you to confirm the execution policy change.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b0f9-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="8b0f9-123">SEE ALSO</span></span>

[<span data-ttu-id="8b0f9-124">about_Execution_Policies</span><span class="sxs-lookup"><span data-stu-id="8b0f9-124">about_Execution_Policies</span></span>](about_Execution_Policies.md)

[<span data-ttu-id="8b0f9-125">about_Group_Policy_Settings</span><span class="sxs-lookup"><span data-stu-id="8b0f9-125">about_Group_Policy_Settings</span></span>](about_Group_Policy_Settings.md)

[<span data-ttu-id="8b0f9-126">about_Scripts</span><span class="sxs-lookup"><span data-stu-id="8b0f9-126">about_Scripts</span></span>](about_Scripts.md)
