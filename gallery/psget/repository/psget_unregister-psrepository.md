---
ms.date: 06/12/2017
contributor: manikb
ms.topic: reference
keywords: ギャラリー, PowerShell, コマンドレット, PSGet
title: Unregister-PSRepository
ms.openlocfilehash: 7847e223ae7edd9ec2417d104e5e8130f92a59cf
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="unregister-psrepository"></a>Unregister-PSRepository

リポジトリの登録を解除します。

## <a name="description"></a>説明

Unregister-PSRepository コマンドレットは現在のユーザーのリポジトリの登録を解除します。
- PSGallery リポジトリの登録解除と再登録は、エンタープライズ シナリオと切断されたシナリオで許可されています。
- ユーザーは、`Register-PSRepository -Default` を実行するだけで PSGallery を再登録できます
- PSGallery は、Publish-Module と Publish-Script コマンドレット内の既定の発行リポジトリであるため、PSGallery が登録されているリポジトリの一覧で使用できない場合はエラーがスローされます。

## <a name="cmdlet-syntax"></a>コマンドレット構文

```powershell
Get-Command -Name Unregister-PSRepository -Module PowerShellGet -Syntax
```
## <a name="cmdlet-online-help-reference"></a>コマンドレット オンライン ヘルプ リファレンス

[Unregister-PSRepository](http://go.microsoft.com/fwlink/?LinkID=517130)

## <a name="example-commands"></a>コマンド例

```powershell
Unregister-PSRepository -Name "MyPrivateGallery"

Get-PSRepository exp | Unregister-PSRepository
```

### <a name="unregistration-and-re-registration-of-the-psgallery-repository-is-allowed-for-an-enterprise-and-disconnected-scenarios"></a>PSGallery リポジトリの登録解除と再登録は、エンタープライズ シナリオと切断されたシナリオで許可されています。
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