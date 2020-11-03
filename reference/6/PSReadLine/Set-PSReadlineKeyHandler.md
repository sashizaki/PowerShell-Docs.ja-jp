---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 7794fc8814364d3ee62b0dece787aa0213dc4ff3
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214907"
---
# <span data-ttu-id="f7127-103">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="f7127-103">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="f7127-104">概要</span><span class="sxs-lookup"><span data-stu-id="f7127-104">SYNOPSIS</span></span>
<span data-ttu-id="f7127-105">ユーザー定義キーまたは PSReadLine キーハンドラー関数にキーをバインドします。</span><span class="sxs-lookup"><span data-stu-id="f7127-105">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="f7127-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f7127-106">SYNTAX</span></span>

### <span data-ttu-id="f7127-107">スクリプト ブロック</span><span class="sxs-lookup"><span data-stu-id="f7127-107">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="f7127-108">機能</span><span class="sxs-lookup"><span data-stu-id="f7127-108">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="f7127-109">Description</span><span class="sxs-lookup"><span data-stu-id="f7127-109">DESCRIPTION</span></span>

<span data-ttu-id="f7127-110">`Set-PSReadLineKeyHandler`キーまたはキーのシーケンスが押されたときに、コマンドレットによって結果がカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="f7127-110">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="f7127-111">ユーザー定義のキーバインドを使用すると、PowerShell スクリプト内から可能なほとんどすべての操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="f7127-111">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="f7127-112">例</span><span class="sxs-lookup"><span data-stu-id="f7127-112">EXAMPLES</span></span>

### <span data-ttu-id="f7127-113">例 1: 関数に方向キーをバインドする</span><span class="sxs-lookup"><span data-stu-id="f7127-113">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="f7127-114">このコマンドは、↑キーを **History Search後方** 関数にバインドします。</span><span class="sxs-lookup"><span data-stu-id="f7127-114">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="f7127-115">この関数は、コマンドラインの現在の内容で始まるコマンドラインを検索します。</span><span class="sxs-lookup"><span data-stu-id="f7127-115">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="f7127-116">例 2: キーをスクリプトブロックにバインドする</span><span class="sxs-lookup"><span data-stu-id="f7127-116">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="f7127-117">この例では、1つのキーを使用してコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f7127-117">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="f7127-118">このコマンドは、 `Ctrl+B` 行をクリアするスクリプトブロックにキーをバインドし、"build" という単語を挿入して、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f7127-118">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="f7127-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f7127-119">PARAMETERS</span></span>

### <span data-ttu-id="f7127-120">-BriefDescription</span><span class="sxs-lookup"><span data-stu-id="f7127-120">-BriefDescription</span></span>

<span data-ttu-id="f7127-121">キーバインドの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="f7127-121">A brief description of the key binding.</span></span> <span data-ttu-id="f7127-122">この説明はコマンドレットによって表示され `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="f7127-122">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7127-123">-コード</span><span class="sxs-lookup"><span data-stu-id="f7127-123">-Chord</span></span>

<span data-ttu-id="f7127-124">関数またはスクリプトブロックにバインドするキーまたはキーのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="f7127-124">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="f7127-125">単一の文字列を使用して1つのバインドを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7127-125">Use a single string to specify a single binding.</span></span> <span data-ttu-id="f7127-126">バインドが一連のキーである場合は、次の例のように、キーをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="f7127-126">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

<span data-ttu-id="f7127-127">このパラメーターは、文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="f7127-127">This parameter accepts an array of strings.</span></span> <span data-ttu-id="f7127-128">各文字列は個別のバインドであり、1つのバインドのキーのシーケンスではありません。</span><span class="sxs-lookup"><span data-stu-id="f7127-128">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Key

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7127-129">-Description</span><span class="sxs-lookup"><span data-stu-id="f7127-129">-Description</span></span>

<span data-ttu-id="f7127-130">コマンドレットの出力に表示されるキーバインドの詳細な説明を指定し `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="f7127-130">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

```yaml
Type: System.String
Parameter Sets: ScriptBlock
Aliases: LongDescription

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7127-131">-関数</span><span class="sxs-lookup"><span data-stu-id="f7127-131">-Function</span></span>

<span data-ttu-id="f7127-132">PSReadLine によって提供される既存のキーハンドラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7127-132">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="f7127-133">このパラメーターを使用すると、既存のキーバインドを再バインドしたり、現在バインドされていないハンドラーをバインドしたりできます。</span><span class="sxs-lookup"><span data-stu-id="f7127-133">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

```yaml
Type: System.String
Parameter Sets: Function
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7127-134">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="f7127-134">-ScriptBlock</span></span>

<span data-ttu-id="f7127-135">コードの入力時に実行するスクリプトブロックの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="f7127-135">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="f7127-136">PSReadLine は、このスクリプトブロックに1つまたは2つのパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="f7127-136">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="f7127-137">最初のパラメーターは、押されたキーを表す **Consolekeyinfo** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="f7127-137">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="f7127-138">2番目の引数には、コンテキストに応じて任意のオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="f7127-138">The second argument can be any object depending on the context.</span></span>

```yaml
Type: System.Management.Automation.ScriptBlock
Parameter Sets: ScriptBlock
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7127-139">-ViMode</span><span class="sxs-lookup"><span data-stu-id="f7127-139">-ViMode</span></span>

<span data-ttu-id="f7127-140">バインドが適用される vi モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="f7127-140">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="f7127-141">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f7127-141">Valid values are:</span></span>

- <span data-ttu-id="f7127-142">挿入</span><span class="sxs-lookup"><span data-stu-id="f7127-142">Insert</span></span>
- <span data-ttu-id="f7127-143">コマンド</span><span class="sxs-lookup"><span data-stu-id="f7127-143">Command</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="f7127-144">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="f7127-144">CommonParameters</span></span>

<span data-ttu-id="f7127-145">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="f7127-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f7127-146">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7127-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f7127-147">入力</span><span class="sxs-lookup"><span data-stu-id="f7127-147">INPUTS</span></span>

### <span data-ttu-id="f7127-148">なし</span><span class="sxs-lookup"><span data-stu-id="f7127-148">None</span></span>

<span data-ttu-id="f7127-149">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="f7127-149">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="f7127-150">出力</span><span class="sxs-lookup"><span data-stu-id="f7127-150">OUTPUTS</span></span>

### <span data-ttu-id="f7127-151">なし</span><span class="sxs-lookup"><span data-stu-id="f7127-151">None</span></span>

<span data-ttu-id="f7127-152">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="f7127-152">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="f7127-153">注</span><span class="sxs-lookup"><span data-stu-id="f7127-153">NOTES</span></span>

## <span data-ttu-id="f7127-154">関連リンク</span><span class="sxs-lookup"><span data-stu-id="f7127-154">RELATED LINKS</span></span>

[<span data-ttu-id="f7127-155">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="f7127-155">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="f7127-156">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="f7127-156">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="f7127-157">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="f7127-157">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="f7127-158">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="f7127-158">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)