---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "以前のバージョンの Windows で Windows PowerShell を開始する"
ms.assetid: 57125436-3d1e-4e7f-b5c4-8f0ecb49d642
ms.openlocfilehash: 52e3acc1fd3009ecad3b7134008e38d4edfb5ca7
ms.sourcegitcommit: d6ab9ab5909ed59cce4ce30e29457e0e75c7ac12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2017
---
# <a name="starting-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="c4c5c-103">以前のバージョンの Windows で Windows PowerShell を開始する</span><span class="sxs-lookup"><span data-stu-id="c4c5c-103">Starting Windows PowerShell on Earlier Versions of Windows</span></span>
<span data-ttu-id="c4c5c-104">このセクションでは、Windows® 7、Windows Server® 2008 R2、Windows Server® 2008 で、Windows PowerShell と Windows PowerShell Integrated Scripting Environment (ISE) を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-104">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows® 7, Windows Server® 2008 R2, and Windows Server® 2008.</span></span> <span data-ttu-id="c4c5c-105">Windows Server® 2008 R2 と Windows Server® 2008 で、Windows PowerShell 2.0 の Windows PowerShell ISE のオプション機能を有効にする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-105">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server® 2008 R2 and Windows Server® 2008.</span></span>

<span data-ttu-id="c4c5c-106">サポートされるシステムで Windows PowerShell 4.0 をインストールするには、[Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkID=293881) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-106">To install Windows PowerShell 4.0 on supported systems, download and install [Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkID=293881).</span></span> <span data-ttu-id="c4c5c-107">詳しくは、「[Windows PowerShell のインストール](Installing-Windows-PowerShell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-107">For more information, see [Installing Windows PowerShell](Installing-Windows-PowerShell.md).</span></span>

<span data-ttu-id="c4c5c-108">サポートされるシステムで Windows PowerShell 3.0 をインストールするには、[Windows Management Framework 3.0](http://go.microsoft.com/fwlink/?LinkID=240290) をダウンロードしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-108">To install Windows PowerShell 3.0 on supported systems, download and install [Windows Management Framework 3.0](http://go.microsoft.com/fwlink/?LinkID=240290).</span></span> <span data-ttu-id="c4c5c-109">詳しくは、「[Windows PowerShell のインストール](Installing-Windows-PowerShell.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-109">For more information, see [Installing Windows PowerShell](Installing-Windows-PowerShell.md).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="c4c5c-110">以前のバージョンの Windows で Windows PowerShell を開始する方法</span><span class="sxs-lookup"><span data-stu-id="c4c5c-110">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>
<span data-ttu-id="c4c5c-111">次のいずれかの方法で、必要に応じて、Windows PowerShell 3.0 または Windows PowerShell 4.0 のインストールされたバージョンを開始します。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-111">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="c4c5c-112">[スタート] メニューからの場合</span><span class="sxs-lookup"><span data-stu-id="c4c5c-112">From the Start Menu</span></span>

- <span data-ttu-id="c4c5c-113">**[スタート]** をクリックし、「**PowerShell**」と入力して **[Windows PowerShell]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-113">Click **Start**, type **PowerShell**, and then click **Windows PowerShell**.</span></span>

- <span data-ttu-id="c4c5c-114">**[スタート]** メニューから、**[スタート]**、**[すべてのプログラム]**、**[アクセサリ]**、**[Windows PowerShell]** フォルダー、**[Windows PowerShell]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-114">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="c4c5c-115">コマンド プロンプトでの場合</span><span class="sxs-lookup"><span data-stu-id="c4c5c-115">At the Command Prompt</span></span>

- <span data-ttu-id="c4c5c-116">Cmd.exe、Windows PowerShell、または Windows PowerShell ISE で Windows PowerShell を開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-116">In Cmd.exe, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

    ```
    PowerShell
    ```

    <span data-ttu-id="c4c5c-117">また、PowerShell.exe プログラムのパラメーターを使って、セッションをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-117">You can also use the parameters of the PowerShell.exe program to customize the session.</span></span> <span data-ttu-id="c4c5c-118">詳しくは、「[PowerShell.exe コマンドラインのヘルプ](../core-powershell/console/PowerShell.exe-Command-Line-Help.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-118">For more information, see [PowerShell.exe Command-Line Help](../core-powershell/console/PowerShell.exe-Command-Line-Help.md).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="c4c5c-119">管理特権を使う場合 ("管理者として実行")</span><span class="sxs-lookup"><span data-stu-id="c4c5c-119">With Administrative privileges ("Run as administrator")</span></span>

1. <span data-ttu-id="c4c5c-120">**[スタート]** をクリックし、「**PowerShell**」と入力し、**[Windows PowerShell]** を右クリックして、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-120">Click **Start**, type **PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="c4c5c-121">以前のリリースの Windows で Windows PowerShell ISE を開始する方法</span><span class="sxs-lookup"><span data-stu-id="c4c5c-121">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>
<span data-ttu-id="c4c5c-122">次のいずれかの方法で Windows PowerShell ISE を開始します。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-122">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="c4c5c-123">[スタート] メニューからの場合</span><span class="sxs-lookup"><span data-stu-id="c4c5c-123">From the Start Menu</span></span>

- <span data-ttu-id="c4c5c-124">**[スタート]** をクリックし、「**ISE**」と入力して **[Windows PowerShell ISE]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-124">Click **Start**, type **ISE**, and then click **Windows PowerShell ISE**.</span></span>

- <span data-ttu-id="c4c5c-125">**[スタート]** メニューから、**[スタート]**、**[すべてのプログラム]**、**[アクセサリ]**、**[Windows PowerShell]** フォルダー、**[Windows PowerShell ISE]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-125">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="c4c5c-126">コマンド プロンプトでの場合</span><span class="sxs-lookup"><span data-stu-id="c4c5c-126">At the Command Prompt</span></span>

- <span data-ttu-id="c4c5c-127">Cmd.exe、Windows PowerShell、または Windows PowerShell ISE で Windows PowerShell を開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-127">In Cmd.exe, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

    ```
    PowerShell_ISE
    ```

    <span data-ttu-id="c4c5c-128">または</span><span class="sxs-lookup"><span data-stu-id="c4c5c-128">or</span></span>

    ```
    ISE
    ```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="c4c5c-129">管理特権を使う場合 ("管理者として実行")</span><span class="sxs-lookup"><span data-stu-id="c4c5c-129">With Administrative privileges ("Run as administrator")</span></span>

1. <span data-ttu-id="c4c5c-130">**[スタート]** をクリックし、「**ISE**」と入力し、**[Windows PowerShell ISE]** を右クリックして、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-130">Click **Start**, type **ISE**, right-click **Windows PowerShell ISE**, and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="c4c5c-131">以前のリリースの Windows で Windows PowerShell ISE を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="c4c5c-131">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>
<span data-ttu-id="c4c5c-132">Windows PowerShell 4.0 および Windows PowerShell 3.0 では、Windows PowerShell ISE は既定ではすべてのバージョンの Windows で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-132">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="c4c5c-133">まだ有効になっていない場合、Windows Management Framework 4.0 または Windows Management Framework 3.0 により有効になります。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-133">If it is not already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="c4c5c-134">Windows PowerShell 2.0 では、Windows PowerShell ISE は既定では Windows 7 で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-134">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="c4c5c-135">ただし、Windows Server 2008 R2 および Windows Server 2008 では省略可能な機能です。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-135">However, on Windows Server 2008 R2 and Windows Server 2008, it is an optional feature.</span></span>

<span data-ttu-id="c4c5c-136">Windows Server 2008 R2 または Windows Server 2008 で Windows PowerShell 2.0 の Windows PowerShell ISE を有効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-136">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="c4c5c-137">Windows PowerShell Integrated Scripting Environment (ISE) を有効にするには</span><span class="sxs-lookup"><span data-stu-id="c4c5c-137">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="c4c5c-138">サーバー マネージャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-138">Start Server Manager.</span></span>

2. <span data-ttu-id="c4c5c-139">**[機能]**、**[機能の追加]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-139">Click **Features** and then click **Add Features**.</span></span>

3. <span data-ttu-id="c4c5c-140">[機能の選択]で、[Windows PowerShell Integrated Scripting Environment (ISE)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5c-140">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

