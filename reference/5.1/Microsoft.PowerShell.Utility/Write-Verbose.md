---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: e16e002ab9e803900712542c329723f6a44a880f
ms.sourcegitcommit: 16883bb67e34b3915798070f60f974bf85160bd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "93224291"
---
# <span data-ttu-id="64ca9-103">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="64ca9-103">Write-Verbose</span></span>

## <span data-ttu-id="64ca9-104">概要</span><span class="sxs-lookup"><span data-stu-id="64ca9-104">SYNOPSIS</span></span>
<span data-ttu-id="64ca9-105">テキストを詳細メッセージ ストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-105">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="64ca9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="64ca9-106">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="64ca9-107">Description</span><span class="sxs-lookup"><span data-stu-id="64ca9-107">DESCRIPTION</span></span>

<span data-ttu-id="64ca9-108">`Write-Verbose`コマンドレットは、PowerShell の詳細メッセージストリームにテキストを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-108">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="64ca9-109">通常、詳細メッセージストリームは、コマンド処理に関する詳細な情報を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-109">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="64ca9-110">既定では、詳細メッセージストリームは表示されませんが、変数の値を変更する `$VerbosePreference` か、任意のコマンドで **verbose** 共通パラメーターを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-110">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="64ca9-111">例</span><span class="sxs-lookup"><span data-stu-id="64ca9-111">EXAMPLES</span></span>

### <span data-ttu-id="64ca9-112">例 1: ステータスメッセージを書き込む</span><span class="sxs-lookup"><span data-stu-id="64ca9-112">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="64ca9-113">これらのコマンドは、 `Write-Verbose` コマンドレットを使用してステータスメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="64ca9-113">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="64ca9-114">既定では、メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="64ca9-114">By default, the message is not displayed.</span></span>

<span data-ttu-id="64ca9-115">2番目のコマンドは、 **verbose** 共通パラメーターを使用します。これにより、変数の値に関係なく、詳細なメッセージが表示され `$VerbosePreference` ます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-115">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="64ca9-116">例 2: $VerbosePreference を設定してステータスメッセージを書き込む</span><span class="sxs-lookup"><span data-stu-id="64ca9-116">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="64ca9-117">これらのコマンドは、 `Write-Verbose` コマンドレットを使用してステータスメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="64ca9-117">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="64ca9-118">既定では、メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="64ca9-118">By default, the message is not displayed.</span></span>

<span data-ttu-id="64ca9-119">最初のコマンドは、ユーザー設定変数に Continue の値を割り当て `$VerbosePreference` ます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-119">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="64ca9-120">既定値のでは、詳細メッセージが表示さ `SilentlyContinue` れません。</span><span class="sxs-lookup"><span data-stu-id="64ca9-120">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="64ca9-121">2 番目のコマンドは、詳細メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-121">The second command writes a verbose message.</span></span>

## <span data-ttu-id="64ca9-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="64ca9-122">PARAMETERS</span></span>

### <span data-ttu-id="64ca9-123">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="64ca9-123">-Message</span></span>

<span data-ttu-id="64ca9-124">表示するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="64ca9-124">Specifies the message to display.</span></span> <span data-ttu-id="64ca9-125">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="64ca9-125">This parameter is required.</span></span> <span data-ttu-id="64ca9-126">また、パイプを使用してメッセージ文字列をにパイプすることもでき `Write-Verbose` ます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-126">You can also pipe a message string to `Write-Verbose`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Msg

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="64ca9-127">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="64ca9-127">CommonParameters</span></span>

<span data-ttu-id="64ca9-128">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="64ca9-128">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="64ca9-129">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64ca9-129">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="64ca9-130">入力</span><span class="sxs-lookup"><span data-stu-id="64ca9-130">INPUTS</span></span>

### <span data-ttu-id="64ca9-131">System.String</span><span class="sxs-lookup"><span data-stu-id="64ca9-131">System.String</span></span>

<span data-ttu-id="64ca9-132">パイプを使用して、メッセージを含む文字列をにパイプ処理でき `Write-Verbose` ます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-132">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="64ca9-133">出力</span><span class="sxs-lookup"><span data-stu-id="64ca9-133">OUTPUTS</span></span>

### <span data-ttu-id="64ca9-134">なし</span><span class="sxs-lookup"><span data-stu-id="64ca9-134">None</span></span>

<span data-ttu-id="64ca9-135">`Write-Verbose` 詳細メッセージストリームにのみ書き込みます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-135">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="64ca9-136">注</span><span class="sxs-lookup"><span data-stu-id="64ca9-136">NOTES</span></span>

- <span data-ttu-id="64ca9-137">詳細メッセージは、コマンドが **Verbose** 共通パラメーターを使用する場合のみ返されます。</span><span class="sxs-lookup"><span data-stu-id="64ca9-137">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="64ca9-138">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64ca9-138">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="64ca9-139">Windows PowerShell のバックグラウンドジョブとリモートコマンドでは、 `$VerbosePreference` ジョブセッションとリモートセッションの変数によって、既定で詳細メッセージが表示されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="64ca9-139">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="64ca9-140">変数の詳細については `$VerbosePreference` 、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64ca9-140">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="64ca9-141">関連リンク</span><span class="sxs-lookup"><span data-stu-id="64ca9-141">RELATED LINKS</span></span>

[<span data-ttu-id="64ca9-142">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="64ca9-142">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="64ca9-143">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="64ca9-143">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="64ca9-144">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="64ca9-144">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="64ca9-145">書き込み-エラー</span><span class="sxs-lookup"><span data-stu-id="64ca9-145">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="64ca9-146">Write-Host</span><span class="sxs-lookup"><span data-stu-id="64ca9-146">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="64ca9-147">Write-Information</span><span class="sxs-lookup"><span data-stu-id="64ca9-147">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="64ca9-148">Write-Output</span><span class="sxs-lookup"><span data-stu-id="64ca9-148">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="64ca9-149">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="64ca9-149">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="64ca9-150">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="64ca9-150">Write-Warning</span></span>](Write-Warning.md)
