---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: c65634a295ccca368d7b4d42eb2bf6bb18753e96
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93212256"
---
# <span data-ttu-id="75176-103">Split-Path</span><span class="sxs-lookup"><span data-stu-id="75176-103">Split-Path</span></span>

## <span data-ttu-id="75176-104">概要</span><span class="sxs-lookup"><span data-stu-id="75176-104">SYNOPSIS</span></span>
<span data-ttu-id="75176-105">指定されたパス部分を返します。</span><span class="sxs-lookup"><span data-stu-id="75176-105">Returns the specified part of a path.</span></span>

## <span data-ttu-id="75176-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="75176-106">SYNTAX</span></span>

### <span data-ttu-id="75176-107">ParentSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="75176-107">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="75176-108">QualifierSet</span><span class="sxs-lookup"><span data-stu-id="75176-108">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> [[-Qualifier]] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="75176-109">LeafSet</span><span class="sxs-lookup"><span data-stu-id="75176-109">LeafSet</span></span>

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="75176-110">LeafBaseSet</span><span class="sxs-lookup"><span data-stu-id="75176-110">LeafBaseSet</span></span>

```
Split-Path [-Path] <String[]> [-LeafBase] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="75176-111">ExtensionSet</span><span class="sxs-lookup"><span data-stu-id="75176-111">ExtensionSet</span></span>

```
Split-Path [-Path] <String[]> [-Extension] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="75176-112">NoQualifierSet</span><span class="sxs-lookup"><span data-stu-id="75176-112">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="75176-113">IsAbsoluteSet</span><span class="sxs-lookup"><span data-stu-id="75176-113">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="75176-114">LiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="75176-114">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="75176-115">Description</span><span class="sxs-lookup"><span data-stu-id="75176-115">DESCRIPTION</span></span>

<span data-ttu-id="75176-116">**Split path** コマンドレットは、親フォルダー、サブフォルダー、ファイル名など、指定されたパスの部分のみを返します。</span><span class="sxs-lookup"><span data-stu-id="75176-116">The **Split-Path** cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span>
<span data-ttu-id="75176-117">また、分割されたパスで参照されている項目を取得したり、パスが相対パスか絶対パスかを判断したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="75176-117">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="75176-118">このコマンドレットを使用すると、選択したパスの一部だけを取得または送信できます。</span><span class="sxs-lookup"><span data-stu-id="75176-118">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="75176-119">例</span><span class="sxs-lookup"><span data-stu-id="75176-119">EXAMPLES</span></span>

### <span data-ttu-id="75176-120">例 1: パスの修飾子を取得する</span><span class="sxs-lookup"><span data-stu-id="75176-120">Example 1: Get the qualifier of a path</span></span>

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

<span data-ttu-id="75176-121">このコマンドは、パスの修飾子だけを返します。</span><span class="sxs-lookup"><span data-stu-id="75176-121">This command returns only the qualifier of the path.</span></span>
<span data-ttu-id="75176-122">修飾子はドライブです。</span><span class="sxs-lookup"><span data-stu-id="75176-122">The qualifier is the drive.</span></span>

### <span data-ttu-id="75176-123">例 2: ファイル名を表示する</span><span class="sxs-lookup"><span data-stu-id="75176-123">Example 2: Display file names</span></span>

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

<span data-ttu-id="75176-124">このコマンドを実行すると、分割されたパスが参照しているファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75176-124">This command displays the files that are referenced by the split path.</span></span>
<span data-ttu-id="75176-125">このパスは最後の項目 (リーフとも呼ばれます) に分割されるので、コマンドはファイル名のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="75176-125">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="75176-126">*Resolve* パラメーターは、分割パスを表示するのではなく、分割パスによって参照される項目を表示するように **分割パス** に指示します。</span><span class="sxs-lookup"><span data-stu-id="75176-126">The *Resolve* parameter tells **Split-Path** to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="75176-127">すべての **分割パス** コマンドと同様に、このコマンドは文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="75176-127">Like all **Split-Path** commands, this command returns strings.</span></span>
<span data-ttu-id="75176-128">ファイルを表す **FileInfo** オブジェクトは返しません。</span><span class="sxs-lookup"><span data-stu-id="75176-128">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="75176-129">例 3: 親コンテナーを取得する</span><span class="sxs-lookup"><span data-stu-id="75176-129">Example 3: Get the parent container</span></span>

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="75176-130">このコマンドは、パスの親コンテナーだけを返します。</span><span class="sxs-lookup"><span data-stu-id="75176-130">This command returns only the parent containers of the path.</span></span>
<span data-ttu-id="75176-131">分割を指定するパラメーターが含まれていないため、分割 **パス** は、 *親* である分割位置の既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="75176-131">Because it does not include any parameters to specify the split, **Split-Path** uses the split location default, which is *Parent* .</span></span>

### <span data-ttu-id="75176-132">例 4: 絶対パスであるかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="75176-132">Example 4: Determines whether a path is absolute</span></span>

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

<span data-ttu-id="75176-133">このコマンドは、パスが相対パスと絶対パスのどちらであるかを特定します。</span><span class="sxs-lookup"><span data-stu-id="75176-133">This command determines whether the path is relative or absolute.</span></span>
<span data-ttu-id="75176-134">この場合、パスは、ドット (.) で表される現在のフォルダーに対する相対パスであるため、$False を返します。</span><span class="sxs-lookup"><span data-stu-id="75176-134">In this case, because the path is relative to the current folder, which is represented by a dot (.), it returns $False.</span></span>

### <span data-ttu-id="75176-135">例 5: 指定したパスに場所を変更する</span><span class="sxs-lookup"><span data-stu-id="75176-135">Example 5: Change location to a specified path</span></span>

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="75176-136">このコマンドは、PowerShell プロファイルが格納されているフォルダーに場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="75176-136">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="75176-137">かっこ内のコマンドは、 **分割パス** を使用して、組み込みの $Profile 変数に格納されているパスの親だけを返します。</span><span class="sxs-lookup"><span data-stu-id="75176-137">The command in parentheses uses **Split-Path** to return only the parent of the path stored in the built-in $Profile variable.</span></span>
<span data-ttu-id="75176-138">*親* パラメーターは、既定の分割位置パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="75176-138">The *Parent* parameter is the default split location parameter.</span></span>
<span data-ttu-id="75176-139">このため、コマンドから省略できます。</span><span class="sxs-lookup"><span data-stu-id="75176-139">Therefore, you can omit it from the command.</span></span>
<span data-ttu-id="75176-140">かっこでは、最初にコマンドを実行するように PowerShell を指示します。</span><span class="sxs-lookup"><span data-stu-id="75176-140">The parentheses direct PowerShell to run the command first.</span></span>
<span data-ttu-id="75176-141">これは、長いパス名を持つフォルダーに移動する場合に便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="75176-141">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="75176-142">例 6: パイプラインを使用してパスを分割する</span><span class="sxs-lookup"><span data-stu-id="75176-142">Example 6: Split a path by using the pipeline</span></span>

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="75176-143">このコマンドは、パイプライン演算子 (|) を使用して、パスを **分割パス** に送信します。</span><span class="sxs-lookup"><span data-stu-id="75176-143">This command uses a pipeline operator (|) to send a path to **Split-Path** .</span></span>
<span data-ttu-id="75176-144">パスを引用符で囲み、1 つのトークンであることを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-144">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="75176-145">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="75176-145">PARAMETERS</span></span>

### <span data-ttu-id="75176-146">-Credential</span><span class="sxs-lookup"><span data-stu-id="75176-146">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="75176-147">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="75176-147">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="75176-148">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="75176-148">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="75176-149">-拡張機能</span><span class="sxs-lookup"><span data-stu-id="75176-149">-Extension</span></span>

<span data-ttu-id="75176-150">このコマンドレットがリーフの拡張のみを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-150">Indicates that this cmdlet returns only the extension of the leaf.</span></span>
<span data-ttu-id="75176-151">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` のみが返さ `.log` れます。</span><span class="sxs-lookup"><span data-stu-id="75176-151">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `.log`.</span></span>

<span data-ttu-id="75176-152">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="75176-152">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75176-153">-IsAbsolute</span><span class="sxs-lookup"><span data-stu-id="75176-153">-IsAbsolute</span></span>

<span data-ttu-id="75176-154">このコマンドレットが絶対パスの場合に $True を返し、相対パスの場合は $False することを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-154">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span>
<span data-ttu-id="75176-155">絶対パスの長さはゼロより大きく、ドット (.) を使用して現在のパスを示すことはできません。</span><span class="sxs-lookup"><span data-stu-id="75176-155">An absolute path has a length greater than zero and does not use a dot (.) to indicate the current path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="75176-156">-リーフ</span><span class="sxs-lookup"><span data-stu-id="75176-156">-Leaf</span></span>

<span data-ttu-id="75176-157">このコマンドレットがパス内の最後の項目またはコンテナーだけを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-157">Indicates that this cmdlet returns only the last item or container in the path.</span></span>
<span data-ttu-id="75176-158">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` Pass1 のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="75176-158">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75176-159">-LeafBase</span><span class="sxs-lookup"><span data-stu-id="75176-159">-LeafBase</span></span>

<span data-ttu-id="75176-160">このコマンドレットがリーフの基本名だけを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-160">Indicates that this cmdlet returns only base name of the leaf.</span></span>
<span data-ttu-id="75176-161">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` のみが返さ `Pass1` れます。</span><span class="sxs-lookup"><span data-stu-id="75176-161">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `Pass1`.</span></span>

<span data-ttu-id="75176-162">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="75176-162">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75176-163">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="75176-163">-LiteralPath</span></span>

<span data-ttu-id="75176-164">分割するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="75176-164">Specifies the paths to be split.</span></span>
<span data-ttu-id="75176-165">*Path* とは異なり、 *LiteralPath* の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="75176-165">Unlike *Path* , the value of *LiteralPath* is used exactly as it is typed.</span></span>
<span data-ttu-id="75176-166">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="75176-166">No characters are interpreted as wildcard characters.</span></span>
<span data-ttu-id="75176-167">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="75176-167">If the path includes escape characters, enclose it in single quotation marks.</span></span>
<span data-ttu-id="75176-168">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="75176-168">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75176-169">-NoQualifier</span><span class="sxs-lookup"><span data-stu-id="75176-169">-NoQualifier</span></span>

<span data-ttu-id="75176-170">このコマンドレットが修飾子なしでパスを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-170">Indicates that this cmdlet returns the path without the qualifier.</span></span>
<span data-ttu-id="75176-171">FileSystem プロバイダーまたはレジストリ プロバイダーの場合、修飾子は、C: または HKCU: などの、プロバイダー パスのドライブです。</span><span class="sxs-lookup"><span data-stu-id="75176-171">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>
<span data-ttu-id="75176-172">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` \Test\Logs\Pass1.log. のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="75176-172">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only \Test\Logs\Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75176-173">-親</span><span class="sxs-lookup"><span data-stu-id="75176-173">-Parent</span></span>

<span data-ttu-id="75176-174">このコマンドレットが、パスで指定された項目またはコンテナーの親コンテナーだけを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-174">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span>
<span data-ttu-id="75176-175">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` C:\Test\Logs. が返されます。</span><span class="sxs-lookup"><span data-stu-id="75176-175">For example, in the path `C:\Test\Logs\Pass1.log`, it returns C:\Test\Logs.</span></span>
<span data-ttu-id="75176-176">*親* パラメーターは、既定の分割位置パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="75176-176">The *Parent* parameter is the default split location parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75176-177">-Path</span><span class="sxs-lookup"><span data-stu-id="75176-177">-Path</span></span>

<span data-ttu-id="75176-178">分割するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="75176-178">Specifies the paths to be split.</span></span>
<span data-ttu-id="75176-179">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="75176-179">Wildcard characters are permitted.</span></span>
<span data-ttu-id="75176-180">パスにスペースが含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="75176-180">If the path includes spaces, enclose it in quotation marks.</span></span>
<span data-ttu-id="75176-181">パイプを使用してこのコマンドレットへのパスをパイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="75176-181">You can also pipe a path to this cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ParentSet, LeafSet, LeafBaseSet, ExtensionSet, QualifierSet, NoQualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="75176-182">-修飾子</span><span class="sxs-lookup"><span data-stu-id="75176-182">-Qualifier</span></span>

<span data-ttu-id="75176-183">このコマンドレットが、指定されたパスの修飾子だけを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-183">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span>
<span data-ttu-id="75176-184">FileSystem プロバイダーまたはレジストリ プロバイダーの場合、修飾子は、C: または HKCU: などの、プロバイダー パスのドライブです。</span><span class="sxs-lookup"><span data-stu-id="75176-184">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as C: or HKCU:.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="75176-185">-解決</span><span class="sxs-lookup"><span data-stu-id="75176-185">-Resolve</span></span>

<span data-ttu-id="75176-186">このコマンドレットによって、パス要素を表示する代わりに、結果として得られる分割パスによって参照される項目が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="75176-186">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="75176-187">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="75176-187">CommonParameters</span></span>

<span data-ttu-id="75176-188">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="75176-188">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="75176-189">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75176-189">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="75176-190">入力</span><span class="sxs-lookup"><span data-stu-id="75176-190">INPUTS</span></span>

### <span data-ttu-id="75176-191">System.String</span><span class="sxs-lookup"><span data-stu-id="75176-191">System.String</span></span>

<span data-ttu-id="75176-192">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="75176-192">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="75176-193">出力</span><span class="sxs-lookup"><span data-stu-id="75176-193">OUTPUTS</span></span>

### <span data-ttu-id="75176-194">System.string、System.string</span><span class="sxs-lookup"><span data-stu-id="75176-194">System.String, System.Boolean</span></span>

<span data-ttu-id="75176-195">**分割パスは、** テキスト文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="75176-195">**Split-Path** returns text strings.</span></span>
<span data-ttu-id="75176-196">*Resolve* パラメーターを指定すると、 **分割パス** は項目の場所を説明する文字列を返します。 **FileInfo** や **RegistryKey** オブジェクトなど、アイテムを表すオブジェクトは返されません。</span><span class="sxs-lookup"><span data-stu-id="75176-196">When you specify the *Resolve* parameter, **Split-Path** returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="75176-197">*Isabsolute* パラメーターを指定すると、 **分割パス** は **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="75176-197">When you specify the *IsAbsolute* parameter, **Split-Path** returns a **Boolean** value.</span></span>

## <span data-ttu-id="75176-198">注</span><span class="sxs-lookup"><span data-stu-id="75176-198">NOTES</span></span>

* <span data-ttu-id="75176-199">分割位置パラメーター ( *Qualifier* 、 *Parent* 、 *Extension* 、 *リーフ* 、 *LeafBase* 、および *noqualifier* ) は排他的です。</span><span class="sxs-lookup"><span data-stu-id="75176-199">The split location parameters ( *Qualifier* , *Parent* , *Extension* , *Leaf* , *LeafBase* , and *NoQualifier* ) are exclusive.</span></span> <span data-ttu-id="75176-200">各コマンドでいずれか 1 つだけを使用できます。</span><span class="sxs-lookup"><span data-stu-id="75176-200">You can use only one in each command.</span></span>

  <span data-ttu-id="75176-201">**パスの名詞を** 含むコマンドレット ( **path** コマンドレット) は、パス名と共に使用され、すべての PowerShell プロバイダーが解釈できる簡潔な形式の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="75176-201">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span>
<span data-ttu-id="75176-202">プログラムやスクリプトで、パス名の全部または一部を特定の形式で表示するために使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="75176-202">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span>
<span data-ttu-id="75176-203">これらは、 **Dirname** 、 **Normpath** 、 **realpath** 、 **Join** 、またはその他のパスマニピュレーターを使用する方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="75176-203">Use them in the way that you would use **Dirname** , **Normpath** , **Realpath** , **Join** , or other path manipulators.</span></span>

  <span data-ttu-id="75176-204">**Path** コマンドレットは、いくつかのプロバイダーと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="75176-204">You can use the **Path** cmdlets together with several providers.</span></span>
<span data-ttu-id="75176-205">これには、ファイルシステム、レジストリ、および証明書プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="75176-205">These include the FileSystem, Registry, and Certificate providers.</span></span>

  <span data-ttu-id="75176-206">**分割パス** は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="75176-206">**Split-Path** is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="75176-207">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="75176-207">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="75176-208">詳細については、「about_Providers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75176-208">For more information, see about_Providers.</span></span>

## <span data-ttu-id="75176-209">関連リンク</span><span class="sxs-lookup"><span data-stu-id="75176-209">RELATED LINKS</span></span>

[<span data-ttu-id="75176-210">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="75176-210">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="75176-211">Join-Path</span><span class="sxs-lookup"><span data-stu-id="75176-211">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="75176-212">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="75176-212">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="75176-213">Test-Path</span><span class="sxs-lookup"><span data-stu-id="75176-213">Test-Path</span></span>](Test-Path.md)
