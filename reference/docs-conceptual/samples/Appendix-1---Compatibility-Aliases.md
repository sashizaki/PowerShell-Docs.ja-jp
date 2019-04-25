---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: 付録 1 - 互換性のあるエイリアス
ms.assetid: 96ad921e-1a57-463e-8e60-424faf8b6ef8
ms.openlocfilehash: 113bbee1af185f98777df5767022d54accb69447
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086308"
---
# <a name="appendix-1---compatibility-aliases"></a>付録 1 - 互換性のあるエイリアス

Windows PowerShell には、UNIX と Cmd のユーザーが使い慣れたコマンド名を Windows PowerShell でも使用できるようにするいくつかの移行エイリアスがあります。 最も一般的なエイリアスについて、対応する Windows PowerShell コマンド、および Windows PowerShell の標準エイリアス (存在する場合) と共に以下の表にまとめました。

エイリアスに対応する Windows PowerShell コマンドは、Windows PowerShell から Get-Alias コマンドレットを使用して検索できます。 たとえば、**get-alias cls** と入力します。

```
CommandType     Name                            Definition
-----------     ----                            ----------
Alias           cls                             Clear-Host
```

|CMD コマンド|UNIX コマンド|PS コマンド|PS エイリアス|
|---------------|----------------|--------------|------------|
|**dir**|**ls**|**Get-ChildItem**|**gci**|
|**cls**|**clear**|**Clear-Host** (関数)|**cls**|
|**del、erase、rmdir**|**rm**|**Remove-Item**|**ri**|
|**copy**|**cp**|**Copy-Item**|**ci**|
|**move**|**mv**|**Move-Item**|**mi**|
|**rename**|**mv**|**Rename-Item**|**rni**|
|**type**|**cat**|**Get-Content**|**gc**|
|**cd**|**cd**|**Set-Location**|**sl**|
|**md**|**mkdir**|**New-Item**|**ni**|
|**pushd**|**pushd**|**Push-Location**|**pushd**|
|**popd**|**popd**|**Pop-Location**|**popd**|