---
ms.date: 11/09/2020
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC を使用した初回起動時の仮想マシンの構成
description: この記事では、初回起動時に DSC を使用して仮想マシンを構成する方法について説明します
ms.openlocfilehash: 09449053ff085209dec6ccbfa800e5d112d1c769
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94389999"
---
# <a name="configure-a-virtual-machines-at-initial-boot-up-by-using-dsc"></a><span data-ttu-id="5ea44-104">DSC を使用した初回起動時の仮想マシンの構成</span><span class="sxs-lookup"><span data-stu-id="5ea44-104">Configure a virtual machines at initial boot-up by using DSC</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ea44-105">適用先:Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="5ea44-105">Applies To: Windows PowerShell 5.0</span></span>

## <a name="requirements"></a><span data-ttu-id="5ea44-106">必要条件</span><span class="sxs-lookup"><span data-stu-id="5ea44-106">Requirements</span></span>

> [!NOTE]
> <span data-ttu-id="5ea44-107">このトピックで説明されている **DSCAutomationHostEnabled** レジストリ キーは、PowerShell 4.0 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="5ea44-107">The **DSCAutomationHostEnabled** registry key described in this topic is not available in PowerShell 4.0.</span></span> <span data-ttu-id="5ea44-108">PowerShell 4.0 の初回起動時に、新しい仮想マシンを構成する方法については、「[Want to Automatically Configure Your Machines Using DSC at Initial Boot-up?](https://devblogs.microsoft.com/powershell/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)」 (初回起動時に DSC を使用して自動的にマシンを構成する方法) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ea44-108">For information on how to configure new virtual machines at initial boot-up in PowerShell 4.0, see [Want to Automatically Configure Your Machines Using DSC at Initial Boot-up?](https://devblogs.microsoft.com/powershell/want-to-automatically-configure-your-machines-using-dsc-at-initial-boot-up/)</span></span>

<span data-ttu-id="5ea44-109">これらの例を実行するには、以下が必要になります。</span><span class="sxs-lookup"><span data-stu-id="5ea44-109">To run these examples, you will need:</span></span>

- <span data-ttu-id="5ea44-110">作業する起動可能な VHD。</span><span class="sxs-lookup"><span data-stu-id="5ea44-110">A bootable VHD to work with.</span></span> <span data-ttu-id="5ea44-111">[Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016) で、Windows Server 2016 の評価版と共に ISO をダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-111">You can download an ISO with an evaluation copy of Windows Server 2016 at [Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-windows-server-2016).</span></span>
  <span data-ttu-id="5ea44-112">「[Creating Bootable Virtual Hard Disks](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10))」 (起動可能な仮想ハード ディスクの作成) で、ISO イメージから VHD を作成する方法に関する手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5ea44-112">You can find instructions on how to create a VHD from an ISO image at [Creating Bootable Virtual Hard Disks](/previous-versions/windows/it-pro/windows-7/gg318049(v=ws.10)).</span></span>
- <span data-ttu-id="5ea44-113">Hyper-V が有効なホスト コンピューター。</span><span class="sxs-lookup"><span data-stu-id="5ea44-113">A host computer that has Hyper-V enabled.</span></span> <span data-ttu-id="5ea44-114">詳細については、「[Hyper-V の概要](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11))」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ea44-114">For information, see [Hyper-V overview](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831531(v=ws.11)).</span></span>

  <span data-ttu-id="5ea44-115">DSC を使用すると、ソフトウェアのインストールと初回起動時のコンピューターの構成を自動化できます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-115">By using DSC, you can automate software installation and configuration for a computer at initial boot-up.</span></span> <span data-ttu-id="5ea44-116">初回起動時のプロセスで実行されるように、起動可能なメディア (VHD など) に構成 MOF ドキュメントまたはメタ構成のいずれかを挿入して、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5ea44-116">You do this by either injecting a configuration MOF document or a metaconfiguration into bootable media (such as a VHD) so that they are run during the initial boot-up process.</span></span> <span data-ttu-id="5ea44-117">この動作は、`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System` の [DSCAutomationHostEnabled レジストリ キー](DSCAutomationHostEnabled.md) によって指定されます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-117">This behavior is specified by the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key under `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System`.</span></span>
  <span data-ttu-id="5ea44-118">このキーの既定値は 2 です。これは、初回起動時に DSC を実行することを許可します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-118">By default, the value of this key is 2, which allows DSC to run at boot time.</span></span>

  <span data-ttu-id="5ea44-119">初回起動時に DSC を実行しない場合は、[DSCAutomationHostEnabled レジストリ キー](DSCAutomationHostEnabled.md)を 0 に設定します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-119">If you do not want DSC to run at boot time, set the value of the [DSCAutomationHostEnabled registry key](DSCAutomationHostEnabled.md) registry key to 0.</span></span>

- <span data-ttu-id="5ea44-120">構成 MOF ドキュメントを VHD に挿入する</span><span class="sxs-lookup"><span data-stu-id="5ea44-120">Inject a configuration MOF document into a VHD</span></span>
- <span data-ttu-id="5ea44-121">DSC のメタ構成を VHD に挿入する</span><span class="sxs-lookup"><span data-stu-id="5ea44-121">Inject a DSC metaconfiguration into a VHD</span></span>
- <span data-ttu-id="5ea44-122">起動時の DSC を無効にする</span><span class="sxs-lookup"><span data-stu-id="5ea44-122">Disable DSC at boot time</span></span>

> [!NOTE]
> <span data-ttu-id="5ea44-123">`Pending.mof` と `MetaConfig.mof` を同時にコンピューターに挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-123">You can inject both `Pending.mof` and `MetaConfig.mof` into a computer at the same time.</span></span>
> <span data-ttu-id="5ea44-124">両方のファイルが存在する場合、`MetaConfig.mof` に指定された設定が優先されます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-124">If both files are present, the settings specified in `MetaConfig.mof` take precedence.</span></span>

## <a name="inject-a-configuration-mof-document-into-a-vhd"></a><span data-ttu-id="5ea44-125">構成 MOF ドキュメントを VHD に挿入する</span><span class="sxs-lookup"><span data-stu-id="5ea44-125">Inject a configuration MOF document into a VHD</span></span>

<span data-ttu-id="5ea44-126">初回起動時に構成を適用するために、コンパイル済みの構成 MOF ドキュメントをその `Pending.mof` ファイルとして VHD に挿入できます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-126">To enact a configuration at initial boot-up, you can inject a compiled configuration MOF document into the VHD as its `Pending.mof` file.</span></span> <span data-ttu-id="5ea44-127">**DSCAutomationHostEnabled** レジストリ キーを 2 (既定値) に設定した場合、コンピューターが最初に起動されたときに、DSC では `Pending.mof` で定義された構成を適用します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-127">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the configuration defined by `Pending.mof` when the computer boots up for the first time.</span></span>

<span data-ttu-id="5ea44-128">この例では次の構成を使用します。ここでは、新しいコンピューターに IIS をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5ea44-128">For this example, we will use the following configuration, which will install IIS on the new computer:</span></span>

```powershell
Configuration SampleIISInstall
{
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    node ('localhost')
    {
        WindowsFeature IIS
        {
            Ensure = 'Present'
            Name   = 'Web-Server'
        }
    }
}
```

### <a name="to-inject-the-configuration-mof-document-on-the-vhd"></a><span data-ttu-id="5ea44-129">VHD 上で構成 MOF ドキュメントを挿入するには</span><span class="sxs-lookup"><span data-stu-id="5ea44-129">To inject the configuration MOF document on the VHD</span></span>

1. <span data-ttu-id="5ea44-130">[Mount-VHD](/powershell/module/hyper-v/mount-vhd) コマンドレットを呼び出して、構成を挿入する VHD をマウントします。</span><span class="sxs-lookup"><span data-stu-id="5ea44-130">Mount the VHD into which you want to inject the configuration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="5ea44-131">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-131">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="5ea44-132">PowerShell 5.0 以降を実行しているコンピューターで、上記の構成 (**SampleIISInstall**) を PowerShell スクリプト (.ps1) ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-132">On a computer running PowerShell 5.0 or later, save the above configuration (**SampleIISInstall**) as a PowerShell script (.ps1) file.</span></span>

1. <span data-ttu-id="5ea44-133">PowerShell コンソールで、.ps1 ファイルを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-133">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

1. <span data-ttu-id="5ea44-134">次の PowerShell コマンドを実行して、MOF ドキュメントをコンパイルします (DSC 構成のコンパイルについては、「[DSC 構成](../configurations/configurations.md)」をご覧ください):</span><span class="sxs-lookup"><span data-stu-id="5ea44-134">Run the following PowerShell commands to compile the MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\SampleIISInstall.ps1
   SampleIISInstall
   ```

1. <span data-ttu-id="5ea44-135">この操作を行うと、`SampleIISInstall` という名前の新しいフォルダーに、`localhost.mof` ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-135">This will create a `localhost.mof` file in a new folder named `SampleIISInstall`.</span></span> <span data-ttu-id="5ea44-136">[Move-Item](/powershell/module/microsoft.powershell.management/move-item) コマンドレットを使用して、`Pending.mof` に名前を変更し、VHD の適切な場所にそのファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-136">Rename and move that file into the proper location on the VHD as `Pending.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span> <span data-ttu-id="5ea44-137">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-137">For example:</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\SampleIISInstall\localhost.mof -Destination E:\Windows\System32\Configuration\Pending.mof
   ```

1. <span data-ttu-id="5ea44-138">[Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) コマンドレットを呼び出して、VHD のマウントを解除します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-138">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span>
   <span data-ttu-id="5ea44-139">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-139">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="5ea44-140">DSC MOF ドキュメントをインストールした VHD を使用して、VM を作成します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-140">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="5ea44-141">初回起動が行われ、オペレーティング システムがインストールされると、IIS がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-141">After initial boot-up and operating system installation, IIS will be installed.</span></span> <span data-ttu-id="5ea44-142">[Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) コマンドレットを呼び出して、これを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-142">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="inject-a-dsc-metaconfiguration-into-a-vhd"></a><span data-ttu-id="5ea44-143">DSC のメタ構成を VHD に挿入する</span><span class="sxs-lookup"><span data-stu-id="5ea44-143">Inject a DSC metaconfiguration into a VHD</span></span>

<span data-ttu-id="5ea44-144">メタ構成 (「[ローカル構成マネージャーの構成](../managing-nodes/metaConfig.md)」を参照) をその `MetaConfig.mof` ファイルとして VHD に挿入して、コンピューターが初回起動時に構成をプルするように構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-144">You can also configure a computer to pull a configuration at initial boot-up by injecting a metaconfiguration (see [Configuring the Local Configuration Manager (LCM)](../managing-nodes/metaConfig.md)) into the VHD as its `MetaConfig.mof` file.</span></span> <span data-ttu-id="5ea44-145">**DSCAutomationHostEnabled** レジストリ キーを 2 (既定値) に設定した場合、コンピューターが最初に起動されたときに、`MetaConfig.mof` で定義されたメタ構成が DSC により LCM に適用されます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-145">If the **DSCAutomationHostEnabled** registry key is set to 2 (the default value), DSC will apply the metaconfiguration defined by `MetaConfig.mof` to the LCM when the computer boots up for the first time.</span></span> <span data-ttu-id="5ea44-146">メタ構成で LCM がプル サーバーから構成をプルする必要があることを指定した場合、コンピューターは初回起動時にプル サーバーから構成をプルしようとします。</span><span class="sxs-lookup"><span data-stu-id="5ea44-146">If the metaconfiguration specifies that the LCM should pull configurations from a pull server, the computer will attempt to pull a configuration from that pull server at initial boot-up.</span></span> <span data-ttu-id="5ea44-147">DSC プル サーバーのセットアップについては、「[DSC Web プル サーバーのセットアップ](../pull-server/pullServer.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5ea44-147">For information about setting up a DSC pull server, see [Setting up a DSC web pull server](../pull-server/pullServer.md).</span></span>

<span data-ttu-id="5ea44-148">この例では、前のセクションで示された構成 (**SampleIISInstall**)、および次のメタ構成の両方を使用します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-148">For this example, we will use both the configuration described in the previous section (**SampleIISInstall**), and the following metaconfiguration:</span></span>

```powershell
[DSCLocalConfigurationManager()]
configuration PullClientBootstrap
{
    Node localhost
    {
        Settings
        {
            RefreshMode = 'Pull'
            RefreshFrequencyMins = 30
            RebootNodeIfNeeded = $true
        }
        ConfigurationRepositoryWeb CONTOSO-PullSrv
        {
            ServerURL = 'https://CONTOSO-PullSrv:8080/PSDSCPullServer.svc'
            RegistrationKey = '140a952b-b9d6-406b-b416-e0f759c9c0e4'
            ConfigurationNames = @('SampleIISInstall')
        }
    }
}
```

### <a name="to-inject-the-metaconfiguration-mof-document-on-the-vhd"></a><span data-ttu-id="5ea44-149">VHD 上でメタ構成 MOF ドキュメントを挿入するには</span><span class="sxs-lookup"><span data-stu-id="5ea44-149">To inject the metaconfiguration MOF document on the VHD</span></span>

1. <span data-ttu-id="5ea44-150">[Mount-VHD](/powershell/module/hyper-v/mount-vhd) コマンドレットを呼び出して、メタ構成を挿入する VHD をマウントします。</span><span class="sxs-lookup"><span data-stu-id="5ea44-150">Mount the VHD into which you want to inject the metaconfiguration by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="5ea44-151">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-151">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="5ea44-152">[DSC Web プル サーバーをセットアップ](../pull-server/pullServer.md)して、**SampleIISInstall** 構成を適切なフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-152">[Set up a DSC web pull server](../pull-server/pullServer.md), and save the **SampleIISInstall** configuration to the appropriate folder.</span></span>

1. <span data-ttu-id="5ea44-153">PowerShell 5.0 以降を実行しているコンピューターで、上記のメタ構成 (**PullClientBootstrap**) を PowerShell スクリプト (.ps1) ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-153">On a computer running PowerShell 5.0 or later, save the above metaconfiguration (**PullClientBootstrap**) as a PowerShell script (.ps1) file.</span></span>

1. <span data-ttu-id="5ea44-154">PowerShell コンソールで、.ps1 ファイルを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-154">In a PowerShell console, navigate to the folder where you saved the .ps1 file.</span></span>

1. <span data-ttu-id="5ea44-155">次の PowerShell コマンドを実行して、メタ構成 MOF ドキュメントをコンパイルします (DSC 構成のコンパイルについては、「[DSC 構成](../configurations/configurations.md)」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="5ea44-155">Run the following PowerShell commands to compile the metaconfiguration MOF document (for information about compiling DSC configurations, see [DSC Configurations](../configurations/configurations.md):</span></span>

   ```powershell
   . .\PullClientBootstrap.ps1
   PullClientBootstrap
   ```

1. <span data-ttu-id="5ea44-156">この操作を行うと、`PullClientBootstrap` という名前の新しいフォルダーに、`localhost.meta.mof` ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-156">This will create a `localhost.meta.mof` file in a new folder named `PullClientBootstrap`.</span></span> <span data-ttu-id="5ea44-157">[Move-Item](/powershell/module/microsoft.powershell.management/move-item) コマンドレットを使用して、`MetaConfig.mof` に名前を変更し、VHD の適切な場所にそのファイルを移動します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-157">Rename and move that file into the proper location on the VHD as `MetaConfig.mof` by using the [Move-Item](/powershell/module/microsoft.powershell.management/move-item) cmdlet.</span></span>

   ```powershell
   Move-Item -Path C:\DSCTest\PullClientBootstrap\localhost.meta.mof -Destination E:\Windows\System32\Configuration\MetaConfig.mof
   ```

1. <span data-ttu-id="5ea44-158">[Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) コマンドレットを呼び出して、VHD のマウントを解除します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-158">Dismount the VHD by calling the [Dismount-VHD](/powershell/module/hyper-v/dismount-vhd) cmdlet.</span></span>
   <span data-ttu-id="5ea44-159">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-159">For example:</span></span>

   ```powershell
   Dismount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="5ea44-160">DSC MOF ドキュメントをインストールした VHD を使用して、VM を作成します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-160">Create a VM by using the VHD where you installed the DSC MOF document.</span></span>

<span data-ttu-id="5ea44-161">初回起動が行われ、オペレーティング システムがインストールされると、DSC はプル サーバーから構成をプルして、IIS がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-161">After initial boot-up and operating system installation, DSC will pull the configuration from the pull server, and IIS will be installed.</span></span> <span data-ttu-id="5ea44-162">[Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) コマンドレットを呼び出して、これを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-162">You can verify this by calling the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature) cmdlet.</span></span>

## <a name="disable-dsc-at-boot-time"></a><span data-ttu-id="5ea44-163">起動時の DSC を無効にする</span><span class="sxs-lookup"><span data-stu-id="5ea44-163">Disable DSC at boot time</span></span>

<span data-ttu-id="5ea44-164">`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled` キーの値は既定で</span><span class="sxs-lookup"><span data-stu-id="5ea44-164">By default, the value of the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System\DSCAutomationHostEnabled`</span></span>
<span data-ttu-id="5ea44-165">2 に設定されます。これにより、コンピューターが保留中または最新の状態である場合に、DSC 構成を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-165">key is set to 2, which allows a DSC configuration to run if the computer is in pending or current state.</span></span> <span data-ttu-id="5ea44-166">初回起動時に構成を実行しない場合は、このキーの値を 0 に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5ea44-166">If you do not want a configuration to run at initial boot-up, you need so set the value of this key to 0:</span></span>

1. <span data-ttu-id="5ea44-167">[Mount-VHD](/powershell/module/hyper-v/mount-vhd) コマンドレットを呼び出して、VHD をマウントします。</span><span class="sxs-lookup"><span data-stu-id="5ea44-167">Mount the VHD by calling the [Mount-VHD](/powershell/module/hyper-v/mount-vhd) cmdlet.</span></span> <span data-ttu-id="5ea44-168">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-168">For example:</span></span>

   ```powershell
   Mount-VHD -Path C:\users\public\documents\vhd\Srv16.vhd
   ```

1. <span data-ttu-id="5ea44-169">`reg load` を呼び出して、VHD からレジストリの `HKLM\Software` サブキーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="5ea44-169">Load the registry `HKLM\Software` subkey from the VHD by calling `reg load`.</span></span>

   ```powershell
   reg load HKLM\Vhd E:\Windows\System32\Config\Software
   ```

1. <span data-ttu-id="5ea44-170">読み込まれたハイブで `DSCAutomationHostEnabled` の値を 0 に変更します。</span><span class="sxs-lookup"><span data-stu-id="5ea44-170">Change the value of `DSCAutomationHostEnabled` to 0 in the loaded hive.</span></span>

   ```powershell
   reg add "HKLM\Vhd\Software\Microsoft\Windows\CurrentVersion\Policies\System" /v DSCAutomationHostEnabled /t REG_DWORD /d 0 /f
   ```

1. <span data-ttu-id="5ea44-171">次のコマンドを実行して、レジストリをアンロードします。</span><span class="sxs-lookup"><span data-stu-id="5ea44-171">Unload the registry by running the following commands:</span></span>

   ```powershell
   reg unload HKLM\Vhd
   ```

## <a name="see-also"></a><span data-ttu-id="5ea44-172">参照</span><span class="sxs-lookup"><span data-stu-id="5ea44-172">See Also</span></span>

[<span data-ttu-id="5ea44-173">DSC 構成</span><span class="sxs-lookup"><span data-stu-id="5ea44-173">DSC Configurations</span></span>](../configurations/configurations.md)

[<span data-ttu-id="5ea44-174">DSCAutomationHostEnabled レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="5ea44-174">DSCAutomationHostEnabled registry key</span></span>](DSCAutomationHostEnabled.md)

[<span data-ttu-id="5ea44-175">ローカル構成マネージャー (LCM) の構成</span><span class="sxs-lookup"><span data-stu-id="5ea44-175">Configuring the Local Configuration Manager (LCM)</span></span>](../managing-nodes/metaConfig.md)

[<span data-ttu-id="5ea44-176">DSC Web プル サーバーのセットアップ</span><span class="sxs-lookup"><span data-stu-id="5ea44-176">Setting up a DSC web pull server</span></span>](../pull-server/pullServer.md)
