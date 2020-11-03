---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 09/07/2018
Module Name: Microsoft.PowerShell.Core
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/functions/get-verb?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 4474bb50c2bf3be10e72d2554190208e956f9040
ms.sourcegitcommit: 7d052985c20761fdf4c6d7ce4e04df4c551c36a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/11/2020
ms.locfileid: "93219496"
---
# <span data-ttu-id="8f0d9-103">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="8f0d9-103">Get-Verb</span></span>

## <span data-ttu-id="8f0d9-104">概要</span><span class="sxs-lookup"><span data-stu-id="8f0d9-104">SYNOPSIS</span></span>
<span data-ttu-id="8f0d9-105">承認された PowerShell 動詞を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-105">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="8f0d9-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="8f0d9-106">SYNTAX</span></span>

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="8f0d9-107">Description</span><span class="sxs-lookup"><span data-stu-id="8f0d9-107">DESCRIPTION</span></span>

<span data-ttu-id="8f0d9-108">関数は、 `Get-Verb` PowerShell コマンドでの使用が承認されている動詞を取得します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-108">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="8f0d9-109">PowerShell では、コマンドレットと関数の名前を Verb-Noun 形式にし、承認された動詞を含めることを推奨しています。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-109">PowerShell recommends cmdlet and function names have the Verb-Noun format and include an approved verb.</span></span> <span data-ttu-id="8f0d9-110">この方法では、コマンド名の一貫性と予測可能性が向上し、使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-110">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="8f0d9-111">未承認の動詞を使用するコマンドは、PowerShell で実行されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-111">Commands that use unapproved verbs run in PowerShell.</span></span> <span data-ttu-id="8f0d9-112">ただし、承認されていない動詞を含むモジュールを名前にインポートすると、コマンドによって `Import-Module` 警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-112">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="8f0d9-113">が返す動詞リストが `Get-Verb` 完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-113">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="8f0d9-114">承認済みの PowerShell 動詞とその説明を更新した一覧については、「Microsoft Docs の承認された [動詞](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-114">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="8f0d9-115">例</span><span class="sxs-lookup"><span data-stu-id="8f0d9-115">EXAMPLES</span></span>

### <span data-ttu-id="8f0d9-116">例 1-すべての動詞の一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="8f0d9-116">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="8f0d9-117">例 2-"un" で始まる承認された動詞の一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="8f0d9-117">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb                 Group
----                 -----
Undo                 Common
Unlock               Common
Unpublish            Data
Uninstall            Lifecycle
Unregister           Lifecycle
Unblock              Security
Unprotect            Security
```

### <span data-ttu-id="8f0d9-118">例 3-セキュリティグループ内のすべての承認された動詞を取得する</span><span class="sxs-lookup"><span data-stu-id="8f0d9-118">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb | Where-Object Group -EQ Security
```

```Output
Verb      Group
----      -----
Block     Security
Grant     Security
Protect   Security
Revoke    Security
Unblock   Security
Unprotect Security
```

### <span data-ttu-id="8f0d9-119">例 4-許可されていない動詞を持つモジュール内のすべてのコマンドを検索する</span><span class="sxs-lookup"><span data-stu-id="8f0d9-119">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="8f0d9-120">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="8f0d9-120">PARAMETERS</span></span>

### <span data-ttu-id="8f0d9-121">-動詞</span><span class="sxs-lookup"><span data-stu-id="8f0d9-121">-verb</span></span>

<span data-ttu-id="8f0d9-122">指定した動詞のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-122">Gets only the specified verbs.</span></span>
<span data-ttu-id="8f0d9-123">動詞の名前または名前パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-123">Enter the name of a verb or a name pattern.</span></span>
<span data-ttu-id="8f0d9-124">ワイルドカードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-124">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: All verbs
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

## <span data-ttu-id="8f0d9-125">入力</span><span class="sxs-lookup"><span data-stu-id="8f0d9-125">INPUTS</span></span>

### <span data-ttu-id="8f0d9-126">なし</span><span class="sxs-lookup"><span data-stu-id="8f0d9-126">None</span></span>

## <span data-ttu-id="8f0d9-127">出力</span><span class="sxs-lookup"><span data-stu-id="8f0d9-127">OUTPUTS</span></span>

### <span data-ttu-id="8f0d9-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span><span class="sxs-lookup"><span data-stu-id="8f0d9-128">Selected.Microsoft.PowerShell.Commands.MemberDefinition</span></span>

## <span data-ttu-id="8f0d9-129">注</span><span class="sxs-lookup"><span data-stu-id="8f0d9-129">NOTES</span></span>

<span data-ttu-id="8f0d9-130">`Get-Verb` Microsoft. PowerShell. MemberDefinition オブジェクトの変更されたバージョンを返します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-130">`Get-Verb` returns a modified version of a Microsoft.PowerShell.Commands.MemberDefinition object.</span></span>
<span data-ttu-id="8f0d9-131">このオブジェクトには MemberDefinition オブジェクトの標準プロパティがありません。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-131">The object does not have the standard properties of a MemberDefinition object.</span></span> <span data-ttu-id="8f0d9-132">代わりに、Verb プロパティと Group プロパティがあります。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-132">Instead it has Verb and Group properties.</span></span> <span data-ttu-id="8f0d9-133">Verb プロパティには文字列と動詞名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-133">The Verb property contains a string with the verb name.</span></span> <span data-ttu-id="8f0d9-134">Group プロパティには文字列と動詞グループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-134">The Group property contains a string with the verb group.</span></span>

<span data-ttu-id="8f0d9-135">PowerShell 動詞は、最も一般的な使用方法に基づいてグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-135">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="8f0d9-136">グループは動詞の検索と比較を簡単にするように設計されています。使用を制限するためではありません。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-136">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="8f0d9-137">あらゆる種類のコマンドにあらゆる承認された動詞を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-137">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="8f0d9-138">各 PowerShell 動詞は、次のいずれかのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-138">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="8f0d9-139">共通: Add など、ほぼすべてのコマンドレットに適用できる汎用アクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-139">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="8f0d9-140">通信: 接続などの通信に適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-140">Communications:  Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="8f0d9-141">データ: バックアップなどのデータ処理に適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-141">Data:  Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="8f0d9-142">診断: デバッグなどの診断に適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-142">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="8f0d9-143">ライフサイクル: 完了など、コマンドレットのライフサイクルに適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-143">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="8f0d9-144">セキュリティ: Revoke など、セキュリティに適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-144">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="8f0d9-145">その他: 他の種類のアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-145">Other: Define other types of actions.</span></span>

<span data-ttu-id="8f0d9-146">やなど、PowerShell と共にインストールされるコマンドレットの中には、 `Tee-Object` 未承認の動詞を使用するものがあり `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-146">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="8f0d9-147">これらのコマンドレットは履歴例外であり、その動詞は **予約済み** として分類されます。</span><span class="sxs-lookup"><span data-stu-id="8f0d9-147">These cmdlets are historic exceptions and their verbs are classified as **reserved**.</span></span>

## <span data-ttu-id="8f0d9-148">関連リンク</span><span class="sxs-lookup"><span data-stu-id="8f0d9-148">RELATED LINKS</span></span>

[<span data-ttu-id="8f0d9-149">Import-Module</span><span class="sxs-lookup"><span data-stu-id="8f0d9-149">Import-Module</span></span>](import-module.md)
