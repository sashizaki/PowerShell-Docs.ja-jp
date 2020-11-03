---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 5/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/set-item?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-Item
ms.openlocfilehash: 5fbdb8345f0d8a1e83a40dbbad2e26fd89960f1d
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212176"
---
# <span data-ttu-id="c558d-103">Set-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-103">Set-Item</span></span>

## <span data-ttu-id="c558d-104">概要</span><span class="sxs-lookup"><span data-stu-id="c558d-104">SYNOPSIS</span></span>
<span data-ttu-id="c558d-105">項目の値を、コマンドで指定した値に変更します。</span><span class="sxs-lookup"><span data-stu-id="c558d-105">Changes the value of an item to the value specified in the command.</span></span>

## <span data-ttu-id="c558d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c558d-106">SYNTAX</span></span>

### <span data-ttu-id="c558d-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="c558d-107">Path (Default)</span></span>

```
Set-Item [-Path] <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="c558d-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c558d-108">LiteralPath</span></span>

```
Set-Item -LiteralPath <String[]> [[-Value] <Object>] [-Force] [-PassThru] [-Filter <String>]
 [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="c558d-109">Description</span><span class="sxs-lookup"><span data-stu-id="c558d-109">DESCRIPTION</span></span>

<span data-ttu-id="c558d-110">`Set-Item`コマンドレットは、変数やレジストリキーなどの項目の値を、コマンドで指定された値に変更します。</span><span class="sxs-lookup"><span data-stu-id="c558d-110">The `Set-Item` cmdlet changes the value of an item, such as a variable or registry key, to the value specified in the command.</span></span>

## <span data-ttu-id="c558d-111">例</span><span class="sxs-lookup"><span data-stu-id="c558d-111">EXAMPLES</span></span>

### <span data-ttu-id="c558d-112">例 1: エイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="c558d-112">Example 1: Create an alias</span></span>

<span data-ttu-id="c558d-113">このコマンドは、メモ帳用に np のエイリアスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c558d-113">This command creates an alias of np for Notepad.</span></span>

```powershell
Set-Item -Path alias:np -Value "c:\windows\notepad.exe"
```

### <span data-ttu-id="c558d-114">例 2: 環境変数の値を変更する</span><span class="sxs-lookup"><span data-stu-id="c558d-114">Example 2: Change the value of an environment variable</span></span>

<span data-ttu-id="c558d-115">このコマンドは、UserRole 環境変数の値を Administrator に変更します。</span><span class="sxs-lookup"><span data-stu-id="c558d-115">This command changes the value of the UserRole environment variable to Administrator.</span></span>

```powershell
Set-Item -Path env:UserRole -Value "Administrator"
```

### <span data-ttu-id="c558d-116">例 3: プロンプト関数を変更する</span><span class="sxs-lookup"><span data-stu-id="c558d-116">Example 3: Modify your prompt function</span></span>

<span data-ttu-id="c558d-117">このコマンドは、パスの前の時刻を表示するように、prompt 関数を変更します。</span><span class="sxs-lookup"><span data-stu-id="c558d-117">This command changes the prompt function so that it displays the time before the path.</span></span>

```powershell
Set-Item -Path function:prompt -Value {'PS '+ (Get-Date -Format t) + " " + (Get-Location) + '> '}
```

### <span data-ttu-id="c558d-118">例 4: プロンプト関数のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="c558d-118">Example 4: Set options for your prompt function</span></span>

<span data-ttu-id="c558d-119">このコマンドは、prompt 関数の **Allscope** オプションと **ReadOnly** オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="c558d-119">This command sets the **AllScope** and **ReadOnly** options for the prompt function.</span></span>
<span data-ttu-id="c558d-120">このコマンドは、の **Options** 動的パラメーターを使用 `Set-Item` します。</span><span class="sxs-lookup"><span data-stu-id="c558d-120">This command uses the **Options** dynamic parameter of `Set-Item`.</span></span>
<span data-ttu-id="c558d-121">**Options** パラメーターは、 `Set-Item` **Alias** プロバイダーまたは **Function** プロバイダーと共に使用する場合にのみ、で使用できます。</span><span class="sxs-lookup"><span data-stu-id="c558d-121">The **Options** parameter is available in `Set-Item` only when you use it with the **Alias** or **Function** provider.</span></span>

```powershell
Set-Item -Path function:prompt -Options "AllScope,ReadOnly"
```

## <span data-ttu-id="c558d-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c558d-122">PARAMETERS</span></span>

### <span data-ttu-id="c558d-123">-Credential</span><span class="sxs-lookup"><span data-stu-id="c558d-123">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="c558d-124">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c558d-124">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="c558d-125">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="c558d-125">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c558d-126">-除外</span><span class="sxs-lookup"><span data-stu-id="c558d-126">-Exclude</span></span>

<span data-ttu-id="c558d-127">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="c558d-127">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="c558d-128">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c558d-128">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c558d-129">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="c558d-129">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="c558d-130">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c558d-130">Wildcard characters are permitted.</span></span> <span data-ttu-id="c558d-131">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="c558d-131">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c558d-132">-Filter</span><span class="sxs-lookup"><span data-stu-id="c558d-132">-Filter</span></span>

<span data-ttu-id="c558d-133">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="c558d-133">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="c558d-134">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="c558d-134">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="c558d-135">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c558d-135">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="c558d-136">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="c558d-136">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c558d-137">-Force</span><span class="sxs-lookup"><span data-stu-id="c558d-137">-Force</span></span>

<span data-ttu-id="c558d-138">読み取り専用のエイリアスや変数など、変更できない項目をコマンドレットが強制的に設定するようにします。</span><span class="sxs-lookup"><span data-stu-id="c558d-138">Forces the cmdlet to set items that cannot otherwise be changed, such as read-only alias or variables.</span></span> <span data-ttu-id="c558d-139">コマンドレットでは、定数のエイリアスまたは変数は変更できません。</span><span class="sxs-lookup"><span data-stu-id="c558d-139">The cmdlet cannot change constant aliases or variables.</span></span>
<span data-ttu-id="c558d-140">実装はプロバイダーごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="c558d-140">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="c558d-141">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c558d-141">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>
<span data-ttu-id="c558d-142">*Force* パラメーターを使用しても、コマンドレットはセキュリティ制限を上書きできません。</span><span class="sxs-lookup"><span data-stu-id="c558d-142">Even using the *Force* parameter, the cmdlet cannot override security restrictions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c558d-143">-Include</span><span class="sxs-lookup"><span data-stu-id="c558d-143">-Include</span></span>

<span data-ttu-id="c558d-144">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="c558d-144">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="c558d-145">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="c558d-145">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="c558d-146">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="c558d-146">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="c558d-147">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c558d-147">Wildcard characters are permitted.</span></span> <span data-ttu-id="c558d-148">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="c558d-148">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="c558d-149">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="c558d-149">-LiteralPath</span></span>

<span data-ttu-id="c558d-150">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c558d-150">Specifies a path to one or more locations.</span></span> <span data-ttu-id="c558d-151">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="c558d-151">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="c558d-152">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="c558d-152">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="c558d-153">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="c558d-153">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="c558d-154">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="c558d-154">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="c558d-155">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c558d-155">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="c558d-156">-PassThru</span><span class="sxs-lookup"><span data-stu-id="c558d-156">-PassThru</span></span>

<span data-ttu-id="c558d-157">項目を表すオブジェクトをパイプラインに渡します。</span><span class="sxs-lookup"><span data-stu-id="c558d-157">Passes an object that represents the item to the pipeline.</span></span>
<span data-ttu-id="c558d-158">既定では、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="c558d-158">By default, this cmdlet does not generate any output.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="c558d-159">-Path</span><span class="sxs-lookup"><span data-stu-id="c558d-159">-Path</span></span>

<span data-ttu-id="c558d-160">項目の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c558d-160">Specifies a path of the location of the items.</span></span>
<span data-ttu-id="c558d-161">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c558d-161">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="c558d-162">-Value</span><span class="sxs-lookup"><span data-stu-id="c558d-162">-Value</span></span>

<span data-ttu-id="c558d-163">項目の新しい値を指定します。</span><span class="sxs-lookup"><span data-stu-id="c558d-163">Specifies a new value for the item.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="c558d-164">-Confirm</span><span class="sxs-lookup"><span data-stu-id="c558d-164">-Confirm</span></span>

<span data-ttu-id="c558d-165">コマンドレットの実行前に確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c558d-165">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="c558d-166">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="c558d-166">-WhatIf</span></span>

<span data-ttu-id="c558d-167">コマンドレットの実行時に発生する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="c558d-167">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="c558d-168">このコマンドレットは実行されません。</span><span class="sxs-lookup"><span data-stu-id="c558d-168">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="c558d-169">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="c558d-169">CommonParameters</span></span>

<span data-ttu-id="c558d-170">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="c558d-170">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="c558d-171">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c558d-171">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="c558d-172">入力</span><span class="sxs-lookup"><span data-stu-id="c558d-172">INPUTS</span></span>

### <span data-ttu-id="c558d-173">System.Object</span><span class="sxs-lookup"><span data-stu-id="c558d-173">System.Object</span></span>

<span data-ttu-id="c558d-174">パイプを使用して、項目の新しい値を表すオブジェクトをこのコマンドレットに渡します。</span><span class="sxs-lookup"><span data-stu-id="c558d-174">You can pipe an object that represents the new value of the item to this cmdlet.</span></span>

## <span data-ttu-id="c558d-175">出力</span><span class="sxs-lookup"><span data-stu-id="c558d-175">OUTPUTS</span></span>

### <span data-ttu-id="c558d-176">None または新しい項目または変更された項目を表すオブジェクト。</span><span class="sxs-lookup"><span data-stu-id="c558d-176">None or an object representing the new or changed item.</span></span>

<span data-ttu-id="c558d-177">このコマンドレットは、 *PassThru* パラメーターを指定した場合に、その項目を表すオブジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="c558d-177">This cmdlet generates an object that represent the item, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="c558d-178">それ以外の場合、このコマンドレットによる出力はありません。</span><span class="sxs-lookup"><span data-stu-id="c558d-178">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="c558d-179">注</span><span class="sxs-lookup"><span data-stu-id="c558d-179">NOTES</span></span>

- <span data-ttu-id="c558d-180">`Set-Item` は、PowerShell FileSystem プロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c558d-180">`Set-Item` is not supported by the PowerShell FileSystem provider.</span></span> <span data-ttu-id="c558d-181">ファイルシステム内の項目の値を変更するには、 `Set-Content` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c558d-181">To change the values of items in the file system, use the `Set-Content` cmdlet.</span></span>
- <span data-ttu-id="c558d-182">レジストリドライブでは、 `HKLM:` および `HKCU:` は `Set-Item` レジストリキーの (既定値) 値のデータを変更します。</span><span class="sxs-lookup"><span data-stu-id="c558d-182">In the Registry drives, `HKLM:` and `HKCU:`, `Set-Item` changes the data in the (Default) value of a registry key.</span></span>
  - <span data-ttu-id="c558d-183">レジストリキーの名前を作成および変更するには、 `New-Item` `Rename-Item` コマンドレットとコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c558d-183">To create and change the names of registry keys, use the `New-Item` and `Rename-Item` cmdlet.</span></span>
  - <span data-ttu-id="c558d-184">レジストリ値の名前とデータを変更するには、 `New-ItemProperty` 、 `Set-ItemProperty` 、および `Rename-ItemProperty` コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="c558d-184">To change the names and data in registry values, use the `New-ItemProperty`, `Set-ItemProperty`, and `Rename-ItemProperty` cmdlets.</span></span>
- <span data-ttu-id="c558d-185">`Set-Item` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="c558d-185">`Set-Item` is designed to work with the data exposed by any provider.</span></span>
  <span data-ttu-id="c558d-186">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PsProvider` します。</span><span class="sxs-lookup"><span data-stu-id="c558d-186">To list the providers available in your session, type `Get-PsProvider`.</span></span>
  <span data-ttu-id="c558d-187">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c558d-187">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="c558d-188">関連リンク</span><span class="sxs-lookup"><span data-stu-id="c558d-188">RELATED LINKS</span></span>

[<span data-ttu-id="c558d-189">Clear-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-189">Clear-Item</span></span>](Clear-Item.md)

[<span data-ttu-id="c558d-190">Copy-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-190">Copy-Item</span></span>](Copy-Item.md)

[<span data-ttu-id="c558d-191">Get-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-191">Get-Item</span></span>](Get-Item.md)

[<span data-ttu-id="c558d-192">Invoke-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-192">Invoke-Item</span></span>](Invoke-Item.md)

[<span data-ttu-id="c558d-193">Move-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-193">Move-Item</span></span>](Move-Item.md)

[<span data-ttu-id="c558d-194">New-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-194">New-Item</span></span>](New-Item.md)

[<span data-ttu-id="c558d-195">Remove-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-195">Remove-Item</span></span>](Remove-Item.md)

[<span data-ttu-id="c558d-196">Rename-Item</span><span class="sxs-lookup"><span data-stu-id="c558d-196">Rename-Item</span></span>](Rename-Item.md)

[<span data-ttu-id="c558d-197">about_Providers</span><span class="sxs-lookup"><span data-stu-id="c558d-197">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

