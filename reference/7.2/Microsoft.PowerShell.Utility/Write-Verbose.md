---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-verbose?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Verbose
ms.openlocfilehash: 177e32106f37c59593bbecac13843f6603327cc9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599542"
---
# <span data-ttu-id="51ca8-102">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="51ca8-102">Write-Verbose</span></span>

## <span data-ttu-id="51ca8-103">概要</span><span class="sxs-lookup"><span data-stu-id="51ca8-103">SYNOPSIS</span></span>
<span data-ttu-id="51ca8-104">テキストを詳細メッセージ ストリームに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-104">Writes text to the verbose message stream.</span></span>

## <span data-ttu-id="51ca8-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="51ca8-105">SYNTAX</span></span>

```
Write-Verbose [-Message] <String> [<CommonParameters>]
```

## <span data-ttu-id="51ca8-106">Description</span><span class="sxs-lookup"><span data-stu-id="51ca8-106">DESCRIPTION</span></span>

<span data-ttu-id="51ca8-107">`Write-Verbose`コマンドレットは、PowerShell の詳細メッセージストリームにテキストを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-107">The `Write-Verbose` cmdlet writes text to the verbose message stream in PowerShell.</span></span> <span data-ttu-id="51ca8-108">通常、詳細メッセージストリームは、コマンド処理に関する詳細な情報を提供するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-108">Typically, the verbose message stream is used to deliver more in depth information about command processing.</span></span>

<span data-ttu-id="51ca8-109">既定では、詳細メッセージストリームは表示されませんが、変数の値を変更する `$VerbosePreference` か、任意のコマンドで **verbose** 共通パラメーターを使用して表示できます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-109">By default, the verbose message stream is not displayed, but you can display it by changing the value of the `$VerbosePreference` variable or using the **Verbose** common parameter in any command.</span></span>

## <span data-ttu-id="51ca8-110">例</span><span class="sxs-lookup"><span data-stu-id="51ca8-110">EXAMPLES</span></span>

### <span data-ttu-id="51ca8-111">例 1: ステータスメッセージを書き込む</span><span class="sxs-lookup"><span data-stu-id="51ca8-111">Example 1: Write a status message</span></span>

```powershell
Write-Verbose -Message "Searching the Application Event Log."
Write-Verbose -Message "Searching the Application Event Log." -Verbose
```

<span data-ttu-id="51ca8-112">これらのコマンドは、 `Write-Verbose` コマンドレットを使用してステータスメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="51ca8-112">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="51ca8-113">既定では、メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="51ca8-113">By default, the message is not displayed.</span></span>

<span data-ttu-id="51ca8-114">2番目のコマンドは、 **verbose** 共通パラメーターを使用します。これにより、変数の値に関係なく、詳細なメッセージが表示され `$VerbosePreference` ます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-114">The second command uses the **Verbose** common parameter, which displays any verbose messages, regardless of the value of the `$VerbosePreference` variable.</span></span>

### <span data-ttu-id="51ca8-115">例 2: $VerbosePreference を設定してステータスメッセージを書き込む</span><span class="sxs-lookup"><span data-stu-id="51ca8-115">Example 2: Set $VerbosePreference and write a status message</span></span>

```powershell
$VerbosePreference = "Continue"
Write-Verbose "Copying file $filename"
```

<span data-ttu-id="51ca8-116">これらのコマンドは、 `Write-Verbose` コマンドレットを使用してステータスメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="51ca8-116">These commands use the `Write-Verbose` cmdlet to display a status message.</span></span> <span data-ttu-id="51ca8-117">既定では、メッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="51ca8-117">By default, the message is not displayed.</span></span>

<span data-ttu-id="51ca8-118">最初のコマンドは、ユーザー設定変数に Continue の値を割り当て `$VerbosePreference` ます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-118">The first command assigns a value of Continue to the `$VerbosePreference` preference variable.</span></span> <span data-ttu-id="51ca8-119">既定値のでは、詳細メッセージが表示さ `SilentlyContinue` れません。</span><span class="sxs-lookup"><span data-stu-id="51ca8-119">The default value, `SilentlyContinue`, suppresses verbose messages.</span></span> <span data-ttu-id="51ca8-120">2 番目のコマンドは、詳細メッセージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-120">The second command writes a verbose message.</span></span>

## <span data-ttu-id="51ca8-121">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="51ca8-121">PARAMETERS</span></span>

### <span data-ttu-id="51ca8-122">-メッセージ</span><span class="sxs-lookup"><span data-stu-id="51ca8-122">-Message</span></span>

<span data-ttu-id="51ca8-123">表示するメッセージを指定します。</span><span class="sxs-lookup"><span data-stu-id="51ca8-123">Specifies the message to display.</span></span> <span data-ttu-id="51ca8-124">このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="51ca8-124">This parameter is required.</span></span> <span data-ttu-id="51ca8-125">また、パイプを使用してメッセージ文字列をにパイプすることもでき `Write-Verbose` ます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-125">You can also pipe a message string to `Write-Verbose`.</span></span>

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

### <span data-ttu-id="51ca8-126">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="51ca8-126">CommonParameters</span></span>

<span data-ttu-id="51ca8-127">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="51ca8-127">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="51ca8-128">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51ca8-128">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="51ca8-129">入力</span><span class="sxs-lookup"><span data-stu-id="51ca8-129">INPUTS</span></span>

### <span data-ttu-id="51ca8-130">System.String</span><span class="sxs-lookup"><span data-stu-id="51ca8-130">System.String</span></span>

<span data-ttu-id="51ca8-131">パイプを使用して、メッセージを含む文字列をにパイプ処理でき `Write-Verbose` ます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-131">You can pipe a string that contains the message to `Write-Verbose`.</span></span>

## <span data-ttu-id="51ca8-132">出力</span><span class="sxs-lookup"><span data-stu-id="51ca8-132">OUTPUTS</span></span>

### <span data-ttu-id="51ca8-133">なし</span><span class="sxs-lookup"><span data-stu-id="51ca8-133">None</span></span>

<span data-ttu-id="51ca8-134">`Write-Verbose` 詳細メッセージストリームにのみ書き込みます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-134">`Write-Verbose` writes only to the verbose message stream.</span></span>

## <span data-ttu-id="51ca8-135">注</span><span class="sxs-lookup"><span data-stu-id="51ca8-135">NOTES</span></span>

- <span data-ttu-id="51ca8-136">詳細メッセージは、コマンドが **Verbose** 共通パラメーターを使用する場合のみ返されます。</span><span class="sxs-lookup"><span data-stu-id="51ca8-136">Verbose messages are returned only when the command uses the **Verbose** common parameter.</span></span> <span data-ttu-id="51ca8-137">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51ca8-137">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>
- <span data-ttu-id="51ca8-138">Windows PowerShell のバックグラウンドジョブとリモートコマンドでは、 `$VerbosePreference` ジョブセッションとリモートセッションの変数によって、既定で詳細メッセージが表示されるかどうかが決まります。</span><span class="sxs-lookup"><span data-stu-id="51ca8-138">In Windows PowerShell background jobs and remote commands, the `$VerbosePreference` variable in the job session and remote session determine whether the verbose message is displayed by default.</span></span>
  <span data-ttu-id="51ca8-139">変数の詳細については `$VerbosePreference` 、「 [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51ca8-139">For more information about the `$VerbosePreference` variable, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md).</span></span>

## <span data-ttu-id="51ca8-140">関連リンク</span><span class="sxs-lookup"><span data-stu-id="51ca8-140">RELATED LINKS</span></span>

[<span data-ttu-id="51ca8-141">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="51ca8-141">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="51ca8-142">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="51ca8-142">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="51ca8-143">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="51ca8-143">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="51ca8-144">Write-Error</span><span class="sxs-lookup"><span data-stu-id="51ca8-144">Write-Error</span></span>](Write-Error.md)

[<span data-ttu-id="51ca8-145">Write-Host</span><span class="sxs-lookup"><span data-stu-id="51ca8-145">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="51ca8-146">Write-Information</span><span class="sxs-lookup"><span data-stu-id="51ca8-146">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="51ca8-147">Write-Output</span><span class="sxs-lookup"><span data-stu-id="51ca8-147">Write-Output</span></span>](Write-Output.md)

[<span data-ttu-id="51ca8-148">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="51ca8-148">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="51ca8-149">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="51ca8-149">Write-Warning</span></span>](Write-Warning.md)
