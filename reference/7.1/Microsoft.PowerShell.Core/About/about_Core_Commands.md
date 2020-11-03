---
description: PowerShell プロバイダーで使用できるように設計されたコマンドレットの一覧を示します。
keywords: powershell,コマンドレット
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_core_commands?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Core_Commands
ms.openlocfilehash: 90723e286c3cc85a9ae9196721f3c0c6909d62ab
ms.sourcegitcommit: f874dc1d4236e06a3df195d179f59e0a7d9f8436
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "93222123"
---
# <a name="about-core-commands"></a>コアコマンドについて

## <a name="short-description"></a>概要
PowerShell プロバイダーで使用できるように設計されたコマンドレットの一覧を示します。

## <a name="long-description"></a>詳細説明

PowerShell には、PowerShell プロバイダーによって公開されるデータストア内の項目を管理するために特に設計された一連のコマンドレットが含まれています。
これらのコマンドレットを同じ方法で使用して、プロバイダーが使用できるようにするさまざまな種類のデータを管理できます。 プロバイダーの詳細については、「get-help about_providers」と入力してください。

たとえば、Get-ChildItem コマンドレットを使用して、ファイルシステムディレクトリ内のファイル、レジストリキーの下にあるキー、または書き込んだりダウンロードしたプロバイダーによって公開されている項目を一覧表示できます。

プロバイダーで使用するように設計されている PowerShell コマンドレットの一覧を次に示します。

Get-childitem コマンドレット

- Get-ChildItem

コンテンツのコマンドレット

- Add-Content
- Clear-Content
- Get-Content
- Set-Content

項目のコマンドレット

- Clear-Item
- Copy-Item
- Get-Item
- Invoke-Item
- Move-Item
- New-Item
- Remove-Item
- Rename-Item
- Set-Item

Get-itemproperty コマンドレット

- Clear-ItemProperty
- Copy-ItemProperty
- Get-ItemProperty
- Move-ItemProperty
- New-ItemProperty
- Remove-ItemProperty
- Rename-ItemProperty
- Set-ItemProperty

Location コマンドレット

- Get-Location
- Pop-Location
- Push-Location
- Set-Location

Path コマンドレット

- Join-Path
- Convert-Path
- Split-Path
- Resolve-Path
- Test-Path

PSDrive コマンドレット

- Get-PSDrive
- New-PSDrive
- Remove-PSDrive

PSProvider コマンドレット

- Get-PSProvider

コマンドレットの詳細については、「」と入力 `get-help <cmdlet-name>` してください。

## <a name="see-also"></a>関連項目

[about_Providers](about_Providers.md)

