---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/add-pssnapin?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Add-PSSnapin
ms.openlocfilehash: 5adba912d91369250ee9891ee2bb2ca0f8cba796
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212123"
---
# <span data-ttu-id="5d63c-103">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="5d63c-103">Add-PSSnapin</span></span>

## <span data-ttu-id="5d63c-104">概要</span><span class="sxs-lookup"><span data-stu-id="5d63c-104">SYNOPSIS</span></span>
<span data-ttu-id="5d63c-105">現在のセッションに 1 つまたは複数の Windows PowerShell スナップインを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-105">Adds one or more Windows PowerShell snap-ins to the current session.</span></span>

## <span data-ttu-id="5d63c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5d63c-106">SYNTAX</span></span>

```
Add-PSSnapin [-Name] <String[]> [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="5d63c-107">Description</span><span class="sxs-lookup"><span data-stu-id="5d63c-107">DESCRIPTION</span></span>

<span data-ttu-id="5d63c-108">コマンドレットでは、 `Add-PSSnapin` 登録済みの Windows PowerShell スナップインを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-108">The `Add-PSSnapin` cmdlet adds registered Windows PowerShell snap-ins to the current session.</span></span> <span data-ttu-id="5d63c-109">スナップインを追加した後、スナップインが現在のセッションでサポートするコマンドレットとプロバイダーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-109">After the snap-ins are added, you can use the cmdlets and providers that the snap-ins support in the current session.</span></span>

<span data-ttu-id="5d63c-110">今後のすべての Windows PowerShell セッションにスナップインを追加するには、 `Add-PSSnapin` Windows powershell プロファイルにコマンドを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-110">To add the snap-in to all future Windows PowerShell sessions, add an `Add-PSSnapin` command to your Windows PowerShell profile.</span></span> <span data-ttu-id="5d63c-111">詳細については、「 [about_Profiles](about/about_Profiles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d63c-111">For more information, see [about_Profiles](about/about_Profiles.md).</span></span>

<span data-ttu-id="5d63c-112">Windows PowerShell 3.0 以降、Windows PowerShell に含まれているコア コマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="5d63c-112">Beginning in Windows PowerShell 3.0, the core commands that are included in Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="5d63c-113">例外は、スナップイン (PSSnapin) の **Microsoft.PowerShell.Core** です。</span><span class="sxs-lookup"><span data-stu-id="5d63c-113">The exception is **Microsoft.PowerShell.Core** , which is a snap-in (PSSnapin).</span></span>
<span data-ttu-id="5d63c-114">既定では、 **Microsoft.PowerShell.Core** スナップインのみがセッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-114">By default, only the **Microsoft.PowerShell.Core** snap-in is added to the session.</span></span> <span data-ttu-id="5d63c-115">モジュールは初回使用時に自動的にインポートされ、Import-Module コマンドレットを使用してインポートできます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-115">Modules are imported automatically on first use and you can use the Import-Module cmdlet to import them.</span></span>

## <span data-ttu-id="5d63c-116">例</span><span class="sxs-lookup"><span data-stu-id="5d63c-116">EXAMPLES</span></span>

### <span data-ttu-id="5d63c-117">例 1: スナップインを追加する</span><span class="sxs-lookup"><span data-stu-id="5d63c-117">Example 1: Add snap-ins</span></span>

```powershell
PS C:\> Add-PSSnapIn -Name Microsoft.Exchange, Microsoft.Windows.AD
```

<span data-ttu-id="5d63c-118">このコマンドは、現在のセッションに、Microsoft Exchange と Active Directory のスナップインを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-118">This command adds the Microsoft Exchange and Active Directory snap-ins to the current session.</span></span>

### <span data-ttu-id="5d63c-119">例 2: 登録されているすべてのスナップインを追加する</span><span class="sxs-lookup"><span data-stu-id="5d63c-119">Example 2: Add all the registered snap-ins</span></span>

```powershell
PS C:\> Get-PSSnapin -Registered | Add-PSSnapin -Passthru
```

<span data-ttu-id="5d63c-120">このコマンドは、セッションにすべての登録済み Windows PowerShell スナップインを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-120">This command adds all of the registered Windows PowerShell snap-ins to the session.</span></span> <span data-ttu-id="5d63c-121">また **、登録済みのパラメーターと** 共に Get-PSSnapin コマンドレットを使用して、登録された各スナップインを表すオブジェクトを取得します。パイプライン演算子 (|) により、結果がに渡され `Add-PSSnapin` 、セッションに追加されます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-121">It uses the Get-PSSnapin cmdlet with the **Registered** parameter to get objects representing each of the registered snap-ins. The pipeline operator (|) passes the result to `Add-PSSnapin`, which adds them to the session.</span></span> <span data-ttu-id="5d63c-122">**PassThru** パラメーターは、追加された各スナップインを表すオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-122">The **PassThru** parameter returns objects that represent each of the added snap-ins.</span></span>

### <span data-ttu-id="5d63c-123">例 3: スナップインを登録して追加する</span><span class="sxs-lookup"><span data-stu-id="5d63c-123">Example 3: Register a snap-in and add it</span></span>

<span data-ttu-id="5d63c-124">最初のコマンドは、Windows PowerShell でインストールされたスナップインを含む現在のセッションに追加されているスナップインを取得します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-124">The first command gets snap-ins that have been added to the current session that include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="5d63c-125">この例では、ManagementFeatures は返されません。</span><span class="sxs-lookup"><span data-stu-id="5d63c-125">In this example, ManagementFeatures is not returned.</span></span> <span data-ttu-id="5d63c-126">これは、セッションに追加されていないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="5d63c-126">This indicates that it has not been added to the session.</span></span>

<span data-ttu-id="5d63c-127">2番目のコマンドは、既にセッションに追加されているスナップインを含む、システムに登録されているスナップインを取得します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-127">The second command gets snap-ins that have been registered on your system, which includes those that have already been added to the session.</span></span> <span data-ttu-id="5d63c-128">Windows PowerShell と共にインストールされるスナップインは含まれません。</span><span class="sxs-lookup"><span data-stu-id="5d63c-128">It does not include the snap-ins that are installed with Windows PowerShell.</span></span> <span data-ttu-id="5d63c-129">この場合、コマンドはスナップインを返しません。これは、ManagementFeatures スナップインがシステムに登録されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-129">In this case, the command does not return any snap-ins. This indicates that the ManagementFeatures snapin has not been registered on the system.</span></span>

<span data-ttu-id="5d63c-130">3番目のコマンドは、.NET Framework の Installutil.exe ツールのパスに対して、installutil.exe というエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-130">The third command creates an alias, installutil, for the path of the InstallUtil tool in .NET Framework.</span></span>

<span data-ttu-id="5d63c-131">4番目のコマンドは、Installutil.exe ツールを使用してスナップインを登録します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-131">The fourth command uses the InstallUtil tool to register the snap-in.</span></span> <span data-ttu-id="5d63c-132">このコマンドでは、スナップインの ManagementCmdlets.dll のパス、ファイル名、またはモジュール名を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-132">The command specifies the path of ManagementCmdlets.dll, the filename or module name of the snap-in.</span></span>

<span data-ttu-id="5d63c-133">5 番目のコマンドは、2 番目のコマンドと同じです。</span><span class="sxs-lookup"><span data-stu-id="5d63c-133">The fifth command is the same as the second command.</span></span> <span data-ttu-id="5d63c-134">今度は、それを使用して ManagementCmdlets スナップインが登録されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-134">This time, you use it to verify that the ManagementCmdlets snap-in is registered.</span></span>

<span data-ttu-id="5d63c-135">6番目のコマンドは、コマンドレットを使用して、 `Add-PSSnapin` ManagementFeatures スナップインをセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-135">The sixth command uses the `Add-PSSnapin` cmdlet to add the ManagementFeatures snap-in to the session.</span></span> <span data-ttu-id="5d63c-136">これは、ファイル名ではなく、スナップインの名前、ManagementFeatures を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-136">It specifies the name of the snap-in, ManagementFeatures, not the file name.</span></span>

<span data-ttu-id="5d63c-137">スナップインがセッションに追加されたことを確認するために、7番目のコマンドは、Get-Command コマンドレットの **Module** パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-137">To verify that the snap-in is added to the session, the seventh command uses the **Module** parameter of the Get-Command cmdlet.</span></span> <span data-ttu-id="5d63c-138">スナップインまたはモジュールによってセッションに追加された項目が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-138">It displays the items that were added to the session by a snap-in or module.</span></span>

<span data-ttu-id="5d63c-139">コマンドレットが返すオブジェクトの **add-pssnapin** プロパティを使用して、コマンドレットが生成された `Get-Command` スナップインまたはモジュールを検索することもできます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-139">You can also use the **PSSnapin** property of the object that the `Get-Command` cmdlet returns to find the snap-in or module in which a cmdlet originated.</span></span> <span data-ttu-id="5d63c-140">8番目のコマンドは、ドット表記を使用して Set-Alias コマンドレットの Add-pssnapin プロパティの値を検索します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-140">The eighth command uses dot notation to find the value of the PSSnapin property of the Set-Alias cmdlet.</span></span>

```powershell
PS C:\> Get-PSSnapin
PS C:\> Get-PSSnapin -Registered
PS C:\> Set-Alias installutil $env:windir\Microsoft.NET\Framework\v2.0.50727\installutil.exe
PS C:\> installutil C:\Dev\Management\ManagementCmdlets.dll
PS C:\> Get-PSSnapin -Registered
PS C:\> add-pssnapin ManagementFeatures
PS C:\> Get-Command -Module ManagementFeatures
PS C:\> (Get-Command Set-Alias).pssnapin
```

<span data-ttu-id="5d63c-141">この例では、スナップインをシステムに登録し、さらにセッションに追加するプロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-141">This example demonstrates the process of registering a snap-in on your system and then adding it to your session.</span></span> <span data-ttu-id="5d63c-142">ManagementFeatures を使用します。これは、ManagementCmdlets.dll という名前のファイルで実装された架空のスナップインです。</span><span class="sxs-lookup"><span data-stu-id="5d63c-142">It uses ManagementFeatures, a fictitious snap-in implemented in a file that is named ManagementCmdlets.dll.</span></span>

## <span data-ttu-id="5d63c-143">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5d63c-143">PARAMETERS</span></span>

### <span data-ttu-id="5d63c-144">-Name</span><span class="sxs-lookup"><span data-stu-id="5d63c-144">-Name</span></span>

<span data-ttu-id="5d63c-145">スナップインの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-145">Specifies the name of the snap-in.</span></span> <span data-ttu-id="5d63c-146">これは、AssemblyName や ModuleName ではなく、名前です。</span><span class="sxs-lookup"><span data-stu-id="5d63c-146">This is the Name, not the AssemblyName or ModuleName.</span></span> <span data-ttu-id="5d63c-147">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-147">Wildcards are permitted.</span></span>

<span data-ttu-id="5d63c-148">システムに登録されているスナップインの名前を確認するには、「」と入力 `Get-PSSnapin -Registered` します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-148">To find the names of the registered snap-ins on your system, type `Get-PSSnapin -Registered`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="5d63c-149">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5d63c-149">-PassThru</span></span>

<span data-ttu-id="5d63c-150">このコマンドレットが、追加された各スナップインを表すオブジェクトを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-150">Indicates that this cmdlet returns an object that represents each added snap-in.</span></span> <span data-ttu-id="5d63c-151">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="5d63c-151">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5d63c-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5d63c-152">CommonParameters</span></span>

<span data-ttu-id="5d63c-153">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5d63c-153">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5d63c-154">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d63c-154">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5d63c-155">入力</span><span class="sxs-lookup"><span data-stu-id="5d63c-155">INPUTS</span></span>

### <span data-ttu-id="5d63c-156">なし</span><span class="sxs-lookup"><span data-stu-id="5d63c-156">None</span></span>
<span data-ttu-id="5d63c-157">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="5d63c-157">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="5d63c-158">出力</span><span class="sxs-lookup"><span data-stu-id="5d63c-158">OUTPUTS</span></span>

### <span data-ttu-id="5d63c-159">なしまたはシステムの管理. PSSnapInInfo</span><span class="sxs-lookup"><span data-stu-id="5d63c-159">None or System.Management.Automation.PSSnapInInfo</span></span>

<span data-ttu-id="5d63c-160">このコマンドレットは、 **PassThru** パラメーターを指定した場合に、スナップインを表す PSSnapInInfo オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-160">This cmdlet returns a PSSnapInInfo object that represents the snap-in if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="5d63c-161">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="5d63c-161">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="5d63c-162">注</span><span class="sxs-lookup"><span data-stu-id="5d63c-162">NOTES</span></span>

* <span data-ttu-id="5d63c-163">Windows PowerShell 3.0 以降、Windows PowerShell と共にインストールされるコア コマンドはモジュールにパッケージ化されています。</span><span class="sxs-lookup"><span data-stu-id="5d63c-163">Beginning in Windows PowerShell 3.0, the core commands that are installed with Windows PowerShell are packaged in modules.</span></span> <span data-ttu-id="5d63c-164">Windows PowerShell 2.0、およびそれ以降のバージョンの Windows PowerShell で古いスタイルのセッションを作成するホストプログラムでは、コアコマンドはスナップイン (PSSnapins) にパッケージ化されます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-164">In Windows PowerShell 2.0, and in host programs that create older-style sessions in later versions of Windows PowerShell, the core commands are packaged in snap-ins (PSSnapins).</span></span> <span data-ttu-id="5d63c-165">例外は、常にスナップインである、 **PowerShell です** 。</span><span class="sxs-lookup"><span data-stu-id="5d63c-165">The exception is **Microsoft.PowerShell.Core** , which is always a snap-in.</span></span> <span data-ttu-id="5d63c-166">また、New-PSSession コマンドレットによって開始されたリモートセッションは、コアスナップインを含む古い形式のセッションです。</span><span class="sxs-lookup"><span data-stu-id="5d63c-166">Also, remote sessions, such as those started by the New-PSSession cmdlet, are older-style sessions that include core snap-ins.</span></span>

  <span data-ttu-id="5d63c-167">コアモジュールで新しいスタイルのセッションを作成する **CreateDefault2** メソッドの詳細については、MSDN ライブラリの「 [CreateDefault2 メソッド](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d63c-167">For information about the **CreateDefault2** method that creates newer-style sessions with core modules, see [CreateDefault2 Method](https://msdn.microsoft.com/library/system.management.automation.runspaces.initialsessionstate.createdefault2) in the MSDN library.</span></span>

* <span data-ttu-id="5d63c-168">スナップインの詳細については、「 [about_PSSnapins](About/about_PSSnapins.md) 」および「 [Windows PowerShell スナップインを作成する方法](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d63c-168">For more information about snap-ins, see [about_PSSnapins](About/about_PSSnapins.md) and [How to Create a Windows PowerShell Snap-in](/powershell/scripting/developer/cmdlet/how-to-create-a-windows-powershell-snap-in).</span></span>
* <span data-ttu-id="5d63c-169">`Add-PSSnapin` 現在のセッションにのみ、スナップインを追加します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-169">`Add-PSSnapin` adds the snap-in only to the current session.</span></span> <span data-ttu-id="5d63c-170">スナップインをすべての Windows PowerShell セッションに追加するには、そのスナップインを Windows PowerShell プロファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-170">To add the snap-in to all Windows PowerShell sessions, add it to your Windows PowerShell profile.</span></span> <span data-ttu-id="5d63c-171">詳細については、「about_Profiles」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d63c-171">For more information, see about_Profiles.</span></span>
* <span data-ttu-id="5d63c-172">Microsoft .NET Framework インストールユーティリティを使用して登録されたスナップインを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5d63c-172">You can add any snap-in that has been registered using the Microsoft .NET Framework install utility.</span></span> <span data-ttu-id="5d63c-173">詳細については、「 [コマンドレット、プロバイダー、およびホストアプリケーションを登録する方法](/previous-versions//ms714644(v=vs.85))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d63c-173">For more information, see [How to Register Cmdlets, Providers, and Host Applications](/previous-versions//ms714644(v=vs.85)).</span></span>
* <span data-ttu-id="5d63c-174">コンピューターに登録されているスナップインの一覧を取得するには、「」と入力 `Get-PSSnapin -Registered` します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-174">To get a list of snap-ins that are registered on your computer, type `Get-PSSnapin -Registered`.</span></span>
* <span data-ttu-id="5d63c-175">スナップインを追加する前に、スナップインのバージョンを確認して、 `Add-PSSnapin` 現在のバージョンの Windows PowerShell と互換性があることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-175">Before adding a snap-in, `Add-PSSnapin` checks the version of the snap-in to verify that it is compatible with the current version of Windows PowerShell.</span></span> <span data-ttu-id="5d63c-176">スナップインがバージョン チェックに失敗した場合、Windows PowerShell はエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="5d63c-176">If the snap-in fails the version check, Windows PowerShell reports an error.</span></span>

## <span data-ttu-id="5d63c-177">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5d63c-177">RELATED LINKS</span></span>

[<span data-ttu-id="5d63c-178">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="5d63c-178">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="5d63c-179">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="5d63c-179">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
