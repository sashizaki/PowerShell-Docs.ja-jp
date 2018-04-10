---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: Windows PowerShell のシステム要件
ms.assetid: 6d1d3c75-3be4-4fc9-8805-ca9b2c454d42
ms.openlocfilehash: a15b5b33b5296befae833e520cfdfbd41a07b122
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="windows-powershell-system-requirements"></a><span data-ttu-id="97aef-103">Windows PowerShell のシステム要件</span><span class="sxs-lookup"><span data-stu-id="97aef-103">Windows PowerShell System Requirements</span></span>
<span data-ttu-id="97aef-104">このトピックでは、Windows PowerShell 3.0、Windows PowerShell 4.0、および Windows PowerShell 5.0 のシステム要件の一覧や、Windows PowerShell Integrated Scripting Environment (ISE)、CIM コマンド、ワークフローなどの特殊な機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="97aef-104">This topic lists the system requirements for Windows PowerShell 3.0, Windows PowerShell 4.0 and Windows PowerShell 5.0, and for special features, such as Windows PowerShell Integrated Scripting Environment (ISE), CIM commands, and workflows.</span></span>

<span data-ttu-id="97aef-105">Windows® 8.1 および Windows Server® 2012 R2 には、必要なプログラムがすべて付属しています。</span><span class="sxs-lookup"><span data-stu-id="97aef-105">Windows® 8.1 and Windows Server® 2012 R2 include all required programs.</span></span> <span data-ttu-id="97aef-106">このトピックは、以前のリリースの Windows のユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="97aef-106">This topic is designed for users of earlier releases of Windows.</span></span>

## <a name="operating-system-requirements"></a><span data-ttu-id="97aef-107">オペレーティング システムの要件</span><span class="sxs-lookup"><span data-stu-id="97aef-107">Operating System Requirements</span></span>
<span data-ttu-id="97aef-108">Windows PowerShell 5.0 は、次のバージョンの Windows で実行できます。</span><span class="sxs-lookup"><span data-stu-id="97aef-108">Windows PowerShell 5.0 runs on the following versions of Windows.</span></span>

- <span data-ttu-id="97aef-109">Windows Server 2016 (既定でインストール済み)</span><span class="sxs-lookup"><span data-stu-id="97aef-109">Windows Server 2016, installed by default</span></span>

- <span data-ttu-id="97aef-110">Windows Server 2012 R2 では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-110">Windows Server 2012 R2, install [Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) to run Windows PowerShell 5.0</span></span>

- <span data-ttu-id="97aef-111">Windows Server 2012 では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-111">Windows Server 2012, install [Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) to run Windows PowerShell 5.0</span></span>

- <span data-ttu-id="97aef-112">Windows Server 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-112">Windows Server 2008 R2 with Service Pack 1, install [Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) to run Windows PowerShell 5.0</span></span>

- <span data-ttu-id="97aef-113">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="97aef-113">Windows 8.1</span></span>

- <span data-ttu-id="97aef-114">Windows 7 (Service Pack 1 適用済み) では、[Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) をインストールして Windows PowerShell 5.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-114">Windows 7 with Service Pack 1, install [Windows Management Framework 5.0](https://www.microsoft.com/en-us/download/details.aspx?id=50395) to run Windows PowerShell 5.0</span></span>

<span data-ttu-id="97aef-115">Windows PowerShell 4.0 は、次のバージョンの Windows で実行できます。</span><span class="sxs-lookup"><span data-stu-id="97aef-115">Windows PowerShell 4.0 runs on the following versions of Windows.</span></span>

- <span data-ttu-id="97aef-116">Windows 8.1 (既定でインストール済み)</span><span class="sxs-lookup"><span data-stu-id="97aef-116">Windows 8.1, installed by default</span></span>

- <span data-ttu-id="97aef-117">Windows Server 2012 R2 (既定でインストール済み)</span><span class="sxs-lookup"><span data-stu-id="97aef-117">Windows Server 2012 R2, installed by default</span></span>

- <span data-ttu-id="97aef-118">Windows® 7 (Service Pack 1 適用済み) では、[Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) をインストールして Windows PowerShell 4.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-118">Windows® 7 with Service Pack 1, install [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to run Windows PowerShell 4.0</span></span>

- <span data-ttu-id="97aef-119">Windows Server® 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) をインストールして Windows PowerShell 4.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-119">Windows Server® 2008 R2 with Service Pack 1, install [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to run Windows PowerShell 4.0</span></span>

<span data-ttu-id="97aef-120">Windows PowerShell 3.0 は、次のバージョンの Windows で実行できます。</span><span class="sxs-lookup"><span data-stu-id="97aef-120">Windows PowerShell 3.0 runs on the following versions of Windows.</span></span>

- <span data-ttu-id="97aef-121">Windows 8 (既定でインストール済み)</span><span class="sxs-lookup"><span data-stu-id="97aef-121">Windows 8, installed by default</span></span>

- <span data-ttu-id="97aef-122">Windows Server 2012 (既定でインストール済み)</span><span class="sxs-lookup"><span data-stu-id="97aef-122">Windows Server 2012, installed by default</span></span>

- <span data-ttu-id="97aef-123">Windows® 7 (Service Pack 1 適用済み) では、[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-123">Windows® 7 with Service Pack 1, install [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) to run Windows PowerShell 3.0</span></span>

- <span data-ttu-id="97aef-124">Windows Server® 2008 R2 (Service Pack 1 適用済み) では、[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-124">Windows Server® 2008 R2 with Service Pack 1, install [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) to run Windows PowerShell 3.0</span></span>

- <span data-ttu-id="97aef-125">Windows Server 2008 (Service Pack 2 適用済み) では、[Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) をインストールして Windows PowerShell 3.0 を実行します</span><span class="sxs-lookup"><span data-stu-id="97aef-125">Windows Server 2008 with Service Pack 2, install [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) to run Windows PowerShell 3.0</span></span>

## <a name="microsoft-net-framework-requirements"></a><span data-ttu-id="97aef-126">Microsoft .NET Framework の要件</span><span class="sxs-lookup"><span data-stu-id="97aef-126">Microsoft .NET Framework Requirements</span></span>
<span data-ttu-id="97aef-127">Windows PowerShell 5.0 には Microsoft .NET Framework 4.5 のフル インストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="97aef-127">Windows PowerShell 5.0 requires the full installation of Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="97aef-128">Windows 8.1 と Windows Server 2012 R2 には、既定で Microsoft .NET Framework 4.5 が付属しています。</span><span class="sxs-lookup"><span data-stu-id="97aef-128">Windows 8.1 and Windows Server 2012 R2 include Microsoft .NET Framework 4.5 by default.</span></span>

<span data-ttu-id="97aef-129">Windows PowerShell 4.0 には Microsoft .NET Framework 4.5 のフル インストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="97aef-129">Windows PowerShell 4.0 requires the full installation of Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="97aef-130">Windows 8.1 と Windows Server 2012 R2 には、既定で Microsoft .NET Framework 4.5 が付属しています。</span><span class="sxs-lookup"><span data-stu-id="97aef-130">Windows 8.1 and Windows Server 2012 R2 include Microsoft .NET Framework 4.5 by default.</span></span>

<span data-ttu-id="97aef-131">Windows PowerShell 3.0 には Microsoft .NET Framework 4 のフル インストールが必要です。</span><span class="sxs-lookup"><span data-stu-id="97aef-131">Windows PowerShell 3.0 requires the full installation of Microsoft .NET Framework 4.</span></span> <span data-ttu-id="97aef-132">Windows 8 と Windows Server 2012 には、既定で Microsoft .NET Framework 4.5 が含まれるため、この要件は満たされています。</span><span class="sxs-lookup"><span data-stu-id="97aef-132">Windows 8 and Windows Server 2012 include Microsoft .NET Framework 4.5 by default, which fulfills this requirement.</span></span>

<span data-ttu-id="97aef-133">Microsoft .NET Framework 4.5 (dotNetFx45_Full_setup.exe) をインストールするには、Microsoft ダウンロード センターの「[Microsoft .NET Framework 4.5](http://go.microsoft.com/fwlink/?LinkID=242919)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97aef-133">To install Microsoft .NET Framework 4.5 (dotNetFx45_Full_setup.exe), see [Microsoft .NET Framework 4.5](http://go.microsoft.com/fwlink/?LinkID=242919) on the Microsoft Download Center.</span></span>

<span data-ttu-id="97aef-134">Microsoft .NET Framework 4 (dotNetFx40_Full_setup.exe) をフル インストールするには、Microsoft ダウンロード センターの「[Microsoft .NET Framework 4 (Web インストーラー)](http://go.microsoft.com/fwlink/?LinkID=212931)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97aef-134">To install the full installation of Microsoft .NET Framework 4 (dotNetFx40_Full_setup.exe), see [Microsoft .NET Framework 4 (Web Installer)](http://go.microsoft.com/fwlink/?LinkID=212931) on the Microsoft Download Center.</span></span>

## <a name="windows-management-framework-40"></a><span data-ttu-id="97aef-135">Windows Management Framework 4.0</span><span class="sxs-lookup"><span data-stu-id="97aef-135">Windows Management Framework 4.0</span></span>
<span data-ttu-id="97aef-136">Windows PowerShell 5.0 には、Windows Server 2008 R2 SP1 と Windows 7 SP1 に Windows Management Framework 4.0 をプレインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="97aef-136">Windows PowerShell 5.0 requires Windows Management Framework 4.0 to be preinstalled on Windows Server 2008 R2 SP1 and Windows 7 SP1.</span></span>

## <a name="ws-management-30"></a><span data-ttu-id="97aef-137">WS-Management 3.0</span><span class="sxs-lookup"><span data-stu-id="97aef-137">WS-Management 3.0</span></span>
<span data-ttu-id="97aef-138">Windows PowerShell 3.0 と Windows PowerShell 4.0 は、WinRM サービスおよび WSMan プロトコルをサポートする WS-Management 3.0 を必要とします。</span><span class="sxs-lookup"><span data-stu-id="97aef-138">Windows PowerShell 3.0 and Windows PowerShell 4.0 require WS-Management 3.0, which supports the WinRM service and WSMan protocol.</span></span> <span data-ttu-id="97aef-139">このプログラムは、Windows 8.1、Windows Server 2012 R2、Windows 8、Windows Server 2012、Windows Management Framework 4.0、Windows Management Framework 3.0 にも組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="97aef-139">This program is included in Windows 8.1, Windows Server 2012 R2, Windows 8, Windows Server 2012, Windows Management Framework 4.0, and Windows Management Framework 3.0.</span></span>

## <a name="windows-management-instrumentation-30"></a><span data-ttu-id="97aef-140">Windows Management Instrumentation 3.0</span><span class="sxs-lookup"><span data-stu-id="97aef-140">Windows Management Instrumentation 3.0</span></span>
<span data-ttu-id="97aef-141">Windows PowerShell 3.0 と Windows PowerShell 4.0 には、Windows Management Instrumentation 3.0 (WMI) が必要です。</span><span class="sxs-lookup"><span data-stu-id="97aef-141">Windows PowerShell 3.0 and Windows PowerShell 4.0 require Windows Management Instrumentation 3.0 (WMI).</span></span> <span data-ttu-id="97aef-142">このプログラムは、Windows 8.1、Windows Server 2012 R2、Windows 8、Windows Server 2012、Windows Management Framework 4.0、Windows Management Framework 3.0 にも組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="97aef-142">This program is included in Windows 8.1, Windows Server 2012 R2, Windows 8, Windows Server 2012, Windows Management Framework 4.0, and Windows Management Framework 3.0.</span></span> <span data-ttu-id="97aef-143">このプログラムがコンピューターにインストールされていない場合、CIM コマンドなどの、WMI を必要とする機能は実行されません。</span><span class="sxs-lookup"><span data-stu-id="97aef-143">If this program is not installed on the computer, features that require WMI, such as CIM commands, do not run.</span></span>

## <a name="common-language-runtime-40"></a><span data-ttu-id="97aef-144">共通言語ランタイム 4.0</span><span class="sxs-lookup"><span data-stu-id="97aef-144">Common Language Runtime 4.0</span></span>
<span data-ttu-id="97aef-145">Windows PowerShell 3.0、Windows PowerShell 4.0、および Windows PowerShell 5.0 は、共通言語ランタイム (CLR) 4.0 に対してコンパイルされます。</span><span class="sxs-lookup"><span data-stu-id="97aef-145">Windows PowerShell 3.0, Windows PowerShell 4.0, and Windows PowerShell 5.0 are compiled against Common Language Runtime (CLR) 4.0.</span></span>

## <a name="graphical-user-interface-requirements"></a><span data-ttu-id="97aef-146">グラフィカル ユーザー インターフェイスの要件</span><span class="sxs-lookup"><span data-stu-id="97aef-146">Graphical User Interface Requirements</span></span>
<span data-ttu-id="97aef-147">Windows PowerShell はグラフィカル ユーザー インターフェイスを必要としないコンソール ベースのアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="97aef-147">Windows PowerShell is a console-based application that does not require a graphical user interface.</span></span> <span data-ttu-id="97aef-148">そのため、画面 (モニター) もユーザー インターフェイスも持たない、Windows Server 2012 R2 または Windows Server 2012 の Server Core インストール オプションなどのコンピューターに適しています。</span><span class="sxs-lookup"><span data-stu-id="97aef-148">As such, is it well suited to computers that do not have screens or monitors, or a user interface, such as the Server Core installation options of Windows Server 2012 R2 or Windows Server 2012.</span></span>

<span data-ttu-id="97aef-149">ただし、次のように一部グラフィカル ユーザー インターフェイスを必要とする項目もあります。</span><span class="sxs-lookup"><span data-stu-id="97aef-149">However, some items, such as the following, require a graphical user interface.</span></span> <span data-ttu-id="97aef-150">詳細については、各項目のヘルプ トピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97aef-150">For details, see the help topic for each item.</span></span>

- <span data-ttu-id="97aef-151">Windows PowerShell Integrated Scripting Environment (ISE)</span><span class="sxs-lookup"><span data-stu-id="97aef-151">Windows PowerShell Integrated Scripting Environment (ISE)</span></span>

- <span data-ttu-id="97aef-152">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="97aef-152">Cmdlets</span></span>

    1.  [<span data-ttu-id="97aef-153">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="97aef-153">Out-GridView</span></span>](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.utility/out-gridview)

    2.  [<span data-ttu-id="97aef-154">Show-Command</span><span class="sxs-lookup"><span data-stu-id="97aef-154">Show-Command</span></span>](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Utility/Show-Command)

    3.  [<span data-ttu-id="97aef-155">Show-ControlPanelItem</span><span class="sxs-lookup"><span data-stu-id="97aef-155">Show-ControlPanelItem</span></span>](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Management/Show-ControlPanelItem)

    4.  [<span data-ttu-id="97aef-156">Show-EventLog</span><span class="sxs-lookup"><span data-stu-id="97aef-156">Show-EventLog</span></span>](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Management/Show-EventLog)

- <span data-ttu-id="97aef-157">パラメーター</span><span class="sxs-lookup"><span data-stu-id="97aef-157">Parameters</span></span>

    1.  <span data-ttu-id="97aef-158">[Get-Help](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Core/Get-Help) コマンドレットの **ShowWindow** パラメーター。</span><span class="sxs-lookup"><span data-stu-id="97aef-158">**ShowWindow** parameter of the [Get-Help](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Core/Get-Help) cmdlet.</span></span>

    2.  <span data-ttu-id="97aef-159">[Register-PSSessionConfiguration](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration) と [Set-PSSessionConfiguration](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration) コマンドレットの **ShowSecurityDescriptorUI** パラメーター。</span><span class="sxs-lookup"><span data-stu-id="97aef-159">**ShowSecurityDescriptorUI** parameter of the [Register-PSSessionConfiguration](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration) and [Set-PSSessionConfiguration](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration) cmdlets.</span></span>

## <a name="windows-powershell-engine-requirements"></a><span data-ttu-id="97aef-160">Windows PowerShell Engine の要件</span><span class="sxs-lookup"><span data-stu-id="97aef-160">Windows PowerShell Engine Requirements</span></span>
<span data-ttu-id="97aef-161">Windows PowerShell 4.0 は、Windows PowerShell 3.0 および Windows PowerShell 2.0 との下位互換性を保つように設計されています。</span><span class="sxs-lookup"><span data-stu-id="97aef-161">Windows PowerShell 4.0 is designed to be backwards compatible with Windows PowerShell 3.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="97aef-162">Windows PowerShell 2.0 と Windows PowerShell 3.0 用に記述されたコマンドレット、プロバイダー、スナップイン、モジュール、スクリプトは、未変更のまま Windows PowerShell 4.0 で実行できます。</span><span class="sxs-lookup"><span data-stu-id="97aef-162">Cmdlets, providers, snap-ins, modules, and scripts written for Windows PowerShell 2.0 and Windows PowerShell 3.0 run unchanged in Windows PowerShell 4.0.</span></span>

<span data-ttu-id="97aef-163">ただし、Microsoft .NET Framework 4 でランタイムのアクティブ化ポリシーが変更されたため、Windows PowerShell 2.0 用に記述され、共通言語ランタイム (CLR) 2.0 でコンパイルされた Windows PowerShell ホスト プログラムは、変更を加えなければ Windows PowerShell 3.0 (CLR 4.0 でコンパイルされたもの) で実行できません。</span><span class="sxs-lookup"><span data-stu-id="97aef-163">However, due to a change in the runtime activation policy in Microsoft .NET Framework 4, Windows PowerShell host programs that were written for Windows PowerShell 2.0 and compiled with Common Language Runtime (CLR) 2.0 cannot run without modification in Windows PowerShell 3.0, which is compiled with CLR 4.0.</span></span>

<span data-ttu-id="97aef-164">Windows PowerShell 2.0 エンジンには最低でも Microsoft .NET Framework 2.0.50727 が必要です。</span><span class="sxs-lookup"><span data-stu-id="97aef-164">The Windows PowerShell 2.0 engine requires Microsoft .NET Framework 2.0.50727 at a minimum.</span></span> <span data-ttu-id="97aef-165">この要件は Microsoft .NET Framework 3.5 Service Pack 1 で満たされています。</span><span class="sxs-lookup"><span data-stu-id="97aef-165">This requirement is fulfilled by Microsoft .NET Framework 3.5 Service Pack 1.</span></span> <span data-ttu-id="97aef-166">Microsoft .NET Framework 4 以降のリリースの Microsoft .NET Framework では、この要件が満たされません。</span><span class="sxs-lookup"><span data-stu-id="97aef-166">This requirement is not fulfilled by Microsoft .NET Framework 4 and later releases of Microsoft .NET Framework.</span></span>

<span data-ttu-id="97aef-167">Windows PowerShell 2.0 エンジンの追加とインストールや、必要なバージョンの Microsoft .NET Framework の追加とインストールについては、「[Windows PowerShell 2.0 エンジンのインストール](Installing-the-Windows-PowerShell-2.0-Engine.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="97aef-167">For information about adding or installing the Windows PowerShell 2.0 engine, and adding or installing the required versions of the Microsoft .NET Framework, see [Installing the Windows PowerShell 2.0 Engine](Installing-the-Windows-PowerShell-2.0-Engine.md).</span></span> <span data-ttu-id="97aef-168">Windows PowerShell 2.0 エンジンの開始に関する情報については、「[Windows PowerShell 2.0 エンジンの開始](Starting-the-Windows-PowerShell-2.0-Engine.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97aef-168">For information about starting the Windows PowerShell 2.0 engine, see [Starting the Windows PowerShell 2.0 Engine](Starting-the-Windows-PowerShell-2.0-Engine.md).</span></span>

## <a name="windows-preinstallation-environment"></a><span data-ttu-id="97aef-169">Windows プレインストール環境</span><span class="sxs-lookup"><span data-stu-id="97aef-169">Windows Preinstallation Environment</span></span>
<span data-ttu-id="97aef-170">Windows PowerShell 2.0、Windows PowerShell 3.0、および Windows PowerShell 4.0 は、Windows プレインストール環境 (Windows PE) で実行できます。</span><span class="sxs-lookup"><span data-stu-id="97aef-170">Windows PowerShell 2.0, Windows PowerShell 3.0, and Windows PowerShell 4.0 run in the Windows Preinstallation Environment (Windows PE).</span></span> <span data-ttu-id="97aef-171">ただし、次のコマンドレットはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97aef-171">However, the following cmdlets are not supported.</span></span>

- [<span data-ttu-id="97aef-172">バックグラウンド インテリジェント転送サービス (BITS) のコマンドレット</span><span class="sxs-lookup"><span data-stu-id="97aef-172">Background Intelligent Transfer Service (BITS) Cmdlets</span></span>](http://go.microsoft.com/fwlink/?LinkId=257514)

- [<span data-ttu-id="97aef-173">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="97aef-173">Get-EventLog</span></span>](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Management/Get-EventLog)

- [<span data-ttu-id="97aef-174">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="97aef-174">Get-WinEvent</span></span>](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Diagnostics/Get-WinEvent)

- [<span data-ttu-id="97aef-175">Save-Help</span><span class="sxs-lookup"><span data-stu-id="97aef-175">Save-Help</span></span>](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Core/Save-Help)

- [<span data-ttu-id="97aef-176">Update-Help</span><span class="sxs-lookup"><span data-stu-id="97aef-176">Update-Help</span></span>](https://docs.microsoft.com/en-us/powershell/module/Microsoft.PowerShell.Core/Update-Help)

<span data-ttu-id="97aef-177">また、**WinRM** サービスは Windows PE に存在しません。</span><span class="sxs-lookup"><span data-stu-id="97aef-177">Also, the **WinRM** service is not present on Windows PE.</span></span>

## <a name="see-also"></a><span data-ttu-id="97aef-178">参照</span><span class="sxs-lookup"><span data-stu-id="97aef-178">See Also</span></span>
- [<span data-ttu-id="97aef-179">Windows PowerShell ファースト ステップ ガイド</span><span class="sxs-lookup"><span data-stu-id="97aef-179">Getting Started with Windows PowerShell</span></span>](../getting-started/Getting-Started-with-Windows-PowerShell.md)
- [<span data-ttu-id="97aef-180">Windows PowerShell のインストール</span><span class="sxs-lookup"><span data-stu-id="97aef-180">Installing Windows PowerShell</span></span>](Installing-Windows-PowerShell.md)
- [<span data-ttu-id="97aef-181">Windows PowerShell の開始</span><span class="sxs-lookup"><span data-stu-id="97aef-181">Starting Windows PowerShell</span></span>](Starting-Windows-PowerShell.md)