---
ms.date: 2017-06-12
contributor: manikb
ms.topic: reference
keywords: "ギャラリー, PowerShell, コマンドレット, PSGet"
title: Unregister-PSRepository
ms.openlocfilehash: 91380210f262208fce39d596bd6c2ad05a819fbf
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="unregister-psrepository" class="xliff"></a>

# Unregister-PSRepository

リポジトリの登録を解除します。

<a id="description" class="xliff"></a>

## 説明

Unregister-PSRepository コマンドレットは現在のユーザーのリポジトリの登録を解除します。
- PSGallery リポジトリの登録解除と再登録は、エンタープライズ シナリオと切断されたシナリオで許可されています。
- ユーザーは、`Register-PSRepository -Default` を実行するだけで PSGallery を再登録できます
- PSGallery は、Publish-Module と Publish-Script コマンドレット内の既定の発行リポジトリであるため、PSGallery が登録されているリポジトリの一覧で使用できない場合はエラーがスローされます。

<a id="cmdlet-syntax" class="xliff"></a>

## コマンドレット構文

```powershell
Get-Command -Name Unregister-PSRepository -Module PowerShellGet -Syntax
```
<a id="cmdlet-online-help-reference" class="xliff"></a>

## コマンドレット オンライン ヘルプ リファレンス

[Unregister-PSRepository](http://go.microsoft.com/fwlink/?LinkID=517130)

<a id="example-commands" class="xliff"></a>

## コマンド例

```powershell
Unregister-PSRepository -Name "MyPrivateGallery"

Get-PSRepository exp | Unregister-PSRepository
```

<a id="unregistration-and-re-registration-of-the-psgallery-repository-is-allowed-for-an-enterprise-and-disconnected-scenarios" class="xliff"></a>

### PSGallery リポジトリの登録解除と再登録は、エンタープライズ シナリオと切断されたシナリオで許可されています。
```powershell

# Unregister PSGallery repository
Unregister-PSRepository PSGallery

# Publish-Module throws an error when PSGallery is not a registered repository
Publish-Module -Name MyModule
publish-module : Unable to find repository 'PSGallery'. Use Get-PSRepository to see all available repositories. Try again after specifying a valid repository name. You can use 'Register-PSRepository -Default' to register the PSGallery repository.
At line:1 char:1
+ publish-module -name mymodule
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidArgument: (PSGallery:String) [Publish-Module], ArgumentException
    + FullyQualifiedErrorId : PSGalleryNotFound,Publish-Module

# Re-register PSGallery repository
Register-PSRepository -Default
```

