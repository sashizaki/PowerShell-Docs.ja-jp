---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
Locale: en-US
Module Name: PSReadLine
ms.date: 12/07/2018
online version: https://docs.microsoft.com/powershell/module/psreadline/remove-psreadlinekeyhandler?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSReadLineKeyHandler
ms.openlocfilehash: d280eba2e717ccfb0b896d62f42079390d1db848
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601398"
---
# <span data-ttu-id="370da-102">Remove-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="370da-102">Remove-PSReadLineKeyHandler</span></span>

## <span data-ttu-id="370da-103">概要</span><span class="sxs-lookup"><span data-stu-id="370da-103">SYNOPSIS</span></span>
<span data-ttu-id="370da-104">キーバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="370da-104">Removes a key binding.</span></span>

## <span data-ttu-id="370da-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="370da-105">SYNTAX</span></span>

```
Remove-PSReadLineKeyHandler [-Chord] <String[]> [-ViMode <ViMode>] [<CommonParameters>]
```

## <span data-ttu-id="370da-106">Description</span><span class="sxs-lookup"><span data-stu-id="370da-106">DESCRIPTION</span></span>

<span data-ttu-id="370da-107">コマンドレットでは、 `Remove-PSReadLineKeyHandler` 指定されたキーバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="370da-107">The `Remove-PSReadLineKeyHandler` cmdlet removes a specified key binding.</span></span>

## <span data-ttu-id="370da-108">例</span><span class="sxs-lookup"><span data-stu-id="370da-108">EXAMPLES</span></span>

### <span data-ttu-id="370da-109">例 1: バインディングを削除する</span><span class="sxs-lookup"><span data-stu-id="370da-109">Example 1: Remove a binding</span></span>

```powershell
Remove-PSReadLineKeyHandler -Chord Ctrl+B
```

<span data-ttu-id="370da-110">このコマンドは、キーの組み合わせまたはコードからバインドを削除し `Ctrl+B` ます。</span><span class="sxs-lookup"><span data-stu-id="370da-110">This command removes the binding from the key combination, or chord, `Ctrl+B`.</span></span> <span data-ttu-id="370da-111">この `Ctrl+B` 記事では、コードを作成し `Set-PSReadLineKeyHandler` ます。</span><span class="sxs-lookup"><span data-stu-id="370da-111">The `Ctrl+B` chord is created in the `Set-PSReadLineKeyHandler` article.</span></span>

## <span data-ttu-id="370da-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="370da-112">PARAMETERS</span></span>

### <span data-ttu-id="370da-113">-コード</span><span class="sxs-lookup"><span data-stu-id="370da-113">-Chord</span></span>

<span data-ttu-id="370da-114">削除するキーまたはキーのシーケンスの配列を指定します。</span><span class="sxs-lookup"><span data-stu-id="370da-114">Specifies an array of keys or sequences of keys to be removed.</span></span> <span data-ttu-id="370da-115">単一のバインドは、1つの文字列を使用して指定します。</span><span class="sxs-lookup"><span data-stu-id="370da-115">A single binding is specified by using a single string.</span></span> <span data-ttu-id="370da-116">バインドが一連のキーである場合は、次の例のように、キーをコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="370da-116">If the binding is a sequence of keys, separate the keys by a comma, as in the following example:</span></span>

`Ctrl+x,Ctrl+l`

<span data-ttu-id="370da-117">このパラメーターは、文字列の配列を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="370da-117">This parameter accepts an array of strings.</span></span> <span data-ttu-id="370da-118">各文字列は個別のバインドであり、1つのバインドのキーのシーケンスではありません。</span><span class="sxs-lookup"><span data-stu-id="370da-118">Each string is a separate binding, not a sequence of keys for a single binding.</span></span>

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

### <span data-ttu-id="370da-119">-ViMode</span><span class="sxs-lookup"><span data-stu-id="370da-119">-ViMode</span></span>

<span data-ttu-id="370da-120">バインドが適用される vi モードを指定します。</span><span class="sxs-lookup"><span data-stu-id="370da-120">Specify which vi mode the binding applies to.</span></span> <span data-ttu-id="370da-121">使用可能な値: Insert、Command。</span><span class="sxs-lookup"><span data-stu-id="370da-121">Possible values are: Insert, Command.</span></span>

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

### <span data-ttu-id="370da-122">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="370da-122">CommonParameters</span></span>

<span data-ttu-id="370da-123">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="370da-123">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="370da-124">詳細については、「[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="370da-124">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="370da-125">入力</span><span class="sxs-lookup"><span data-stu-id="370da-125">INPUTS</span></span>

### <span data-ttu-id="370da-126">なし</span><span class="sxs-lookup"><span data-stu-id="370da-126">None</span></span>

<span data-ttu-id="370da-127">このコマンドレットにパイプを使用してオブジェクトを渡すことはできません。</span><span class="sxs-lookup"><span data-stu-id="370da-127">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="370da-128">出力</span><span class="sxs-lookup"><span data-stu-id="370da-128">OUTPUTS</span></span>

### <span data-ttu-id="370da-129">なし</span><span class="sxs-lookup"><span data-stu-id="370da-129">None</span></span>

## <span data-ttu-id="370da-130">注</span><span class="sxs-lookup"><span data-stu-id="370da-130">NOTES</span></span>

## <span data-ttu-id="370da-131">関連リンク</span><span class="sxs-lookup"><span data-stu-id="370da-131">RELATED LINKS</span></span>

[<span data-ttu-id="370da-132">Get-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="370da-132">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="370da-133">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="370da-133">Get-PSReadLineOption</span></span>](Get-PSReadLineOption.md)

[<span data-ttu-id="370da-134">設定-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="370da-134">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="370da-135">設定-PSReadLineKeyHandler</span><span class="sxs-lookup"><span data-stu-id="370da-135">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)

