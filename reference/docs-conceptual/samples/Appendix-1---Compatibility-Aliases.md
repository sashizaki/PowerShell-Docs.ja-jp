---
ms.date: 08/03/2020
keywords: powershell,コマンドレット
title: 付録 1 - 互換性のあるエイリアス
ms.openlocfilehash: e5bd170fea6b6109d2ef4fd58863d6cc8a0e3ae1
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758501"
---
# <a name="appendix-1---compatibility-aliases"></a>付録 1 - 互換性のあるエイリアス

PowerShell には、**UNIX** と **cmd.exe** のユーザーが使い慣れたコマンドを使用できるようにするさまざまなエイリアスがあります。
そのコマンドと、それに関連する PowerShell コマンドレットおよび PowerShell エイリアスを次の表に示します。

|            cmd.exe コマンド            | UNIX コマンド | PowerShell コマンドレット | PowerShell エイリアス |
| ------------------------------------- | ------------ | ----------------- | ---------------- |
| **cd**、**chdir**                     | **cd**       | `Set-Location`    | `sl`             |
| **cls**                               | **オフ**    | `Clear-Host`      | `cls`            |
| **copy**                              | **cp**       | `Copy-Item`       | `cpi`            |
| **del**、**erase**、**rd**、**rmdir** | **rm**       | `Remove-Item`     | `ri`             |
| **dir**                               | **ls**       | `Get-ChildItem`   | `gci`            |
| **echo**                              | **echo**     | `Write-Output`    | `write`          |
| **md**                                | **mkdir**    | `New-Item`        | `ni`             |
| **move**                              | **mv**       | `Move-Item`       | `mi`             |
| **popd**                              | **popd**     | `Pop-Location`    | `popd`           |
| **pushd**                             | **pushd**    | `Push-Location`   | `pushd`          |
| **ren**                               | **mv**       | `Rename-Item`     | `rni`            |
| **type**                              | **cat**      | `Get-Content`     | `gc`             |

PowerShell エイリアスを検索するには、[Get-Alias](xref:Microsoft.PowerShell.Utility.Get-Alias) コマンドレットを使用します。 コマンドレットのエイリアスを表示するには、**Definition** パラメーターを使用して、コマンドレット名を指定します。
または、エイリアスのコマンドレット名を検索するには、**Name** パラメーターを使用して、エイリアスを指定します。

```powershell
Get-Alias -Definition Get-ChildItem
```

```Output
CommandType     Name
-----------     ----
Alias           dir -> Get-ChildItem
Alias           gci -> Get-ChildItem
Alias           ls -> Get-ChildItem
```

```powershell
Get-Alias -Name gci
```

```Output
CommandType     Name
-----------     ----
Alias           gci -> Get-ChildItem
```
