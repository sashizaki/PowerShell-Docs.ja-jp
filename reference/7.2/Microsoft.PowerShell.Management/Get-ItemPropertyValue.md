---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: b8980febb80a4e7dfaefba46649ac49b5b41b427
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605166"
---
# <span data-ttu-id="9f842-102">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="9f842-102">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="9f842-103">概要</span><span class="sxs-lookup"><span data-stu-id="9f842-103">SYNOPSIS</span></span>
<span data-ttu-id="9f842-104">指定した項目の1つ以上のプロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f842-104">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="9f842-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="9f842-105">SYNTAX</span></span>

### <span data-ttu-id="9f842-106">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="9f842-106">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="9f842-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9f842-107">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="9f842-108">Description</span><span class="sxs-lookup"><span data-stu-id="9f842-108">DESCRIPTION</span></span>

<span data-ttu-id="9f842-109">は、 `Get-ItemPropertyValue` *path* パラメーターまたは *LiteralPath* パラメーターで指定したパスにある *Name* パラメーターを使用するときに、指定したプロパティの現在の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f842-109">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="9f842-110">例</span><span class="sxs-lookup"><span data-stu-id="9f842-110">EXAMPLES</span></span>

### <span data-ttu-id="9f842-111">例 1: ProductID プロパティの値を取得する</span><span class="sxs-lookup"><span data-stu-id="9f842-111">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="9f842-112">このコマンドは、Windows レジストリプロバイダーの "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" オブジェクトの **ProductID** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f842-112">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="9f842-113">例 2: ファイルまたはフォルダーの最終書き込み時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="9f842-113">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="9f842-114">このコマンドは、 **Lastwritetime** プロパティの値を取得します。または、ファイルまたはフォルダーが "C:\Users\Test\Documents\ModuleToAssembly" フォルダーから最後に変更されたときに、FileSystem プロバイダーで動作しています。</span><span class="sxs-lookup"><span data-stu-id="9f842-114">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="9f842-115">例 3: ファイルまたはフォルダーの複数のプロパティ値を取得する</span><span class="sxs-lookup"><span data-stu-id="9f842-115">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="9f842-116">このコマンドは、フォルダーの **Lastwritetime** **、値の取得、** および **ルート** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="9f842-116">This command gets the values of the **LastWriteTime**, **CreationTime**, and **Root** properties of a folder.</span></span> <span data-ttu-id="9f842-117">プロパティの値は、プロパティ名を指定した順序で返されます。</span><span class="sxs-lookup"><span data-stu-id="9f842-117">The property values are returned in the order in which you specified the property names.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime,CreationTime,Root
```

```output
Wednesday, September 3, 2014 2:53:22 PM
Wednesday, September 3, 2014 2:53:10 PM

Name              : C:\
Parent            :
Exists            : True
Root              : C:\
FullName          : C:\
Extension         :
CreationTime      : 9/1/2014 4:59:45 AM
CreationTimeUtc   : 9/1/2014 11:59:45 AM
LastAccessTime    : 9/27/2014 5:22:02 PM
LastAccessTimeUtc : 9/28/2014 12:22:02 AM
LastWriteTime     : 9/27/2014 5:22:02 PM
LastWriteTimeUtc  : 9/28/2014 12:22:02 AM
Attributes        : Hidden, System, Directory
BaseName          : C:\
Target            :
LinkType          :
Mode              : d--hs-
```

## <span data-ttu-id="9f842-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="9f842-118">PARAMETERS</span></span>

### <span data-ttu-id="9f842-119">-Credential</span><span class="sxs-lookup"><span data-stu-id="9f842-119">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="9f842-120">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9f842-120">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="9f842-121">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9f842-121">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="9f842-122">-除外</span><span class="sxs-lookup"><span data-stu-id="9f842-122">-Exclude</span></span>

<span data-ttu-id="9f842-123">このコマンドレットによって操作で除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="9f842-123">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="9f842-124">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9f842-124">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9f842-125">パス要素またはパターン (など) を入力し `*.txt` ます。</span><span class="sxs-lookup"><span data-stu-id="9f842-125">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="9f842-126">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f842-126">Wildcard characters are permitted.</span></span> <span data-ttu-id="9f842-127">**Exclude** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="9f842-127">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9f842-128">-Filter</span><span class="sxs-lookup"><span data-stu-id="9f842-128">-Filter</span></span>

<span data-ttu-id="9f842-129">**パス** パラメーターを修飾するフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f842-129">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="9f842-130">[ファイルシステム](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md)プロバイダーは、フィルターの使用をサポートする唯一のインストール済み PowerShell プロバイダーです。</span><span class="sxs-lookup"><span data-stu-id="9f842-130">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="9f842-131">**ファイルシステム** フィルター言語の構文については、 [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f842-131">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="9f842-132">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="9f842-132">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="9f842-133">-Include</span><span class="sxs-lookup"><span data-stu-id="9f842-133">-Include</span></span>

<span data-ttu-id="9f842-134">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="9f842-134">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="9f842-135">このパラメーターの値は、**Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="9f842-135">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="9f842-136">パス要素またはパターン (など) を入力し `"*.txt"` ます。</span><span class="sxs-lookup"><span data-stu-id="9f842-136">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="9f842-137">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f842-137">Wildcard characters are permitted.</span></span> <span data-ttu-id="9f842-138">**Include** パラメーターは、コマンドに項目の内容 (など) が含まれている場合にのみ有効になり `C:\Windows\*` ます。ワイルドカード文字は、ディレクトリの内容を指定し `C:\Windows` ます。</span><span class="sxs-lookup"><span data-stu-id="9f842-138">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

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

### <span data-ttu-id="9f842-139">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="9f842-139">-LiteralPath</span></span>

<span data-ttu-id="9f842-140">1 つ以上の場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="9f842-140">Specifies a path to one or more locations.</span></span> <span data-ttu-id="9f842-141">**LiteralPath** の値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="9f842-141">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="9f842-142">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="9f842-142">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="9f842-143">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="9f842-143">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="9f842-144">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="9f842-144">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="9f842-145">詳細については、「 [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f842-145">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

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

### <span data-ttu-id="9f842-146">-Name</span><span class="sxs-lookup"><span data-stu-id="9f842-146">-Name</span></span>

<span data-ttu-id="9f842-147">取得するプロパティの名前を 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="9f842-147">Specifies the name of the property or properties to retrieve.</span></span>
<span data-ttu-id="9f842-148">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f842-148">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="9f842-149">-Path</span><span class="sxs-lookup"><span data-stu-id="9f842-149">-Path</span></span>

<span data-ttu-id="9f842-150">項目のパスを 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="9f842-150">Specifies the path to the item or items.</span></span>
<span data-ttu-id="9f842-151">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9f842-151">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="9f842-152">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="9f842-152">CommonParameters</span></span>

<span data-ttu-id="9f842-153">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="9f842-153">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="9f842-154">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f842-154">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="9f842-155">入力</span><span class="sxs-lookup"><span data-stu-id="9f842-155">INPUTS</span></span>

### <span data-ttu-id="9f842-156">System.String</span><span class="sxs-lookup"><span data-stu-id="9f842-156">System.String</span></span>

<span data-ttu-id="9f842-157">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="9f842-157">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="9f842-158">出力</span><span class="sxs-lookup"><span data-stu-id="9f842-158">OUTPUTS</span></span>

### <span data-ttu-id="9f842-159">System.string、System.string、System.string です。</span><span class="sxs-lookup"><span data-stu-id="9f842-159">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="9f842-160">このコマンドレットは、取得する項目のプロパティ値ごとにオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="9f842-160">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="9f842-161">オブジェクトの種類は、取得されるプロパティ値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="9f842-161">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="9f842-162">たとえば、ファイルシステムドライブでは、コマンドレットはファイルまたはフォルダーを返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f842-162">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="9f842-163">注</span><span class="sxs-lookup"><span data-stu-id="9f842-163">NOTES</span></span>

<span data-ttu-id="9f842-164">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="9f842-164">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="9f842-165">セッションで使用可能なプロバイダーの一覧を表示するには、コマンドレットを実行し `Get-PSProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="9f842-165">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="9f842-166">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f842-166">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="9f842-167">関連リンク</span><span class="sxs-lookup"><span data-stu-id="9f842-167">RELATED LINKS</span></span>

[<span data-ttu-id="9f842-168">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f842-168">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="9f842-169">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f842-169">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="9f842-170">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f842-170">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="9f842-171">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="9f842-171">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="9f842-172">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f842-172">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="9f842-173">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f842-173">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="9f842-174">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f842-174">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="9f842-175">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f842-175">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="9f842-176">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="9f842-176">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="9f842-177">about_Providers</span><span class="sxs-lookup"><span data-stu-id="9f842-177">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)

