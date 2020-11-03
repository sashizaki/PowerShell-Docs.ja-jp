---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: 1c6a21880bba0f074388c6e32baa8e1c7e93413d
ms.sourcegitcommit: ae8b89e12c6fa2108075888dd6da92788d6c2888
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "93225064"
---
# <span data-ttu-id="da449-103">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="da449-103">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="da449-104">概要</span><span class="sxs-lookup"><span data-stu-id="da449-104">SYNOPSIS</span></span>
<span data-ttu-id="da449-105">キーバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="da449-105">Removes a key binding.</span></span>

## <span data-ttu-id="da449-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da449-106">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="da449-107">Description</span><span class="sxs-lookup"><span data-stu-id="da449-107">DESCRIPTION</span></span>

<span data-ttu-id="da449-108">コマンドレットでは、 `Remove-PSReadLineKeyHandler` 指定されたキーバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="da449-108">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="da449-109">例</span><span class="sxs-lookup"><span data-stu-id="da449-109">EXAMPLES</span></span>

### <span data-ttu-id="da449-110">例 1: バインディングを削除する</span><span class="sxs-lookup"><span data-stu-id="da449-110">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="da449-111">このコマンドは、キーの組み合わせまたはコードからバインドを削除し `Ctrl+B` ます。</span><span class="sxs-lookup"><span data-stu-id="da449-111">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="da449-112">この `Ctrl+B` 記事では、コードを作成し `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="da449-112">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="da449-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da449-113">PARAMETERS</span></span>

### <span data-ttu-id="da449-114">-コード</span><span class="sxs-lookup"><span data-stu-id="da449-114">-Chord</span></span>

<span data-ttu-id="da449-115">削除するキーまたはキーのシーケンスの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="da449-115">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="da449-116">単一のバインドは、1つの文字列を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="da449-116">A single binding is specified by using a single string.</span></span> <span data-ttu-id="da449-117">バインドが一連のキーである場合は、次の例のように、キーをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="da449-117">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="da449-118">このパラメーターは、文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="da449-118">This parameter accepts an array of strings.</span></span> <span data-ttu-id="da449-119">各文字列は個別のバインドであり、1つのバインドのキーのシーケンスではありません。</span><span class="sxs-lookup"><span data-stu-id="da449-119">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="da449-120">-ViMode</span><span class="sxs-lookup"><span data-stu-id="da449-120">-ViMode</span></span>

<span data-ttu-id="da449-121">バインドが適用される vi モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="da449-121">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="da449-122">使用可能な値: Insert、Command。</span><span class="sxs-lookup"><span data-stu-id="da449-122">Possible values are: Insert, Command.</span></span>

```yaml
Type: Microsoft.PowerShell.ViMode
Parameter Sets: (All)
Aliases:
Accepted values: Insert, Command

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da449-123">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="da449-123">CommonParameters</span></span>

<span data-ttu-id="da449-124">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="da449-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da449-125">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="da449-125">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="da449-126">入力</span><span class="sxs-lookup"><span data-stu-id="da449-126">INPUTS</span></span>

### <span data-ttu-id="da449-127">なし</span><span class="sxs-lookup"><span data-stu-id="da449-127">None</span></span>

<span data-ttu-id="da449-128">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="da449-128">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="da449-129">出力</span><span class="sxs-lookup"><span data-stu-id="da449-129">OUTPUTS</span></span>

### <span data-ttu-id="da449-130">なし</span><span class="sxs-lookup"><span data-stu-id="da449-130">None</span></span>

## <span data-ttu-id="da449-131">注</span><span class="sxs-lookup"><span data-stu-id="da449-131">NOTES</span></span>

## <span data-ttu-id="da449-132">関連リンク</span><span class="sxs-lookup"><span data-stu-id="da449-132">RELATED LINKS</span></span>

[<span data-ttu-id="da449-133">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="da449-133">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="da449-134">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="da449-134">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="da449-135">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="da449-135">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="da449-136">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="da449-136">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
