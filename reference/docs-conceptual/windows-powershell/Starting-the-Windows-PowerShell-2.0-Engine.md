---
ms.date: 06/05/2017
keywords: powershell,コマンドレット
title: Windows PowerShell 2.0 エンジンの使用
ms.openlocfilehash: c5ac92159d63e5669643908016186ed32dfb46db
ms.sourcegitcommit: 3e343f005fe76960c998ef1869a1a093d37ef349
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "85216024"
---
# <a name="using-the-windows-powershell-20-engine"></a><span data-ttu-id="88e38-103">Windows PowerShell 2.0 エンジンの使用</span><span class="sxs-lookup"><span data-stu-id="88e38-103">Using the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="88e38-104">Windows PowerShell は、以前のバージョンとの下位互換性を保つように設計されています。</span><span class="sxs-lookup"><span data-stu-id="88e38-104">Windows PowerShell is designed to be backward compatible with previous versions.</span></span> <span data-ttu-id="88e38-105">Windows PowerShell 2.0 用に記述されたコマンドレット、プロバイダー、スナップイン、モジュール、スクリプトは、変更することなく新しいバージョンの Windows PowerShell で実行できます。</span><span class="sxs-lookup"><span data-stu-id="88e38-105">Cmdlets, providers, snap-ins, modules, and scripts written for Windows PowerShell 2.0 run unchanged in newer versions Windows PowerShell.</span></span> <span data-ttu-id="88e38-106">ただし、Microsoft .NET Framework 4 では、ランタイムのアクティブ化ポリシーが変更されました。</span><span class="sxs-lookup"><span data-stu-id="88e38-106">However, Microsoft .NET Framework 4 changed the runtime activation policy.</span></span>
<span data-ttu-id="88e38-107">Windows PowerShell 2.0 用に記述され、共通言語ランタイム (CLR) 2.0 でコンパイルされた Windows PowerShell ホスト プログラムは、変更を加えなければ、CLR 4.0 以降でコンパイルされた新しいバージョンの Windows PowerShell で実行できません。</span><span class="sxs-lookup"><span data-stu-id="88e38-107">Windows PowerShell host programs written for Windows PowerShell 2.0 and compiled with Common Language Runtime (CLR) 2.0 cannot run without modification in new versions Windows PowerShell that are compiled with CLR 4.0 (or higher).</span></span>

<span data-ttu-id="88e38-108">Windows PowerShell 2.0 エンジンは、既存のスクリプトまたはホスト プログラムが Windows PowerShell 5.1 との互換性がないために実行できない場合に限り使用することが意図されています。</span><span class="sxs-lookup"><span data-stu-id="88e38-108">The Windows PowerShell 2.0 Engine is intended to be used only when an existing script or host program cannot run because it is incompatible with Windows PowerShell 5.1.</span></span> <span data-ttu-id="88e38-109">この例には、古いバージョンの Exchange または SQL Server モジュールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="88e38-109">Examples of this include older versions of Exchange or SQL Server modules.</span></span> <span data-ttu-id="88e38-110">そのようなケースはまれと考えられます。</span><span class="sxs-lookup"><span data-stu-id="88e38-110">Such cases are expected to be rare.</span></span>

<span data-ttu-id="88e38-111">Windows PowerShell 2.0 エンジンを必要とする多くのプログラムは、エンジンを自動的に起動します。</span><span class="sxs-lookup"><span data-stu-id="88e38-111">Many programs that require the Windows PowerShell 2.0 Engine start it automatically.</span></span> <span data-ttu-id="88e38-112">次の手順は、エンジンを手動で起動する必要のあるまれな状況のためのものです。</span><span class="sxs-lookup"><span data-stu-id="88e38-112">These instructions are included for the rare situations in which you need to start the engine manually.</span></span>

## <a name="deprecation-and-security-concerns"></a><span data-ttu-id="88e38-113">非推奨とセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="88e38-113">Deprecation and security concerns</span></span>

<span data-ttu-id="88e38-114">Windows PowerShell 2.0 は、2017 年 8 月に非推奨となりました。</span><span class="sxs-lookup"><span data-stu-id="88e38-114">Windows PowerShell 2.0 was deprecated in August, 2017.</span></span> <span data-ttu-id="88e38-115">詳細については、PowerShell ブログの[お知らせ][]を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e38-115">For more information, see the [announcement][] on the PowerShell blog.</span></span>

<span data-ttu-id="88e38-116">Windows PowerShell 2.0 には、バージョン 3、4、および 5 で追加された強化機能とセキュリティ機能の多くがありません。</span><span class="sxs-lookup"><span data-stu-id="88e38-116">Windows PowerShell 2.0 is missing a significant amount of the hardening and security features added in versions 3, 4, and 5.</span></span> <span data-ttu-id="88e38-117">ユーザーはなるべくこれを使用しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="88e38-117">We highly, highly recommend that users not use it if they can help it.</span></span> <span data-ttu-id="88e38-118">詳細については、「[シェルとスクリプト言語のセキュリティの比較][]」および「[PowerShell ♥ ブルー チーム][blueteam]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e38-118">For more information, see [A Comparison of Shell and Scripting Language Security][] and [PowerShell ♥ the Blue Team][blueteam].</span></span>

## <a name="installing-and-enabling-required-programs"></a><span data-ttu-id="88e38-119">必要なプログラムのインストールと有効化</span><span class="sxs-lookup"><span data-stu-id="88e38-119">Installing and Enabling Required Programs</span></span>

<span data-ttu-id="88e38-120">Windows PowerShell 2.0 エンジンを起動する前に、Windows PowerShell 2.0 エンジンと Microsoft .NET Framework 3.5 Service Pack 1 を有効にします。</span><span class="sxs-lookup"><span data-stu-id="88e38-120">Before starting the Windows PowerShell 2.0 Engine, enable the Windows PowerShell 2.0 Engine and Microsoft .NET Framework 3.5 with Service Pack 1.</span></span> <span data-ttu-id="88e38-121">方法については、「[Windows PowerShell のインストール][]」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="88e38-121">For instructions, see [Installing Windows PowerShell][].</span></span>

<span data-ttu-id="88e38-122">Windows Management Framework 3.0 以降がインストールされているシステムには、すべての必要なコンポーネントが揃っています。</span><span class="sxs-lookup"><span data-stu-id="88e38-122">Systems on which Windows Management Framework 3.0 or higher is installed have all of the required components.</span></span> <span data-ttu-id="88e38-123">これ以上の構成は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="88e38-123">No further configuration is necessary.</span></span> <span data-ttu-id="88e38-124">Windows Management Framework のインストールについては、[WMF のインストールと構成][]に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e38-124">For information about installing Windows Management Framework, see [Install and configure WMF][].</span></span>

## <a name="how-to-start-the-windows-powershell-20-engine"></a><span data-ttu-id="88e38-125">Windows PowerShell 2.0 エンジンを起動する方法</span><span class="sxs-lookup"><span data-stu-id="88e38-125">How to start the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="88e38-126">Windows PowerShell を起動すると、既定で最新バージョンが起動します。</span><span class="sxs-lookup"><span data-stu-id="88e38-126">When you start Windows PowerShell the newest version starts by default.</span></span> <span data-ttu-id="88e38-127">Windows PowerShell 2.0 エンジンで Windows PowerShell を起動するには、`PowerShell.exe` の Version パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="88e38-127">To start Windows PowerShell with the Windows PowerShell 2.0 Engine, use the Version parameter of `PowerShell.exe`.</span></span> <span data-ttu-id="88e38-128">コマンドは、Windows PowerShell と Cmd.exe を含む任意のコマンド プロンプトで実行できます。</span><span class="sxs-lookup"><span data-stu-id="88e38-128">You can run the command at any command prompt, including Windows PowerShell and Cmd.exe.</span></span>

```
PowerShell.exe -Version 2
```

## <a name="how-to-start-a-remote-session-with-the-windows-powershell-20-engine"></a><span data-ttu-id="88e38-129">Windows PowerShell 2.0 エンジンを使用してリモート セッションを開始する方法</span><span class="sxs-lookup"><span data-stu-id="88e38-129">How to start a remote session with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="88e38-130">リモート セッションで Windows PowerShell 2.0 エンジンを実行するには、Windows PowerShell 2.0 エンジンを読み込むリモート コンピューターでセッション構成 ("_エンドポイント_" とも呼ばれる) を作成します。</span><span class="sxs-lookup"><span data-stu-id="88e38-130">To run the Windows PowerShell 2.0 Engine in a remote session, create a session configuration (also known as an _endpoint_) on the remote computer that loads the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="88e38-131">セッション構成は、リモート コンピューターに保存され、許可されているユーザーは誰でもそれを使って Windows PowerShell 2.0 エンジンを使用するセッションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="88e38-131">The session configuration is saved on the remote computer and can be used by any authorized user to create sessions that use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="88e38-132">これは、通常システム管理者によって実行される高度なタスクです。</span><span class="sxs-lookup"><span data-stu-id="88e38-132">This is an advanced task that is typically performed by a system administrator.</span></span>

<span data-ttu-id="88e38-133">次の手順では、[Register-PSSessionConfiguration][] コマンドレットの **PSVersion** パラメーターを使用して、Windows PowerShell 2.0 エンジンを使用するセッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="88e38-133">The following procedure uses the **PSVersion** parameter of the [Register-PSSessionConfiguration][] cmdlet to create a session configuration that uses the Windows PowerShell 2.0 Engine.</span></span> <span data-ttu-id="88e38-134">[New-PSSessionConfigurationFile][] コマンドレットの **PowerShellVersion** パラメーターを使用して、Windows PowerShell 2.0 エンジンを読み込むセッションのセッション構成ファイルを作成することも、[Set-PSSessionConfiguration][] パラメーターの **PSVersion** パラメーターを使用して、Windows PowerShell 2.0 エンジンを使用するようにセッション構成を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="88e38-134">You can also use the **PowerShellVersion** parameter of the [New-PSSessionConfigurationFile][] cmdlet to create a session configuration file for a session that loads the Windows PowerShell 2.0 Engine and you can use the **PSVersion** parameter of the [Set-PSSessionConfiguration][] parameter to change a session configuration to use the Windows PowerShell 2.0 Engine.</span></span>

<span data-ttu-id="88e38-135">セッション構成ファイルの詳細については、「[about_Session_Configuration_Files][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e38-135">For more information about session configuration files, see [about_Session_Configuration_Files][].</span></span>
<span data-ttu-id="88e38-136">セットアップとセキュリティを含むセッション構成の詳細については、「[about_Session_Configurations][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e38-136">For information about session configurations, including setup and security, see [about_Session_Configurations][].</span></span>

### <a name="to-start-a-remote-windows-powershell-20-session"></a><span data-ttu-id="88e38-137">リモートの Windows PowerShell 2.0 セッションを開始するには</span><span class="sxs-lookup"><span data-stu-id="88e38-137">To start a remote Windows PowerShell 2.0 session</span></span>

1. <span data-ttu-id="88e38-138">Windows PowerShell 2.0 エンジンを必要とするセッション構成を作成するには、**PSVersion** パラメーターに値 `2.0` を指定して `Register-PSSessionConfiguration` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="88e38-138">To create a session configuration that requires the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet with a value of `2.0`.</span></span>
   <span data-ttu-id="88e38-139">接続の "サーバー側" (受信側) にあるコンピューターでこのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="88e38-139">Run this command on the computer at the "server side" or receiving end of the connection.</span></span>

   <span data-ttu-id="88e38-140">次のサンプル コマンドは、Server01 コンピューター上に PS2 セッション構成を作成します。</span><span class="sxs-lookup"><span data-stu-id="88e38-140">The following sample command creates the PS2 session configuration on the Server01 computer.</span></span> <span data-ttu-id="88e38-141">このコマンドを実行するには、 **[管理者として実行]** オプションを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="88e38-141">To run this command, start Windows PowerShell with the **Run as administrator** option.</span></span>

   ```powershell
   Register-PSSessionConfiguration -Name PS2 -PSVersion 2.0
   ```

1. <span data-ttu-id="88e38-142">PS2 セッション構成を使用する Server01 コンピューターでセッションを作成するには、リモート セッションを作成するコマンドレット (`New-PSSession` コマンドレットなど) の **ConfigurationName** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="88e38-142">To create a session on the Server01 computer that uses the PS2 session configuration, use the **ConfigurationName** parameter of cmdlets that create a remote session, such as the \`New-PSSession cmdlet.</span></span>

   <span data-ttu-id="88e38-143">セッション構成を使用するセッションを開始すると、Windows PowerShell 2.0 エンジンが自動的にセッションに読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="88e38-143">When a session that uses the session configuration starts, the Windows PowerShell 2.0 Engine is automatically loaded into the session.</span></span>

   <span data-ttu-id="88e38-144">次のコマンドは、PS2 セッション構成を使用する Server01 コンピューターでセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="88e38-144">The following command starts a session on the Server01 computer that uses the PS2 session configuration.</span></span> <span data-ttu-id="88e38-145">このコマンドでは、セッションが `$s` 変数に保存されます。</span><span class="sxs-lookup"><span data-stu-id="88e38-145">The command saves the session in the `$s` variable.</span></span>

   ```powershell
   $s = New-PSSession -ComputerName Server01 -ConfigurationName PS2
   ```

## <a name="how-to-start-a-background-job-with-the-windows-powershell-20-engine"></a><span data-ttu-id="88e38-146">Windows PowerShell 2.0 エンジンを使用してバックグラウンド ジョブを開始する方法</span><span class="sxs-lookup"><span data-stu-id="88e38-146">How to start a background job with the Windows PowerShell 2.0 Engine</span></span>

<span data-ttu-id="88e38-147">Windows PowerShell 2.0 エンジンを使用してバックグラウンド ジョブを開始するには、[Start-Job][] コマンドレットの **PSVersion** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="88e38-147">To start a background job with the Windows PowerShell 2.0 Engine, use the **PSVersion** parameter of the [Start-Job][] cmdlet.</span></span>

<span data-ttu-id="88e38-148">次のコマンドは、Windows PowerShell 2.0 エンジンを使用してバックグラウンド ジョブを開始します。</span><span class="sxs-lookup"><span data-stu-id="88e38-148">The following command starts a background job with the Windows PowerShell 2.0 Engine</span></span>

```powershell
Start-Job {Get-Process} -PSVersion 2.0
```

<span data-ttu-id="88e38-149">バックグラウンド ジョブの詳細については、「[about_Jobs][]」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e38-149">For more information about background jobs, see [about_Jobs][].</span></span>

<!-- link references -->
[お知らせ]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[announcement]: https://devblogs.microsoft.com/powershell/windows-powershell-2-0-deprecation/
[シェルとスクリプト言語のセキュリティの比較]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[A Comparison of Shell and Scripting Language Security]: https://devblogs.microsoft.com/powershell/a-comparison-of-shell-and-scripting-language-security/
[blueteam]: https://devblogs.microsoft.com/powershell/powershell-the-blue-team/
[Windows PowerShell のインストール]: install/Installing-Windows-PowerShell.md
[Installing Windows PowerShell]: install/Installing-Windows-PowerShell.md
[WMF のインストールと構成]: wmf/setup/install-configure.md
[Install and configure WMF]: wmf/setup/install-configure.md
[Register-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Register-PSSessionConfiguration
[New-PSSessionConfigurationFile]: /powershell/module/Microsoft.PowerShell.Core/New-PSSessionConfigurationFile
[Set-PSSessionConfiguration]: /powershell/module/Microsoft.PowerShell.Core/Set-PSSessionConfiguration
[about_Session_Configuration_Files]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configuration_Files
[about_Session_Configurations]: /powershell/module/Microsoft.PowerShell.Core/about/about_Session_Configurations
[Start-Job]: /powershell/module/microsoft.powershell.core/start-job
[about_Jobs]: /powershell/module/microsoft.powershell.core/about/about_jobs
