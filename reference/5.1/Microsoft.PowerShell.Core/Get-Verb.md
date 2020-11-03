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
# Get-Verb

## 概要
承認された PowerShell 動詞を取得します。

## SYNTAX

```
Get-Verb [[-verb] <String[]>] [<CommonParameters>]
```

## Description

関数は、 `Get-Verb` PowerShell コマンドでの使用が承認されている動詞を取得します。

PowerShell では、コマンドレットと関数の名前を Verb-Noun 形式にし、承認された動詞を含めることを推奨しています。 この方法では、コマンド名の一貫性と予測可能性が向上し、使いやすくなります。

未承認の動詞を使用するコマンドは、PowerShell で実行されます。 ただし、承認されていない動詞を含むモジュールを名前にインポートすると、コマンドによって `Import-Module` 警告メッセージが表示されます。

> [!NOTE]
> が返す動詞リストが `Get-Verb` 完全ではない可能性があります。 承認済みの PowerShell 動詞とその説明を更新した一覧については、「Microsoft Docs の承認された [動詞](../../docs-conceptual/developer/cmdlet/approved-verbs-for-windows-powershell-commands.md) 」を参照してください。

## 例

### 例 1-すべての動詞の一覧を取得する

```powershell
Get-Verb
```

### 例 2-"un" で始まる承認された動詞の一覧を取得する

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

### 例 3-セキュリティグループ内のすべての承認された動詞を取得する

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

### 例 4-許可されていない動詞を持つモジュール内のすべてのコマンドを検索する

```powershell
Get-Command -Module Microsoft.PowerShell.Utility | Where-Object Verb -NotIn (Get-Verb).Verb
```

```Output
CommandType     Name            Version    Source
-----------     ----            -------    ------
Cmdlet          Sort-Object     3.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Tee-Object      3.1.0.0    Microsoft.PowerShell.Utility
```

## PARAMETERS

### -動詞

指定した動詞のみを取得します。
動詞の名前または名前パターンを入力します。
ワイルドカードを指定できます。

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

## 入力

### なし

## 出力

### Selected.Microsoft.PowerShell.Commands.MemberDefinition

## 注

`Get-Verb` Microsoft. PowerShell. MemberDefinition オブジェクトの変更されたバージョンを返します。
このオブジェクトには MemberDefinition オブジェクトの標準プロパティがありません。 代わりに、Verb プロパティと Group プロパティがあります。 Verb プロパティには文字列と動詞名が含まれます。 Group プロパティには文字列と動詞グループが含まれます。

PowerShell 動詞は、最も一般的な使用方法に基づいてグループに割り当てられます。 グループは動詞の検索と比較を簡単にするように設計されています。使用を制限するためではありません。 あらゆる種類のコマンドにあらゆる承認された動詞を使用できます。

各 PowerShell 動詞は、次のいずれかのグループに割り当てられます。

- 共通: Add など、ほぼすべてのコマンドレットに適用できる汎用アクションを定義します。
- 通信: 接続などの通信に適用されるアクションを定義します。
- データ: バックアップなどのデータ処理に適用されるアクションを定義します。
- 診断: デバッグなどの診断に適用されるアクションを定義します。
- ライフサイクル: 完了など、コマンドレットのライフサイクルに適用されるアクションを定義します。
- セキュリティ: Revoke など、セキュリティに適用されるアクションを定義します。
- その他: 他の種類のアクションを定義します。

やなど、PowerShell と共にインストールされるコマンドレットの中には、 `Tee-Object` 未承認の動詞を使用するものがあり `Where-Object` ます。 これらのコマンドレットは履歴例外であり、その動詞は **予約済み** として分類されます。

## 関連リンク

[Import-Module](import-module.md)
