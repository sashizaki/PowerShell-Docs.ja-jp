---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: 0ec3466aaaf6ed1ac78b62d88a5a6cce99153673
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600989"
---
# <span data-ttu-id="e3b5c-102">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="e3b5c-102">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="e3b5c-103">概要</span><span class="sxs-lookup"><span data-stu-id="e3b5c-103">SYNOPSIS</span></span>
<span data-ttu-id="e3b5c-104">ユーザー定義キーまたは PSReadLine キーハンドラー関数にキーをバインドします。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-104">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="e3b5c-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="e3b5c-105">SYNTAX</span></span>

### <span data-ttu-id="e3b5c-106">スクリプト ブロック</span><span class="sxs-lookup"><span data-stu-id="e3b5c-106">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="e3b5c-107">Function</span><span class="sxs-lookup"><span data-stu-id="e3b5c-107">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="e3b5c-108">Description</span><span class="sxs-lookup"><span data-stu-id="e3b5c-108">DESCRIPTION</span></span>

<span data-ttu-id="e3b5c-109">`Set-PSReadLineKeyHandler`キーまたはキーのシーケンスが押されたときに、コマンドレットによって結果がカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-109">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="e3b5c-110">ユーザー定義のキーバインドを使用すると、PowerShell スクリプト内から可能なほとんどすべての操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-110">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="e3b5c-111">例</span><span class="sxs-lookup"><span data-stu-id="e3b5c-111">EXAMPLES</span></span>

### <span data-ttu-id="e3b5c-112">例 1: 関数に方向キーをバインドする</span><span class="sxs-lookup"><span data-stu-id="e3b5c-112">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="e3b5c-113">このコマンドは、↑キーを **History Search後方** 関数にバインドします。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-113">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="e3b5c-114">この関数は、コマンドラインの現在の内容で始まるコマンドラインを検索します。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-114">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="e3b5c-115">例 2: キーをスクリプトブロックにバインドする</span><span class="sxs-lookup"><span data-stu-id="e3b5c-115">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="e3b5c-116">この例では、1つのキーを使用してコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-116">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="e3b5c-117">このコマンドは、 `Ctrl+B` 行をクリアするスクリプトブロックにキーをバインドし、"build" という単語を挿入して、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-117">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="e3b5c-118">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="e3b5c-118">PARAMETERS</span></span>

### <span data-ttu-id="e3b5c-119">-BriefDescription</span><span class="sxs-lookup"><span data-stu-id="e3b5c-119">-BriefDescription</span></span>

<span data-ttu-id="e3b5c-120">キーバインドの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-120">A brief description of the key binding.</span></span> <span data-ttu-id="e3b5c-121">この説明はコマンドレットによって表示され `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-121">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="e3b5c-122">-コード</span><span class="sxs-lookup"><span data-stu-id="e3b5c-122">-Chord</span></span>

<span data-ttu-id="e3b5c-123">関数またはスクリプトブロックにバインドするキーまたはキーのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-123">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="e3b5c-124">単一の文字列を使用して1つのバインドを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-124">Use a single string to specify a single binding.</span></span> <span data-ttu-id="e3b5c-125">バインドが一連のキーである場合は、次の例のように、キーをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-125">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

<span data-ttu-id="e3b5c-126">このパラメーターは、文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-126">This parameter accepts an array of strings.</span></span> <span data-ttu-id="e3b5c-127">各文字列は個別のバインドであり、1つのバインドのキーのシーケンスではありません。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-127">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="e3b5c-128">-Description</span><span class="sxs-lookup"><span data-stu-id="e3b5c-128">-Description</span></span>

<span data-ttu-id="e3b5c-129">コマンドレットの出力に表示されるキーバインドの詳細な説明を指定し `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-129">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="e3b5c-130">-関数</span><span class="sxs-lookup"><span data-stu-id="e3b5c-130">-Function</span></span>

<span data-ttu-id="e3b5c-131">PSReadLine によって提供される既存のキーハンドラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-131">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="e3b5c-132">このパラメーターを使用すると、既存のキーバインドを再バインドしたり、現在バインドされていないハンドラーをバインドしたりできます。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-132">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

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

### <span data-ttu-id="e3b5c-133">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="e3b5c-133">-ScriptBlock</span></span>

<span data-ttu-id="e3b5c-134">コードの入力時に実行するスクリプトブロックの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-134">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="e3b5c-135">PSReadLine は、このスクリプトブロックに1つまたは2つのパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-135">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="e3b5c-136">最初のパラメーターは、押されたキーを表す **Consolekeyinfo** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-136">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="e3b5c-137">2番目の引数には、コンテキストに応じて任意のオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-137">The second argument can be any object depending on the context.</span></span>

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

### <span data-ttu-id="e3b5c-138">-ViMode</span><span class="sxs-lookup"><span data-stu-id="e3b5c-138">-ViMode</span></span>

<span data-ttu-id="e3b5c-139">バインドが適用される vi モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-139">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="e3b5c-140">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-140">Valid values are:</span></span>

- <span data-ttu-id="e3b5c-141">挿入</span><span class="sxs-lookup"><span data-stu-id="e3b5c-141">Insert</span></span>
- <span data-ttu-id="e3b5c-142">コマンド</span><span class="sxs-lookup"><span data-stu-id="e3b5c-142">Command</span></span>

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

### <span data-ttu-id="e3b5c-143">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="e3b5c-143">CommonParameters</span></span>

<span data-ttu-id="e3b5c-144">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="e3b5c-145">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="e3b5c-146">入力</span><span class="sxs-lookup"><span data-stu-id="e3b5c-146">INPUTS</span></span>

### <span data-ttu-id="e3b5c-147">なし</span><span class="sxs-lookup"><span data-stu-id="e3b5c-147">None</span></span>

<span data-ttu-id="e3b5c-148">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-148">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="e3b5c-149">出力</span><span class="sxs-lookup"><span data-stu-id="e3b5c-149">OUTPUTS</span></span>

### <span data-ttu-id="e3b5c-150">なし</span><span class="sxs-lookup"><span data-stu-id="e3b5c-150">None</span></span>

<span data-ttu-id="e3b5c-151">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-151">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="e3b5c-152">注</span><span class="sxs-lookup"><span data-stu-id="e3b5c-152">NOTES</span></span>

## <span data-ttu-id="e3b5c-153">関連リンク</span><span class="sxs-lookup"><span data-stu-id="e3b5c-153">RELATED LINKS</span></span>

[<span data-ttu-id="e3b5c-154">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="e3b5c-154">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="e3b5c-155">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="e3b5c-155">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="e3b5c-156">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="e3b5c-156">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="e3b5c-157">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="e3b5c-157">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

