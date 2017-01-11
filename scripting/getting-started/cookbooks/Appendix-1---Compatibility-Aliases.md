---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "PowerShell, コマンドレット"
ms.date: 2016-12-12
title: "付録 1 - 互換性のあるエイリアス"
ms.technology: powershell
ms.assetid: 96ad921e-1a57-463e-8e60-424faf8b6ef8
ms.openlocfilehash: 126c124bd9bd4aa7c724fc0ef0b075a649d66f44
ms.sourcegitcommit: 8acbf9827ad8f4ef9753f826ecaff58495ca51b0
translationtype: HT
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

