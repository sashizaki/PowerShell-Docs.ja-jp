---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: b839b476bb4ef7f8d73b158d61f0e8cbc1265e60
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="import-dscresource-keyword-supports--moduleversion-parameter"></a><span data-ttu-id="177a5-102">-ModuleVersion パラメーターをサポートする Import-DscResource キーワード</span><span class="sxs-lookup"><span data-stu-id="177a5-102">Import-DscResource keyword supports -ModuleVersion parameter</span></span>

<span data-ttu-id="177a5-103">DSC 構成を作成するときに使用できる、`Import-DscResource` dynamic キーワードに新しいパラメーターを追加しました。</span><span class="sxs-lookup"><span data-stu-id="177a5-103">We have added a new parameter to the `Import-DscResource` dynamic keyword available when authoring DSC configurations.</span></span> <span data-ttu-id="177a5-104">構成の作成者は、どのモジュール バージョンから DSC リソースを読み込むかを正確に指定できます。</span><span class="sxs-lookup"><span data-stu-id="177a5-104">Configuration authors can now specify exactly which module version to load the DSC resources from.</span></span> <span data-ttu-id="177a5-105">キーワードの新しい構文は次の通りです:</span><span class="sxs-lookup"><span data-stu-id="177a5-105">The new syntax of the keyword is:</span></span>

```powershell
Import-DscResource [-Name <ResourceName(s)>] [-ModuleName <ModuleName(s)>] [-ModuleVersion <ModuleVersion>]
```

* <span data-ttu-id="177a5-106">**Name**: インポートする 1 つまたは複数のリソースの名前。</span><span class="sxs-lookup"><span data-stu-id="177a5-106">**Name**: Names of one or more resources to import.</span></span>
* <span data-ttu-id="177a5-107">**ModuleName**: モジュール名、またはインポートする 1 つまたは複数のモジュールの ModuleSpecification オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="177a5-107">**ModuleName**: Module names or ModuleSpecification objects of one or more modules to import.</span></span>
* <span data-ttu-id="177a5-108">**ModuleVersion**: インポートするモジュールのバージョン。</span><span class="sxs-lookup"><span data-stu-id="177a5-108">**ModuleVersion**: Version of module ot import.</span></span> <span data-ttu-id="177a5-109">ModuleName が使用される場合、1 つの名前で 1 つのモジュールのみを表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="177a5-109">If used, ModuleName must represent only one module by name.</span></span> 

<span data-ttu-id="177a5-110">Windows PowerShell ISE では、IntelliSense と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="177a5-110">In the Windows PowerShell ISE, it shows up with IntelliSense:</span></span>

![](../images/Import-DscResource-Modversion.jpg)

<span data-ttu-id="177a5-111">**注**: `–ModuleVersion` パラメーターは `–ModuleName` パラメーターと組み合わせてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="177a5-111">**Note**: the `–ModuleVersion` parameter can only be used in combination with the `–ModuleName` parameter.</span></span> <span data-ttu-id="177a5-112">`–Name` パラメーターのみを使用したリソース名では、使用できません。</span><span class="sxs-lookup"><span data-stu-id="177a5-112">It cannot be used with resource names using only the `–Name` parameter.</span></span>

<span data-ttu-id="177a5-113">これまでは、DSC リソースを読み込むときに、モジュールのバージョンを指定する唯一の方法は、`–ModuleName @{ModuleName="UserConfigProvider";ModuleVersion="3.0"}` などのモジュール指定オブジェクトを使用する方法のみでした。</span><span class="sxs-lookup"><span data-stu-id="177a5-113">Before this, the only way to specify the module version when loading DSC resources was by using the Module specification object e.g.: `–ModuleName @{ModuleName="UserConfigProvider";ModuleVersion="3.0"}`</span></span>

