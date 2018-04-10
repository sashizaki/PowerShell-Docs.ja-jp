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
# <a name="unregister-psrepository"></a><span data-ttu-id="3d630-103">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="3d630-103">Unregister-PSRepository</span></span>

<span data-ttu-id="3d630-104">リポジトリの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="3d630-104">Unregisters a repository.</span></span>

## <a name="description"></a><span data-ttu-id="3d630-105">説明</span><span class="sxs-lookup"><span data-stu-id="3d630-105">Description</span></span>

<span data-ttu-id="3d630-106">Unregister-PSRepository コマンドレットは現在のユーザーのリポジトリの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="3d630-106">The Unregister-PSRepository cmdlet unregisters a repository for the current user.</span></span>
- <span data-ttu-id="3d630-107">PSGallery リポジトリの登録解除と再登録は、エンタープライズ シナリオと切断されたシナリオで許可されています。</span><span class="sxs-lookup"><span data-stu-id="3d630-107">Unregistration and re-registration of the PSGallery repository is allowed for an enterprise and disconnected scenarios.</span></span>
- <span data-ttu-id="3d630-108">ユーザーは、`Register-PSRepository -Default` を実行するだけで PSGallery を再登録できます</span><span class="sxs-lookup"><span data-stu-id="3d630-108">Users can re-register the PSGallery by simply running `Register-PSRepository -Default`</span></span>
- <span data-ttu-id="3d630-109">PSGallery は、Publish-Module と Publish-Script コマンドレット内の既定の発行リポジトリであるため、PSGallery が登録されているリポジトリの一覧で使用できない場合はエラーがスローされます。</span><span class="sxs-lookup"><span data-stu-id="3d630-109">Since PSGallery is the default publish repository in Publish-Module and Publish-Script cmdlets, an error will be thrown if PSGallery is not available in the registered repository list.</span></span>

## <a name="cmdlet-syntax"></a><span data-ttu-id="3d630-110">コマンドレット構文</span><span class="sxs-lookup"><span data-stu-id="3d630-110">Cmdlet syntax</span></span>

```powershell
Get-Command -Name Unregister-PSRepository -Module PowerShellGet -Syntax
```
## <a name="cmdlet-online-help-reference"></a><span data-ttu-id="3d630-111">コマンドレット オンライン ヘルプ リファレンス</span><span class="sxs-lookup"><span data-stu-id="3d630-111">Cmdlet online help reference</span></span>

[<span data-ttu-id="3d630-112">Unregister-PSRepository</span><span class="sxs-lookup"><span data-stu-id="3d630-112">Unregister-PSRepository</span></span>](http://go.microsoft.com/fwlink/?LinkID=517130)

## <a name="example-commands"></a><span data-ttu-id="3d630-113">コマンド例</span><span class="sxs-lookup"><span data-stu-id="3d630-113">Example commands</span></span>

```powershell
Unregister-PSRepository -Name "MyPrivateGallery"

Get-PSRepository exp | Unregister-PSRepository
```

### <a name="unregistration-and-re-registration-of-the-psgallery-repository-is-allowed-for-an-enterprise-and-disconnected-scenarios"></a><span data-ttu-id="3d630-114">PSGallery リポジトリの登録解除と再登録は、エンタープライズ シナリオと切断されたシナリオで許可されています。</span><span class="sxs-lookup"><span data-stu-id="3d630-114">Unregistration and re-registration of the PSGallery repository is allowed for an enterprise and disconnected scenarios.</span></span>
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