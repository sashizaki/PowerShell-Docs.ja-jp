---
title: "付録 1 - 互換性のあるエイリアス"
ms.date: 2016-05-11
keywords: powershell,cmdlet
description: 
ms.topic: article
author: jpjofre
manager: dongill
ms.prod: powershell
ms.assetid: 96ad921e-1a57-463e-8e60-424faf8b6ef8
translationtype: Human Translation
ms.sourcegitcommit: 03ac4b90d299b316194f1fa932e7dbf62d4b1c8e
ms.openlocfilehash: 38a6cb1b0402825b307652e6747ea65baafd1d8b

---

# 付録 1 - 互換性のあるエイリアス
Windows PowerShell には、UNIX と Cmd のユーザーが使い慣れたコマンド名を Windows PowerShell でも使用できるようにするいくつかの移行エイリアスがあります。 最も一般的なエイリアスについて、対応する Windows PowerShell コマンド、および Windows PowerShell の標準エイリアス (存在する場合) と共に以下の表にまとめました。

エイリアスに対応する Windows PowerShell コマンドは、Windows PowerShell から Get\-Alias コマンドレットを使用して検索できます。 たとえば、「**get\-alias cls**」と入力します。

```
CommandType     Name                            Definition
-----------     ----                            ----------
Alias           cls                             Clear-Host
```

|CMD コマンド|UNIX コマンド|PS コマンド|PS エイリアス|
|---------------|----------------|--------------|------------|
|**dir**|**ls**|**Get\-ChildItem**|**gci**|
|**cls**|**clear**|**Clear\-Host** (関数)|N\/A|
|**del、erase、rmdir**|**rm**|**Remove\-Item**|**ri**|
|**copy**|**cp**|**Copy\-Item**|**ci**|
|**move**|**mv**|**Move\-Item**|**mi**|
|**rename**|**mv**|**Rename\-Item**|**rni**|
|**型**|**cat**|**Get\-Content**|**gc**|
|**cd**|**cd**|**Set\-Location**|**sl**|
|**md**|**mkdir**|**New\-Item**|**ni**|
|N\/A|**pushd**|**Push\-Location**|N\/A|
|N\/A|**popd**|**Pop\-Location**|N\/A|




<!--HONumber=Jun16_HO4-->


