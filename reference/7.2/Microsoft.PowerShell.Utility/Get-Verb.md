---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/07/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-verb?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Verb
ms.openlocfilehash: 6aba1c87a5d711cbfe84f9f6f6d1051acbcd524a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600412"
---
# <span data-ttu-id="405ac-102">Get-Verb</span><span class="sxs-lookup"><span data-stu-id="405ac-102">Get-Verb</span></span>

## <span data-ttu-id="405ac-103">概要</span><span class="sxs-lookup"><span data-stu-id="405ac-103">SYNOPSIS</span></span>
<span data-ttu-id="405ac-104">承認された PowerShell 動詞を取得します。</span><span class="sxs-lookup"><span data-stu-id="405ac-104">Gets approved PowerShell verbs.</span></span>

## <span data-ttu-id="405ac-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="405ac-105">SYNTAX</span></span>

```
Get-Verb [[-Verb] <String[]>] [[-Group] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="405ac-106">Description</span><span class="sxs-lookup"><span data-stu-id="405ac-106">DESCRIPTION</span></span>

<span data-ttu-id="405ac-107">関数は、 `Get-Verb` PowerShell コマンドでの使用が承認されている動詞を取得します。</span><span class="sxs-lookup"><span data-stu-id="405ac-107">The `Get-Verb` function gets verbs that are approved for use in PowerShell commands.</span></span>

<span data-ttu-id="405ac-108">PowerShell コマンドレットと関数名の形式を指定し、承認された動詞を含めることをお勧めし `Verb-Noun` ます。</span><span class="sxs-lookup"><span data-stu-id="405ac-108">It is recommended that PowerShell cmdlet and function names have the `Verb-Noun` format and include an approved verb.</span></span> <span data-ttu-id="405ac-109">この方法では、コマンド名の一貫性と予測可能性が向上し、使いやすくなります。</span><span class="sxs-lookup"><span data-stu-id="405ac-109">This practice makes command names more consistent, predictable, and easier to use.</span></span>

<span data-ttu-id="405ac-110">未承認の動詞を使用するコマンドは、PowerShell でも実行できます。</span><span class="sxs-lookup"><span data-stu-id="405ac-110">Commands that use unapproved verbs, still run in PowerShell.</span></span> <span data-ttu-id="405ac-111">ただし、承認されていない動詞を含むモジュールを名前にインポートすると、コマンドによって `Import-Module` 警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="405ac-111">However, when you import a module that includes a command with an unapproved verb in its name, the `Import-Module` command displays a warning message.</span></span>

> [!NOTE]
> <span data-ttu-id="405ac-112">が返す動詞リストが `Get-Verb` 完全ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="405ac-112">The verb list that `Get-Verb` returns might not be complete.</span></span> <span data-ttu-id="405ac-113">承認済みの PowerShell 動詞とその説明を更新した一覧については、「Microsoft Docs の承認された [動詞](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="405ac-113">For an updated list of approved PowerShell verbs with descriptions, see [Approved Verbs](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) in the Microsoft Docs.</span></span>

## <span data-ttu-id="405ac-114">例</span><span class="sxs-lookup"><span data-stu-id="405ac-114">Examples</span></span>

### <span data-ttu-id="405ac-115">例 1-すべての動詞の一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="405ac-115">Example 1 - Get a list of all verbs</span></span>

```powershell
Get-Verb
```

### <span data-ttu-id="405ac-116">例 2-"un" で始まる承認された動詞の一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="405ac-116">Example 2 - Get a list of approved verbs that begin with "un"</span></span>

```powershell
Get-Verb un*
```

```Output
Verb       AliasPrefix Group     Description
----       ----------- -----     -----------
Undo       un          Common    Sets a resource to its previous state
Unlock     uk          Common    Releases a resource that was locked
Unpublish  ub          Data      Makes a resource unavailable to others
Uninstall  us          Lifecycle Removes a resource from an indicated location
Unregister ur          Lifecycle Removes the entry for a resource from a repository
Unblock    ul          Security  Removes restrictions to a resource
Unprotect  up          Security  Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="405ac-117">例 3-セキュリティグループ内のすべての承認された動詞を取得する</span><span class="sxs-lookup"><span data-stu-id="405ac-117">Example 3 - Get all approved verbs in the Security group</span></span>

```powershell
Get-Verb -Group Security
```

```Output
Verb      AliasPrefix Group    Description
----      ----------- -----    -----------
Block     bl          Security Restricts access to a resource
Grant     gr          Security Allows access to a resource
Protect   pt          Security Safeguards a resource from attack or loss
Revoke    rk          Security Specifies an action that does not allow access to a resource
Unblock   ul          Security Removes restrictions to a resource
Unprotect up          Security Removes safeguards from a resource that were added to prevent it from attack or loss
```

### <span data-ttu-id="405ac-118">例 4-許可されていない動詞を持つモジュール内のすべてのコマンドを検索する</span><span class="sxs-lookup"><span data-stu-id="405ac-118">Example 4 - Finds all commands in a module that have unapproved verbs</span></span>

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## <span data-ttu-id="405ac-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="405ac-119">PARAMETERS</span></span>

### <span data-ttu-id="405ac-120">-動詞</span><span class="sxs-lookup"><span data-stu-id="405ac-120">-Verb</span></span>

<span data-ttu-id="405ac-121">指定した動詞のみを取得します。</span><span class="sxs-lookup"><span data-stu-id="405ac-121">Gets only the specified verbs.</span></span> <span data-ttu-id="405ac-122">動詞の名前または名前パターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="405ac-122">Enter the name of a verb or a name pattern.</span></span> <span data-ttu-id="405ac-123">ワイルドカードを指定できます。</span><span class="sxs-lookup"><span data-stu-id="405ac-123">Wildcards are allowed.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:
Accepted values: Common, Communications, Data, Diagnostic, Lifecycle, Other, Security

Required: False
Position: 1
Default value: All groups
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="405ac-124">-Group</span><span class="sxs-lookup"><span data-stu-id="405ac-124">-Group</span></span>

<span data-ttu-id="405ac-125">指定されたグループのみを取得します。</span><span class="sxs-lookup"><span data-stu-id="405ac-125">Gets only the specified groups.</span></span> <span data-ttu-id="405ac-126">グループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="405ac-126">Enter the name of a group.</span></span> <span data-ttu-id="405ac-127">ワイルドカードは使用できません。</span><span class="sxs-lookup"><span data-stu-id="405ac-127">Wildcards are not allowed.</span></span>

<span data-ttu-id="405ac-128">このパラメーターは、PowerShell 6.0 で導入されました。</span><span class="sxs-lookup"><span data-stu-id="405ac-128">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: All verbs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="405ac-129">共通パラメーター</span><span class="sxs-lookup"><span data-stu-id="405ac-129">CommonParameters</span></span>

<span data-ttu-id="405ac-130">このコマンドレットは、一般的なパラメーターをサポートしています。-Debug、-ErrorAction、-ErrorVariable、-InformationAction、-InformationVariable、-OutVariable、-OutBuffer、-PipelineVariable、-Verbose、-WarningAction、-WarningVariable です。</span><span class="sxs-lookup"><span data-stu-id="405ac-130">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="405ac-131">詳細については、「[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="405ac-131">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="405ac-132">入力</span><span class="sxs-lookup"><span data-stu-id="405ac-132">INPUTS</span></span>

### <span data-ttu-id="405ac-133">なし</span><span class="sxs-lookup"><span data-stu-id="405ac-133">None</span></span>

## <span data-ttu-id="405ac-134">出力</span><span class="sxs-lookup"><span data-stu-id="405ac-134">OUTPUTS</span></span>

### <span data-ttu-id="405ac-135">VerbInfo (システム管理)</span><span class="sxs-lookup"><span data-stu-id="405ac-135">System.Management.Automation.VerbInfo</span></span>

## <span data-ttu-id="405ac-136">注</span><span class="sxs-lookup"><span data-stu-id="405ac-136">NOTES</span></span>

<span data-ttu-id="405ac-137">PowerShell 動詞は、最も一般的な使用方法に基づいてグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="405ac-137">PowerShell verbs are assigned to a group based on their most common use.</span></span> <span data-ttu-id="405ac-138">グループは動詞の検索と比較を簡単にするように設計されています。使用を制限するためではありません。</span><span class="sxs-lookup"><span data-stu-id="405ac-138">The groups are designed to make the verbs easy to find and compare, not to restrict their use.</span></span> <span data-ttu-id="405ac-139">あらゆる種類のコマンドにあらゆる承認された動詞を使用できます。</span><span class="sxs-lookup"><span data-stu-id="405ac-139">You can use any approved verb for any type of command.</span></span>

<span data-ttu-id="405ac-140">各 PowerShell 動詞は、次のいずれかのグループに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="405ac-140">Each PowerShell verb is assigned to one of the following groups.</span></span>

- <span data-ttu-id="405ac-141">共通: Add など、ほぼすべてのコマンドレットに適用できる汎用アクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="405ac-141">Common: Define generic actions that can apply to almost any cmdlet, such as Add.</span></span>
- <span data-ttu-id="405ac-142">通信: 接続などの通信に適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="405ac-142">Communications: Define actions that apply to communications, such as Connect.</span></span>
- <span data-ttu-id="405ac-143">データ: バックアップなどのデータ処理に適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="405ac-143">Data: Define actions that apply to data handling, such as Backup.</span></span>
- <span data-ttu-id="405ac-144">診断: デバッグなどの診断に適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="405ac-144">Diagnostic: Define actions that apply to diagnostics, such as Debug.</span></span>
- <span data-ttu-id="405ac-145">ライフサイクル: 完了など、コマンドレットのライフサイクルに適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="405ac-145">Lifecycle: Define actions that apply to the lifecycle of a cmdlet, such as Complete.</span></span>
- <span data-ttu-id="405ac-146">セキュリティ: Revoke など、セキュリティに適用されるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="405ac-146">Security: Define actions that apply to security, such as Revoke.</span></span>
- <span data-ttu-id="405ac-147">その他: 他の種類のアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="405ac-147">Other: Define other types of actions.</span></span>

<span data-ttu-id="405ac-148">やなど、PowerShell と共にインストールされるコマンドレットの中には、 `Tee-Object` 未承認の動詞を使用するものがあり `Where-Object` ます。</span><span class="sxs-lookup"><span data-stu-id="405ac-148">Some of the cmdlets that are installed with PowerShell, such as `Tee-Object` and `Where-Object`, use unapproved verbs.</span></span> <span data-ttu-id="405ac-149">これらのコマンドレットは履歴例外であり、その動詞は **予約済み** として分類されます。</span><span class="sxs-lookup"><span data-stu-id="405ac-149">These cmdlets are historic exceptions and their verbs are classified as **reserved**.</span></span>

## <span data-ttu-id="405ac-150">関連リンク</span><span class="sxs-lookup"><span data-stu-id="405ac-150">RELATED LINKS</span></span>

[<span data-ttu-id="405ac-151">Import-Module</span><span class="sxs-lookup"><span data-stu-id="405ac-151">Import-Module</span></span>](../microsoft.powershell.core/import-module.md)

