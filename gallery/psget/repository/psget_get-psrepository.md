---
description: 
manager: carolz
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,コマンドレット,ギャラリー"
ms.date: 2016-10-14
contributor: manikb
title: psget_get psrepository
ms.technology: powershell
translationtype: Human Translation
ms.sourcegitcommit: e6c526d1074f61154d03b92b6bf6f599976f5936
ms.openlocfilehash: 3d0b67d012528a1ef59d8f5a1b16903d931426a3

---

# Get-PSRepository

コンピューター上の登録されているリポジトリを取得します。

## 説明

Get-PSRepository コマンドレットでは、コンピューター上の現在のユーザーに対して登録されている PowerShell モジュール リポジトリを取得します。

登録されている各リポジトリに対して、Get-PSRepository は PSRepository オブジェクトを返します。これは必要に応じて登録済みのリポジトリの登録を解除するための Unregister-PSRepository にパイプできます。

## コマンドレット構文
```powershell
Get-Command -Name Get-PSRepository -Module PowerShellGet -Syntax
```

## コマンドレット オンライン ヘルプ リファレンス

[Get-PSRepository](http://go.microsoft.com/fwlink/?LinkID=517127)

## コマンド例

```powershell

# Properties of Get-PSRepository returned object
Get-PSRepository PSGallery | Format-List * -Force

Name                      : PSGallery
SourceLocation            : https://www.powershellgallery.com/api/v2/
Trusted                   : False
Registered                : True
InstallationPolicy        : Untrusted
PackageManagementProvider : NuGet
PublishLocation           : https://www.powershellgallery.com/api/v2/package/
ScriptSourceLocation      : https://www.powershellgallery.com/api/v2/items/psscript/
ScriptPublishLocation     : https://www.powershellgallery.com/api/v2/package/
ProviderOptions           : {}

# Get all registered repositories
Get-PSRepository

# Get a specific registered repository
Get-PSRepository PSGallery

Name                      InstallationPolicy   SourceLocation
----                      ------------------   --------------
PSGallery                 Untrusted            https://www.powershellgallery.com/api/v2/

# Get registered repository with wildcards
Get-PSRepository *Gallery*

```




<!--HONumber=Oct16_HO2-->


