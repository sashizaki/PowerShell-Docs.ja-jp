---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 5/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-variable?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Variable
ms.openlocfilehash: f544a33a4d2aa2cabd330ce7cc30c5270eeff897
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93213008"
---
# <span data-ttu-id="81b2f-103">Get-Variable</span><span class="sxs-lookup"><span data-stu-id="81b2f-103">Get-Variable</span></span>

## <span data-ttu-id="81b2f-104">概要</span><span class="sxs-lookup"><span data-stu-id="81b2f-104">SYNOPSIS</span></span>
<span data-ttu-id="81b2f-105">現在のコンソール内の変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-105">Gets the variables in the current console.</span></span>

## <span data-ttu-id="81b2f-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="81b2f-106">SYNTAX</span></span>

```
Get-Variable [[-Name] <String[]>] [-ValueOnly] [-Include <String[]>] [-Exclude <String[]>] [-Scope <String>]
 [<CommonParameters>]
```

## <span data-ttu-id="81b2f-107">Description</span><span class="sxs-lookup"><span data-stu-id="81b2f-107">DESCRIPTION</span></span>

<span data-ttu-id="81b2f-108">`Get-Variable`コマンドレットは、現在のコンソールで PowerShell 変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-108">The `Get-Variable` cmdlet gets the PowerShell variables in the current console.</span></span>
<span data-ttu-id="81b2f-109">**ValueOnly** パラメーターを指定することで変数の値だけを取得できます。また、返される変数を名前でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-109">You can retrieve just the values of the variables by specifying the **ValueOnly** parameter, and you can filter the variables returned by name.</span></span>

## <span data-ttu-id="81b2f-110">例</span><span class="sxs-lookup"><span data-stu-id="81b2f-110">EXAMPLES</span></span>

### <span data-ttu-id="81b2f-111">例 1: 文字で変数を取得する</span><span class="sxs-lookup"><span data-stu-id="81b2f-111">Example 1: Get variables by letter</span></span>

<span data-ttu-id="81b2f-112">このコマンドは、文字 m で始まる名前を持つ変数を取得します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-112">This command gets variables with names that begin with the letter m.</span></span>
<span data-ttu-id="81b2f-113">コマンドは、変数の値も取得します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-113">The command also gets the value of the variables.</span></span>

```powershell
Get-Variable m*
```

### <span data-ttu-id="81b2f-114">例 2: 文字によって変数の値を取得する</span><span class="sxs-lookup"><span data-stu-id="81b2f-114">Example 2: Get variable values by letter</span></span>

<span data-ttu-id="81b2f-115">このコマンドは、名前が m で始まる変数の値のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-115">This command gets only the values of the variables that have names that begin with m.</span></span>

```powershell
Get-Variable m* -ValueOnly
```

### <span data-ttu-id="81b2f-116">例 3: 2 文字で変数を取得する</span><span class="sxs-lookup"><span data-stu-id="81b2f-116">Example 3: Get variables by two letters</span></span>

<span data-ttu-id="81b2f-117">このコマンドは、文字 M または文字 P で始まる変数に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-117">This command gets information about the variables that begin with either the letter M or the letter P.</span></span>

```powershell
Get-Variable -Include M*,P*
```

### <span data-ttu-id="81b2f-118">例 4: スコープによって変数を取得する</span><span class="sxs-lookup"><span data-stu-id="81b2f-118">Example 4: Get variables by scope</span></span>

<span data-ttu-id="81b2f-119">最初のコマンドは、ローカル スコープで定義されている変数のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-119">The first command gets only the variables that are defined in the local scope.</span></span>
<span data-ttu-id="81b2f-120">これはと同じであり、とし `Get-Variable -Scope Local` て省略でき `gv -s 0` ます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-120">It is equivalent to `Get-Variable -Scope Local` and can be abbreviated as `gv -s 0`.</span></span>

<span data-ttu-id="81b2f-121">2番目のコマンドは、コマンドレットを使用して、 `Compare-Object` 親スコープ (スコープ 1) で定義されているが、ローカルスコープ (スコープ 0) でのみ表示される変数を検索します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-121">The second command uses the `Compare-Object` cmdlet to find the variables that are defined in the parent scope (Scope 1) but are visible only in the local scope (Scope 0).</span></span>

```powershell
Get-Variable -Scope 0
Compare-Object (Get-Variable -Scope 0) (Get-Variable -Scope 1)
```

## <span data-ttu-id="81b2f-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="81b2f-122">PARAMETERS</span></span>

### <span data-ttu-id="81b2f-123">-除外</span><span class="sxs-lookup"><span data-stu-id="81b2f-123">-Exclude</span></span>

<span data-ttu-id="81b2f-124">このコマンドレットによって操作から除外される項目の配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-124">Specifies an array of items that this cmdlet excludes from the operation.</span></span>
<span data-ttu-id="81b2f-125">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-125">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="81b2f-126">-Include</span><span class="sxs-lookup"><span data-stu-id="81b2f-126">-Include</span></span>

<span data-ttu-id="81b2f-127">コマンドレットが動作する項目の配列を指定します。他の項目は除外されます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-127">Specifies an array of items upon which the cmdlet will act, excluding all others.</span></span>
<span data-ttu-id="81b2f-128">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-128">Wildcards are permitted.</span></span>

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

### <span data-ttu-id="81b2f-129">-Name</span><span class="sxs-lookup"><span data-stu-id="81b2f-129">-Name</span></span>

<span data-ttu-id="81b2f-130">変数の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-130">Specifies the name of the variable.</span></span>
<span data-ttu-id="81b2f-131">ワイルドカードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-131">Wildcards are permitted.</span></span>
<span data-ttu-id="81b2f-132">パイプを使用して変数名をにパイプすることもでき `Get-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-132">You can also pipe a variable name to `Get-Variable`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="81b2f-133">-スコープ</span><span class="sxs-lookup"><span data-stu-id="81b2f-133">-Scope</span></span>

<span data-ttu-id="81b2f-134">スコープ内の変数を指定します。このパラメーターに指定できる値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="81b2f-134">Specifies the variables in the scope.The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="81b2f-135">**グローバル**</span><span class="sxs-lookup"><span data-stu-id="81b2f-135">**Global**</span></span>
- <span data-ttu-id="81b2f-136">**ローカル**</span><span class="sxs-lookup"><span data-stu-id="81b2f-136">**Local**</span></span>
- <span data-ttu-id="81b2f-137">**スクリプト**</span><span class="sxs-lookup"><span data-stu-id="81b2f-137">**Script**</span></span>
- <span data-ttu-id="81b2f-138">現在のスコープに対して相対的な数値 (0 ~ スコープの数。0は現在のスコープ、1はその親)</span><span class="sxs-lookup"><span data-stu-id="81b2f-138">A number relative to the current scope (0 through the number of scopes, where 0 is the current scope and 1 is its parent)</span></span>

<span data-ttu-id="81b2f-139">既定値は **Local** です。</span><span class="sxs-lookup"><span data-stu-id="81b2f-139">**Local** is the default.</span></span>
<span data-ttu-id="81b2f-140">詳細については、「 [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81b2f-140">For more information, see [about_Scopes](../Microsoft.PowerShell.Core/About/about_Scopes.md).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="81b2f-141">-ValueOnly</span><span class="sxs-lookup"><span data-stu-id="81b2f-141">-ValueOnly</span></span>

<span data-ttu-id="81b2f-142">このコマンドレットが変数の値のみを取得することを示します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-142">Indicates that this cmdlet gets only the value of the variable.</span></span>

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

### <span data-ttu-id="81b2f-143">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="81b2f-143">CommonParameters</span></span>

<span data-ttu-id="81b2f-144">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="81b2f-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="81b2f-145">詳細については、「[about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="81b2f-145">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="81b2f-146">入力</span><span class="sxs-lookup"><span data-stu-id="81b2f-146">INPUTS</span></span>

### <span data-ttu-id="81b2f-147">System.String</span><span class="sxs-lookup"><span data-stu-id="81b2f-147">System.String</span></span>

<span data-ttu-id="81b2f-148">パイプを使用して、変数名を含む文字列をに渡し `Get-Variable` ます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-148">You can pipe a string that contains the variable name to `Get-Variable`.</span></span>

## <span data-ttu-id="81b2f-149">出力</span><span class="sxs-lookup"><span data-stu-id="81b2f-149">OUTPUTS</span></span>

### <span data-ttu-id="81b2f-150">システム管理. PSVariable</span><span class="sxs-lookup"><span data-stu-id="81b2f-150">System.Management.Automation.PSVariable</span></span>

<span data-ttu-id="81b2f-151">このコマンドレットは、取得した各変数の **AutomationPSVariable** オブジェクトを返します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-151">This cmdlet returns a **System.Management.AutomationPSVariable** object for each variable that it gets.</span></span> <span data-ttu-id="81b2f-152">オブジェクトの型は変数に依存します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-152">The object type depends on the variable.</span></span>

### <span data-ttu-id="81b2f-153">System.object []</span><span class="sxs-lookup"><span data-stu-id="81b2f-153">System.Object[]</span></span>

<span data-ttu-id="81b2f-154">**Valueonly** パラメーターを指定すると、指定した変数の値がコレクションの場合、 `Get-Variable` はを返し `[System.Object[]]` ます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-154">When you specify the **ValueOnly** parameter, if the specified variable's value is a collection, `Get-Variable` returns a `[System.Object[]]`.</span></span> <span data-ttu-id="81b2f-155">この動作により、通常のパイプライン操作によって変数の値が一度に1つずつ処理されるのを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-155">This behavior prevents normal pipeline operation from processing the variable's values one at a time.</span></span> <span data-ttu-id="81b2f-156">コレクションの列挙を強制する回避策として、 `Get-Variable` コマンドをかっこで囲みます。</span><span class="sxs-lookup"><span data-stu-id="81b2f-156">A workaround to force collection enumeration is to enclose the `Get-Variable` command in parenthesis.</span></span>

## <span data-ttu-id="81b2f-157">注</span><span class="sxs-lookup"><span data-stu-id="81b2f-157">NOTES</span></span>

- <span data-ttu-id="81b2f-158">このコマンドレットは、環境変数を管理しません。</span><span class="sxs-lookup"><span data-stu-id="81b2f-158">This cmdlet does not manage environment variables.</span></span> <span data-ttu-id="81b2f-159">環境変数を管理するには、環境変数プロバイダーを使用します。</span><span class="sxs-lookup"><span data-stu-id="81b2f-159">To manage environment variables, you can use the environment variable provider.</span></span>

## <span data-ttu-id="81b2f-160">関連リンク</span><span class="sxs-lookup"><span data-stu-id="81b2f-160">RELATED LINKS</span></span>

[<span data-ttu-id="81b2f-161">Clear-Variable</span><span class="sxs-lookup"><span data-stu-id="81b2f-161">Clear-Variable</span></span>](Clear-Variable.md)

[<span data-ttu-id="81b2f-162">New-Variable</span><span class="sxs-lookup"><span data-stu-id="81b2f-162">New-Variable</span></span>](New-Variable.md)

[<span data-ttu-id="81b2f-163">Remove-Variable</span><span class="sxs-lookup"><span data-stu-id="81b2f-163">Remove-Variable</span></span>](Remove-Variable.md)

[<span data-ttu-id="81b2f-164">Set-Variable</span><span class="sxs-lookup"><span data-stu-id="81b2f-164">Set-Variable</span></span>](Set-Variable.md)

