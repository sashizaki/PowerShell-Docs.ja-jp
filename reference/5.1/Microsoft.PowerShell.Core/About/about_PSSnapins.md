---
description: Windows PowerShell スナップインについて説明し、それらを使用および管理する方法を示します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssnapins?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSnapins
ms.openlocfilehash: 494b3275e4fe8a3aacdc358317950542962957cf
ms.sourcegitcommit: 2c311274ce721cd1072dcf2dc077226789e21868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2020
ms.locfileid: "94388894"
---
# <a name="about-pssnapins"></a><span data-ttu-id="60fc2-104">PSSnapins について</span><span class="sxs-lookup"><span data-stu-id="60fc2-104">About PSSnapins</span></span>

## <a name="short-description"></a><span data-ttu-id="60fc2-105">概要</span><span class="sxs-lookup"><span data-stu-id="60fc2-105">SHORT DESCRIPTION</span></span>

<span data-ttu-id="60fc2-106">Windows PowerShell スナップインについて説明し、それらを使用および管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-106">Describes  Windows PowerShell snap-ins and shows how to use and manage them.</span></span>

## <a name="long-description"></a><span data-ttu-id="60fc2-107">詳細説明</span><span class="sxs-lookup"><span data-stu-id="60fc2-107">LONG DESCRIPTION</span></span>

<span data-ttu-id="60fc2-108">Windows PowerShell スナップインは、Windows PowerShell プロバイダーと、 \/ またはコマンドレットを含む Microsoft .NET Framework アセンブリです。</span><span class="sxs-lookup"><span data-stu-id="60fc2-108">A Windows PowerShell snap-in is a Microsoft .NET Framework assembly that contains Windows PowerShell providers and\/or cmdlets.</span></span> <span data-ttu-id="60fc2-109">Windows PowerShell には一連の基本的なスナップインが含まれていますが、作成したり他のユーザーから取得したプロバイダーやコマンドレットを含むスナップインを追加することで、Windows PowerShell のパワーと値を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-109">Windows PowerShell includes a set of basic snap-ins, but you can extend the power and value of Windows PowerShell by adding snap-ins that contain providers and cmdlets that you create or get from others.</span></span>

<span data-ttu-id="60fc2-110">スナップインを追加すると、そのスナップインに含まれているコマンドレットとプロバイダーは、現在のセッションですぐに使用できるようになりますが、変更は現在のセッションにのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-110">When you add a snap-in, the cmdlets and providers that it contains are immediately available for use in the current session, but the change affects only the current session.</span></span>

<span data-ttu-id="60fc2-111">今後のすべてのセッションにスナップインを追加するには、そのスナップインを Windows PowerShell プロファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-111">To add the snap-in to all future sessions, save it in your Windows PowerShell profile.</span></span> <span data-ttu-id="60fc2-112">また、Export-Console コマンドレットを使用して、スナップイン名をコンソールファイルに保存し、今後のセッションで使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-112">You can also use the Export-Console cmdlet to save the snap-in names to a console file and then use it in future sessions.</span></span> <span data-ttu-id="60fc2-113">複数のコンソールファイルを、それぞれ異なるスナップインのセットで保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-113">You can even save multiple console files, each with a different set of snap-ins.</span></span>

<span data-ttu-id="60fc2-114">注: windows powershell スナップイン (PSSnapins) は、windows PowerShell 3.0 および Windows PowerShell 2.0 で使用できます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-114">NOTE: Windows PowerShell snap-ins (PSSnapins) are available for use in Windows PowerShell 3.0 and Windows PowerShell 2.0.</span></span> <span data-ttu-id="60fc2-115">これらは、今後のバージョンで変更されたり使用できなくなったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="60fc2-115">They might be altered or unavailable in subsequent versions.</span></span> <span data-ttu-id="60fc2-116">Windows PowerShell のコマンドレットとプロバイダーをパッケージするには、モジュールを使用します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-116">To package Windows PowerShell cmdlets and providers, use modules.</span></span> <span data-ttu-id="60fc2-117">モジュールの作成と、モジュールへのスナップインの変換の詳細については、「 [Windows PowerShell モジュールの記述](/powershell/scripting/developer/module/writing-a-windows-powershell-module)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60fc2-117">For information about creating modules and converting snap-ins to modules, see [Writing a Windows PowerShell Module](/powershell/scripting/developer/module/writing-a-windows-powershell-module).</span></span>

### <a name="finding-snap-ins"></a><span data-ttu-id="60fc2-118">スナップインの検索</span><span class="sxs-lookup"><span data-stu-id="60fc2-118">FINDING SNAP-INS</span></span>

<span data-ttu-id="60fc2-119">コンピューター上の Windows PowerShell スナップインの一覧を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-119">To get a list of the  Windows PowerShell snap-ins on your computer, type:</span></span>

```powershell
Get-PSSnapin
```

<span data-ttu-id="60fc2-120">各 Windows PowerShell プロバイダーのスナップインを取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-120">To get the snap-in for each  Windows PowerShell provider, type:</span></span>

```powershell
Get-PSProvider | Format-List name, pssnapin
```

<span data-ttu-id="60fc2-121">Windows PowerShell スナップインでコマンドレットの一覧を取得するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-121">To get a list of the cmdlets in a  Windows PowerShell snap-in, type:</span></span>

```powershell
Get-Command -Module <snap-in_name>
```

### <a name="installing-a-snap-in"></a><span data-ttu-id="60fc2-122">スナップインのインストール</span><span class="sxs-lookup"><span data-stu-id="60fc2-122">INSTALLING A SNAP-IN</span></span>

<span data-ttu-id="60fc2-123">組み込みのスナップインはシステムに登録され、Windows PowerShell の起動時に既定のセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-123">The built-in snap-ins are registered in the system and added to the default session when you start Windows PowerShell.</span></span> <span data-ttu-id="60fc2-124">ただし、他のユーザーから作成または取得したスナップインを登録してから、セッションにスナップインを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60fc2-124">However, you have to register snap-ins that you create or obtain from others and then add the snap-ins to your session.</span></span>

### <a name="registering-a-snap-in"></a><span data-ttu-id="60fc2-125">スナップインの登録</span><span class="sxs-lookup"><span data-stu-id="60fc2-125">REGISTERING A SNAP-IN</span></span>

<span data-ttu-id="60fc2-126">Windows PowerShell スナップインは、.dll ファイルにコンパイルされる .NET Framework の言語で記述されたプログラムです。</span><span class="sxs-lookup"><span data-stu-id="60fc2-126">A Windows PowerShell snap-in is a program written in a .NET Framework language that is compiled into a .dll file.</span></span> <span data-ttu-id="60fc2-127">スナップインでプロバイダーとコマンドレットを使用するには、最初にスナップインを登録 (レジストリに追加) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60fc2-127">To use the providers and cmdlets in a snap-in, you must first register the snap-in (add it to the registry).</span></span>

<span data-ttu-id="60fc2-128">ほとんどのスナップインには、.dll ファイルを登録するインストールプログラム (.exe または .msi ファイル) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="60fc2-128">Most snap-ins include an installation program (an .exe or .msi file) that registers the .dll file for you.</span></span> <span data-ttu-id="60fc2-129">ただし、.dll ファイルとしてスナップインを受け取った場合は、システムに登録することができます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-129">However, if you receive a snap-in as a .dll file, you can register it on your system.</span></span> <span data-ttu-id="60fc2-130">詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60fc2-130">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>

<span data-ttu-id="60fc2-131">システムに登録されているすべてのスナップインを取得したり、スナップインが登録されていることを確認したりするには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-131">To get all the registered snap-ins on your system or to verify that a snap-in is registered, type:</span></span>

```powershell
Get-PSSnapin -registered
```

### <a name="adding-the-snap-in-to-the-current-session"></a><span data-ttu-id="60fc2-132">現在のセッションにスナップインを追加しています</span><span class="sxs-lookup"><span data-stu-id="60fc2-132">ADDING THE SNAP-IN TO THE CURRENT SESSION</span></span>

<span data-ttu-id="60fc2-133">登録されているスナップインを現在のセッションに追加するには、Add-PsSnapin コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-133">To add a registered snap-in to the current session, use the Add-PsSnapin cmdlet.</span></span> <span data-ttu-id="60fc2-134">たとえば、Microsoft SQL Server スナップインをセッションに追加するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-134">For example, to add the Microsoft SQL Server snap-in to the session, type:</span></span>

```powershell
Add-PSSnapin sql
```

<span data-ttu-id="60fc2-135">コマンドが完了すると、スナップインのプロバイダーとコマンドレットがセッションで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="60fc2-135">After the command is completed, the providers and cmdlets in the snap-in are available in the session.</span></span> <span data-ttu-id="60fc2-136">ただし、保存しない限り、現在のセッションでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-136">However, they are available only in the current session unless you save them.</span></span>

### <a name="saving-the-snap-ins"></a><span data-ttu-id="60fc2-137">スナップインを保存しています</span><span class="sxs-lookup"><span data-stu-id="60fc2-137">SAVING THE SNAP-INS</span></span>

<span data-ttu-id="60fc2-138">今後の Windows PowerShell セッションでスナップインを使用するには、Windows PowerShell プロファイルに Add-PsSnapin コマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-138">To use a snap-in in future Windows PowerShell sessions, add the Add-PsSnapin command to your Windows PowerShell profile.</span></span> <span data-ttu-id="60fc2-139">または、スナップインの名前をコンソールファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="60fc2-139">Or, export the snap-in names to a console file.</span></span>

<span data-ttu-id="60fc2-140">プロファイルに Add-PSSnapin コマンドを追加すると、それ以降のすべての Windows PowerShell セッションで使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="60fc2-140">If you add the Add-PSSnapin command to your profile, it is available in all future Windows PowerShell sessions.</span></span> <span data-ttu-id="60fc2-141">セッションでスナップインの名前をエクスポートする場合、スナップインが必要な場合にのみ、エクスポートファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-141">If you export the names of the snap-ins in your session, you can use the export file only when you need the snap-ins.</span></span>

<span data-ttu-id="60fc2-142">Windows PowerShell プロファイルに Add-PsSnapin コマンドを追加するには、プロファイルを開き、コマンドを貼り付けるか入力して、プロファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-142">To add the Add-PsSnapin command to your Windows PowerShell profile, open your profile, paste or type the command, and then save the profile.</span></span> <span data-ttu-id="60fc2-143">詳細については、「about_Profiles」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60fc2-143">For more information, see about_Profiles.</span></span>

<span data-ttu-id="60fc2-144">コンソールファイル (. .psc1) でセッションからスナップインを保存するには、Export-Console コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-144">To save the snap-ins from a session in console file (.psc1), use the Export-Console cmdlet.</span></span> <span data-ttu-id="60fc2-145">たとえば、現在のセッション構成のスナップインを現在のディレクトリの .psc1 ファイルに保存するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-145">For example, to save the snap-ins in the current session configuration to the NewConsole.psc1 file in the current directory, type:</span></span>

```powershell
Export-Console NewConsole
```

<span data-ttu-id="60fc2-146">詳細については、「Export-Console」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60fc2-146">For more information, see Export-Console.</span></span>

### <a name="opening-windows-powershell-with-a-console-file"></a><span data-ttu-id="60fc2-147">コンソールファイルを使用して WINDOWS POWERSHELL を開く</span><span class="sxs-lookup"><span data-stu-id="60fc2-147">OPENING WINDOWS POWERSHELL WITH A CONSOLE FILE</span></span>

<span data-ttu-id="60fc2-148">スナップインを含むコンソールファイルを使用するには、Cmd.exe または別の Windows PowerShell セッションでコマンドプロンプトから Windows PowerShell (PowerShell.exe) を起動します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-148">To use a console file that includes the snap-in, start Windows PowerShell (PowerShell.exe) from the command prompt in Cmd.exe or in another Windows PowerShell session.</span></span> <span data-ttu-id="60fc2-149">PsConsoleFile パラメーターを使用して、スナップインを含むコンソールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-149">Use the PsConsoleFile parameter to specify the console file that includes the snap-in.</span></span> <span data-ttu-id="60fc2-150">たとえば、次のコマンドは、.psc1 コンソールファイルを使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-150">For example, the following command starts Windows PowerShell with the NewConsole.psc1 console file:</span></span>

```powershell
PowerShell.exe -psconsolefile NewConsole.psc1
```

<span data-ttu-id="60fc2-151">スナップインのプロバイダーとコマンドレットが、セッションで使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="60fc2-151">The providers and cmdlets in the snapin are now available for use in the session.</span></span>

### <a name="removing-a-snap-in"></a><span data-ttu-id="60fc2-152">スナップインの削除</span><span class="sxs-lookup"><span data-stu-id="60fc2-152">REMOVING A SNAP-IN</span></span>

<span data-ttu-id="60fc2-153">現在のセッションから Windows PowerShell スナップインを削除するには、Remove-PsSnapin コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-153">To remove a Windows PowerShell snap-in from the current session, use the Remove-PsSnapin cmdlet.</span></span> <span data-ttu-id="60fc2-154">たとえば、現在のセッションから SQL Server スナップインを削除するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-154">For example, to remove the SQL Server snap-in from the current session, type:</span></span>

```powershell
Remove-PSSnapin sql
```

<span data-ttu-id="60fc2-155">このコマンドレットは、セッションからスナップインを削除します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-155">This cmdlet removes the snap-in from the session.</span></span> <span data-ttu-id="60fc2-156">スナップインはまだ読み込まれていますが、サポートされているプロバイダーとコマンドレットは使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="60fc2-156">The snap-in is still loaded, but the providers and cmdlets that it supports are no longer available.</span></span>

### <a name="built-in-commands"></a><span data-ttu-id="60fc2-157">組み込みコマンド</span><span class="sxs-lookup"><span data-stu-id="60fc2-157">BUILT-IN COMMANDS</span></span>

<span data-ttu-id="60fc2-158">Windows powershell 2.0 および windows PowerShell 3.0 以降の古いスタイルのホストプログラムでは、Windows PowerShell と共にインストールされる組み込みのコマンドは、すべての Windows PowerShell セッションに自動的に追加されるスナップインにパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-158">In Windows PowerShell 2.0 and in older-style host programs in Windows PowerShell 3.0 and later, the built-in commands that are installed with Windows PowerShell are packaged in snap-ins that are added automatically to every Windows PowerShell session.</span></span>

<span data-ttu-id="60fc2-159">Windows PowerShell 3.0 以降では、新しいスタイルのホストプログラム (InitialSessionState. CreateDefault2 メソッドを使用してセッションを開始するもの) が含まれています。組み込みのコマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="60fc2-159">Beginning in Windows PowerShell 3.0, in newer-style host programs -- those that start sessions by using the InitialSessionState.CreateDefault2 method -- the built-in commands are packaged in modules.</span></span> <span data-ttu-id="60fc2-160">例外は、常にスナップインとして表示される、PowerShell です。</span><span class="sxs-lookup"><span data-stu-id="60fc2-160">The exception is Microsoft.PowerShell.Core, which always appears as a snap-in.</span></span> <span data-ttu-id="60fc2-161">コアスナップインは、既定ではすべてのセッションに含まれています。</span><span class="sxs-lookup"><span data-stu-id="60fc2-161">The Core snap-in is included in every session by default.</span></span> <span data-ttu-id="60fc2-162">組み込みモジュールは、初回使用時に自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-162">The built-in modules are loaded automatically on first-use.</span></span>

<span data-ttu-id="60fc2-163">注: New-PSSession コマンドレットを使用して開始されたセッションを含めたリモートセッションは、組み込みコマンドがスナップインにパッケージ化されている古い形式のセッションです。</span><span class="sxs-lookup"><span data-stu-id="60fc2-163">NOTE: Remote sessions, including sessions that are started by using the New-PSSession cmdlet, are older-style sessions in which the built-in commands are packaged in snap-ins.</span></span>

<span data-ttu-id="60fc2-164">次のスナップイン (モジュール) は、Windows PowerShell と共にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-164">The following snap-ins (or modules) are installed with Windows PowerShell.</span></span>

- <span data-ttu-id="60fc2-165">Microsoft. PowerShell-Windows PowerShell の基本機能の管理に使用するプロバイダーとコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="60fc2-165">Microsoft.PowerShell.Core - Contains providers and cmdlets used to manage the basic features of Windows PowerShell.</span></span> <span data-ttu-id="60fc2-166">これには、FileSystem、Registry、Alias、Environment、Function、および Variable プロバイダーと、Get-help、Get-Command、および Get-help などの基本的なコマンドレットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-166">It includes the FileSystem, Registry, Alias, Environment, Function, and Variable providers and basic cmdlets like Get-Help, Get-Command, and Get-History.</span></span>

- <span data-ttu-id="60fc2-167">Microsoft. PowerShell-Windows PowerShell ホストによって使用されるコマンドレットが含まれています。たとえば、Start-Transcript や、トランスクリプトを停止します。</span><span class="sxs-lookup"><span data-stu-id="60fc2-167">Microsoft.PowerShell.Host - Contains cmdlets used by the Windows PowerShell host, such as Start-Transcript and Stop-Transcript.</span></span>

- <span data-ttu-id="60fc2-168">Microsoft. PowerShell. 管理-Windows ベースの機能の管理に使用される Get-Service や Get-ChildItem などのコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="60fc2-168">Microsoft.PowerShell.Management - Contains cmdlets such as Get-Service and Get-ChildItem that are used to manage Windows-based features.</span></span>

- <span data-ttu-id="60fc2-169">Get-authenticodesignature-Windows PowerShell のセキュリティを管理するために使用される証明書プロバイダーとコマンドレットが含まれています。たとえば、Get Acl、Convertto-html、SecureString などです。</span><span class="sxs-lookup"><span data-stu-id="60fc2-169">Microsoft.PowerShell.Security - Contains the Certificate provider and cmdlets used to manage Windows PowerShell security, such as Get-Acl, Get-AuthenticodeSignature, and ConvertTo-SecureString.</span></span>

- <span data-ttu-id="60fc2-170">Microsoft. PowerShell: オブジェクトとデータを操作するために使用するコマンドレットが含まれています (Get Member、Write Host、Format List など)。</span><span class="sxs-lookup"><span data-stu-id="60fc2-170">Microsoft.PowerShell.Utility - Contains cmdlets used to manipulate objects and data, such as Get-Member, Write-Host, and Format-List.</span></span>

- <span data-ttu-id="60fc2-171">Enable-wsmancredssp-Connect-WSMan やなど、Windows リモート管理サービスを管理する WSMan プロバイダーとコマンドレットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="60fc2-171">Microsoft.WSMan.Management - Contains the WSMan provider and cmdlets that manage the Windows Remote Management service, such as Connect-WSMan and Enable-WSManCredSSP.</span></span>

## <a name="logging-snap-in-events"></a><span data-ttu-id="60fc2-172">スナップインイベントのログ記録</span><span class="sxs-lookup"><span data-stu-id="60fc2-172">LOGGING SNAP-IN EVENTS</span></span>

<span data-ttu-id="60fc2-173">Windows PowerShell 3.0 以降では、モジュールの LogPipelineExecutionDetails プロパティを TRUE に設定することにより、Windows PowerShell モジュールおよびスナップインでコマンドレットの実行イベントを記録できます。</span><span class="sxs-lookup"><span data-stu-id="60fc2-173">Beginning in Windows PowerShell 3.0, you can record execution events for the cmdlets in Windows PowerShell modules and snap-ins by setting the LogPipelineExecutionDetails property of modules and snap-ins to TRUE.</span></span> <span data-ttu-id="60fc2-174">詳細については、「 [about_EventLogs](about_EventLogs.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60fc2-174">For more information, see [about_EventLogs](about_EventLogs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60fc2-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="60fc2-175">SEE ALSO</span></span>

[<span data-ttu-id="60fc2-176">Add-pssnapin</span><span class="sxs-lookup"><span data-stu-id="60fc2-176">Add-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Add-PSSnapin)

[<span data-ttu-id="60fc2-177">Add-pssnapin</span><span class="sxs-lookup"><span data-stu-id="60fc2-177">Get-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSnapin)

[<span data-ttu-id="60fc2-178">Add-pssnapin</span><span class="sxs-lookup"><span data-stu-id="60fc2-178">Remove-PsSnapin</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSnapin)

[<span data-ttu-id="60fc2-179">Export-Console</span><span class="sxs-lookup"><span data-stu-id="60fc2-179">Export-Console</span></span>](xref:Microsoft.PowerShell.Core.Export-Console)

[<span data-ttu-id="60fc2-180">Get-Command</span><span class="sxs-lookup"><span data-stu-id="60fc2-180">Get-Command</span></span>](xref:Microsoft.PowerShell.Core.Get-Command)

[<span data-ttu-id="60fc2-181">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="60fc2-181">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="60fc2-182">about_Modules</span><span class="sxs-lookup"><span data-stu-id="60fc2-182">about_Modules</span></span>](about_Modules.md)

## <a name="keywords"></a><span data-ttu-id="60fc2-183">KEYWORDS</span><span class="sxs-lookup"><span data-stu-id="60fc2-183">KEYWORDS</span></span>

<span data-ttu-id="60fc2-184">about_Snapins、about_Snap_ins、about_Snap</span><span class="sxs-lookup"><span data-stu-id="60fc2-184">about_Snapins, about_Snap_ins, about_Snap-ins</span></span>
