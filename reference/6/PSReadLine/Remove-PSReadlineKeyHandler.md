---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: 6a15e829f589fbccf0da3479a22f24cdf3fc81ae
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214899"
---
# <span data-ttu-id="5627d-103">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="5627d-103">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="5627d-104">概要</span><span class="sxs-lookup"><span data-stu-id="5627d-104">SYNOPSIS</span></span>
<span data-ttu-id="5627d-105">キーバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="5627d-105">Removes a key binding.</span></span>

## <span data-ttu-id="5627d-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5627d-106">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="5627d-107">Description</span><span class="sxs-lookup"><span data-stu-id="5627d-107">DESCRIPTION</span></span>

<span data-ttu-id="5627d-108">コマンドレットでは、 `Remove-PSReadLineKeyHandler` 指定されたキーバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="5627d-108">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="5627d-109">例</span><span class="sxs-lookup"><span data-stu-id="5627d-109">EXAMPLES</span></span>

### <span data-ttu-id="5627d-110">例 1: バインディングを削除する</span><span class="sxs-lookup"><span data-stu-id="5627d-110">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="5627d-111">このコマンドは、キーの組み合わせまたはコードからバインドを削除し `Ctrl+B` ます。</span><span class="sxs-lookup"><span data-stu-id="5627d-111">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="5627d-112">この `Ctrl+B` 記事では、コードを作成し `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="5627d-112">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="5627d-113">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="5627d-113">PARAMETERS</span></span>

### <span data-ttu-id="5627d-114">-コード</span><span class="sxs-lookup"><span data-stu-id="5627d-114">-Chord</span></span>

<span data-ttu-id="5627d-115">削除するキーまたはキーのシーケンスの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="5627d-115">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="5627d-116">単一のバインドは、1つの文字列を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="5627d-116">A single binding is specified by using a single string.</span></span> <span data-ttu-id="5627d-117">バインドが一連のキーである場合は、次の例のように、キーをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="5627d-117">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="5627d-118">このパラメーターは、文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="5627d-118">This parameter accepts an array of strings.</span></span> <span data-ttu-id="5627d-119">各文字列は個別のバインドであり、1つのバインドのキーのシーケンスではありません。</span><span class="sxs-lookup"><span data-stu-id="5627d-119">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="5627d-120">-ViMode</span><span class="sxs-lookup"><span data-stu-id="5627d-120">-ViMode</span></span>

<span data-ttu-id="5627d-121">バインドが適用される vi モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="5627d-121">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="5627d-122">使用可能な値: Insert、Command。</span><span class="sxs-lookup"><span data-stu-id="5627d-122">Possible values are: Insert, Command.</span></span>

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

### <span data-ttu-id="5627d-123">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="5627d-123">CommonParameters</span></span>

<span data-ttu-id="5627d-124">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="5627d-124">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5627d-125">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5627d-125">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5627d-126">入力</span><span class="sxs-lookup"><span data-stu-id="5627d-126">INPUTS</span></span>

### <span data-ttu-id="5627d-127">なし</span><span class="sxs-lookup"><span data-stu-id="5627d-127">None</span></span>

<span data-ttu-id="5627d-128">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="5627d-128">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="5627d-129">出力</span><span class="sxs-lookup"><span data-stu-id="5627d-129">OUTPUTS</span></span>

### <span data-ttu-id="5627d-130">なし</span><span class="sxs-lookup"><span data-stu-id="5627d-130">None</span></span>

## <span data-ttu-id="5627d-131">注</span><span class="sxs-lookup"><span data-stu-id="5627d-131">NOTES</span></span>

## <span data-ttu-id="5627d-132">関連リンク</span><span class="sxs-lookup"><span data-stu-id="5627d-132">RELATED LINKS</span></span>

[<span data-ttu-id="5627d-133">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="5627d-133">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="5627d-134">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="5627d-134">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="5627d-135">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="5627d-135">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="5627d-136">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="5627d-136">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)
