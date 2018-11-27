---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell の開始
ms.assetid: 59b649a2-c90c-4cf4-bf95-a740c59148e7
ms.openlocfilehash: 9184e8b0e508610e7f4775f1032f3a69c93bb8c1
ms.sourcegitcommit: 221b7daab7f597f8b2e4864cf9b5d9dda9b9879b
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "52320535"
---
# <a name="starting-windows-powershell"></a><span data-ttu-id="50eb4-103">Windows PowerShell の開始</span><span class="sxs-lookup"><span data-stu-id="50eb4-103">Starting Windows PowerShell</span></span>
<span data-ttu-id="50eb4-104">PowerShell は、複数のホストに埋め込まれているスクリプト エンジン dll です。</span><span class="sxs-lookup"><span data-stu-id="50eb4-104">PowerShell is a scripting engine dll which is embedded into multiple hosts.</span></span>  <span data-ttu-id="50eb4-105">開始するホストとして最も一般的なものは、対話型コマンド ラインの PowerShell.exe および対話型スクリプト環境の PowerShell_ISE.exe です。</span><span class="sxs-lookup"><span data-stu-id="50eb4-105">The most common host you will start are the interactive command line PowerShell.exe and the Interactive Scripting Environment PowerShell_ISE.exe.</span></span>

<span data-ttu-id="50eb4-106">Windows Server® 2012 R2、Windows® 8.1、Windows Server 2012、Windows 8 で Windows PowerShell® を開始するには、「[一般的な管理タスクとナビゲーション](https://technet.microsoft.com/library/hh831491.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50eb4-106">To start Windows PowerShell® on Windows Server® 2012 R2, Windows® 8.1, Windows Server 2012, and Windows 8, see [Common Management Tasks and Navigation](https://technet.microsoft.com/library/hh831491.aspx).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="50eb4-107">以前のバージョンの Windows で Windows PowerShell を開始する方法</span><span class="sxs-lookup"><span data-stu-id="50eb4-107">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>

<span data-ttu-id="50eb4-108">このセクションでは、Windows® 7、Windows Server® 2008 R2、Windows Server® 2008 で、Windows PowerShell と Windows PowerShell Integrated Scripting Environment (ISE) を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-108">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows® 7, Windows Server® 2008 R2, and Windows Server® 2008.</span></span> <span data-ttu-id="50eb4-109">Windows Server® 2008 R2 と Windows Server® 2008 で、Windows PowerShell 2.0 の Windows PowerShell ISE のオプション機能を有効にする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-109">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server® 2008 R2 and Windows Server® 2008.</span></span>

<span data-ttu-id="50eb4-110">次のいずれかの方法で、必要に応じて、Windows PowerShell 3.0 または Windows PowerShell 4.0 のインストールされたバージョンを開始します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-110">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="50eb4-111">[スタート] メニューからの場合</span><span class="sxs-lookup"><span data-stu-id="50eb4-111">From the Start Menu</span></span>

- <span data-ttu-id="50eb4-112">**[スタート]** をクリックし、「**PowerShell**」と入力して **[Windows PowerShell]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-112">Click **Start**, type **PowerShell**, and then click **Windows PowerShell**.</span></span>
- <span data-ttu-id="50eb4-113">**[スタート]** メニューから、**[スタート]**、**[すべてのプログラム]**、**[アクセサリ]**、**[Windows PowerShell]** フォルダー、**[Windows PowerShell]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-113">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="50eb4-114">コマンド プロンプトでの場合</span><span class="sxs-lookup"><span data-stu-id="50eb4-114">At the Command Prompt</span></span>

<span data-ttu-id="50eb4-115">Cmd.exe、Windows PowerShell、または Windows PowerShell ISE で Windows PowerShell を開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-115">In Cmd.exe, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell
```

<span data-ttu-id="50eb4-116">また、PowerShell.exe プログラムのパラメーターを使って、セッションをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="50eb4-116">You can also use the parameters of the PowerShell.exe program to customize the session.</span></span> <span data-ttu-id="50eb4-117">詳しくは、「[PowerShell.exe コマンドラインのヘルプ](../core-powershell/console/PowerShell.exe-Command-Line-Help.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="50eb4-117">For more information, see [PowerShell.exe Command-Line Help](../core-powershell/console/PowerShell.exe-Command-Line-Help.md).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="50eb4-118">管理特権を使う場合 ("管理者として実行")</span><span class="sxs-lookup"><span data-stu-id="50eb4-118">With Administrative privileges ("Run as administrator")</span></span>

<span data-ttu-id="50eb4-119">**[スタート]** をクリックし、「**PowerShell**」と入力し、**[Windows PowerShell]** を右クリックして、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-119">Click **Start**, type **PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="50eb4-120">以前のリリースの Windows で Windows PowerShell ISE を開始する方法</span><span class="sxs-lookup"><span data-stu-id="50eb4-120">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="50eb4-121">次のいずれかの方法で Windows PowerShell ISE を開始します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-121">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="50eb4-122">[スタート] メニューからの場合</span><span class="sxs-lookup"><span data-stu-id="50eb4-122">From the Start Menu</span></span>

- <span data-ttu-id="50eb4-123">**[スタート]** をクリックし、「**ISE**」と入力して **[Windows PowerShell ISE]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-123">Click **Start**, type **ISE**, and then click **Windows PowerShell ISE**.</span></span>
- <span data-ttu-id="50eb4-124">**[スタート]** メニューから、**[スタート]**、**[すべてのプログラム]**、**[アクセサリ]**、**[Windows PowerShell]** フォルダー、**[Windows PowerShell ISE]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-124">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="50eb4-125">コマンド プロンプトでの場合</span><span class="sxs-lookup"><span data-stu-id="50eb4-125">At the Command Prompt</span></span>

<span data-ttu-id="50eb4-126">Cmd.exe、Windows PowerShell、または Windows PowerShell ISE で Windows PowerShell を開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-126">In Cmd.exe, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell_ISE
```

<span data-ttu-id="50eb4-127">または</span><span class="sxs-lookup"><span data-stu-id="50eb4-127">or</span></span>

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="50eb4-128">管理特権を使う場合 ("管理者として実行")</span><span class="sxs-lookup"><span data-stu-id="50eb4-128">With Administrative privileges ("Run as administrator")</span></span>

<span data-ttu-id="50eb4-129">**[スタート]** をクリックし、「**ISE**」と入力し、**[Windows PowerShell ISE]** を右クリックして、**[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-129">Click **Start**, type **ISE**, right-click **Windows PowerShell ISE**, and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="50eb4-130">以前のリリースの Windows で Windows PowerShell ISE を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="50eb4-130">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="50eb4-131">Windows PowerShell 4.0 および Windows PowerShell 3.0 では、Windows PowerShell ISE は既定ではすべてのバージョンの Windows で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="50eb4-131">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="50eb4-132">まだ有効になっていない場合、Windows Management Framework 4.0 または Windows Management Framework 3.0 により有効になります。</span><span class="sxs-lookup"><span data-stu-id="50eb4-132">If it is not already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="50eb4-133">Windows PowerShell 2.0 では、Windows PowerShell ISE は既定では Windows 7 で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="50eb4-133">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="50eb4-134">ただし、Windows Server 2008 R2 および Windows Server 2008 では省略可能な機能です。</span><span class="sxs-lookup"><span data-stu-id="50eb4-134">However, on Windows Server 2008 R2 and Windows Server 2008, it is an optional feature.</span></span>

<span data-ttu-id="50eb4-135">Windows Server 2008 R2 または Windows Server 2008 で Windows PowerShell 2.0 の Windows PowerShell ISE を有効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="50eb4-135">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="50eb4-136">Windows PowerShell Integrated Scripting Environment (ISE) を有効にするには</span><span class="sxs-lookup"><span data-stu-id="50eb4-136">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="50eb4-137">サーバー マネージャーを起動します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-137">Start Server Manager.</span></span>
2. <span data-ttu-id="50eb4-138">**[機能]**、**[機能の追加]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-138">Click **Features** and then click **Add Features**.</span></span>
3. <span data-ttu-id="50eb4-139">[機能の選択]で、[Windows PowerShell Integrated Scripting Environment (ISE)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-139">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="50eb4-140">32 ビット版の Windows PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="50eb4-140">Starting the 32-Bit Version of Windows PowerShell</span></span>

<span data-ttu-id="50eb4-141">64 ビット コンピューターに Windows PowerShell をインストールする場合、64 ビット版に加えて、**Windows PowerShell (x86)**、つまり Windows PowerShell の 32 ビット版もインストールされます。</span><span class="sxs-lookup"><span data-stu-id="50eb4-141">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)**, a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="50eb4-142">Windows PowerShell を実行すると、既定では 64 ビット版が実行されます。</span><span class="sxs-lookup"><span data-stu-id="50eb4-142">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="50eb4-143">ただし、32 ビット版を必要とするモジュールを使用するときや、32 ビットのコンピューターにリモートで接続しているときなど、**Windows PowerShell (x86)** の実行を必要とすることもときどきあります。</span><span class="sxs-lookup"><span data-stu-id="50eb4-143">However, you might occasionally need to run **Windows PowerShell (x86)**, such as when you are using a module that requires the 32-bit version or when you are connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="50eb4-144">Windows PowerShell の 32 ビット版を起動するには、次の手順のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-144">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-server-2012-r2"></a><span data-ttu-id="50eb4-145">Windows Server® 2012 R2 の場合</span><span class="sxs-lookup"><span data-stu-id="50eb4-145">In Windows Server® 2012 R2</span></span>

- <span data-ttu-id="50eb4-146">**[スタート]** 画面で、「**Windows PowerShell (x86)**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-146">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="50eb4-147">**[Windows PowerShell x86]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-147">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="50eb4-148">**サーバー マネージャー**の **[ツール]** メニューから、**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-148">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-149">デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell x86**」と入力し、**[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-149">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-150">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="50eb4-150">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-server-2012"></a><span data-ttu-id="50eb4-151">Windows Server® 2012 の場合</span><span class="sxs-lookup"><span data-stu-id="50eb4-151">In Windows Server® 2012</span></span>

- <span data-ttu-id="50eb4-152">**[スタート]** 画面で、「**PowerShell**」と入力して **[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-152">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-153">**サーバー マネージャー**の **[ツール]** メニューから、**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-153">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-154">デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell**」と入力し、**[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-154">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-155">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="50eb4-155">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-81"></a><span data-ttu-id="50eb4-156">Windows® 8.1 の場合</span><span class="sxs-lookup"><span data-stu-id="50eb4-156">In Windows® 8.1</span></span>

- <span data-ttu-id="50eb4-157">**[スタート]** 画面で、「**Windows PowerShell (x86)**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-157">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="50eb4-158">**[Windows PowerShell x86]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-158">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="50eb4-159">Windows 8.1 の[リモート サーバー管理ツール](https://go.microsoft.com/fwlink/?LinkID=304145)を実行している場合、**[サーバー管理ツール]** メニューから [Windows PowerShell x86] を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="50eb4-159">If you are running [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span>
  <span data-ttu-id="50eb4-160">**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-160">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-161">デスクトップで、右上隅にカーソルを移動し、**[検索]** をクリックする。「**PowerShell x86**」と入力し、**[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-161">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-162">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="50eb4-162">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-8"></a><span data-ttu-id="50eb4-163">In Windows® 8 の場合</span><span class="sxs-lookup"><span data-stu-id="50eb4-163">In Windows® 8</span></span>

- <span data-ttu-id="50eb4-164">**[スタート]** 画面で、右上隅にカーソルを移動し、**[設定]** をクリックし、**[タイル]** をクリックします。そして、**[管理ツールを表示する]** スライダーを [はい] に移動させます。</span><span class="sxs-lookup"><span data-stu-id="50eb4-164">On the **Start** screen, move the cursor to the upper right corner, click **Settings**, click **Tiles**, and then move the **Show Administrative Tools** slider to Yes.</span></span> <span data-ttu-id="50eb4-165">次に「**PowerShell**」と入力し、**[Windows PowerShell(x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-165">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-166">Windows 8 の[リモート サーバー管理ツール](https://www.microsoft.com/download/details.aspx?id=28972)を実行している場合、**[サーバー管理ツール]** メニューから [Windows PowerShell x86] を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="50eb4-166">If you are running [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="50eb4-167">**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="50eb4-167">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-168">**[スタート]** 画面またはデスクトップで、「**PowerShell (x86)**」と入力し、**[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="50eb4-168">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="50eb4-169">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="50eb4-169">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>