---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: Get-PSRepository
ms.openlocfilehash: 97279a8ed0087c835fb924991484959cd7237016
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="get-psrepository"></a>Get-PSRepository

コンピューター上の登録されているリポジトリを取得します。

## <a name="description"></a>説明

Get-PSRepository コマンドレットでは、コンピューター上の現在のユーザーに対して登録されている PowerShell モジュール リポジトリを取得します。

登録されている各リポジトリに対して、Get-PSRepository は PSRepository オブジェクトを返します。これは必要に応じて登録済みのリポジトリの登録を解除するための Unregister-PSRepository にパイプできます。

## <a name="cmdlet-syntax"></a>コマンドレット構文
```powershell
Get-Command -Name Get-PSRepository -Module PowerShellGet -Syntax
```

## <a name="cmdlet-online-help-reference"></a>コマンドレット オンライン ヘルプ リファレンス

[Get-PSRepository](http://go.microsoft.com/fwlink/?LinkID=517127)

## <a name="example-commands"></a>コマンド例

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