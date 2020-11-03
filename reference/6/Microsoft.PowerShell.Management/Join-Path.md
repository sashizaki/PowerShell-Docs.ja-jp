---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/join-path?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Join-Path
ms.openlocfilehash: 7752688a04057861fffdbc7b30c293239acb132e
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213192"
---
# <span data-ttu-id="d7376-103">Join-Path</span><span class="sxs-lookup"><span data-stu-id="d7376-103">Join-Path</span></span>

## <span data-ttu-id="d7376-104">概要</span><span class="sxs-lookup"><span data-stu-id="d7376-104">SYNOPSIS</span></span>
<span data-ttu-id="d7376-105">パスと子パスを 1 つのパスに結合します。</span><span class="sxs-lookup"><span data-stu-id="d7376-105">Combines a path and a child path into a single path.</span></span>

## <span data-ttu-id="d7376-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d7376-106">SYNTAX</span></span>

```
Join-Path [-Path] <String[]> [-ChildPath] <String> [[-AdditionalChildPath] <String[]>] [-Resolve]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## <span data-ttu-id="d7376-107">Description</span><span class="sxs-lookup"><span data-stu-id="d7376-107">DESCRIPTION</span></span>

<span data-ttu-id="d7376-108">コマンドレットでは、 `Join-Path` パスと子パスを1つのパスに結合します。</span><span class="sxs-lookup"><span data-stu-id="d7376-108">The `Join-Path` cmdlet combines a path and child-path into a single path.</span></span>
<span data-ttu-id="d7376-109">パスの区切り記号はプロバイダーによって追加されます。</span><span class="sxs-lookup"><span data-stu-id="d7376-109">The provider supplies the path delimiters.</span></span>

## <span data-ttu-id="d7376-110">例</span><span class="sxs-lookup"><span data-stu-id="d7376-110">EXAMPLES</span></span>

### <span data-ttu-id="d7376-111">例 1: パスと子パスを結合する</span><span class="sxs-lookup"><span data-stu-id="d7376-111">Example 1: Combine a path with a child path</span></span>

```powershell
PS C:\> Join-Path -Path "path" -ChildPath "childpath"
```

```output
path\childpath
```

<span data-ttu-id="d7376-112">このコマンドは、を使用し `Join-Path` てパスを childpath と結合します。</span><span class="sxs-lookup"><span data-stu-id="d7376-112">This command uses `Join-Path` to combine a path with a childpath.</span></span>

<span data-ttu-id="d7376-113">コマンドはプロバイダーから実行されるため、 `FileSystem` `\` パスを結合するための区切り記号を提供します。</span><span class="sxs-lookup"><span data-stu-id="d7376-113">Since the command is executed from the `FileSystem` provider, it provides the `\` delimiter to join the paths.</span></span>

### <span data-ttu-id="d7376-114">例 2: ディレクトリの区切り記号が既に含まれているパスを結合する</span><span class="sxs-lookup"><span data-stu-id="d7376-114">Example 2: Combine paths that already contain directory separators</span></span>

```powershell
PS C:\> Join-Path -Path "path\" -ChildPath "\childpath"
```

```output
path\childpath
```

<span data-ttu-id="d7376-115">既存のディレクトリの区切り記号 `\` と処理されるため `Path` 、との間に区切り記号が1つだけ存在します。 `ChildPath`</span><span class="sxs-lookup"><span data-stu-id="d7376-115">Existing directory separators `\` and handled so there is only one separator between `Path` and `ChildPath`</span></span>

### <span data-ttu-id="d7376-116">例 3: 子パスをパスに結合してファイルとフォルダーを表示する</span><span class="sxs-lookup"><span data-stu-id="d7376-116">Example 3: Display files and folders by joining a path with a child path</span></span>

```powershell
Join-Path "C:\win*" "System*" -Resolve
```

<span data-ttu-id="d7376-117">このコマンドは、C:\ Win \* パスと System 子パスを結合することによって参照されるファイルとフォルダーを表示し \* ます。</span><span class="sxs-lookup"><span data-stu-id="d7376-117">This command displays the files and folders that are referenced by joining the C:\Win\* path and the System\* child path.</span></span>
<span data-ttu-id="d7376-118">と同じファイルおよびフォルダーが表示され `Get-ChildItem` ますが、各項目の完全修飾パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d7376-118">It displays the same files and folders as `Get-ChildItem`, but it displays the fully qualified path to each item.</span></span>
<span data-ttu-id="d7376-119">このコマンドでは、 `Path` および `ChildPath` 省略可能なパラメーター名は省略されています。</span><span class="sxs-lookup"><span data-stu-id="d7376-119">In this command, the `Path` and `ChildPath` optional parameter names are omitted.</span></span>

### <span data-ttu-id="d7376-120">例 4: PowerShell レジストリプロバイダーで Join-Path を使用する</span><span class="sxs-lookup"><span data-stu-id="d7376-120">Example 4: Use Join-Path with the PowerShell registry provider</span></span>

```powershell
PS HKLM:\> Join-Path -Path System -ChildPath *ControlSet* -Resolve
```

```output
HKLM:\System\ControlSet001
HKLM:\System\CurrentControlSet
```

<span data-ttu-id="d7376-121">このコマンドを実行すると、 `HKLM\System` を含むレジストリサブキーのレジストリキーが表示され `ControlSet` ます。</span><span class="sxs-lookup"><span data-stu-id="d7376-121">This command displays the registry keys in the `HKLM\System` registry subkey that include `ControlSet`.</span></span>

<span data-ttu-id="d7376-122">パラメーターは、 `Resolve` 現在のプロバイダーパスのワイルドカードを含む、結合されたパスの解決を試みます。 `HKLM:\`</span><span class="sxs-lookup"><span data-stu-id="d7376-122">The `Resolve` parameter, attempts to resolve the joined path, including wildcards from the current provider path `HKLM:\`</span></span>

### <span data-ttu-id="d7376-123">例 5: 複数のパスルートと子パスを結合する</span><span class="sxs-lookup"><span data-stu-id="d7376-123">Example 5: Combine multiple path roots with a child path</span></span>

```powershell
Join-Path -Path C:, D:, E:, F: -ChildPath New
```

```output
C:\New
D:\New
E:\New
F:\New
```

<span data-ttu-id="d7376-124">このコマンドは `Join-Path` 、を使用して、複数のパスルートと子パスを結合します。</span><span class="sxs-lookup"><span data-stu-id="d7376-124">This command uses `Join-Path` to combine multiple path roots with a child path.</span></span>

> [!NOTE]
> <span data-ttu-id="d7376-125">によって指定されたドライブ `Path` が存在する必要があります。存在しない場合、そのエントリの結合は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d7376-125">The Drives specified by `Path` must exist or the join of that entry will fail.</span></span>

### <span data-ttu-id="d7376-126">例 6: ファイルシステムドライブのルートと子パスを結合する</span><span class="sxs-lookup"><span data-stu-id="d7376-126">Example 6: Combine the roots of a file system drive with a child path</span></span>

```powershell
Get-PSDrive -PSProvider filesystem | ForEach-Object {$_.root} | Join-Path -ChildPath "Subdir"
```

```output
C:\Subdir
D:\Subdir
```

<span data-ttu-id="d7376-127">このコマンドは、コンソールの各 PowerShell ファイルシステムドライブのルートと Subdir 子パスを結合します。</span><span class="sxs-lookup"><span data-stu-id="d7376-127">This command combines the roots of each PowerShell file system drive in the console with the Subdir child path.</span></span>

<span data-ttu-id="d7376-128">このコマンドは、コマンドレットを使用して、 `Get-PSDrive` FileSystem プロバイダーによってサポートされる PowerShell ドライブを取得します。</span><span class="sxs-lookup"><span data-stu-id="d7376-128">The command uses the `Get-PSDrive` cmdlet to get the PowerShell drives supported by the FileSystem provider.</span></span>
<span data-ttu-id="d7376-129">ステートメントは、 `ForEach-Object` オブジェクトの Root プロパティのみ `PSDriveInfo` を選択し、指定された子パスと結合します。</span><span class="sxs-lookup"><span data-stu-id="d7376-129">The `ForEach-Object` statement selects only the Root property of the `PSDriveInfo` objects and combines it with the specified child path.</span></span>

<span data-ttu-id="d7376-130">出力には、コンピューター上の PowerShell ドライブに、C:\Program Files ディレクトリにマップされたドライブが含まれていることが示されています。</span><span class="sxs-lookup"><span data-stu-id="d7376-130">The output shows that the PowerShell drives on the computer included a drive mapped to the C:\Program Files directory.</span></span>

### <span data-ttu-id="d7376-131">例 7: 不特定数のパスを結合する</span><span class="sxs-lookup"><span data-stu-id="d7376-131">Example 7: Combine an indefinite number of paths</span></span>

```powershell
Join-Path a b c d e f g
```

```Output
a\b\c\d\e\f\g
```

<span data-ttu-id="d7376-132">パラメーターを使用すると `AdditionalChildPath` 、無制限の数のパスを結合できます。</span><span class="sxs-lookup"><span data-stu-id="d7376-132">The `AdditionalChildPath` parameter allows the joining of an unlimited number of paths.</span></span>

<span data-ttu-id="d7376-133">この例では、パラメーター名が使用されていないため、" `Path` b" と " `ChildPath` c-g" をにバインドします。 `AdditionalChildPath`</span><span class="sxs-lookup"><span data-stu-id="d7376-133">In this example, no parameter names are used, thus "a" binds to `Path`, "b" to `ChildPath` and "c-g" to `AdditionalChildPath`</span></span>

## <span data-ttu-id="d7376-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d7376-134">PARAMETERS</span></span>

### <span data-ttu-id="d7376-135">-AdditionalChildPath</span><span class="sxs-lookup"><span data-stu-id="d7376-135">-AdditionalChildPath</span></span>

<span data-ttu-id="d7376-136">*Path* パラメーターの値に追加する要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="d7376-136">Specifies additional elements to append to the value of the *Path* parameter.</span></span> <span data-ttu-id="d7376-137">`ChildPath`パラメーターは必須ですが、指定する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="d7376-137">The `ChildPath` parameter is still mandatory and must be specified as well.</span></span>

<span data-ttu-id="d7376-138">このパラメーターは、 `ValueFromRemainingArguments` 不特定数のパスに参加できるようにするプロパティで指定します。</span><span class="sxs-lookup"><span data-stu-id="d7376-138">This parameter is specified with the `ValueFromRemainingArguments` property which enables joining an indefinite number of paths.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d7376-139">-ChildPath</span><span class="sxs-lookup"><span data-stu-id="d7376-139">-ChildPath</span></span>

<span data-ttu-id="d7376-140">パラメーターの値に追加する要素を指定し `Path` ます。</span><span class="sxs-lookup"><span data-stu-id="d7376-140">Specifies the elements to append to the value of the `Path` parameter.</span></span>
<span data-ttu-id="d7376-141">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7376-141">Wildcards are permitted.</span></span>
<span data-ttu-id="d7376-142">パラメーター `ChildPath` は必須ですが、パラメーター名 ("ChildPath") は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d7376-142">The `ChildPath` parameter is required, although the parameter name ("ChildPath") is optional.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="d7376-143">-Credential</span><span class="sxs-lookup"><span data-stu-id="d7376-143">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d7376-144">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d7376-144">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d7376-145">別のユーザーの権限を借用したり、このコマンドレットの実行時に資格情報を昇格させたりするには、 [Invoke コマンド](../Microsoft.PowerShell.Core/Invoke-Command.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7376-145">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

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

### <span data-ttu-id="d7376-146">-Path</span><span class="sxs-lookup"><span data-stu-id="d7376-146">-Path</span></span>

<span data-ttu-id="d7376-147">子パスを追加するメイン パスを 1 つ以上指定します。</span><span class="sxs-lookup"><span data-stu-id="d7376-147">Specifies the main path (or paths) to which the child-path is appended.</span></span>
<span data-ttu-id="d7376-148">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d7376-148">Wildcards are permitted.</span></span>

<span data-ttu-id="d7376-149">の値によって、 `Path` どのプロバイダーがパスを結合し、パスの区切り記号が追加されます。</span><span class="sxs-lookup"><span data-stu-id="d7376-149">The value of `Path` determines which provider joins the paths and adds the path delimiters.</span></span>
<span data-ttu-id="d7376-150">パラメーター `Path` は必須ですが、パラメーター名 ("Path") は省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d7376-150">The `Path` parameter is required, although the parameter name ("Path") is optional.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSPath

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d7376-151">-解決</span><span class="sxs-lookup"><span data-stu-id="d7376-151">-Resolve</span></span>

<span data-ttu-id="d7376-152">このコマンドレットが、現在のプロバイダーからの結合されたパスを解決しようとすることを示します。</span><span class="sxs-lookup"><span data-stu-id="d7376-152">Indicates that this cmdlet should attempt to resolve the joined path from the current provider.</span></span>

- <span data-ttu-id="d7376-153">ワイルドカードを使用すると、コマンドレットは、結合されたパスに一致するすべてのパスを返します。</span><span class="sxs-lookup"><span data-stu-id="d7376-153">If wildcards are used, the cmdlet returns all paths that match the joined path.</span></span>
- <span data-ttu-id="d7376-154">ワイルドカードが使用されて **いない場合** 、パスが存在しない場合は、コマンドレットでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d7376-154">If **no** wildcards are used, the cmdlet will error if the path does not exist.</span></span>

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

### <span data-ttu-id="d7376-155">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d7376-155">CommonParameters</span></span>

<span data-ttu-id="d7376-156">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d7376-156">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d7376-157">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7376-157">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d7376-158">入力</span><span class="sxs-lookup"><span data-stu-id="d7376-158">INPUTS</span></span>

### <span data-ttu-id="d7376-159">System.String</span><span class="sxs-lookup"><span data-stu-id="d7376-159">System.String</span></span>

<span data-ttu-id="d7376-160">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="d7376-160">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="d7376-161">出力</span><span class="sxs-lookup"><span data-stu-id="d7376-161">OUTPUTS</span></span>

### <span data-ttu-id="d7376-162">System.String</span><span class="sxs-lookup"><span data-stu-id="d7376-162">System.String</span></span>

<span data-ttu-id="d7376-163">このコマンドレットは、結果として得られるパスを含む文字列を返します。</span><span class="sxs-lookup"><span data-stu-id="d7376-163">This cmdlet returns a string that contains the resulting path.</span></span>

## <span data-ttu-id="d7376-164">注</span><span class="sxs-lookup"><span data-stu-id="d7376-164">NOTES</span></span>

<span data-ttu-id="d7376-165">パスの名詞を含むコマンドレット (Path コマンドレット) は、パス名を操作し、すべての PowerShell プロバイダーが解釈できる簡潔な形式の名前を返します。</span><span class="sxs-lookup"><span data-stu-id="d7376-165">The cmdlets that contain the Path noun (the Path cmdlets) manipulate path names and return the names in a concise format that all PowerShell providers can interpret.</span></span> <span data-ttu-id="d7376-166">プログラムやスクリプトで、パス名の全部または一部を特定の形式で表示するために使用することを目的としています。</span><span class="sxs-lookup"><span data-stu-id="d7376-166">They are designed for use in programs and scripts where you want to display all or part of a path name in a particular format.</span></span> <span data-ttu-id="d7376-167">Dirname、Normpath、Realpath、Join など、他のパス操作コマンドレットと同じように使用します。</span><span class="sxs-lookup"><span data-stu-id="d7376-167">Use them like you would use Dirname, Normpath, Realpath, Join, or other path manipulators.</span></span>

<span data-ttu-id="d7376-168">Path コマンドレットは、、、およびプロバイダーを含むいくつかのプロバイダーで使用でき `FileSystem` `Registry` `Certificate` ます。</span><span class="sxs-lookup"><span data-stu-id="d7376-168">You can use the path cmdlets with several providers, including the `FileSystem`, `Registry`, and `Certificate` providers.</span></span>

<span data-ttu-id="d7376-169">このコマンドレットは、プロバイダーによって公開されるデータを使用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="d7376-169">This cmdlet is designed to work with the data exposed by any provider.</span></span>
<span data-ttu-id="d7376-170">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="d7376-170">To list the providers available in your session, type `Get-PSProvider`.</span></span>
<span data-ttu-id="d7376-171">詳細については、「[about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7376-171">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d7376-172">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d7376-172">RELATED LINKS</span></span>

[<span data-ttu-id="d7376-173">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="d7376-173">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="d7376-174">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="d7376-174">Resolve-Path</span></span>](Resolve-Path.md)

[<span data-ttu-id="d7376-175">Split-Path</span><span class="sxs-lookup"><span data-stu-id="d7376-175">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="d7376-176">Test-Path</span><span class="sxs-lookup"><span data-stu-id="d7376-176">Test-Path</span></span>](Test-Path.md)

[<span data-ttu-id="d7376-177">Get-PSProvider</span><span class="sxs-lookup"><span data-stu-id="d7376-177">Get-PSProvider</span></span>](Get-PSProvider.md)

[<span data-ttu-id="d7376-178">Get-ChildItem</span><span class="sxs-lookup"><span data-stu-id="d7376-178">Get-ChildItem</span></span>](Get-ChildItem.md)

[<span data-ttu-id="d7376-179">Get-PSDrive</span><span class="sxs-lookup"><span data-stu-id="d7376-179">Get-PSDrive</span></span>](Get-PSDrive.md)
