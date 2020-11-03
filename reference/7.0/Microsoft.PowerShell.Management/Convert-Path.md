---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: fa66e42e182a7dea830ab30373682e4d1e6601e3
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210627"
---
# <span data-ttu-id="74979-103">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="74979-103">Convert-Path</span></span>

## <span data-ttu-id="74979-104">概要</span><span class="sxs-lookup"><span data-stu-id="74979-104">SYNOPSIS</span></span>
<span data-ttu-id="74979-105">PowerShell パスから PowerShell プロバイダーパスへのパスを変換します。</span><span class="sxs-lookup"><span data-stu-id="74979-105">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="74979-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="74979-106">SYNTAX</span></span>

### <span data-ttu-id="74979-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="74979-107">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [<CommonParameters>]
```

### <span data-ttu-id="74979-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="74979-108">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [<CommonParameters>]
```

## <span data-ttu-id="74979-109">Description</span><span class="sxs-lookup"><span data-stu-id="74979-109">DESCRIPTION</span></span>

<span data-ttu-id="74979-110">`Convert-Path`コマンドレットは、powershell パスのパスを powershell プロバイダーのパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="74979-110">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="74979-111">例</span><span class="sxs-lookup"><span data-stu-id="74979-111">EXAMPLES</span></span>

### <span data-ttu-id="74979-112">例 1: 作業ディレクトリを標準のファイルシステムパスに変換する</span><span class="sxs-lookup"><span data-stu-id="74979-112">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="74979-113">この例では、ドット () で表される現在の作業ディレクトリを `.` 標準のファイルシステムパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="74979-113">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="74979-114">例 2: プロバイダーのパスを標準のレジストリパスに変換する</span><span class="sxs-lookup"><span data-stu-id="74979-114">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="74979-115">この例では、PowerShell プロバイダーのパスを標準のレジストリパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="74979-115">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="74979-116">例 3: パスを文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="74979-116">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="74979-117">この例では、ファイルシステムプロバイダーである現在のプロバイダーのホームディレクトリへのパスを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="74979-117">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="74979-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="74979-118">PARAMETERS</span></span>

### <span data-ttu-id="74979-119">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="74979-119">-LiteralPath</span></span>

<span data-ttu-id="74979-120">文字列配列として、変換するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="74979-120">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="74979-121">**LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="74979-121">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="74979-122">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="74979-122">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="74979-123">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="74979-123">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="74979-124">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="74979-124">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="74979-125">-Path</span><span class="sxs-lookup"><span data-stu-id="74979-125">-Path</span></span>

<span data-ttu-id="74979-126">変換する PowerShell パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="74979-126">Specifies the PowerShell path to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="74979-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="74979-127">CommonParameters</span></span>

<span data-ttu-id="74979-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="74979-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="74979-129">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74979-129">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="74979-130">入力</span><span class="sxs-lookup"><span data-stu-id="74979-130">INPUTS</span></span>

### <span data-ttu-id="74979-131">System.String</span><span class="sxs-lookup"><span data-stu-id="74979-131">System.String</span></span>

<span data-ttu-id="74979-132">パイプを使用して、パスをこのコマンドレットにパイプすることはできますが、リテラルパスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="74979-132">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="74979-133">出力</span><span class="sxs-lookup"><span data-stu-id="74979-133">OUTPUTS</span></span>

### <span data-ttu-id="74979-134">System.String</span><span class="sxs-lookup"><span data-stu-id="74979-134">System.String</span></span>

<span data-ttu-id="74979-135">このコマンドレットは、変換されたパスを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="74979-135">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="74979-136">注</span><span class="sxs-lookup"><span data-stu-id="74979-136">NOTES</span></span>

<span data-ttu-id="74979-137">パスの名詞を含むコマンドレットは、パス名を操作し、すべての PowerShell プロバイダーが解釈できる簡潔な形式の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="74979-137">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="74979-138">プログラムやスクリプトで、パス名の全部または一部を特定の形式で表示するために使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="74979-138">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="74979-139">**Dirname** 、 **Normpath** 、 **realpath** 、 **Join** 、またはその他のパスマニピュレーターを使用する場合と同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="74979-139">Use them like you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="74979-140">パス コマンドレットは、FileSystem、Registry、Certificate など、いくつかのプロバイダーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="74979-140">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="74979-141">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="74979-141">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="74979-142">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="74979-142">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="74979-143">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74979-143">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="74979-144">`Convert-Path` 既存のパスのみを変換します。</span><span class="sxs-lookup"><span data-stu-id="74979-144">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="74979-145">まだ存在しない場所を変換するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="74979-145">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="74979-146">関連リンク</span><span class="sxs-lookup"><span data-stu-id="74979-146">RELATED LINKS</span></span>

[<span data-ttu-id="74979-147">Join-Path</span><span class="sxs-lookup"><span data-stu-id="74979-147">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="74979-148">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="74979-148">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="74979-149">Split-Path</span><span class="sxs-lookup"><span data-stu-id="74979-149">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="74979-150">Test-Path</span><span class="sxs-lookup"><span data-stu-id="74979-150">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="74979-151">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="74979-151">Get-PSProvider</span></span>](Get-PSProvider.md)