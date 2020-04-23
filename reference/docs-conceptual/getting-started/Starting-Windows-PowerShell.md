---
ms.date: 12/05/2019
keywords: powershell,コマンドレット
title: Windows PowerShell の開始
ms.openlocfilehash: 97b15a4cd79c77a391451ba917f985f9d99db3f5
ms.sourcegitcommit: 6545c60578f7745be015111052fd7769f8289296
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "74953825"
---
# <a name="starting-windows-powershell"></a><span data-ttu-id="85892-103">Windows PowerShell の開始</span><span class="sxs-lookup"><span data-stu-id="85892-103">Starting Windows PowerShell</span></span>

<span data-ttu-id="85892-104">Windows PowerShell は、複数のホストに埋め込まれているスクリプト エンジン `.DLL` です。</span><span class="sxs-lookup"><span data-stu-id="85892-104">Windows PowerShell is a scripting engine `.DLL` that's embedded into multiple hosts.</span></span> <span data-ttu-id="85892-105">開始するホストとして最も一般的なものは、対話型コマンド ラインの **powershell.exe** および対話型スクリプト環境の **powershell_ise.exe** です。</span><span class="sxs-lookup"><span data-stu-id="85892-105">The most common hosts you'll start are the interactive command-line **powershell.exe** and the Interactive Scripting Environment **powershell_ise.exe**.</span></span>

<span data-ttu-id="85892-106">Windows Server® 2012 R2、Windows® 8.1、Windows Server 2012、Windows 8 で Windows PowerShell® を開始するには、「[Windows の一般的な管理タスクとナビゲーション](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85892-106">To start Windows PowerShell® on Windows Server® 2012 R2, Windows® 8.1, Windows Server 2012, and Windows 8, see [Common Management Tasks and Navigation in Windows](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831491(v=ws.11)).</span></span>

## <a name="powershell-core-has-renamed-binary"></a><span data-ttu-id="85892-107">PowerShell Core でバイナリ名が変更されました</span><span class="sxs-lookup"><span data-stu-id="85892-107">PowerShell Core has renamed binary</span></span>

<span data-ttu-id="85892-108">PowerShell とも呼ばれている PowerShell Core はオープン ソースのバージョン 6 以降であり、.NET Core が使用されます。</span><span class="sxs-lookup"><span data-stu-id="85892-108">PowerShell Core, referred to as PowerShell, is version 6 and higher that's open source and uses .NET Core.</span></span> <span data-ttu-id="85892-109">サポートされているバージョンは、Windows、macOS、Linux で使用できます。</span><span class="sxs-lookup"><span data-stu-id="85892-109">Supported versions are available on Windows, macOS, and Linux.</span></span>

<span data-ttu-id="85892-110">PowerShell 6 以降、PowerShell バイナリの名前が Windows で **pwsh.exe** に、macOS と Linux で **pwsh** に変更されました。</span><span class="sxs-lookup"><span data-stu-id="85892-110">Beginning in PowerShell 6, the PowerShell binary was renamed **pwsh.exe** for Windows and **pwsh** for macOS and Linux.</span></span> <span data-ttu-id="85892-111">**pwsh-preview** を使用し、PowerShell プレビュー バージョンを開始できます。</span><span class="sxs-lookup"><span data-stu-id="85892-111">You can start PowerShell preview versions using **pwsh-preview**.</span></span> <span data-ttu-id="85892-112">詳細については、「[PowerShell Core 6.0 の新機能](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe)」と「[pwsh について](/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85892-112">For more information, see [What's New in PowerShell Core 6.0](/powershell/scripting/whats-new/what-s-new-in-powershell-core-60#renamed-powershellexe-to-pwshexe) and [About pwsh](/powershell/module/microsoft.powershell.core/about/about_pwsh?view=powershell-7).</span></span>

<span data-ttu-id="85892-113">PowerShell 7 のコマンド リファレンスとインストール ドキュメントは次のリンクから見つかります。</span><span class="sxs-lookup"><span data-stu-id="85892-113">To find cmdlet reference and installation documentation for PowerShell 7, use the following links:</span></span>

| <span data-ttu-id="85892-114">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="85892-114">Document</span></span> | <span data-ttu-id="85892-115">Link</span><span class="sxs-lookup"><span data-stu-id="85892-115">Link</span></span> |
| ----- | ----- |
| <span data-ttu-id="85892-116">コマンドレット リファレンス</span><span class="sxs-lookup"><span data-stu-id="85892-116">Cmdlet reference</span></span> | [<span data-ttu-id="85892-117">PowerShell モジュール ブラウザー</span><span class="sxs-lookup"><span data-stu-id="85892-117">PowerShell Module Browser</span></span>](/powershell/module/?view=powershell-7) |
| <span data-ttu-id="85892-118">Windows インストール</span><span class="sxs-lookup"><span data-stu-id="85892-118">Windows installation</span></span> | [<span data-ttu-id="85892-119">Windows に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="85892-119">Installing PowerShell Core on Windows</span></span>](/powershell/scripting/install/installing-powershell-core-on-windows?view=powershell-7) |
| <span data-ttu-id="85892-120">macOS インストール</span><span class="sxs-lookup"><span data-stu-id="85892-120">macOS installation</span></span> | [<span data-ttu-id="85892-121">macOS に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="85892-121">Installing PowerShell Core on macOS</span></span>](/powershell/scripting/install/installing-powershell-core-on-macos?view=powershell-7) |
| <span data-ttu-id="85892-122">Linux インストール</span><span class="sxs-lookup"><span data-stu-id="85892-122">Linux installation</span></span> | [<span data-ttu-id="85892-123">Linux に PowerShell Core をインストールする</span><span class="sxs-lookup"><span data-stu-id="85892-123">Installing PowerShell Core on Linux</span></span>](/powershell/scripting/install/installing-powershell-core-on-linux?view=powershell-7) |

<span data-ttu-id="85892-124">他の PowerShell バージョンのコンテンツを表示するには、「[PowerShell ドキュメントの使用方法](../how-to-use-docs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85892-124">To view content for other PowerShell versions, see [How to use the PowerShell documentation](../how-to-use-docs.md).</span></span>

## <a name="how-to-start-windows-powershell-on-earlier-versions-of-windows"></a><span data-ttu-id="85892-125">以前のバージョンの Windows で Windows PowerShell を開始する方法</span><span class="sxs-lookup"><span data-stu-id="85892-125">How to Start Windows PowerShell on Earlier Versions of Windows</span></span>

<span data-ttu-id="85892-126">このセクションでは、Windows® 7、Windows Server® 2008 R2、Windows Server® 2008 で、Windows PowerShell と Windows PowerShell Integrated Scripting Environment (ISE) を開始する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="85892-126">This section explains how to start Windows PowerShell and Windows PowerShell Integrated Scripting Environment (ISE) on Windows® 7, Windows Server® 2008 R2, and Windows Server® 2008.</span></span> <span data-ttu-id="85892-127">Windows Server® 2008 R2 と Windows Server® 2008 で、Windows PowerShell 2.0 の Windows PowerShell ISE のオプション機能を有効にする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="85892-127">It also explains how to enable the optional feature for Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server® 2008 R2 and Windows Server® 2008.</span></span>

<span data-ttu-id="85892-128">次のいずれかの方法で、必要に応じて、Windows PowerShell 3.0 または Windows PowerShell 4.0 のインストールされたバージョンを開始します。</span><span class="sxs-lookup"><span data-stu-id="85892-128">Use any of the following methods to start the installed version of Windows PowerShell 3.0, or Windows PowerShell 4.0, where applicable.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="85892-129">[スタート] メニューからの場合</span><span class="sxs-lookup"><span data-stu-id="85892-129">From the Start Menu</span></span>

- <span data-ttu-id="85892-130">**[スタート]** をクリックし、「**PowerShell**」と入力して **[Windows PowerShell]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-130">Click **Start**, type **PowerShell**, and then click **Windows PowerShell**.</span></span>
- <span data-ttu-id="85892-131">**[スタート]** メニューから、 **[スタート]** 、 **[すべてのプログラム]** 、 **[アクセサリ]** 、 **[Windows PowerShell]** フォルダー、 **[Windows PowerShell]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-131">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="85892-132">コマンド プロンプトでの場合</span><span class="sxs-lookup"><span data-stu-id="85892-132">At the Command Prompt</span></span>

<span data-ttu-id="85892-133">**cmd.exe**、Windows PowerShell、または Windows PowerShell ISE で Windows PowerShell を開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="85892-133">In **cmd.exe**, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell
```

<span data-ttu-id="85892-134">また、**powershell.exe** プログラムのパラメーターを使って、セッションをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="85892-134">You can also use the parameters of the **powershell.exe** program to customize the session.</span></span> <span data-ttu-id="85892-135">詳しくは、「[PowerShell.exe コマンドラインのヘルプ](../core-powershell/console/PowerShell.exe-Command-Line-Help.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85892-135">For more information, see [PowerShell.exe Command-Line Help](../core-powershell/console/PowerShell.exe-Command-Line-Help.md).</span></span>

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="85892-136">管理特権を使う場合 (管理者として実行)</span><span class="sxs-lookup"><span data-stu-id="85892-136">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="85892-137">**[スタート]** をクリックし、「**PowerShell**」と入力し、 **[Windows PowerShell]** を右クリックして、 **[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-137">Click **Start**, type **PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>

## <a name="how-to-start-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="85892-138">以前のリリースの Windows で Windows PowerShell ISE を開始する方法</span><span class="sxs-lookup"><span data-stu-id="85892-138">How to Start Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="85892-139">次のいずれかの方法で Windows PowerShell ISE を開始します。</span><span class="sxs-lookup"><span data-stu-id="85892-139">Use any of the following methods to start Windows PowerShell ISE.</span></span>

#### <a name="from-the-start-menu"></a><span data-ttu-id="85892-140">[スタート] メニューからの場合</span><span class="sxs-lookup"><span data-stu-id="85892-140">From the Start Menu</span></span>

- <span data-ttu-id="85892-141">**[スタート]** をクリックし、「**ISE**」と入力して **[Windows PowerShell ISE]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-141">Click **Start**, type **ISE**, and then click **Windows PowerShell ISE**.</span></span>
- <span data-ttu-id="85892-142">**[スタート]** メニューから、 **[スタート]** 、 **[すべてのプログラム]** 、 **[アクセサリ]** 、 **[Windows PowerShell]** フォルダー、 **[Windows PowerShell ISE]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-142">From the **Start** menu, click **Start**, click **All Programs**, click **Accessories**, click the **Windows PowerShell** folder, and then click **Windows PowerShell ISE**.</span></span>

#### <a name="at-the-command-prompt"></a><span data-ttu-id="85892-143">コマンド プロンプトでの場合</span><span class="sxs-lookup"><span data-stu-id="85892-143">At the Command Prompt</span></span>

<span data-ttu-id="85892-144">**cmd.exe**、Windows PowerShell、または Windows PowerShell ISE で Windows PowerShell を開始するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="85892-144">In **cmd.exe**, Windows PowerShell, or Windows PowerShell ISE, to start Windows PowerShell, type:</span></span>

```
PowerShell_ISE
```

<span data-ttu-id="85892-145">or</span><span class="sxs-lookup"><span data-stu-id="85892-145">or</span></span>

```
ISE
```

#### <a name="with-administrative-privileges-run-as-administrator"></a><span data-ttu-id="85892-146">管理特権を使う場合 (管理者として実行)</span><span class="sxs-lookup"><span data-stu-id="85892-146">With Administrative privileges (Run as administrator)</span></span>

<span data-ttu-id="85892-147">**[スタート]** をクリックし、「**ISE**」と入力し、 **[Windows PowerShell ISE]** を右クリックして、 **[管理者として実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-147">Click **Start**, type **ISE**, right-click **Windows PowerShell ISE**, and then click **Run as administrator**.</span></span>

## <a name="how-to-enable-windows-powershell-ise-on-earlier-releases-of-windows"></a><span data-ttu-id="85892-148">以前のリリースの Windows で Windows PowerShell ISE を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="85892-148">How to Enable Windows PowerShell ISE on Earlier Releases of Windows</span></span>

<span data-ttu-id="85892-149">Windows PowerShell 4.0 および Windows PowerShell 3.0 では、Windows PowerShell ISE は既定ではすべてのバージョンの Windows で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="85892-149">In Windows PowerShell 4.0 and Windows PowerShell 3.0, Windows PowerShell ISE is enabled by default on all versions of Windows.</span></span> <span data-ttu-id="85892-150">まだ有効になっていない場合、Windows Management Framework 4.0 または Windows Management Framework 3.0 により有効になります。</span><span class="sxs-lookup"><span data-stu-id="85892-150">If it isn't already enabled, Windows Management Framework 4.0 or Windows Management Framework 3.0 enables it.</span></span>

<span data-ttu-id="85892-151">Windows PowerShell 2.0 では、Windows PowerShell ISE は既定では Windows 7 で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="85892-151">In Windows PowerShell 2.0, Windows PowerShell ISE is enabled by default on Windows 7.</span></span> <span data-ttu-id="85892-152">ただし、Windows Server 2008 R2 および Windows Server 2008 では省略可能な機能です。</span><span class="sxs-lookup"><span data-stu-id="85892-152">However, on Windows Server 2008 R2 and Windows Server 2008, it's an optional feature.</span></span>

<span data-ttu-id="85892-153">Windows Server 2008 R2 または Windows Server 2008 で Windows PowerShell 2.0 の Windows PowerShell ISE を有効にするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="85892-153">To enable Windows PowerShell ISE in Windows PowerShell 2.0 on Windows Server 2008 R2 or Windows Server 2008, use the following procedure.</span></span>

#### <a name="to-enable-windows-powershell-integrated-scripting-environment-ise"></a><span data-ttu-id="85892-154">Windows PowerShell Integrated Scripting Environment (ISE) を有効にするには</span><span class="sxs-lookup"><span data-stu-id="85892-154">To enable Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

1. <span data-ttu-id="85892-155">Server Manager を起動します。</span><span class="sxs-lookup"><span data-stu-id="85892-155">Start Server Manager.</span></span>
2. <span data-ttu-id="85892-156">**[機能]** 、 **[機能の追加]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-156">Click **Features** and then click **Add Features**.</span></span>
3. <span data-ttu-id="85892-157">[機能の選択]で、[Windows PowerShell Integrated Scripting Environment (ISE)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-157">In Select Features, click Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

## <a name="starting-the-32-bit-version-of-windows-powershell"></a><span data-ttu-id="85892-158">32 ビット版の Windows PowerShell を起動する</span><span class="sxs-lookup"><span data-stu-id="85892-158">Starting the 32-Bit Version of Windows PowerShell</span></span>

<span data-ttu-id="85892-159">64 ビット コンピューターに Windows PowerShell をインストールする場合、64 ビット版に加えて、**Windows PowerShell (x86)** 、つまり Windows PowerShell の 32 ビット版もインストールされます。</span><span class="sxs-lookup"><span data-stu-id="85892-159">When you install Windows PowerShell on a 64-bit computer, **Windows PowerShell (x86)**, a 32-bit version of Windows PowerShell is installed in addition to the 64-bit version.</span></span> <span data-ttu-id="85892-160">Windows PowerShell を実行すると、既定では 64 ビット版が実行されます。</span><span class="sxs-lookup"><span data-stu-id="85892-160">When you run Windows PowerShell, the 64-bit version runs by default.</span></span>

<span data-ttu-id="85892-161">ただし、32 ビット版を必要とするモジュールを使用するときや、32 ビットのコンピューターにリモートで接続しているときなど、**Windows PowerShell (x86)** の実行を必要とすることもときどきあります。</span><span class="sxs-lookup"><span data-stu-id="85892-161">However, you might occasionally need to run **Windows PowerShell (x86)**, such as when you're using a module that requires the 32-bit version or when you're connecting remotely to a 32-bit computer.</span></span>

<span data-ttu-id="85892-162">Windows PowerShell の 32 ビット版を起動するには、次の手順のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="85892-162">To start a 32-bit version of Windows PowerShell, use any of the following procedures.</span></span>

#### <a name="in-windows-server-2012-r2"></a><span data-ttu-id="85892-163">Windows Server® 2012 R2 の場合</span><span class="sxs-lookup"><span data-stu-id="85892-163">In Windows Server® 2012 R2</span></span>

- <span data-ttu-id="85892-164">**[スタート]** 画面で、「**Windows PowerShell (x86)** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="85892-164">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="85892-165">**[Windows PowerShell x86]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-165">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="85892-166">**サーバー マネージャー**の **[ツール]** メニューから、 **[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85892-166">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-167">デスクトップで、右上隅にカーソルを移動し、 **[検索]** をクリックする。「**PowerShell x86**」と入力し、 **[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-167">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-168">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="85892-168">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-server-2012"></a><span data-ttu-id="85892-169">Windows Server® 2012 の場合</span><span class="sxs-lookup"><span data-stu-id="85892-169">In Windows Server® 2012</span></span>

- <span data-ttu-id="85892-170">**[スタート]** 画面で、「**PowerShell**」と入力して **[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-170">On the **Start** screen, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-171">**サーバー マネージャー**の **[ツール]** メニューから、 **[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85892-171">In **Server Manager**, from the **Tools** menu, select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-172">デスクトップで、右上隅にカーソルを移動し、 **[検索]** をクリックする。「**PowerShell**」と入力し、 **[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-172">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-173">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="85892-173">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-81"></a><span data-ttu-id="85892-174">Windows® 8.1 の場合</span><span class="sxs-lookup"><span data-stu-id="85892-174">In Windows® 8.1</span></span>

- <span data-ttu-id="85892-175">**[スタート]** 画面で、「**Windows PowerShell (x86)** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="85892-175">On the **Start** screen, type **Windows PowerShell (x86)**.</span></span> <span data-ttu-id="85892-176">**[Windows PowerShell x86]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-176">Click the **Windows PowerShell x86** tile.</span></span>
- <span data-ttu-id="85892-177">Windows 8.1 の[リモート サーバー管理ツール](https://go.microsoft.com/fwlink/?LinkID=304145)を実行している場合、 **[サーバー管理ツール]** メニューから [Windows PowerShell x86] を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="85892-177">If you're running [Remote Server Administration Tools](https://go.microsoft.com/fwlink/?LinkID=304145) for Windows 8.1, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="85892-178">**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85892-178">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-179">デスクトップで、右上隅にカーソルを移動し、 **[検索]** をクリックする。「**PowerShell x86**」と入力し、 **[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-179">On the desktop, move the cursor to the upper right corner, click **Search**, type **PowerShell x86** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-180">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="85892-180">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>

#### <a name="in-windows-8"></a><span data-ttu-id="85892-181">In Windows® 8 の場合</span><span class="sxs-lookup"><span data-stu-id="85892-181">In Windows® 8</span></span>

- <span data-ttu-id="85892-182">**[スタート]** 画面で、右上隅にカーソルを移動し、 **[設定]** をクリックし、 **[タイル]** をクリックします。そして、 **[管理ツールを表示する]** スライダーを **[はい]** に移動させます。</span><span class="sxs-lookup"><span data-stu-id="85892-182">On the **Start** screen, move the cursor to the upper right corner, click **Settings**, click **Tiles**, and then move the **Show Administrative Tools** slider to **Yes**.</span></span> <span data-ttu-id="85892-183">次に「**PowerShell**」と入力し、 **[Windows PowerShell(x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-183">Then, type **PowerShell** and click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-184">Windows 8 の[リモート サーバー管理ツール](https://www.microsoft.com/download/details.aspx?id=28972)を実行している場合、 **[サーバー管理ツール]** メニューから [Windows PowerShell x86] を開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="85892-184">If you're running [Remote Server Administration Tools](https://www.microsoft.com/download/details.aspx?id=28972) for Windows 8, you can also open Windows PowerShell x86 from the **Server ManagerTools** menu.</span></span> <span data-ttu-id="85892-185">**[Windows PowerShell (x86)]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="85892-185">Select **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-186">**[スタート]** 画面またはデスクトップで、「**PowerShell (x86)** 」と入力し、 **[Windows PowerShell (x86)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="85892-186">On the **Start** screen or the desktop, type **PowerShell (x86)** and then click **Windows PowerShell (x86)**.</span></span>
- <span data-ttu-id="85892-187">コマンド ラインで、次のように入力します。`%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span><span class="sxs-lookup"><span data-stu-id="85892-187">Via command line, enter: `%SystemRoot%\SysWOW64\WindowsPowerShell\v1.0\powershell.exe`</span></span>
