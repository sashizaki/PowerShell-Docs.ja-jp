---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/export-console?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Export-Console
ms.openlocfilehash: 7b643b5f9b6868a5da988b19b65dead24f986f67
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212059"
---
# <span data-ttu-id="79613-103">Export-Console</span><span class="sxs-lookup"><span data-stu-id="79613-103">Export-Console</span></span>

## <span data-ttu-id="79613-104">概要</span><span class="sxs-lookup"><span data-stu-id="79613-104">SYNOPSIS</span></span>
<span data-ttu-id="79613-105">現在のセッションのスナップインの名前をコンソール ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="79613-105">Exports the names of snap-ins in the current session to a console file.</span></span>

## <span data-ttu-id="79613-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="79613-106">SYNTAX</span></span>

```
Export-Console [[-Path] <String>] [-Force] [-NoClobber] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="79613-107">Description</span><span class="sxs-lookup"><span data-stu-id="79613-107">DESCRIPTION</span></span>
<span data-ttu-id="79613-108">**Export console** コマンドレットは、現在のセッションの windows powershell スナップインの名前を windows powershell コンソールファイル (. .psc1) にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="79613-108">The **Export-Console** cmdlet exports the names of the Windows PowerShell snap-ins in the current session to a Windows PowerShell console file (.psc1).</span></span>
<span data-ttu-id="79613-109">このコマンドレットを使用すると、将来のセッションで使用するためにスナップインを保存できます。</span><span class="sxs-lookup"><span data-stu-id="79613-109">You can use this cmdlet to save the snap-ins for use in future sessions.</span></span>

<span data-ttu-id="79613-110">.Psc1 コンソールファイルのスナップインをセッションに追加するには、コマンドラインで Cmd.exe または別の Windows PowerShell セッションを使用して Windows PowerShell (Powershell.exe) を起動し、Powershell.exe の *Psconsolefile* パラメーターを使用してコンソールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="79613-110">To add the snap-ins in the .psc1 console file to a session, start Windows PowerShell (Powershell.exe) at the command line by using Cmd.exe or another Windows PowerShell session, and then use the *PSConsoleFile* parameter of Powershell.exe to specify the console file.</span></span>

<span data-ttu-id="79613-111">Windows PowerShell スナップインの詳細については、「about_PSSnapins」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79613-111">For more information about Windows PowerShell snap-ins, see about_PSSnapins.</span></span>

## <span data-ttu-id="79613-112">例</span><span class="sxs-lookup"><span data-stu-id="79613-112">EXAMPLES</span></span>

### <span data-ttu-id="79613-113">例 1: 現在のセッションでスナップインの名前をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="79613-113">Example 1: Export the names of snap-ins in the current session</span></span>

```
PS C:\> Export-Console -Path $pshome\Consoles\ConsoleS1.psc1
```

<span data-ttu-id="79613-114">このコマンドを実行すると、現在のセッションの Windows PowerShell スナップインの名前が、Windows PowerShell インストールフォルダー $pshome の [コンソール] フォルダーの Consoles1.psc1 ファイルにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="79613-114">This command exports the names of Windows PowerShell snap-ins in the current session to the ConsoleS1.psc1 file in the Consoles folder of the Windows PowerShell installation folder, $pshome.</span></span>

### <span data-ttu-id="79613-115">例 2: 最新のコンソールファイルにスナップインの名前をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="79613-115">Example 2: Export the names of snap-ins to the most recent console file</span></span>

```
PS C:\> Export-Console
```

<span data-ttu-id="79613-116">このコマンドは、Windows PowerShell スナップインの名前を、現在のセッションから、現在のセッションで最近使用された Windows PowerShell コンソール ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="79613-116">This command exports the names of Windows PowerShell snap-ins from current session to the Windows PowerShell console file that was most recently used in the current session.</span></span>
<span data-ttu-id="79613-117">前のファイルの内容は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="79613-117">It overwrites the previous file contents.</span></span>

<span data-ttu-id="79613-118">現在のセッション中に、コンソール ファイルをエクスポートしていない場合は、続行するためのアクセス許可の入力が求められ、その後、ファイル名の入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="79613-118">If you have not exported a console file during the current session, you are prompted for permission to continue and then prompted for a file name.</span></span>

### <span data-ttu-id="79613-119">例 3: スナップインを追加し、スナップインの名前をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="79613-119">Example 3: Add a snap-in and export the names of snap-ins</span></span>

```
PS C:\> Add-PSSnapin NewPSSnapin
PS C:\> Export-Console -path NewPSSnapinConsole.psc1
PS C:\> powershell.exe -PsConsoleFile NewPsSnapinConsole.psc1
```

<span data-ttu-id="79613-120">これらのコマンドは、NewPSSnapin Windows PowerShell スナップインを現在のセッションに追加し、現在のセッションの Windows PowerShell スナップインの名前をコンソール ファイルにエクスポートして、コンソール ファイルで Windows PowerShell セッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="79613-120">These commands add the NewPSSnapin Windows PowerShell snap-in to the current session, export the names of Windows PowerShell snap-ins in the current session to a console file, and then start a Windows PowerShell session with the console file.</span></span>

<span data-ttu-id="79613-121">最初のコマンドは、 **add-pssnapin** コマンドレットを使用して、NewPSSnapin スナップインを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="79613-121">The first command uses the **Add-PSSnapin** cmdlet to add the NewPSSnapin snap-in to the current session.</span></span>
<span data-ttu-id="79613-122">システムに登録されている Windows PowerShell スナップインのみを追加できます。</span><span class="sxs-lookup"><span data-stu-id="79613-122">You can only add Windows PowerShell snap-ins that are registered on your system.</span></span>

<span data-ttu-id="79613-123">2 番目のコマンドは、Windows PowerShell スナップインの名前を NewPSSnapinConsole.psc1 ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="79613-123">The second command exports the Windows PowerShell snap-in names to the NewPSSnapinConsole.psc1 file.</span></span>

<span data-ttu-id="79613-124">3 番目のコマンドは、NewPSSnapinConsole.psc1 ファイルを使用して、Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="79613-124">The third command starts Windows PowerShell with the NewPSSnapinConsole.psc1 file.</span></span>
<span data-ttu-id="79613-125">コンソール ファイルには Windows PowerShell スナップインの名前が含まれるため、スナップイン内のコマンドレットとプロバイダーを現在のセッションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="79613-125">Because the console file includes the Windows PowerShell snap-in name, the cmdlets and providers in the snap-in are available in the current session.</span></span>

### <span data-ttu-id="79613-126">例 4: スナップインの名前を指定した場所にエクスポートする</span><span class="sxs-lookup"><span data-stu-id="79613-126">Example 4: Export names of snap-ins to a specified location</span></span>

```
PS C:\> export-console -path Console01
PS C:\> notepad console01.psc1
<?xml version="1.0" encoding="utf-8"?>
<PSConsoleFile ConsoleSchemaVersion="1.0">
  <PSVersion>2.0</PSVersion>
  <PSSnapIns>
     <PSSnapIn Name="NewPSSnapin" />
  </PSSnapIns>
</PSConsoleFile>
```

<span data-ttu-id="79613-127">このコマンドは、現在のセッションの Windows PowerShell スナップインの名前を、現在のディレクトリ内の Console01.psc1 ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="79613-127">This command exports the names of the Windows PowerShell snap-ins in the current session to the Console01.psc1 file in the current directory.</span></span>

<span data-ttu-id="79613-128">2 番目のコマンドは、メモ帳で、Console01.psc1 ファイルの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="79613-128">The second command displays the contents of the Console01.psc1 file in Notepad.</span></span>

### <span data-ttu-id="79613-129">例 5: 更新するコンソールファイルを決定する</span><span class="sxs-lookup"><span data-stu-id="79613-129">Example 5: Determine the console file to update</span></span>

```
PS C:\> powershell.exe -PSConsoleFile Console01.psc1
PS C:\> Add-PSSnapin MySnapin
PS C:\> Export-Console NewConsole.psc1
PS C:\> $ConsoleFileName
PS C:\> Add-PSSnapin SnapIn03
PS C:\> Export-Console
```

<span data-ttu-id="79613-130">この例では、$ConsoleFileName の自動変数を使用して、 *Path* パラメーター値を指定せずに **エクスポートコンソール** を使用する場合に更新されるコンソールファイルを決定する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="79613-130">This example shows how to use the $ConsoleFileName automatic variable to determine the console file that will be updated if you use **Export-Console** without a *Path* parameter value.</span></span>

<span data-ttu-id="79613-131">最初のコマンドは、PowerShell.exe の *Psconsolefile* パラメーターを使用して、.psc1 ファイルと共に Windows PowerShell を開きます。</span><span class="sxs-lookup"><span data-stu-id="79613-131">The first command uses the *PSConsoleFile* parameter of PowerShell.exe to open Windows PowerShell with the Console01.psc1 file.</span></span>

<span data-ttu-id="79613-132">2番目のコマンドは、 **add-pssnapin** コマンドレットを使用して、Mysnapin イン Windows PowerShell スナップインを現在のセッションに追加します。</span><span class="sxs-lookup"><span data-stu-id="79613-132">The second command uses the **Add-PSSnapin** cmdlet to add the MySnapin Windows PowerShell snap-in to the current session.</span></span>

<span data-ttu-id="79613-133">3番目のコマンドは、 **Export-console** コマンドレットを使用して、セッション内のすべての Windows PowerShell スナップインの名前を newconsole ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="79613-133">The third command uses the **Export-Console** cmdlet to export the names of all the Windows PowerShell snap-ins in the session to the NewConsole.psc1 file.</span></span>

<span data-ttu-id="79613-134">4番目のコマンドは、$ConsoleFileName 変数を表示します。</span><span class="sxs-lookup"><span data-stu-id="79613-134">The fourth command displays the $ConsoleFileName variable.</span></span>
<span data-ttu-id="79613-135">これには、最近使用したコンソールファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="79613-135">It contains the most recently used console file.</span></span>
<span data-ttu-id="79613-136">サンプル出力は NewConsole.ps1 が最近使用されたファイルであることを示しています。</span><span class="sxs-lookup"><span data-stu-id="79613-136">The sample output shows that NewConsole.ps1 is the most recently used file.</span></span>

<span data-ttu-id="79613-137">5 番目のコマンドは、SnapIn03 を現在のコンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="79613-137">The fifth command adds SnapIn03 to the current console.</span></span>

<span data-ttu-id="79613-138">6番目のコマンドは、 *Path* パラメーターを指定せずに、 **Export Console** コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="79613-138">The sixth command uses the **Export-Console** cmdlet without a *Path* parameter.</span></span>
<span data-ttu-id="79613-139">このコマンドは、現在のセッションのすべての Windows PowerShell スナップインの名前を最近使用されたファイルである NewConsole.psc1 にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="79613-139">This command exports the names of all the Windows PowerShell snap-ins in the current session to the most recently used file, NewConsole.psc1.</span></span>

## <span data-ttu-id="79613-140">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="79613-140">PARAMETERS</span></span>

### <span data-ttu-id="79613-141">-Force</span><span class="sxs-lookup"><span data-stu-id="79613-141">-Force</span></span>
<span data-ttu-id="79613-142">ファイルに読み取り専用属性が指定されている場合でも、このコマンドレットによってコンソールファイル内のデータが警告なしに上書きされることを示します。</span><span class="sxs-lookup"><span data-stu-id="79613-142">Indicates that this cmdlet overwrites the data in a console file without warning, even if the file has the read-only attribute.</span></span>
<span data-ttu-id="79613-143">読み取り専用属性は変更され、コマンドの完了時にリセットされません。</span><span class="sxs-lookup"><span data-stu-id="79613-143">The read-only attribute is changed and is not reset when the command finishes.</span></span>

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

### <span data-ttu-id="79613-144">-NoClobber</span><span class="sxs-lookup"><span data-stu-id="79613-144">-NoClobber</span></span>
<span data-ttu-id="79613-145">このコマンドレットによって既存のコンソールファイルが上書きされないことを示します。</span><span class="sxs-lookup"><span data-stu-id="79613-145">Indicates that this cmdlet does not overwrite  an existing console file.</span></span>
<span data-ttu-id="79613-146">既定では、指定されたパスにファイルが存在する場合、 **エクスポート** は警告なしでファイルを上書きします。</span><span class="sxs-lookup"><span data-stu-id="79613-146">By default, if a file occurs in the specified path, **Export-Console** overwrites the file without warning.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NoOverwrite

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79613-147">-Path</span><span class="sxs-lookup"><span data-stu-id="79613-147">-Path</span></span>
<span data-ttu-id="79613-148">コンソール ファイル (\*.psc1) のパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="79613-148">Specifies a path and file name for the console file (\*.psc1).</span></span>
<span data-ttu-id="79613-149">省略可能なパスと名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="79613-149">Enter an optional path and name.</span></span>
<span data-ttu-id="79613-150">ワイルドカード文字は使用できません。</span><span class="sxs-lookup"><span data-stu-id="79613-150">Wildcard characters are not permitted.</span></span>

<span data-ttu-id="79613-151">ファイル名のみを指定すると、.psc1 ファイル名拡張子を持つファイルが現在のディレクトリ **に作成さ** れます。</span><span class="sxs-lookup"><span data-stu-id="79613-151">If you specify only a file name, **Export-Console** creates a file that has that name and the .psc1 file name extension in the current directory.</span></span>

<span data-ttu-id="79613-152">このパラメーターは、 *Psconsolefile* パラメーターを指定して Windows PowerShell を開いているか、現在のセッション中にコンソールファイルをエクスポートしていない場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="79613-152">This parameter is required unless you have opened Windows PowerShell with the *PSConsoleFile* parameter or exported a console file during the current session.</span></span>
<span data-ttu-id="79613-153">また、 *NoClobber* パラメーターを使用して、現在のコンソールファイルが上書きされないようにする場合にも必要です。</span><span class="sxs-lookup"><span data-stu-id="79613-153">It is also required when you use the *NoClobber* parameter to prevent the current console file from being overwritten.</span></span>

<span data-ttu-id="79613-154">このパラメーターを省略すると、このセッションで最近使用されたコンソールファイル **が上書きさ** れます。</span><span class="sxs-lookup"><span data-stu-id="79613-154">If you omit this parameter, **Export-Console** overwrites the console file that was used most recently in this session.</span></span>
<span data-ttu-id="79613-155">最近使用したコンソールファイルのパスは、$ConsoleFileName 自動変数の値に格納されます。</span><span class="sxs-lookup"><span data-stu-id="79613-155">The path of the most recently used console file is stored in the value of the $ConsoleFileName automatic variable.</span></span>
<span data-ttu-id="79613-156">詳細については、「about_Automatic_Variables」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79613-156">For more information, see about_Automatic_Variables.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PSPath

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="79613-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="79613-157">-Confirm</span></span>
<span data-ttu-id="79613-158">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="79613-158">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79613-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="79613-159">-WhatIf</span></span>
<span data-ttu-id="79613-160">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="79613-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="79613-161">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="79613-161">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="79613-162">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="79613-162">CommonParameters</span></span>
<span data-ttu-id="79613-163">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="79613-163">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="79613-164">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79613-164">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="79613-165">入力</span><span class="sxs-lookup"><span data-stu-id="79613-165">INPUTS</span></span>

### <span data-ttu-id="79613-166">System.String</span><span class="sxs-lookup"><span data-stu-id="79613-166">System.String</span></span>
<span data-ttu-id="79613-167">パイプを使用してパス文字列をこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="79613-167">You can pipe a path string to this cmdlet.</span></span>

## <span data-ttu-id="79613-168">出力</span><span class="sxs-lookup"><span data-stu-id="79613-168">OUTPUTS</span></span>

### <span data-ttu-id="79613-169">システム. IO. FileInfo</span><span class="sxs-lookup"><span data-stu-id="79613-169">System.IO.FileInfo</span></span>
<span data-ttu-id="79613-170">このコマンドレットは、エクスポートされたエイリアスを含むファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="79613-170">This cmdlet creates a file that contains the exported aliases.</span></span>

## <span data-ttu-id="79613-171">注</span><span class="sxs-lookup"><span data-stu-id="79613-171">NOTES</span></span>

* <span data-ttu-id="79613-172">コンソール ファイル (.psc1) を使用してセッションを開始すると、コンソール ファイルの名前が自動的に $ConsoleFileName の自動変数に格納されます。</span><span class="sxs-lookup"><span data-stu-id="79613-172">When a console file (.psc1) is used to start the session, the name of the console file is automatically stored in the $ConsoleFileName automatic variable.</span></span> <span data-ttu-id="79613-173">$ConsoleFileName の値は、 **エクスポートコンソール** の *Path* パラメーターを使用して新しいコンソールファイルを指定したときに更新されます。</span><span class="sxs-lookup"><span data-stu-id="79613-173">The value of $ConsoleFileName is updated when you use the *Path* parameter of **Export-Console** to specify a new console file.</span></span> <span data-ttu-id="79613-174">コンソールファイルが使用されていない場合、$ConsoleFileName には値 ($Null) がありません。</span><span class="sxs-lookup"><span data-stu-id="79613-174">When no console file is used, $ConsoleFileName has no value ($Null).</span></span>

  <span data-ttu-id="79613-175">新しいセッションで Windows PowerShell コンソール ファイルを使用するには、次の構文を使用して Windows PowerShell を起動します。</span><span class="sxs-lookup"><span data-stu-id="79613-175">To use a Windows PowerShell console file in a new session, use the following syntax to start Windows PowerShell:</span></span>

  `powershell.exe -PsConsoleFile \<ConsoleFile\>.psc1`

  <span data-ttu-id="79613-176">Windows PowerShell プロファイルに Add-PSSnapin コマンドを追加することで、今後のセッションで使用するために Windows PowerShell スナップインを保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="79613-176">You can also save Windows PowerShell snap-ins for future sessions by adding an Add-PSSnapin command to your Windows PowerShell profile.</span></span>
<span data-ttu-id="79613-177">詳細については、「about_Profiles」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="79613-177">For more information, see about_Profiles.</span></span>


## <span data-ttu-id="79613-178">関連リンク</span><span class="sxs-lookup"><span data-stu-id="79613-178">RELATED LINKS</span></span>

[<span data-ttu-id="79613-179">Add-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="79613-179">Add-PSSnapin</span></span>](Add-PSSnapin.md)

[<span data-ttu-id="79613-180">Get-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="79613-180">Get-PSSnapin</span></span>](Get-PSSnapin.md)

[<span data-ttu-id="79613-181">Remove-PSSnapin</span><span class="sxs-lookup"><span data-stu-id="79613-181">Remove-PSSnapin</span></span>](Remove-PSSnapin.md)
