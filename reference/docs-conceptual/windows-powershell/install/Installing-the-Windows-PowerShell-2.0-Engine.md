---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: Windows PowerShell 2.0 エンジンのインストール
description: Windows PowerShell 2.0 エンジンは、Windows のオプション機能です。 この記事では、その機能をインストールする方法と、必要な要件について説明します。
ms.openlocfilehash: c82725c34f5c5864eba0c88eb33ecac9e43f86d3
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663967"
---
# <a name="installing-the-windows-powershell-20-engine"></a><span data-ttu-id="06224-105">Windows PowerShell 2.0 エンジンのインストール</span><span class="sxs-lookup"><span data-stu-id="06224-105">Installing the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="06224-106">このトピックでは、Windows PowerShell 2.0 エンジンのインストール方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="06224-106">This topic explains how to install the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="06224-107">Windows PowerShell 3.0 は、Windows PowerShell 2.0 との下位互換性を保つように設計されています。</span><span class="sxs-lookup"><span data-stu-id="06224-107">Windows PowerShell 3.0 is designed to be backwards compatible with Windows PowerShell 2.0.</span></span> <span data-ttu-id="06224-108">Windows PowerShell 2.0 用に記述されたコマンドレット、プロバイダー、スナップイン、モジュール、スクリプトは、未変更のまま Windows PowerShell 3.0 と Windows PowerShell 4.0 で実行できます。</span><span class="sxs-lookup"><span data-stu-id="06224-108">Cmdlets, providers, snap-ins, modules, and scripts written for Windows PowerShell 2.0 run unchanged in Windows PowerShell 3.0 and Windows PowerShell 4.0.</span></span> <span data-ttu-id="06224-109">ただし、Microsoft .NET Framework 4 でランタイムのアクティブ化ポリシーが変更されたため、Windows PowerShell 2.0 用に記述され、共通言語ランタイム (CLR) 2.0 でコンパイルされた Windows PowerShell ホスト プログラムは、変更を加えなければ新しいリリースの Windows PowerShell (CLR 4.0 でコンパイルされたもの) で実行できません。</span><span class="sxs-lookup"><span data-stu-id="06224-109">However, due to a change in the runtime activation policy in Microsoft .NET Framework 4, Windows PowerShell host programs that were written for Windows PowerShell 2.0 and compiled with Common Language Runtime (CLR) 2.0 cannot run without modification in later releases of Windows PowerShell, which is compiled with CLR 4.0.</span></span>

<span data-ttu-id="06224-110">これらの変更の影響を受けるコマンドやホスト プログラムとの下位互換性を維持するため、Windows PowerShell 2.0、Windows PowerShell 3.0、および Windows PowerShell 4.0 のエンジンは、side-by-side で実行できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="06224-110">To maintain backward compatibility with commands and host programs that are affected by these changes, the Windows PowerShell 2.0, Windows PowerShell 3.0, and Windows PowerShell 4.0 engines are designed to run side-by-side.</span></span> <span data-ttu-id="06224-111">また、Windows PowerShell 2.0 エンジンは Windows Server 2012 R2、Windows 8.1、Windows 8、Windows Server 2012、Windows Management Framework 3.0 にも組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="06224-111">Also, the Windows PowerShell 2.0 Engine is included in Windows Server 2012 R2, Windows 8.1, Windows 8, Windows Server 2012, and Windows Management Framework 3.0.</span></span> <span data-ttu-id="06224-112">Windows PowerShell 2.0 エンジンは、既存のスクリプトまたはホスト プログラムが Windows PowerShell 3.0、Windows PowerShell 4.0、Microsoft .NET Framework 4 との互換性がないために実行できない場合に限り使用することを意図しています。</span><span class="sxs-lookup"><span data-stu-id="06224-112">The Windows PowerShell 2.0 Engine is intended to be used only when an existing script or host program cannot run because it is incompatible with Windows PowerShell 3.0, Windows PowerShell 4.0, or Microsoft .NET Framework 4.</span></span> <span data-ttu-id="06224-113">そのようなケースはまれと考えられます。</span><span class="sxs-lookup"><span data-stu-id="06224-113">Such cases are expected to be rare.</span></span>

<span data-ttu-id="06224-114">Windows PowerShell 2.0 エンジンは、Windows Server 2012 R2、Windows 8.1、Windows&reg; 8、Windows Server&reg; 2012 のオプション機能です。</span><span class="sxs-lookup"><span data-stu-id="06224-114">The Windows PowerShell 2.0 Engine is an optional feature of Windows Server 2012 R2, Windows 8.1, Windows&reg; 8 and Windows Server&reg; 2012.</span></span> <span data-ttu-id="06224-115">以前のバージョンの Windows に Windows Management Framework 3.0 をインストールすると、Windows PowerShell のインストール ディレクトリ内で Windows PowerShell 2.0 インストールが Windows PowerShell 3.0 のインストールによって完全に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="06224-115">On earlier versions of Windows, when you install Windows Management Framework 3.0, the Windows PowerShell 3.0 installation completely replaces the Windows PowerShell 2.0 installation in the Windows PowerShell installation directory.</span></span> <span data-ttu-id="06224-116">ただし、Windows PowerShell 2.0 エンジンは保持されます。</span><span class="sxs-lookup"><span data-stu-id="06224-116">However, the Windows PowerShell 2.0 Engine is retained.</span></span>

<span data-ttu-id="06224-117">Windows PowerShell 2.0 エンジンの開始に関する情報については、「[Windows PowerShell 2.0 エンジンの開始](../Starting-the-Windows-PowerShell-2.0-Engine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06224-117">For information about starting the Windows PowerShell 2.0 Engine, see [Starting the Windows PowerShell 2.0 Engine](../Starting-the-Windows-PowerShell-2.0-Engine.md).</span></span>

## <a name="on-windows-81-and-windows-8"></a><span data-ttu-id="06224-118">Windows 8 および Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="06224-118">On Windows 8.1 and Windows 8</span></span>

<span data-ttu-id="06224-119">Windows 8.1 と Windows 8 では、Windows PowerShell 2.0 エンジンの機能が既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="06224-119">On Windows 8.1 and Windows 8, the Windows PowerShell 2.0 Engine feature is turned on by default.</span></span>
<span data-ttu-id="06224-120">ただし、この機能を使うには、この機能に必要な Microsoft .NET Framework 3.5 オプションをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="06224-120">However, to use it, you need to turn on the option for Microsoft .NET Framework 3.5, which it requires.</span></span> <span data-ttu-id="06224-121">このセクションでは、Windows PowerShell 2.0 エンジンの機能をオンまたはオフにする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="06224-121">This section also explains how to turn the Windows PowerShell 2.0 Engine feature on and off.</span></span>

#### <a name="to-turn-on-net-framework-35"></a><span data-ttu-id="06224-122">.NET Framework 3.5 をオンにするには</span><span class="sxs-lookup"><span data-stu-id="06224-122">To turn on .NET Framework 3.5</span></span>

1. <span data-ttu-id="06224-123">**[スタート]** 画面で、「 **Windows の機能** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="06224-123">On the **Start** screen, type **Windows Features**.</span></span>
2. <span data-ttu-id="06224-124">**アプリ** バーで、 **[設定]** をクリックしてから、 **[Windows の機能の有効化または無効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06224-124">On the **Apps** bar, click **Settings** , and then click **Turn Windows features on or off**.</span></span>
3. <span data-ttu-id="06224-125">**[Windows の機能]** ボックスで、 **[.NET Framework 3.5 (.NET 2.0 および 3.0 を含む)]** をオンにします。</span><span class="sxs-lookup"><span data-stu-id="06224-125">In the **Windows Features** box, click **.NET Framework 3.5 (includes .NET 2.0 and 3.0** to select it.</span></span>

   <span data-ttu-id="06224-126">**[.NET Framework 3.5 (.NET 2.0 および 3.0 を含む)]** を選択すると、ボックスが塗りつぶされて、機能の一部のみが選択された状態になります。</span><span class="sxs-lookup"><span data-stu-id="06224-126">When you select **.NET Framework 3.5 (includes .NET 2.0 and 3.0** , the box fills to indicate that only part of the feature is selected.</span></span> <span data-ttu-id="06224-127">Windows PowerShell 2.0 エンジンの場合はこの状態で十分です。</span><span class="sxs-lookup"><span data-stu-id="06224-127">However, this is sufficient for the Windows PowerShell 2.0 Engine.</span></span>

#### <a name="to-turn-the-windows-powershell-20-engine-on-and-off"></a><span data-ttu-id="06224-128">Windows PowerShell 2.0 エンジンをオンまたはオフにするには</span><span class="sxs-lookup"><span data-stu-id="06224-128">To turn the Windows PowerShell 2.0 Engine on and off</span></span>

1. <span data-ttu-id="06224-129">**[スタート]** 画面で、「 **Windows の機能** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="06224-129">On the **Start** screen, type **Windows Features**.</span></span>

2. <span data-ttu-id="06224-130">**アプリ** バーで、 **[設定]** をクリックしてから、 **[Windows の機能の有効化または無効化]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="06224-130">On the **Apps** bar, click **Settings** , and then click **Turn Windows features on or off**.</span></span>

3. <span data-ttu-id="06224-131">**[Windows の機能]** ボックスで、[ **Windows PowerShell 2.0** ] ノードを展開し、[ **Windows PowerShell 2.0** エンジン] ボックスをクリックして、オンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="06224-131">In the **Windows Features** box, expand the **Windows PowerShell 2.0** node, and click the **Windows PowerShell 2.0 Engine** box to select or clear it.</span></span>

## <a name="on-windows-server-2012-r2-and-windows-server-2012"></a><span data-ttu-id="06224-132">Windows Server 2012 R2 または Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="06224-132">On Windows Server 2012 R2 and Windows Server 2012</span></span>

<span data-ttu-id="06224-133">次の手順を実行して、Windows PowerShell 2.0 エンジンと Microsoft .NET Framework 3.5 の機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="06224-133">Use the following procedures to add the Windows PowerShell 2.0 Engine and Microsoft .NET Framework 3.5 features.</span></span> <span data-ttu-id="06224-134">Windows PowerShell 2.0 エンジンには最低でも Microsoft .NET Framework 2.0.50727 が必要です。</span><span class="sxs-lookup"><span data-stu-id="06224-134">The Windows PowerShell 2.0 Engine requires Microsoft .NET Framework 2.0.50727 at a minimum.</span></span> <span data-ttu-id="06224-135">この要件は Microsoft .NET Framework 3.5 で満たされます。</span><span class="sxs-lookup"><span data-stu-id="06224-135">This requirement is fulfilled by Microsoft .NET Framework 3.5.</span></span>

#### <a name="to-add-the-net-framework-35-feature"></a><span data-ttu-id="06224-136">.NET Framework 3.5 の機能を追加するには</span><span class="sxs-lookup"><span data-stu-id="06224-136">To add the .NET Framework 3.5 feature</span></span>

1. <span data-ttu-id="06224-137">**サーバー マネージャー** で、 **[管理]** メニューから **[役割と機能の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="06224-137">In **Server Manager** , from the **Manage** menu, select **Add Roles and Features**.</span></span>

    <span data-ttu-id="06224-138">または、 **サーバー マネージャー** で、 **[すべてのサーバー]** をクリックし、サーバー名を右クリックしてから、 **[役割と機能の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="06224-138">Or in **Server Manager** , click **All Servers** , right-click a server name, and then select  **Add Roles and Features**.</span></span>

2. <span data-ttu-id="06224-139">**[インストールの種類]** ページで **[役割ベースまたは機能ベースのインストール]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="06224-139">On the **Installation Type** page, select **Role-based or feature-based installation**.</span></span>

3. <span data-ttu-id="06224-140">**[機能]** ページで、 **[.NET 3.5 Framework 機能]** ノードを展開し、 **[.NET Framework 3.5 (.NET 2.0 および 3.0 を含む)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="06224-140">On the **Features** page, expand the **.NET 3.5 Framework Features** node and select **.NET Framework 3.5 (includes .NET 2.0 and 3.0)**.</span></span>

   <span data-ttu-id="06224-141">このノードの下にあるその他のオプションは、Windows PowerShell 2.0 エンジンには必要ありません。</span><span class="sxs-lookup"><span data-stu-id="06224-141">The other options under that node are not required for the Windows PowerShell 2.0 Engine.</span></span>

#### <a name="to-add-the-windows-powershell-20-engine-feature"></a><span data-ttu-id="06224-142">Windows PowerShell 2.0 エンジンの機能を追加するには</span><span class="sxs-lookup"><span data-stu-id="06224-142">To add the Windows PowerShell 2.0 Engine feature</span></span>

- <span data-ttu-id="06224-143">**サーバー マネージャー** で、 **[管理]** メニューから **[役割と機能の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="06224-143">In **Server Manager** , from the **Manage** menu, select **Add Roles and Features**.</span></span>

  <span data-ttu-id="06224-144">または、 **サーバー マネージャー** で、 **[すべてのサーバー]** をクリックし、サーバー名を右クリックしてから、 **[役割と機能の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="06224-144">Or **Server Manager** , click **All Servers** , right-click a server name, and then select **Add Roles and Features**.</span></span>

- <span data-ttu-id="06224-145">**[インストールの種類]** ページで **[役割ベースまたは機能ベースのインストール]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="06224-145">On the **Installation Type** page, select **Role-based or feature-based installation**.</span></span>

- <span data-ttu-id="06224-146">**[機能]** ページで、 **[Windows PowerShell (インストール済み)]** ノードを展開し、 **[Windows PowerShell 2.0 エンジン]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="06224-146">On the **Features** page, expand the **Windows PowerShell (Installed)** node and select **Windows PowerShell 2.0 Engine**.</span></span>

<span data-ttu-id="06224-147">Windows PowerShell 2.0 エンジンの開始に関する情報については、「[Windows PowerShell 2.0 エンジンの開始](../Starting-the-Windows-PowerShell-2.0-Engine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06224-147">For information about starting the Windows PowerShell 2.0 Engine, see [Starting the Windows PowerShell 2.0 Engine](../Starting-the-Windows-PowerShell-2.0-Engine.md).</span></span>

## <a name="on-earlier-systems"></a><span data-ttu-id="06224-148">以前のシステムの場合</span><span class="sxs-lookup"><span data-stu-id="06224-148">On Earlier Systems</span></span>

<span data-ttu-id="06224-149">Windows 7、Windows Server 2008 R2、および Windows Server 2012 に Windows PowerShell 4.0 をインストールする [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkID=293881) パッケージには、Windows PowerShell 2.0 エンジンが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="06224-149">The [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkID=293881) package that installs Windows PowerShell 4.0 on Windows 7, Windows Server 2008 R2, and Windows Server 2012, includes the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="06224-150">Windows PowerShell 2.0 をエンジンは有効になっており、使用準備が整っていますので、追加のインストールや、セットアップ、構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="06224-150">The Windows PowerShell 2.0 Engine is enabled and ready to use, if necessary, without additional installation, setup, or configuration.</span></span>

<span data-ttu-id="06224-151">Windows 7、Windows Server 2008 R2、および Windows Server 2008 に Windows PowerShell 3.0 をインストールする Windows Management Framework 3.0 パッケージには、Windows PowerShell 2.0 エンジンが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="06224-151">The Windows Management Framework 3.0 package that installs Windows PowerShell 3.0 on Windows 7, Windows Server 2008 R2, and Windows Server 2008, includes the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="06224-152">Windows PowerShell 2.0 をエンジンは有効になっており、使用準備が整っていますので、追加のインストールや、セットアップ、構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="06224-152">The Windows PowerShell 2.0 Engine is enabled and ready to use, if necessary, without additional installation, setup, or configuration.</span></span>

## <a name="see-also"></a><span data-ttu-id="06224-153">参照</span><span class="sxs-lookup"><span data-stu-id="06224-153">See Also</span></span>

- [<span data-ttu-id="06224-154">Windows PowerShell のシステム要件</span><span class="sxs-lookup"><span data-stu-id="06224-154">Windows PowerShell System Requirements</span></span>](Windows-PowerShell-System-Requirements.md)
- [<span data-ttu-id="06224-155">Windows PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="06224-155">Installing Windows PowerShell</span></span>](Installing-Windows-PowerShell.md)
- <span data-ttu-id="06224-156">[Windows PowerShell の開始](/previous-versions/ms714415(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="06224-156">[Starting Windows PowerShell](/previous-versions/ms714415(v=vs.85))</span></span>
- [<span data-ttu-id="06224-157">Windows PowerShell 2.0 エンジンの開始</span><span class="sxs-lookup"><span data-stu-id="06224-157">Starting the Windows PowerShell 2.0 Engine</span></span>](../Starting-the-Windows-PowerShell-2.0-Engine.md)
