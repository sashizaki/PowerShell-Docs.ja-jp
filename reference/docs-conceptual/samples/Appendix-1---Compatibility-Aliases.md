---
ms.date: 09/09/2019
keywords: PowerShell, コマンドレット
title: 付録 1 - 互換性のあるエイリアス
ms.openlocfilehash: 2351fdf23711fe1417f7e3fc3cca5b642d5a59fc
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "70848167"
---
# <a name="appendix-1---compatibility-aliases"></a>付録 1 - 互換性のあるエイリアス

PowerShell には、**UNIX** と **cmd.exe** のユーザーが使い慣れたコマンドを使用できるようにするさまざまなエイリアスがあります。
そのコマンドと、それに関連する PowerShell コマンドレットおよび PowerShell エイリアスを次の表に示します。

|cmd.exe コマンド|UNIX コマンド|PowerShell コマンドレット|PowerShell エイリアス|
|---------------|----------------|--------------|------------|
|**cls**|**clear**|`Clear-Host` (関数)|`cls`|
|**copy**|**cp**|`Copy-Item`|`cpi`|
|**dir**|**ls**|`Get-ChildItem`|`gci`|
|**type**|**cat**|`Get-Content`|`gc`|
|**move**|**mv**|`Move-Item`|`mi`|
|**md**|**mkdir**|`New-Item`|`ni`|
|**pushd**|**pushd**|`Push-Location`|`pushd`|
|**popd**|**popd**|`Pop-Location`|`popd`|
|**del**、**erase**、**rd**、**rmdir**|**rm**|`Remove-Item`|`ri`|
|**ren**|**mv**|`Rename-Item`|`rni`|
|**cd**、**chdir**|**cd**|`Set-Location`|`sl`|

PowerShell エイリアスを検索するには、[Get-Alias](/powershell/module/Microsoft.PowerShell.Utility/Get-Alias) コマンドレットを使用します。 コマンドレットのエイリアスを表示するには、**Definition** パラメーターを使用して、コマンドレット名を指定します。
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
