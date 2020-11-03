---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 10/18/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-itempropertyvalue?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ItemPropertyValue
ms.openlocfilehash: 2dbbbfeac3810f79b976b6a68ab3089e91707fb3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215416"
---
# <span data-ttu-id="63f8b-103">Get-ItemPropertyValue</span><span class="sxs-lookup"><span data-stu-id="63f8b-103">Get-ItemPropertyValue</span></span>

## <span data-ttu-id="63f8b-104">概要</span><span class="sxs-lookup"><span data-stu-id="63f8b-104">SYNOPSIS</span></span>
<span data-ttu-id="63f8b-105">指定した項目の1つ以上のプロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-105">Gets the value for one or more properties of a specified item.</span></span>

## <span data-ttu-id="63f8b-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="63f8b-106">SYNTAX</span></span>

### <span data-ttu-id="63f8b-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="63f8b-107">Path (Default)</span></span>

```
Get-ItemPropertyValue [[-Path] <String[]>] [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="63f8b-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="63f8b-108">LiteralPath</span></span>

```
Get-ItemPropertyValue -LiteralPath <String[]> [-Name] <String[]> [-Filter <String>] [-Include <String[]>]
 [-Exclude <String[]>] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="63f8b-109">Description</span><span class="sxs-lookup"><span data-stu-id="63f8b-109">DESCRIPTION</span></span>

<span data-ttu-id="63f8b-110">は、 `Get-ItemPropertyValue` *path* パラメーターまたは *LiteralPath* パラメーターで指定したパスにある *Name* パラメーターを使用するときに、指定したプロパティの現在の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-110">The `Get-ItemPropertyValue` gets the current value for a property that you specify when you use the *Name* parameter, located in a path that you specify with either the *Path* or *LiteralPath* parameters.</span></span>

## <span data-ttu-id="63f8b-111">例</span><span class="sxs-lookup"><span data-stu-id="63f8b-111">EXAMPLES</span></span>

### <span data-ttu-id="63f8b-112">例 1: ProductID プロパティの値を取得する</span><span class="sxs-lookup"><span data-stu-id="63f8b-112">Example 1: Get the value of the ProductID property</span></span>

<span data-ttu-id="63f8b-113">このコマンドは、Windows レジストリプロバイダーの "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" オブジェクトの **ProductID** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-113">This command gets the value of the **ProductID** property of the "\SOFTWARE\Microsoft\Windows NT\CurrentVersion" object in the Windows Registry provider.</span></span>

```powershell
Get-ItemPropertyValue 'HKLM:\SOFTWARE\Microsoft\Windows NT\CurrentVersion' -Name ProductID
```

```output
94253-50000-11141-AA785
```

### <span data-ttu-id="63f8b-114">例 2: ファイルまたはフォルダーの最終書き込み時刻を取得する</span><span class="sxs-lookup"><span data-stu-id="63f8b-114">Example 2: Get the last write time of a file or folder</span></span>

<span data-ttu-id="63f8b-115">このコマンドは、 **Lastwritetime** プロパティの値を取得します。または、ファイルまたはフォルダーが "C:\Users\Test\Documents\ModuleToAssembly" フォルダーから最後に変更されたときに、FileSystem プロバイダーで動作しています。</span><span class="sxs-lookup"><span data-stu-id="63f8b-115">This command gets the value of the **LastWriteTime** property, or the last time a file or folder was changed, from the "C:\Users\Test\Documents\ModuleToAssembly" folder, working in the FileSystem provider.</span></span>

```powershell
Get-ItemPropertyValue -Path C:\Users\Test\Documents\ModuleToAssembly -Name LastWriteTime
```

```output
Wednesday, September 3, 2014 2:53:22 PM
```

### <span data-ttu-id="63f8b-116">例 3: ファイルまたはフォルダーの複数のプロパティ値を取得する</span><span class="sxs-lookup"><span data-stu-id="63f8b-116">Example 3: Get multiple property values of a file or folder</span></span>

<span data-ttu-id="63f8b-117">このコマンドは、フォルダーの **Lastwritetime** **、値の取得、** および **ルート** プロパティの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-117">This command gets the values of the **LastWriteTime** , **CreationTime** , and **Root** properties of a folder.</span></span>
<span data-ttu-id="63f8b-118">プロパティの値は、プロパティ名を指定した順序で返されます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-118">The property values are returned in the order in which you specified the property names.</span></span>

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

## <span data-ttu-id="63f8b-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="63f8b-119">PARAMETERS</span></span>

### <span data-ttu-id="63f8b-120">-Credential</span><span class="sxs-lookup"><span data-stu-id="63f8b-120">-Credential</span></span>

<span data-ttu-id="63f8b-121">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-121">Specifies a user account that has permission to perform this action.</span></span>
<span data-ttu-id="63f8b-122">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="63f8b-122">The default is the current user.</span></span>

<span data-ttu-id="63f8b-123">「User01」や「Domain01\User01」のようなユーザー名を入力するか、  コマンドレットで生成されるような `Get-Credential` オブジェクトを入力します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-123">Type a user name, such as "User01" or "Domain01\User01", or enter a **PSCredential** object, such as one generated by the `Get-Credential` cmdlet.</span></span>
<span data-ttu-id="63f8b-124">ユーザー名を入力すると、パスワードの入力を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-124">If you type a user name, you are prompted for a password.</span></span>

> [!WARNING]
> <span data-ttu-id="63f8b-125">このパラメーターは、Windows PowerShell でインストールされるプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="63f8b-125">This parameter is not supported by any providers installed with Windows PowerShell.</span></span>

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

### <span data-ttu-id="63f8b-126">-除外</span><span class="sxs-lookup"><span data-stu-id="63f8b-126">-Exclude</span></span>

<span data-ttu-id="63f8b-127">このコマンドレットによって操作から除外される項目を文字列配列として指定します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-127">Specifies, as a string array, an item or items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="63f8b-128">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-128">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="63f8b-129">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-129">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="63f8b-130">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-130">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="63f8b-131">-Filter</span><span class="sxs-lookup"><span data-stu-id="63f8b-131">-Filter</span></span>

<span data-ttu-id="63f8b-132">プロバイダーの形式または言語でフィルターを指定します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-132">Specifies a filter in the format or language of the provider.</span></span>
<span data-ttu-id="63f8b-133">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-133">The value of this parameter qualifies the **Path** parameter.</span></span>

<span data-ttu-id="63f8b-134">ワイルドカード文字の使用など、フィルターの構文はプロバイダーによって異なります。</span><span class="sxs-lookup"><span data-stu-id="63f8b-134">The syntax of the filter, including the use of wildcard characters, depends on the provider.</span></span>
<span data-ttu-id="63f8b-135">フィルターは他のパラメーターよりも効率的です。これは、取得後にオブジェクトを PowerShell でフィルター処理するのではなく、コマンドレットがオブジェクトを取得するときに、フィルターが適用されるためです。</span><span class="sxs-lookup"><span data-stu-id="63f8b-135">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

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

### <span data-ttu-id="63f8b-136">-Include</span><span class="sxs-lookup"><span data-stu-id="63f8b-136">-Include</span></span>

<span data-ttu-id="63f8b-137">文字列配列として、このコマンドレットによって操作に含まれる項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span>
<span data-ttu-id="63f8b-138">このパラメーターの値は、 **Path** パラメーターを修飾します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-138">The value of this parameter qualifies the **Path** parameter.</span></span>
<span data-ttu-id="63f8b-139">「\*.txt」などのパス要素またはパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-139">Enter a path element or pattern, such as "\*.txt".</span></span>
<span data-ttu-id="63f8b-140">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-140">Wildcard characters are permitted.</span></span>

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

### <span data-ttu-id="63f8b-141">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="63f8b-141">-LiteralPath</span></span>

<span data-ttu-id="63f8b-142">プロパティの現在の場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-142">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="63f8b-143">**Path** パラメーターと異なり、 **LiteralPath** の値は入力したとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-143">Unlike the **Path** parameter, the value of **LiteralPath** is used exactly as it is typed.</span></span>
<span data-ttu-id="63f8b-144">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="63f8b-144">No characters are interpreted as wildcards.</span></span>
<span data-ttu-id="63f8b-145">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-145">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="63f8b-146">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="63f8b-146">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="63f8b-147">-Name</span><span class="sxs-lookup"><span data-stu-id="63f8b-147">-Name</span></span>

<span data-ttu-id="63f8b-148">取得するプロパティの名前を 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-148">Specifies the name of the property or properties to retrieve.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63f8b-149">-Path</span><span class="sxs-lookup"><span data-stu-id="63f8b-149">-Path</span></span>

<span data-ttu-id="63f8b-150">項目のパスを 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-150">Specifies the path to the item or items.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="63f8b-151">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="63f8b-151">-UseTransaction</span></span>

<span data-ttu-id="63f8b-152">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-152">Includes the command in the active transaction.</span></span>
<span data-ttu-id="63f8b-153">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="63f8b-153">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="63f8b-154">詳細については、「about_Transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f8b-154">For more information, see about_Transactions.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="63f8b-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="63f8b-155">CommonParameters</span></span>

<span data-ttu-id="63f8b-156">このコマンドレットは、、、、、、、、、、、およびの共通パラメーターをサポートしてい `-Debug` `-ErrorAction` `-ErrorVariable` `-InformationAction` `-InformationVariable` `-OutVariable` `-OutBuffer` `-PipelineVariable` `-Verbose` `-WarningAction` `-WarningVariable` ます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-156">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="63f8b-157">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f8b-157">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="63f8b-158">入力</span><span class="sxs-lookup"><span data-stu-id="63f8b-158">INPUTS</span></span>

### <span data-ttu-id="63f8b-159">System.String</span><span class="sxs-lookup"><span data-stu-id="63f8b-159">System.String</span></span>

<span data-ttu-id="63f8b-160">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-160">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="63f8b-161">出力</span><span class="sxs-lookup"><span data-stu-id="63f8b-161">OUTPUTS</span></span>

### <span data-ttu-id="63f8b-162">System.string、System.string、System.string です。</span><span class="sxs-lookup"><span data-stu-id="63f8b-162">System.Boolean, System.String, System.DateTime</span></span>

<span data-ttu-id="63f8b-163">このコマンドレットは、取得する項目のプロパティ値ごとにオブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="63f8b-163">This cmdlet returns an object for each item property value that it gets.</span></span>
<span data-ttu-id="63f8b-164">オブジェクトの種類は、取得されるプロパティ値によって異なります。</span><span class="sxs-lookup"><span data-stu-id="63f8b-164">The object type depends on the property value that is retrieved.</span></span>
<span data-ttu-id="63f8b-165">たとえば、ファイルシステムドライブでは、コマンドレットはファイルまたはフォルダーを返す場合があります。</span><span class="sxs-lookup"><span data-stu-id="63f8b-165">For example, in a file system drive, the cmdlet might return a file or folder.</span></span>

## <span data-ttu-id="63f8b-166">注</span><span class="sxs-lookup"><span data-stu-id="63f8b-166">NOTES</span></span>

<span data-ttu-id="63f8b-167">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="63f8b-167">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="63f8b-168">セッションで使用可能なプロバイダーの一覧を表示するには、コマンドレットを実行し `Get-PSProvider` ます。</span><span class="sxs-lookup"><span data-stu-id="63f8b-168">To list the providers available in your session, run the `Get-PSProvider` cmdlet.</span></span> <span data-ttu-id="63f8b-169">詳細については、「about_Providers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="63f8b-169">For more information, see about_Providers.</span></span>

## <span data-ttu-id="63f8b-170">関連リンク</span><span class="sxs-lookup"><span data-stu-id="63f8b-170">RELATED LINKS</span></span>

[<span data-ttu-id="63f8b-171">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63f8b-171">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="63f8b-172">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63f8b-172">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="63f8b-173">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63f8b-173">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="63f8b-174">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63f8b-174">Move-ItemProperty</span></span>](Move-ItemProperty.md)

[<span data-ttu-id="63f8b-175">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63f8b-175">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="63f8b-176">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63f8b-176">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="63f8b-177">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63f8b-177">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="63f8b-178">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="63f8b-178">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="63f8b-179">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="63f8b-179">Get-PSProvider</span></span>](Get-PSProvider.md)
