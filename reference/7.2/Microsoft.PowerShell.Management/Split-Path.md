---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: e2498c02d42123e207b49e622654d3cb881fc0fc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602418"
---
# <span data-ttu-id="a04ba-102">Split-Path</span><span class="sxs-lookup"><span data-stu-id="a04ba-102">Split-Path</span></span>

## <span data-ttu-id="a04ba-103">概要</span><span class="sxs-lookup"><span data-stu-id="a04ba-103">SYNOPSIS</span></span>
<span data-ttu-id="a04ba-104">指定されたパス部分を返します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-104">Returns the specified part of a path.</span></span>

## <span data-ttu-id="a04ba-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a04ba-105">SYNTAX</span></span>

### <span data-ttu-id="a04ba-106">ParentSet (既定値)</span><span class="sxs-lookup"><span data-stu-id="a04ba-106">ParentSet (Default)</span></span>

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="a04ba-107">LeafSet</span><span class="sxs-lookup"><span data-stu-id="a04ba-107">LeafSet</span></span>

```
Split-Path [-Path] <String[]> -Leaf [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

### <span data-ttu-id="a04ba-108">LeafBaseSet</span><span class="sxs-lookup"><span data-stu-id="a04ba-108">LeafBaseSet</span></span>

```
Split-Path [-Path] <String[]> -LeafBase [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="a04ba-109">ExtensionSet</span><span class="sxs-lookup"><span data-stu-id="a04ba-109">ExtensionSet</span></span>

```
Split-Path [-Path] <String[]> -Extension [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="a04ba-110">QualifierSet</span><span class="sxs-lookup"><span data-stu-id="a04ba-110">QualifierSet</span></span>

```
Split-Path [-Path] <String[]> -Qualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="a04ba-111">NoQualifierSet</span><span class="sxs-lookup"><span data-stu-id="a04ba-111">NoQualifierSet</span></span>

```
Split-Path [-Path] <String[]> -NoQualifier [-Resolve] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="a04ba-112">IsAbsoluteSet</span><span class="sxs-lookup"><span data-stu-id="a04ba-112">IsAbsoluteSet</span></span>

```
Split-Path [-Path] <String[]> [-Resolve] -IsAbsolute [-Credential <PSCredential>]
 [<CommonParameters>]
```

### <span data-ttu-id="a04ba-113">LiteralPathSet</span><span class="sxs-lookup"><span data-stu-id="a04ba-113">LiteralPathSet</span></span>

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="a04ba-114">Description</span><span class="sxs-lookup"><span data-stu-id="a04ba-114">DESCRIPTION</span></span>

<span data-ttu-id="a04ba-115">`Split-Path`このコマンドレットは、親フォルダー、サブフォルダー、ファイル名など、指定されたパスの部分のみを返します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-115">The `Split-Path` cmdlet returns only the specified part of a path, such as the parent folder, a subfolder, or a file name.</span></span> <span data-ttu-id="a04ba-116">また、分割されたパスで参照されている項目を取得したり、パスが相対パスか絶対パスかを判断したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-116">It can also get items that are referenced by the split path and tell whether the path is relative or absolute.</span></span>

<span data-ttu-id="a04ba-117">このコマンドレットを使用すると、選択したパスの一部だけを取得または送信できます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-117">You can use this cmdlet to get or submit only a selected part of a path.</span></span>

## <span data-ttu-id="a04ba-118">例</span><span class="sxs-lookup"><span data-stu-id="a04ba-118">EXAMPLES</span></span>

### <span data-ttu-id="a04ba-119">例 1: パスの修飾子を取得する</span><span class="sxs-lookup"><span data-stu-id="a04ba-119">Example 1: Get the qualifier of a path</span></span>

```powershell
Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
```

```Output
HKCU:
```

<span data-ttu-id="a04ba-120">このコマンドは、パスの修飾子だけを返します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-120">This command returns only the qualifier of the path.</span></span> <span data-ttu-id="a04ba-121">修飾子はドライブです。</span><span class="sxs-lookup"><span data-stu-id="a04ba-121">The qualifier is the drive.</span></span>

### <span data-ttu-id="a04ba-122">例 2: ファイル名を表示する</span><span class="sxs-lookup"><span data-stu-id="a04ba-122">Example 2: Display file names</span></span>

```powershell
Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
```

```Output
Pass1.log
Pass2.log
...
```

<span data-ttu-id="a04ba-123">このコマンドを実行すると、分割されたパスが参照しているファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-123">This command displays the files that are referenced by the split path.</span></span> <span data-ttu-id="a04ba-124">このパスは最後の項目 (リーフとも呼ばれます) に分割されるので、コマンドはファイル名のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-124">Because this path is split to the last item, also known as the leaf, the command displays only the file names.</span></span>

<span data-ttu-id="a04ba-125">**Resolve** パラメーターは、分割パスを表示 `Split-Path` するのではなく、分割パスによって参照される項目を表示するように指示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-125">The **Resolve** parameter tells `Split-Path` to display the items that the split path references, instead of displaying the split path.</span></span>

<span data-ttu-id="a04ba-126">すべて `Split-Path` のコマンドと同様に、このコマンドは文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-126">Like all `Split-Path` commands, this command returns strings.</span></span> <span data-ttu-id="a04ba-127">ファイルを表す **FileInfo** オブジェクトは返しません。</span><span class="sxs-lookup"><span data-stu-id="a04ba-127">It does not return **FileInfo** objects that represent the files.</span></span>

### <span data-ttu-id="a04ba-128">例 3: 親コンテナーを取得する</span><span class="sxs-lookup"><span data-stu-id="a04ba-128">Example 3: Get the parent container</span></span>

```powershell
Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
```

```Output
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

<span data-ttu-id="a04ba-129">このコマンドは、パスの親コンテナーだけを返します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-129">This command returns only the parent containers of the path.</span></span> <span data-ttu-id="a04ba-130">分割を指定するパラメーターが含まれていないので、で `Split-Path` は、 **親** である分割位置の既定値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-130">Because it does not include any parameters to specify the split, `Split-Path` uses the split location default, which is **Parent**.</span></span>

### <span data-ttu-id="a04ba-131">例 4: 絶対パスであるかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="a04ba-131">Example 4: Determines whether a path is absolute</span></span>

```powershell
Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
```

```Output
False
```

<span data-ttu-id="a04ba-132">このコマンドは、パスが相対パスと絶対パスのどちらであるかを特定します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-132">This command determines whether the path is relative or absolute.</span></span> <span data-ttu-id="a04ba-133">この場合、パスはドット () で表される現在のフォルダーに対して相対的であるため、 `.` を返し `$False` ます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-133">In this case, because the path is relative to the current folder, which is represented by a dot (`.`), it returns `$False`.</span></span>

### <span data-ttu-id="a04ba-134">例 5: 指定したパスに場所を変更する</span><span class="sxs-lookup"><span data-stu-id="a04ba-134">Example 5: Change location to a specified path</span></span>

```powershell
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

<span data-ttu-id="a04ba-135">このコマンドは、PowerShell プロファイルが格納されているフォルダーに場所を変更します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-135">This command changes your location to the folder that contains the PowerShell profile.</span></span>

<span data-ttu-id="a04ba-136">かっこ内のコマンドは、を使用して、 `Split-Path` 組み込み変数に格納されているパスの親だけを返し `$Profile` ます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-136">The command in parentheses uses `Split-Path` to return only the parent of the path stored in the built-in `$Profile` variable.</span></span> <span data-ttu-id="a04ba-137">**親** パラメーターは、既定の分割位置パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a04ba-137">The **Parent** parameter is the default split location parameter.</span></span>
<span data-ttu-id="a04ba-138">このため、コマンドから省略できます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-138">Therefore, you can omit it from the command.</span></span> <span data-ttu-id="a04ba-139">かっこでは、最初にコマンドを実行するように PowerShell を指示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-139">The parentheses direct PowerShell to run the command first.</span></span> <span data-ttu-id="a04ba-140">これは、長いパス名を持つフォルダーに移動する場合に便利な方法です。</span><span class="sxs-lookup"><span data-stu-id="a04ba-140">This is a useful way to move to a folder that has a long path name.</span></span>

### <span data-ttu-id="a04ba-141">例 6: パイプラインを使用してパスを分割する</span><span class="sxs-lookup"><span data-stu-id="a04ba-141">Example 6: Split a path by using the pipeline</span></span>

```powershell
'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
```

```Output
C:\Documents and Settings\User01\My Documents
```

<span data-ttu-id="a04ba-142">このコマンドは、パイプライン演算子 () を使用して、 `|` パスをに送信 `Split-Path` します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-142">This command uses a pipeline operator (`|`) to send a path to `Split-Path`.</span></span> <span data-ttu-id="a04ba-143">パスを引用符で囲み、1 つのトークンであることを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-143">The path is enclosed in quotation marks to indicate that it is a single token.</span></span>

## <span data-ttu-id="a04ba-144">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a04ba-144">PARAMETERS</span></span>

### <span data-ttu-id="a04ba-145">-Credential</span><span class="sxs-lookup"><span data-stu-id="a04ba-145">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="a04ba-146">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a04ba-146">This parameter is not supported by any providers installed with PowerShell.</span></span> <span data-ttu-id="a04ba-147">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-147">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="a04ba-148">-拡張機能</span><span class="sxs-lookup"><span data-stu-id="a04ba-148">-Extension</span></span>

<span data-ttu-id="a04ba-149">このコマンドレットがリーフの拡張のみを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-149">Indicates that this cmdlet returns only the extension of the leaf.</span></span> <span data-ttu-id="a04ba-150">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` のみが返さ `.log` れます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-150">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `.log`.</span></span>

<span data-ttu-id="a04ba-151">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a04ba-151">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ExtensionSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a04ba-152">-IsAbsolute</span><span class="sxs-lookup"><span data-stu-id="a04ba-152">-IsAbsolute</span></span>

<span data-ttu-id="a04ba-153">このコマンドレットが絶対パスの場合に $True を返し、相対パスの場合は $False することを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-153">Indicates that this cmdlet returns $True if the path is absolute and $False if it is relative.</span></span> <span data-ttu-id="a04ba-154">絶対パスの長さはゼロより大きく、ドット () を使用して `.` 現在のパスを示すことはできません。</span><span class="sxs-lookup"><span data-stu-id="a04ba-154">An absolute path has a length greater than zero and does not use a dot (`.`) to indicate the current path.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="a04ba-155">-リーフ</span><span class="sxs-lookup"><span data-stu-id="a04ba-155">-Leaf</span></span>

<span data-ttu-id="a04ba-156">このコマンドレットがパス内の最後の項目またはコンテナーだけを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-156">Indicates that this cmdlet returns only the last item or container in the path.</span></span> <span data-ttu-id="a04ba-157">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` Pass1 のみが返されます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-157">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only Pass1.log.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a04ba-158">-LeafBase</span><span class="sxs-lookup"><span data-stu-id="a04ba-158">-LeafBase</span></span>

<span data-ttu-id="a04ba-159">このコマンドレットがリーフの基本名だけを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-159">Indicates that this cmdlet returns only base name of the leaf.</span></span> <span data-ttu-id="a04ba-160">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` のみが返さ `Pass1` れます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-160">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `Pass1`.</span></span>

<span data-ttu-id="a04ba-161">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="a04ba-161">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafBaseSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a04ba-162">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="a04ba-162">-LiteralPath</span></span>

<span data-ttu-id="a04ba-163">分割するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-163">Specifies the paths to be split.</span></span> <span data-ttu-id="a04ba-164">**Path** とは異なり、**LiteralPath** の値は入力した内容のまま使用されます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-164">Unlike **Path**, the value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="a04ba-165">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="a04ba-165">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="a04ba-166">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-166">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="a04ba-167">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="a04ba-167">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="a04ba-168">-NoQualifier</span><span class="sxs-lookup"><span data-stu-id="a04ba-168">-NoQualifier</span></span>

<span data-ttu-id="a04ba-169">このコマンドレットが修飾子なしでパスを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-169">Indicates that this cmdlet returns the path without the qualifier.</span></span> <span data-ttu-id="a04ba-170">ファイルシステムまたはレジストリプロバイダーの場合、修飾子はやなどのプロバイダーパスのドライブです `C:` `HKCU:` 。</span><span class="sxs-lookup"><span data-stu-id="a04ba-170">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`.</span></span> <span data-ttu-id="a04ba-171">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` のみが返さ `\Test\Logs\Pass1.log` れます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-171">For example, in the path `C:\Test\Logs\Pass1.log`, it returns only `\Test\Logs\Pass1.log`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a04ba-172">-親</span><span class="sxs-lookup"><span data-stu-id="a04ba-172">-Parent</span></span>

<span data-ttu-id="a04ba-173">このコマンドレットが、パスで指定された項目またはコンテナーの親コンテナーだけを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-173">Indicates that this cmdlet returns only the parent containers of the item or of the container specified by the path.</span></span> <span data-ttu-id="a04ba-174">たとえば、パスでは、 `C:\Test\Logs\Pass1.log` が返さ `C:\Test\Logs` れます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-174">For example, in the path `C:\Test\Logs\Pass1.log`, it returns `C:\Test\Logs`.</span></span>
<span data-ttu-id="a04ba-175">**親** パラメーターは、既定の分割位置パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="a04ba-175">The **Parent** parameter is the default split location parameter.</span></span>

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

### <span data-ttu-id="a04ba-176">-Path</span><span class="sxs-lookup"><span data-stu-id="a04ba-176">-Path</span></span>

<span data-ttu-id="a04ba-177">分割するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-177">Specifies the paths to be split.</span></span> <span data-ttu-id="a04ba-178">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-178">Wildcard characters are permitted.</span></span> <span data-ttu-id="a04ba-179">パスにスペースが含まれる場合は、二重引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-179">If the path includes spaces, enclose it in quotation marks.</span></span> <span data-ttu-id="a04ba-180">パイプを使用してこのコマンドレットへのパスをパイプすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-180">You can also pipe a path to this cmdlet.</span></span>

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

### <span data-ttu-id="a04ba-181">-修飾子</span><span class="sxs-lookup"><span data-stu-id="a04ba-181">-Qualifier</span></span>

<span data-ttu-id="a04ba-182">このコマンドレットが、指定されたパスの修飾子だけを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-182">Indicates that this cmdlet returns only the qualifier of the specified path.</span></span> <span data-ttu-id="a04ba-183">ファイルシステムまたはレジストリプロバイダーの場合、修飾子はやなどのプロバイダーパスのドライブです `C:` `HKCU:` 。</span><span class="sxs-lookup"><span data-stu-id="a04ba-183">For the FileSystem or registry providers, the qualifier is the drive of the provider path, such as `C:` or `HKCU:`.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="a04ba-184">-解決</span><span class="sxs-lookup"><span data-stu-id="a04ba-184">-Resolve</span></span>

<span data-ttu-id="a04ba-185">このコマンドレットによって、パス要素を表示する代わりに、結果として得られる分割パスによって参照される項目が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-185">Indicates that this cmdlet displays the items that are referenced by the resulting split path instead of displaying the path elements.</span></span>

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

### <span data-ttu-id="a04ba-186">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="a04ba-186">CommonParameters</span></span>

<span data-ttu-id="a04ba-187">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="a04ba-187">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a04ba-188">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a04ba-188">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a04ba-189">入力</span><span class="sxs-lookup"><span data-stu-id="a04ba-189">INPUTS</span></span>

### <span data-ttu-id="a04ba-190">System.String</span><span class="sxs-lookup"><span data-stu-id="a04ba-190">System.String</span></span>

<span data-ttu-id="a04ba-191">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-191">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="a04ba-192">出力</span><span class="sxs-lookup"><span data-stu-id="a04ba-192">OUTPUTS</span></span>

### <span data-ttu-id="a04ba-193">System.string、System.string</span><span class="sxs-lookup"><span data-stu-id="a04ba-193">System.String, System.Boolean</span></span>

<span data-ttu-id="a04ba-194">`Split-Path` 文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-194">`Split-Path` returns text strings.</span></span> <span data-ttu-id="a04ba-195">**Resolve** パラメーターを指定すると、は `Split-Path` 項目の場所を説明する文字列を返します。 **FileInfo** や **RegistryKey** オブジェクトなどの項目を表すオブジェクトは返しません。</span><span class="sxs-lookup"><span data-stu-id="a04ba-195">When you specify the **Resolve** parameter, `Split-Path` returns a string that describes the location of the items; it does not return objects that represent the items, such as a **FileInfo** or **RegistryKey** object.</span></span>

<span data-ttu-id="a04ba-196">**Isabsolute** パラメーターを指定すると、は `Split-Path` **ブール** 値を返します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-196">When you specify the **IsAbsolute** parameter, `Split-Path` returns a **Boolean** value.</span></span>

## <span data-ttu-id="a04ba-197">注</span><span class="sxs-lookup"><span data-stu-id="a04ba-197">NOTES</span></span>

- <span data-ttu-id="a04ba-198">分割位置パラメーター (**Qualifier**、 **Parent**、 **Extension**、 **リーフ**、 **LeafBase**、および **noqualifier**) は排他的です。</span><span class="sxs-lookup"><span data-stu-id="a04ba-198">The split location parameters (**Qualifier**, **Parent**, **Extension**, **Leaf**, **LeafBase**, and **NoQualifier**) are exclusive.</span></span> <span data-ttu-id="a04ba-199">各コマンドでいずれか 1 つだけを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-199">You can use only one in each command.</span></span>

- <span data-ttu-id="a04ba-200">**パスの名詞を** 含むコマンドレット ( **path** コマンドレット) は、パス名と共に使用され、すべての PowerShell プロバイダーが解釈できる簡潔な形式の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-200">The cmdlets that contain the **Path** noun (the **Path** cmdlets) work with path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="a04ba-201">プログラムやスクリプトで、パス名の全部または一部を特定の形式で表示するために使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="a04ba-201">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="a04ba-202">これらは、 **Dirname**、 **Normpath**、 **realpath**、 **Join**、またはその他のパスマニピュレーターを使用する方法で使用します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-202">Use them in the way that you would use **Dirname**, **Normpath**, **Realpath**, **Join**, or other path manipulators.</span></span>

- <span data-ttu-id="a04ba-203">**Path** コマンドレットは、いくつかのプロバイダーと共に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-203">You can use the **Path** cmdlets together with several providers.</span></span> <span data-ttu-id="a04ba-204">これには、ファイルシステム、レジストリ、および証明書プロバイダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a04ba-204">These include the FileSystem, Registry, and Certificate providers.</span></span>

- <span data-ttu-id="a04ba-205">`Split-Path` は、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a04ba-205">`Split-Path` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="a04ba-206">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="a04ba-206">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="a04ba-207">詳細については、「about_Providers」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a04ba-207">For more information, see about_Providers.</span></span>

## <span data-ttu-id="a04ba-208">関連リンク</span><span class="sxs-lookup"><span data-stu-id="a04ba-208">RELATED LINKS</span></span>

[<span data-ttu-id="a04ba-209">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="a04ba-209">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="a04ba-210">Join-Path</span><span class="sxs-lookup"><span data-stu-id="a04ba-210">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="a04ba-211">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="a04ba-211">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="a04ba-212">Test-Path</span><span class="sxs-lookup"><span data-stu-id="a04ba-212">Test-Path</span></span>](Test-Path.md)
