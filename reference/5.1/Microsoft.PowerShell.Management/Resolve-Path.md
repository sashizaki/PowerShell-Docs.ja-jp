---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 03/12/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/resolve-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Resolve-Path
ms.openlocfilehash: a48f2c5f62990258f14195eda934bbf4bbe589a1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214483"
---
# <span data-ttu-id="e6880-103">Resolve-Path</span><span class="sxs-lookup"><span data-stu-id="e6880-103">Resolve-Path</span></span>

## <span data-ttu-id="e6880-104">概要</span><span class="sxs-lookup"><span data-stu-id="e6880-104">SYNOPSIS</span></span>
<span data-ttu-id="e6880-105">パス中のワイルドカード文字を解決し、パスの内容を表示します。</span><span class="sxs-lookup"><span data-stu-id="e6880-105">Resolves the wildcard characters in a path, and displays the path contents.</span></span>

## <span data-ttu-id="e6880-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e6880-106">SYNTAX</span></span>

### <span data-ttu-id="e6880-107">パス (既定値)</span><span class="sxs-lookup"><span data-stu-id="e6880-107">Path (Default)</span></span>

```
Resolve-Path [-Path] <String[]> [-Relative] [-Credential <PSCredential>] [-UseTransaction] [<CommonParameters>]
```

### <span data-ttu-id="e6880-108">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e6880-108">LiteralPath</span></span>

```
Resolve-Path -LiteralPath <String[]> [-Relative] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## <span data-ttu-id="e6880-109">Description</span><span class="sxs-lookup"><span data-stu-id="e6880-109">DESCRIPTION</span></span>

<span data-ttu-id="e6880-110">`Resolve-Path`コマンドレットは、指定された場所にあるワイルドカードパターンに一致する項目とコンテナーを表示します。</span><span class="sxs-lookup"><span data-stu-id="e6880-110">The `Resolve-Path` cmdlet displays the items and containers that match the wildcard pattern at the location specified.</span></span> <span data-ttu-id="e6880-111">一致には、ファイル、フォルダー、レジストリキー、または PSDrive プロバイダーからアクセスできるその他のオブジェクトを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e6880-111">The match can include files, folders, registry keys, or any other object accessible from a PSDrive provider.</span></span>

## <span data-ttu-id="e6880-112">例</span><span class="sxs-lookup"><span data-stu-id="e6880-112">EXAMPLES</span></span>

### <span data-ttu-id="e6880-113">例 1: ホームフォルダーのパスを解決する</span><span class="sxs-lookup"><span data-stu-id="e6880-113">Example 1: Resolve the home folder path</span></span>

<span data-ttu-id="e6880-114">チルダ文字 (~) は、現在のユーザーのホームフォルダーの短縮表記です。</span><span class="sxs-lookup"><span data-stu-id="e6880-114">The tilde character (~) is shorthand notation for the current user's home folder.</span></span> <span data-ttu-id="e6880-115">次の例 `Resolve-Path` では、完全修飾パス値を返します。</span><span class="sxs-lookup"><span data-stu-id="e6880-115">This example shows `Resolve-Path` returning the fully qualified path value.</span></span>

```powershell
PS C:\> Resolve-Path ~
```

```Output
Path
----
C:\Users\User01
```

### <span data-ttu-id="e6880-116">例 2: Windows フォルダーのパスを解決する</span><span class="sxs-lookup"><span data-stu-id="e6880-116">Example 2: Resolve the path of the Windows folder</span></span>

```powershell
PS C:\> Resolve-Path -Path "windows"
```

```Output
Path
----
C:\Windows
```

<span data-ttu-id="e6880-117">C: ドライブのルートから実行すると、このコマンドは C: ドライブ内の Windows フォルダーのパスを返します。</span><span class="sxs-lookup"><span data-stu-id="e6880-117">When run from the root of the C: drive, this command returns the path of the Windows folder in the C: drive.</span></span>

### <span data-ttu-id="e6880-118">例 3: Windows フォルダー内のすべてのパスを取得する</span><span class="sxs-lookup"><span data-stu-id="e6880-118">Example 3: Get all paths in the Windows folder</span></span>

```powershell
PS C:\> "C:\windows\*" | Resolve-Path
```

<span data-ttu-id="e6880-119">このコマンドは、C:\Windows フォルダー内のすべてのフォルダーを返します。</span><span class="sxs-lookup"><span data-stu-id="e6880-119">This command returns all of the folders in the C:\Windows folder.</span></span> <span data-ttu-id="e6880-120">このコマンドは、パイプライン演算子 (|) を使用して、パス文字列をに送信し `Resolve-Path` ます。</span><span class="sxs-lookup"><span data-stu-id="e6880-120">The command uses a pipeline operator (|) to send a path string to `Resolve-Path`.</span></span>

### <span data-ttu-id="e6880-121">例 4: UNC パスを解決する</span><span class="sxs-lookup"><span data-stu-id="e6880-121">Example 4: Resolve a UNC path</span></span>

```powershell
PS C:\> Resolve-Path -Path "\\Server01\public"
```

<span data-ttu-id="e6880-122">このコマンドは、汎用名前付け規則 (UNC) パスを解決し、そのパス以下の共有を返します。</span><span class="sxs-lookup"><span data-stu-id="e6880-122">This command resolves a Universal Naming Convention (UNC) path and returns the shares in the path.</span></span>

### <span data-ttu-id="e6880-123">例 5: 相対パスを取得する</span><span class="sxs-lookup"><span data-stu-id="e6880-123">Example 5: Get relative paths</span></span>

```powershell
PS C:\> Resolve-Path -Path "c:\prog*" -Relative
```

```Output
.\Program Files
.\Program Files (x86)
.\programs.txt
```

<span data-ttu-id="e6880-124">このコマンドは、C: ドライブのルートにあるディレクトリの相対パスを返します。</span><span class="sxs-lookup"><span data-stu-id="e6880-124">This command returns relative paths for the directories at the root of the C: drive.</span></span>

### <span data-ttu-id="e6880-125">例 6: 角かっこを含むパスを解決する</span><span class="sxs-lookup"><span data-stu-id="e6880-125">Example 6: Resolve a path containing brackets</span></span>

<span data-ttu-id="e6880-126">この例では、 **LiteralPath** パラメーターを使用して、テスト \[ xml サブフォルダーのパスを解決し \] ます。</span><span class="sxs-lookup"><span data-stu-id="e6880-126">This example uses the **LiteralPath** parameter to resolve the path of the Test\[xml\] subfolder.</span></span>
<span data-ttu-id="e6880-127">**LiteralPath** を使用すると、角かっこが正規表現ではなく通常の文字として扱われます。</span><span class="sxs-lookup"><span data-stu-id="e6880-127">Using **LiteralPath** causes the brackets to be treated as normal characters rather than a regular expression.</span></span>

```powershell
PS C:\> Resolve-Path -LiteralPath 'test[xml]'
```

## <span data-ttu-id="e6880-128">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e6880-128">PARAMETERS</span></span>

### <span data-ttu-id="e6880-129">-Credential</span><span class="sxs-lookup"><span data-stu-id="e6880-129">-Credential</span></span>

<span data-ttu-id="e6880-130">この処理を実行するアクセス許可を持つユーザー アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="e6880-130">Specifies a user account that has permission to perform this action.</span></span> <span data-ttu-id="e6880-131">既定値は現在のユーザーです。</span><span class="sxs-lookup"><span data-stu-id="e6880-131">The default is the current user.</span></span>

<span data-ttu-id="e6880-132">User01 や Domain01\user01」などのユーザー名を入力するか、 **PSCredential** オブジェクトを渡します。</span><span class="sxs-lookup"><span data-stu-id="e6880-132">Type a user name, such as User01 or Domain01\User01, or pass a **PSCredential** object.</span></span> <span data-ttu-id="e6880-133">コマンドレットを使用して **PSCredential** オブジェクトを作成でき `Get-Credential` ます。</span><span class="sxs-lookup"><span data-stu-id="e6880-133">You can create a **PSCredential** object using the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="e6880-134">ユーザー名を入力すると、このコマンドレットによってパスワードの入力が求められます。</span><span class="sxs-lookup"><span data-stu-id="e6880-134">If you type a user name, this cmdlet prompts you for a password.</span></span>

<span data-ttu-id="e6880-135">このパラメーターは、PowerShell でインストールされたプロバイダーではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e6880-135">This parameter is not supported by any providers installed with PowerShell.</span></span>

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

### <span data-ttu-id="e6880-136">-LiteralPath</span><span class="sxs-lookup"><span data-stu-id="e6880-136">-LiteralPath</span></span>

<span data-ttu-id="e6880-137">解決するパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e6880-137">Specifies the path to be resolved.</span></span> <span data-ttu-id="e6880-138">**LiteralPath** パラメーターの値は、型指定されたとおりに使用されます。</span><span class="sxs-lookup"><span data-stu-id="e6880-138">The value of the **LiteralPath** parameter is used exactly as typed.</span></span> <span data-ttu-id="e6880-139">ワイルドカードとして解釈される文字はありません。</span><span class="sxs-lookup"><span data-stu-id="e6880-139">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="e6880-140">パスにエスケープ文字が含まれている場合は、単一引用符で囲みます。</span><span class="sxs-lookup"><span data-stu-id="e6880-140">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="e6880-141">単一引用符で囲まれた文字はエスケープシーケンスとして解釈されません。</span><span class="sxs-lookup"><span data-stu-id="e6880-141">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

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

### <span data-ttu-id="e6880-142">-Path</span><span class="sxs-lookup"><span data-stu-id="e6880-142">-Path</span></span>

<span data-ttu-id="e6880-143">解決する PowerShell パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e6880-143">Specifies the PowerShell path to resolve.</span></span> <span data-ttu-id="e6880-144">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="e6880-144">This parameter is required.</span></span> <span data-ttu-id="e6880-145">パイプを使用してパス文字列をにパイプすることもでき `Resolve-Path` ます。</span><span class="sxs-lookup"><span data-stu-id="e6880-145">You can also pipe a path string to `Resolve-Path`.</span></span> <span data-ttu-id="e6880-146">ワイルドカード文字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e6880-146">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="e6880-147">-相対</span><span class="sxs-lookup"><span data-stu-id="e6880-147">-Relative</span></span>

<span data-ttu-id="e6880-148">このコマンドレットが相対パスを返すことを示します。</span><span class="sxs-lookup"><span data-stu-id="e6880-148">Indicates that this cmdlet returns a relative path.</span></span>

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

### <span data-ttu-id="e6880-149">-UseTransaction</span><span class="sxs-lookup"><span data-stu-id="e6880-149">-UseTransaction</span></span>
<span data-ttu-id="e6880-150">アクティブなトランザクションのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6880-150">Includes the command in the active transaction.</span></span>
<span data-ttu-id="e6880-151">このパラメーターは、トランザクションが進行中の場合のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="e6880-151">This parameter is valid only when a transaction is in progress.</span></span>
<span data-ttu-id="e6880-152">詳細については、「about_transactions」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6880-152">For more information, see about_transactions.</span></span>

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

### <span data-ttu-id="e6880-153">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e6880-153">CommonParameters</span></span>

<span data-ttu-id="e6880-154">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e6880-154">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e6880-155">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6880-155">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="e6880-156">入力</span><span class="sxs-lookup"><span data-stu-id="e6880-156">INPUTS</span></span>

### <span data-ttu-id="e6880-157">System.String</span><span class="sxs-lookup"><span data-stu-id="e6880-157">System.String</span></span>

<span data-ttu-id="e6880-158">パイプを使用して、このコマンドレットへのパスを含む文字列をパイプすることができます。</span><span class="sxs-lookup"><span data-stu-id="e6880-158">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="e6880-159">出力</span><span class="sxs-lookup"><span data-stu-id="e6880-159">OUTPUTS</span></span>

### <span data-ttu-id="e6880-160">システムの管理. PathInfo、System.string</span><span class="sxs-lookup"><span data-stu-id="e6880-160">System.Management.Automation.PathInfo, System.String</span></span>

<span data-ttu-id="e6880-161">**Pathinfo** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="e6880-161">Returns a **PathInfo** object.</span></span> <span data-ttu-id="e6880-162">**相対** パラメーターを指定した場合、解決されたパスの文字列値を返します。</span><span class="sxs-lookup"><span data-stu-id="e6880-162">Returns a string value for the resolved path if you specify the **Relative** parameter.</span></span>

## <span data-ttu-id="e6880-163">注</span><span class="sxs-lookup"><span data-stu-id="e6880-163">NOTES</span></span>

<span data-ttu-id="e6880-164">`*-Path`コマンドレットは、ファイルシステム、レジストリ、および証明書プロバイダーで動作します。</span><span class="sxs-lookup"><span data-stu-id="e6880-164">The `*-Path` cmdlets work with the FileSystem, Registry, and Certificate providers.</span></span>

<span data-ttu-id="e6880-165">`Resolve-Path` は、任意のプロバイダーと連携するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e6880-165">`Resolve-Path` is designed to work with any provider.</span></span> <span data-ttu-id="e6880-166">セッションで使用可能なプロバイダーの一覧を表示するには、「」と入力 `Get-PSProvider` します。</span><span class="sxs-lookup"><span data-stu-id="e6880-166">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="e6880-167">詳細については、「 [about_providers](../microsoft.powershell.core/about/about_providers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6880-167">For more information, see [about_providers](../microsoft.powershell.core/about/about_providers.md).</span></span>

<span data-ttu-id="e6880-168">`Resolve-Path` は既存のパスのみを解決します。</span><span class="sxs-lookup"><span data-stu-id="e6880-168">`Resolve-Path` only resolves existing paths.</span></span> <span data-ttu-id="e6880-169">まだ存在しない場所を解決するために使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="e6880-169">It cannot be used to resolve a location that does not exist yet.</span></span>

## <span data-ttu-id="e6880-170">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e6880-170">RELATED LINKS</span></span>

[<span data-ttu-id="e6880-171">Convert-Path</span><span class="sxs-lookup"><span data-stu-id="e6880-171">Convert-Path</span></span>](Convert-Path.md)

[<span data-ttu-id="e6880-172">Join-Path</span><span class="sxs-lookup"><span data-stu-id="e6880-172">Join-Path</span></span>](Join-Path.md)

[<span data-ttu-id="e6880-173">Split-Path</span><span class="sxs-lookup"><span data-stu-id="e6880-173">Split-Path</span></span>](Split-Path.md)

[<span data-ttu-id="e6880-174">Test-Path</span><span class="sxs-lookup"><span data-stu-id="e6880-174">Test-Path</span></span>](Test-Path.md)
