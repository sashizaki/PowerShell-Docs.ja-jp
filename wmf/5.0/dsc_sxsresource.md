---
ms.date: 2017-06-12
author: JKeithB
ms.topic: reference
keywords: "WMF, PowerShell, セットアップ"
ms.openlocfilehash: 3261e5a07b8181190a04de3f210da50f23bb2953
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
# <a name="side-by-side-module-versioning-support-for-dsc-resources"></a><span data-ttu-id="d0919-102">DSC リソースのサイド バイ サイドのモジュール バージョン管理サポート</span><span class="sxs-lookup"><span data-stu-id="d0919-102">Side-By-Side Module Versioning Support for DSC Resources</span></span>

<span data-ttu-id="d0919-103">DSC リソースに含まれるモジュールは、サイド バイ サイドでインストールして、システムにインストールされるリソースの特定のバージョンを DSC 構成が使うようにできます。</span><span class="sxs-lookup"><span data-stu-id="d0919-103">Modules containing DSC resources can be installed side-by-side, and DSC configurations can use a specific version of the resource that is installed on the system.</span></span>

<span data-ttu-id="d0919-104">詳細については、「[複数のバージョンがあるリソースの使用](https://msdn.microsoft.com/powershell/dsc/sxsresource)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0919-104">For more information, see [Using resources with multiple versions](https://msdn.microsoft.com/powershell/dsc/sxsresource).</span></span>

## <a name="known-issues"></a><span data-ttu-id="d0919-105">既知の問題</span><span class="sxs-lookup"><span data-stu-id="d0919-105">Known issues</span></span>

<span data-ttu-id="d0919-106">このリリースでは、サイド バイ サイドのインストールについて次に挙げる既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="d0919-106">In this release, the following are known issues of side-by-side installation:</span></span>

-   <span data-ttu-id="d0919-107">同じ構成内で DSC リソースの 2 つの異なるバージョンを使うことはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d0919-107">Using two different versions of the DSC resource within the same configuration is not supported.</span></span>

