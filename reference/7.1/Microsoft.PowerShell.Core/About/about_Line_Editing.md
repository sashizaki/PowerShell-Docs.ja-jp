---
description: PowerShell コマンドプロンプトでコマンドを編集する方法について説明します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 07/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_line_editing?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Line_Editing
ms.openlocfilehash: 31659994e5b99cddd7374badff10e3286b1a4916
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93220443"
---
# <a name="about-line-editing"></a><span data-ttu-id="2a4d4-104">行の編集について</span><span class="sxs-lookup"><span data-stu-id="2a4d4-104">About Line Editing</span></span>

## <a name="short-description"></a><span data-ttu-id="2a4d4-105">簡単な説明</span><span class="sxs-lookup"><span data-stu-id="2a4d4-105">Short description</span></span>

<span data-ttu-id="2a4d4-106">PowerShell コマンドプロンプトでコマンドを編集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-106">Describes how to edit commands at the PowerShell command prompt.</span></span>

## <a name="long-description"></a><span data-ttu-id="2a4d4-107">長い説明</span><span class="sxs-lookup"><span data-stu-id="2a4d4-107">Long description</span></span>

<span data-ttu-id="2a4d4-108">Powershell コンソールには、PowerShell コマンドプロンプトでコマンドを編集するための便利なショートカットキーがあります。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-108">The PowerShell console has some useful keyboard shortcuts to help you edit commands at the PowerShell command prompt.</span></span>

### <a name="add-a-line"></a><span data-ttu-id="2a4d4-109">線を追加する</span><span class="sxs-lookup"><span data-stu-id="2a4d4-109">Add a line</span></span>

<span data-ttu-id="2a4d4-110">線を追加するには、Shift キーを押し<kbd>ながら</kbd> + <kbd>enter</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-110">To add a line, press <kbd>Shift</kbd>+<kbd>Enter</kbd>.</span></span>

<span data-ttu-id="2a4d4-111">複数の行を追加できます。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-111">You can add multiple lines.</span></span> <span data-ttu-id="2a4d4-112">追加の各行は `>>` 、継続のプロンプトで始まります。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-112">Each additional line begins with `>>`, the continuation prompt.</span></span> <span data-ttu-id="2a4d4-113"><kbd>Enter</kbd>キーを押してコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-113">Press <kbd>Enter</kbd> to execute the command.</span></span>

### <a name="move-left-and-right"></a><span data-ttu-id="2a4d4-114">左右に移動</span><span class="sxs-lookup"><span data-stu-id="2a4d4-114">Move left and right</span></span>

<span data-ttu-id="2a4d4-115">カーソルを1文字左に移動するには、 <kbd>左矢印</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-115">To move the cursor one character to the left, press the <kbd>Left arrow</kbd>.</span></span>

<span data-ttu-id="2a4d4-116">カーソルを1単語左に移動するには、 <kbd>ctrl</kbd> + <kbd>左方向</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-116">To move the cursor one word to the left, press <kbd>Ctrl</kbd>+<kbd>Left arrow</kbd>.</span></span>

<span data-ttu-id="2a4d4-117">カーソルを1文字右に移動するには、 <kbd>右矢印</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-117">To move the cursor one character to the right, press the <kbd>Right arrow</kbd>.</span></span>

<span data-ttu-id="2a4d4-118">カーソルを1ワード右に移動するには、 <kbd>ctrl</kbd>キーを押しながら + <kbd>右方向</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-118">To move the cursor one word to the right, press <kbd>Ctrl</kbd>+<kbd>Right arrow</kbd>.</span></span>

### <a name="move-to-a-lines-beginning-or-end"></a><span data-ttu-id="2a4d4-119">行の先頭または末尾に移動する</span><span class="sxs-lookup"><span data-stu-id="2a4d4-119">Move to a line's beginning or end</span></span>

<span data-ttu-id="2a4d4-120">行の先頭に移動するには、[ <kbd>ホーム</kbd>] を押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-120">To move to the beginning of a line, press <kbd>Home</kbd>.</span></span>

<span data-ttu-id="2a4d4-121">行の末尾に移動するには、[ <kbd>終了</kbd>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-121">To move to the end of a line, press <kbd>End</kbd>.</span></span>

<span data-ttu-id="2a4d4-122">行が追加された場合は、 <kbd>Home</kbd> キーまたは <kbd>end</kbd> キーを2回押して、行の先頭または末尾に移動します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-122">If lines were added, press <kbd>Home</kbd> or <kbd>End</kbd> twice to move to the beginning or end of the lines.</span></span>

### <a name="delete-characters"></a><span data-ttu-id="2a4d4-123">文字の削除</span><span class="sxs-lookup"><span data-stu-id="2a4d4-123">Delete characters</span></span>

<span data-ttu-id="2a4d4-124">カーソルの位置の背後にある文字を削除するには、 <kbd>Backspace</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-124">To delete the character behind the cursor's position, press <kbd>Backspace</kbd>.</span></span>

<span data-ttu-id="2a4d4-125">カーソルの位置にある文字を削除するには、 <kbd>del キーを</kbd>押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-125">To delete the character at the cursor's position, press <kbd>Delete</kbd>.</span></span>

### <a name="delete-characters-from-a-line"></a><span data-ttu-id="2a4d4-126">行から文字を削除する</span><span class="sxs-lookup"><span data-stu-id="2a4d4-126">Delete characters from a line</span></span>

<span data-ttu-id="2a4d4-127">カーソルの位置から行末までのすべての文字を削除するには、 <kbd>ctrl</kbd> + <kbd>end</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-127">To delete all the characters from the cursor's position to the end of a line, press <kbd>Ctrl</kbd>+<kbd>End</kbd>.</span></span>

<span data-ttu-id="2a4d4-128">カーソルの位置から行頭までのすべての文字を削除するには、 <kbd>ctrl</kbd> + <kbd>Home</kbd>キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-128">To delete all the characters from the cursor's position to the beginning of a line, press <kbd>Ctrl</kbd>+<kbd>Home</kbd>.</span></span>

<span data-ttu-id="2a4d4-129">行が追加された場合、現在の行と追加された行から文字が削除されます。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-129">If lines were added, characters are deleted from the current line and the lines that were added.</span></span>

### <a name="insert-and-overstrike-mode"></a><span data-ttu-id="2a4d4-130">Insert および上書きモード</span><span class="sxs-lookup"><span data-stu-id="2a4d4-130">Insert and overstrike mode</span></span>

<span data-ttu-id="2a4d4-131">上書きモードに変更するには、[ <kbd>挿入</kbd>] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-131">To change to overwrite mode, press <kbd>Insert</kbd>.</span></span> <span data-ttu-id="2a4d4-132">挿入モードに戻るには、もう一度 <kbd>insert</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-132">To return to insert mode, press <kbd>Insert</kbd> again.</span></span>

### <a name="tab-completion"></a><span data-ttu-id="2a4d4-133">Tab 補完機能</span><span class="sxs-lookup"><span data-stu-id="2a4d4-133">Tab completion</span></span>

<span data-ttu-id="2a4d4-134">コマンドレット名、パラメーター、またはパスを完了するには、 <kbd>tab</kbd> キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-134">To complete a cmdlet name, a parameter, or a path, press the <kbd>Tab</kbd> key.</span></span> <span data-ttu-id="2a4d4-135">値の一覧をスクロールするには、 <kbd>tab</kbd> キーをもう一度押します。</span><span class="sxs-lookup"><span data-stu-id="2a4d4-135">To scroll through a list of values, press the <kbd>Tab</kbd> key again.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a4d4-136">関連項目</span><span class="sxs-lookup"><span data-stu-id="2a4d4-136">See also</span></span>

[<span data-ttu-id="2a4d4-137">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="2a4d4-137">about_Command_Syntax</span></span>](about_Command_Syntax.md)

[<span data-ttu-id="2a4d4-138">about_Path_Syntax</span><span class="sxs-lookup"><span data-stu-id="2a4d4-138">about_Path_Syntax</span></span>](about_Path_Syntax.md)

[<span data-ttu-id="2a4d4-139">about_PSReadline</span><span class="sxs-lookup"><span data-stu-id="2a4d4-139">about_PSReadline</span></span>](../../PSReadline/About/about_PSReadline.md)
