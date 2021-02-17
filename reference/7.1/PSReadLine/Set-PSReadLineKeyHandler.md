---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadLine
ms.date: 02/16/2021
online version: https://docs.microsoft.com/powershell/module/psreadline/set-psreadlinekeyhandler?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PSReadLineKeyHandler
ms.openlocfilehash: a6b3d437917e26909f5dd116f3d0afa944f4138d
ms.sourcegitcommit: 4f1c2fe700b8a0544c59e371eb7cfbc6d852b185
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/17/2021
ms.locfileid: "100563342"
---
# <span data-ttu-id="d677c-103">Set-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="d677c-103">Set-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="d677c-104">概要</span><span class="sxs-lookup"><span data-stu-id="d677c-104">SYNOPSIS</span></span>
<span data-ttu-id="d677c-105">ユーザー定義キーまたは PSReadLine キーハンドラー関数にキーをバインドします。</span><span class="sxs-lookup"><span data-stu-id="d677c-105">Binds keys to user-defined or PSReadLine key handler functions.</span></span>

## <span data-ttu-id="d677c-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d677c-106">SYNTAX</span></span>

### <span data-ttu-id="d677c-107">スクリプト ブロック</span><span class="sxs-lookup"><span data-stu-id="d677c-107">ScriptBlock</span></span>

```
Set-PSReadLineKeyHandler [-ScriptBlock] <ScriptBlock> [-BriefDescription <String>]
 [-Description <String>] [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

### <span data-ttu-id="d677c-108">機能</span><span class="sxs-lookup"><span data-stu-id="d677c-108">Function</span></span>

```
Set-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [-Function] <String>
 [<CommonParameters>]
```

## <span data-ttu-id="d677c-109">Description</span><span class="sxs-lookup"><span data-stu-id="d677c-109">DESCRIPTION</span></span>

<span data-ttu-id="d677c-110">`Set-PSReadLineKeyHandler`キーまたはキーのシーケンスが押されたときに、コマンドレットによって結果がカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="d677c-110">The `Set-PSReadLineKeyHandler` cmdlet customizes the result when a key or sequence of keys is pressed.</span></span> <span data-ttu-id="d677c-111">ユーザー定義のキーバインドを使用すると、PowerShell スクリプト内から可能なほとんどすべての操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="d677c-111">With user-defined key bindings, you can do almost anything that is possible from within a PowerShell script.</span></span>

## <span data-ttu-id="d677c-112">例</span><span class="sxs-lookup"><span data-stu-id="d677c-112">EXAMPLES</span></span>

### <span data-ttu-id="d677c-113">例 1: 関数に方向キーをバインドする</span><span class="sxs-lookup"><span data-stu-id="d677c-113">Example 1: Bind the arrow key to a function</span></span>

<span data-ttu-id="d677c-114">このコマンドは、↑キーを **History Search後方** 関数にバインドします。</span><span class="sxs-lookup"><span data-stu-id="d677c-114">This command binds the up arrow key to the **HistorySearchBackward** function.</span></span> <span data-ttu-id="d677c-115">この関数は、コマンドラインの現在の内容で始まるコマンドラインを検索します。</span><span class="sxs-lookup"><span data-stu-id="d677c-115">This function searches command history for command lines that start with the current contents of the command line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord UpArrow -Function HistorySearchBackward
```

### <span data-ttu-id="d677c-116">例 2: キーをスクリプトブロックにバインドする</span><span class="sxs-lookup"><span data-stu-id="d677c-116">Example 2: Bind a key to a script block</span></span>

<span data-ttu-id="d677c-117">この例では、1つのキーを使用してコマンドを実行する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="d677c-117">This example shows how a single key can be used to run a command.</span></span> <span data-ttu-id="d677c-118">このコマンドは、 `Ctrl+B` 行をクリアするスクリプトブロックにキーをバインドし、"build" という単語を挿入して、その行を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d677c-118">The command binds the key `Ctrl+B` to a script block that clears the line, inserts the word "build", and then accepts the line.</span></span>

```powershell
Set-PSReadLineKeyHandler -Chord Ctrl+B -ScriptBlock {
    [Microsoft.PowerShell.PSConsoleReadLine]::RevertLine()
    [Microsoft.PowerShell.PSConsoleReadLine]::Insert('build')
    [Microsoft.PowerShell.PSConsoleReadLine]::AcceptLine()
}
```

## <span data-ttu-id="d677c-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d677c-119">PARAMETERS</span></span>

### <span data-ttu-id="d677c-120">-BriefDescription</span><span class="sxs-lookup"><span data-stu-id="d677c-120">-BriefDescription</span></span>

<span data-ttu-id="d677c-121">キーバインドの簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="d677c-121">A brief description of the key binding.</span></span> <span data-ttu-id="d677c-122">この説明はコマンドレットによって表示され `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="d677c-122">This description is displayed by the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="d677c-123">-コード</span><span class="sxs-lookup"><span data-stu-id="d677c-123">-Chord</span></span>

<span data-ttu-id="d677c-124">関数またはスクリプトブロックにバインドするキーまたはキーのシーケンス。</span><span class="sxs-lookup"><span data-stu-id="d677c-124">The key or sequence of keys to be bound to a function or script block.</span></span> <span data-ttu-id="d677c-125">単一の文字列を使用して1つのバインドを指定します。</span><span class="sxs-lookup"><span data-stu-id="d677c-125">Use a single string to specify a single binding.</span></span> <span data-ttu-id="d677c-126">バインドが一連のキーである場合は、次の例のように、キーをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="d677c-126">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+X,Ctrl+L`

> [!NOTE]
> <span data-ttu-id="d677c-127">PSReadLine 2.0.0 の場合、 **コード** パラメーターでは **大文字と小文字が区別** されます。</span><span class="sxs-lookup"><span data-stu-id="d677c-127">As of PSReadLine 2.0.0, the **Chord** parameter is **case-sensitive**.</span></span> <span data-ttu-id="d677c-128">つまり、 `Ctrl+X` と `Ctrl+x` は異なるバインドを作成します。</span><span class="sxs-lookup"><span data-stu-id="d677c-128">Meaning, `Ctrl+X` and `Ctrl+x` will create different bindings.</span></span>

<span data-ttu-id="d677c-129">このパラメーターは、文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="d677c-129">This parameter accepts an array of strings.</span></span> <span data-ttu-id="d677c-130">各文字列は個別のバインドであり、1つのバインドのキーのシーケンスではありません。</span><span class="sxs-lookup"><span data-stu-id="d677c-130">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="d677c-131">-Description</span><span class="sxs-lookup"><span data-stu-id="d677c-131">-Description</span></span>

<span data-ttu-id="d677c-132">コマンドレットの出力に表示されるキーバインドの詳細な説明を指定し `Get-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="d677c-132">Specifies a more detailed description of the key binding that is visible in the output of the `Get-PSReadLineKeyHandler` cmdlet.</span></span>

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

### <span data-ttu-id="d677c-133">-関数</span><span class="sxs-lookup"><span data-stu-id="d677c-133">-Function</span></span>

<span data-ttu-id="d677c-134">PSReadLine によって提供される既存のキーハンドラーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d677c-134">Specifies the name of an existing key handler provided by PSReadLine.</span></span> <span data-ttu-id="d677c-135">このパラメーターを使用すると、既存のキーバインドを再バインドしたり、現在バインドされていないハンドラーをバインドしたりできます。</span><span class="sxs-lookup"><span data-stu-id="d677c-135">This parameter lets you rebind existing key bindings, or bind a handler that is currently unbound.</span></span>

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

### <span data-ttu-id="d677c-136">-ScriptBlock</span><span class="sxs-lookup"><span data-stu-id="d677c-136">-ScriptBlock</span></span>

<span data-ttu-id="d677c-137">コードの入力時に実行するスクリプトブロックの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="d677c-137">Specifies a script block value to run when the chord is entered.</span></span> <span data-ttu-id="d677c-138">PSReadLine は、このスクリプトブロックに1つまたは2つのパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="d677c-138">PSReadLine passes one or two parameters to this script block.</span></span> <span data-ttu-id="d677c-139">最初のパラメーターは、押されたキーを表す **Consolekeyinfo** オブジェクトです。</span><span class="sxs-lookup"><span data-stu-id="d677c-139">The first parameter is a **ConsoleKeyInfo** object representing the key pressed.</span></span> <span data-ttu-id="d677c-140">2番目の引数には、コンテキストに応じて任意のオブジェクトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="d677c-140">The second argument can be any object depending on the context.</span></span>

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

### <span data-ttu-id="d677c-141">-ViMode</span><span class="sxs-lookup"><span data-stu-id="d677c-141">-ViMode</span></span>

<span data-ttu-id="d677c-142">バインドが適用される vi モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="d677c-142">Specify which vi mode the binding applies to.</span></span>

<span data-ttu-id="d677c-143">次の値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="d677c-143">Valid values are:</span></span>

- <span data-ttu-id="d677c-144">挿入</span><span class="sxs-lookup"><span data-stu-id="d677c-144">Insert</span></span>
- <span data-ttu-id="d677c-145">コマンド</span><span class="sxs-lookup"><span data-stu-id="d677c-145">Command</span></span>

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

### <span data-ttu-id="d677c-146">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="d677c-146">CommonParameters</span></span>

<span data-ttu-id="d677c-147">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="d677c-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d677c-148">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d677c-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d677c-149">入力</span><span class="sxs-lookup"><span data-stu-id="d677c-149">INPUTS</span></span>

### <span data-ttu-id="d677c-150">なし</span><span class="sxs-lookup"><span data-stu-id="d677c-150">None</span></span>

<span data-ttu-id="d677c-151">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="d677c-151">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="d677c-152">出力</span><span class="sxs-lookup"><span data-stu-id="d677c-152">OUTPUTS</span></span>

### <span data-ttu-id="d677c-153">なし</span><span class="sxs-lookup"><span data-stu-id="d677c-153">None</span></span>

<span data-ttu-id="d677c-154">このコマンドレットは出力を生成しません。</span><span class="sxs-lookup"><span data-stu-id="d677c-154">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d677c-155">注</span><span class="sxs-lookup"><span data-stu-id="d677c-155">NOTES</span></span>

## <span data-ttu-id="d677c-156">関連リンク</span><span class="sxs-lookup"><span data-stu-id="d677c-156">RELATED LINKS</span></span>

[<span data-ttu-id="d677c-157">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="d677c-157">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="d677c-158">-PSReadLineKeyHandler を削除します。</span><span class="sxs-lookup"><span data-stu-id="d677c-158">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="d677c-159">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="d677c-159">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="d677c-160">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="d677c-160">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

