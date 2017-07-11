---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: Find-RoleCapability
ms.openlocfilehash: 77c5b492d9681fa05315401fba410c508af1d13b
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="find-rolecapability" class="xliff"></a>

# Find-RoleCapability

モジュール内のロール機能を検索します。

<a id="description" class="xliff"></a>

## 説明
Find-RoleCapability コマンドレットは、モジュール内の PowerShell ロール機能を検索します。 Find-RoleCapability は、登録されているリポジトリ内のモジュールを検索します。 このコマンドレットが検索するロール機能ごとに、PSGetRoleCapabilityInfo オブジェクトを返します。 PSGetRoleCapabilityInfo オブジェクトを Install-Module コマンドレットに渡して、ロール機能を含むモジュールをインストールできます。
PowerShell ロール機能は、Just Enough Administration (JEA) エンドポイントでユーザーが利用できるコマンド、アプリケーションなどを定義します。 ロール機能は、拡張子が .psrc のファイルによって定義されます。

- Find-RoleCapability は、次のバージョン パラメーターでフィルター処理できます。MinimumVersion、RequiredVersion、AllVersions。
  - これらのパラメーターは同時に指定できません。
  - これらのバージョン パラメーターは、ワイルドカードを含まない 1 つのモジュール名が指定されている場合にのみ許可されます。
  - RequiredVersion パラメーターが指定されていない場合、Find-RoleCapability は指定された最小バージョン以上の最新バージョンのモジュールを返すか、または最新バージョンのモジュールを返します (最小バージョンが指定されていない場合)。
  - RequiredVersion パラメーターが指定されている場合、Find-RoleCapability は指定したバージョンに完全に一致するバージョンのモジュールのみを返します。
- Find-RoleCapability では、-Tag パラメーターを使用してモジュールのメタデータをフィルター処理できます
- Find-RoleCapability では、-Filter パラメーターを使用してリポジトリ固有の検索言語をフィルター処理できます。
- Find-RoleCapability では、登録されているリポジトリのすべてまたは一部からモジュール上でフィルター処理できます。

<a id="cmdlet-syntax" class="xliff"></a>

## コマンドレット構文
```powershell
Get-Command -Name Find-RoleCapability -Module PowerShellGet -Syntax
```

<a id="cmdlet-online-help-reference" class="xliff"></a>

## コマンドレット オンライン ヘルプ リファレンス

[Find-RoleCapability](http://go.microsoft.com/fwlink/?LinkId=718029)

<a id="example-commands" class="xliff"></a>

## コマンド例
```powershell

# Find a specific role capability
Find-RoleCapability -Name Maintenance

Name                                Version    ModuleName                          Repository
----                                -------    ----------                          ----------
Maintenance                         1.5.0      RoleCapModule                       PrivatePSGallery

# Find multiple role capabilities
Find-RoleCapability -Name MyJeaRole, Maintenance

# Find all available role capabilities from all registered repositories
Find-RoleCapability

# Find available role capabilities from few registered repositories
Find-RoleCapability -Repository PSGallery,PrivatePSGallery

# Find all role capabilities in a specified repository
Find-RoleCapability -Repository PSGallery

# Find a role capability defined in a specific module
Find-RoleCapability -Name Maintenance -ModuleName RoleCapModule

# Find role capabilities from all versions of a module
Find-RoleCapability -ModuleName RoleCapModule -AllVersions

# Find role capabilities with module name and MinimumVersion.
Find-RoleCapability -ModuleName RoleCapModule -MinimumVersion 1.1

# Find role capabilities with module name and exact version
Find-RoleCapability -ModuleName RoleCapModule -RequiredVersion 1.4.0

# Find role capabilities defined modules with -Filter based search. -Filter searches in description and module names
Find-RoleCapability -Filter Cookbook
Find-RoleCapability -Filter RBAC

# Find all role capabilities with tags Azure or DSC in module metadata
Find-RoleCapability -Tag Azure, DSC

```

