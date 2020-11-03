---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/convert-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Convert-Path
ms.openlocfilehash: a442d8ff9f021e1ec05671d9190d35ef97ff4d72
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215544"
---
# <span data-ttu-id="d0a88-103">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="d0a88-103">Convert-Path</span></span>

## <span data-ttu-id="d0a88-104">概要</span><span class="sxs-lookup"><span data-stu-id="d0a88-104">SYNOPSIS</span></span>
<span data-ttu-id="d0a88-105">PowerShell パスから PowerShell プロバイダーパスへのパスを変換します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-105">Converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="d0a88-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d0a88-106">SYNTAX</span></span>

### <span data-ttu-id="d0a88-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="d0a88-107">Path (Default)</span></span>

```
Convert-Path [-Path] <String[]> [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="d0a88-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d0a88-108">LiteralPath</span></span>

```
Convert-Path -LiteralPath <String[]> [-UseTransaction] [<CommonParameters>]
```

## <span data-ttu-id="d0a88-109">Description</span><span class="sxs-lookup"><span data-stu-id="d0a88-109">DESCRIPTION</span></span>

<span data-ttu-id="d0a88-110">`Convert-Path`コマンドレットは、powershell パスのパスを powershell プロバイダーのパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-110">The `Convert-Path` cmdlet converts a path from a PowerShell path to a PowerShell provider path.</span></span>

## <span data-ttu-id="d0a88-111">例</span><span class="sxs-lookup"><span data-stu-id="d0a88-111">EXAMPLES</span></span>

### <span data-ttu-id="d0a88-112">例 1: 作業ディレクトリを標準のファイルシステムパスに変換する</span><span class="sxs-lookup"><span data-stu-id="d0a88-112">Example 1: Convert the working directory to a standard file system path</span></span>

<span data-ttu-id="d0a88-113">この例では、ドット () で表される現在の作業ディレクトリを `.` 標準のファイルシステムパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-113">This example converts the current working directory, which is represented by a dot (`.`), to a standard FileSystem path.</span></span>

```
PS C:\> Convert-Path .
C:\
```

### <span data-ttu-id="d0a88-114">例 2: プロバイダーのパスを標準のレジストリパスに変換する</span><span class="sxs-lookup"><span data-stu-id="d0a88-114">Example 2: Convert a provider path to a standard registry path</span></span>

<span data-ttu-id="d0a88-115">この例では、PowerShell プロバイダーのパスを標準のレジストリパスに変換します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-115">This example converts the PowerShell provider path to a standard registry path.</span></span>

```powershell
PS C:\> Convert-Path HKLM:\Software\Microsoft
HKEY_LOCAL_MACHINE\Software\Microsoft
```

### <span data-ttu-id="d0a88-116">例 3: パスを文字列に変換する</span><span class="sxs-lookup"><span data-stu-id="d0a88-116">Example 3: Convert a path to a string</span></span>

<span data-ttu-id="d0a88-117">この例では、ファイルシステムプロバイダーである現在のプロバイダーのホームディレクトリへのパスを文字列に変換します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-117">This example converts the path to the home directory of the current provider, which is the FileSystem provider, to a string.</span></span>

```powershell
PS C:\> Convert-Path ~
C:\Users\User01
```

## <span data-ttu-id="d0a88-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d0a88-118">PARAMETERS</span></span>

### <span data-ttu-id="d0a88-119">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d0a88-119">-LiteralPath</span></span>

<span data-ttu-id="d0a88-120">文字列配列として、変換するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-120">Specifies, as a string array, the path to be converted.</span></span> <span data-ttu-id="d0a88-121">**LiteralPath** パラメーターの値は、入力されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="d0a88-121">The value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="d0a88-122">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="d0a88-122">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d0a88-123">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="d0a88-123">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d0a88-124">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="d0a88-124">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="d0a88-125">-Path</span><span class="sxs-lookup"><span data-stu-id="d0a88-125">-Path</span></span>

<span data-ttu-id="d0a88-126">変換する PowerShell パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-126">Specifies the PowerShell path to be converted.</span></span>

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

### <span data-ttu-id="d0a88-127">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="d0a88-127">-UseTransaction</span></span>
<span data-ttu-id="d0a88-128">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d0a88-128">Includes the command in the active transaction.</span></span>
<span data-ttu-id="d0a88-129">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="d0a88-129">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="d0a88-130">詳細については、「about_transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0a88-130">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="d0a88-131">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d0a88-131">CommonParameters</span></span>

<span data-ttu-id="d0a88-132">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d0a88-132">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d0a88-133">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0a88-133">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d0a88-134">入力</span><span class="sxs-lookup"><span data-stu-id="d0a88-134">INPUTS</span></span>

### <span data-ttu-id="d0a88-135">System.String</span><span class="sxs-lookup"><span data-stu-id="d0a88-135">System.String</span></span>

<span data-ttu-id="d0a88-136">パイプを使用して、パスをこのコマンドレットにパイプすることはできますが、リテラルパスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="d0a88-136">You can pipe a path, but not a literal path, to this cmdlet.</span></span>

## <span data-ttu-id="d0a88-137">出力</span><span class="sxs-lookup"><span data-stu-id="d0a88-137">OUTPUTS</span></span>

### <span data-ttu-id="d0a88-138">System.String</span><span class="sxs-lookup"><span data-stu-id="d0a88-138">System.String</span></span>

<span data-ttu-id="d0a88-139">このコマンドレットは、変換されたパスを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-139">This cmdlet returns a string that contains the converted path.</span></span>

## <span data-ttu-id="d0a88-140">注</span><span class="sxs-lookup"><span data-stu-id="d0a88-140">NOTES</span></span>

<span data-ttu-id="d0a88-141">パスの名詞を含むコマンドレットは、パス名を操作し、すべての PowerShell プロバイダーが解釈できる簡潔な形式の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-141">The cmdlets that contain the Path noun manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="d0a88-142">プログラムやスクリプトで、パス名の全部または一部を特定の形式で表示するために使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="d0a88-142">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="d0a88-143">**Dirname** 、 **Normpath** 、 **realpath** 、 **Join** 、またはその他のパスマニピュレーターを使用する場合と同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-143">Use them like you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

<span data-ttu-id="d0a88-144">パス コマンドレットは、FileSystem、Registry、Certificate など、いくつかのプロバイダーで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d0a88-144">You can use the path cmdlets with several providers, including the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="d0a88-145">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d0a88-145">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d0a88-146">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-146">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d0a88-147">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0a88-147">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

<span data-ttu-id="d0a88-148">`Convert-Path` 既存のパスのみを変換します。</span><span class="sxs-lookup"><span data-stu-id="d0a88-148">`Convert-Path` only converts existing paths.</span></span> <span data-ttu-id="d0a88-149">まだ存在しない場所を変換するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="d0a88-149">It cannot be used to convert a location that does not exist yet.</span></span>

## <span data-ttu-id="d0a88-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d0a88-150">RELATED LINKS</span></span>

[<span data-ttu-id="d0a88-151">Join-Path</span><span class="sxs-lookup"><span data-stu-id="d0a88-151">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="d0a88-152">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="d0a88-152">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="d0a88-153">Split-Path</span><span class="sxs-lookup"><span data-stu-id="d0a88-153">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="d0a88-154">Test-Path</span><span class="sxs-lookup"><span data-stu-id="d0a88-154">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="d0a88-155">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="d0a88-155">Get-PSProvider</span></span>](Get-PSProvider.md)
