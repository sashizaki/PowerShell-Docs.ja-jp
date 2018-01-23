---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "DSC リソース"
ms.openlocfilehash: 0994616673b5e447c69c09154bfdb9b9126a88c8
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="dsc-resources"></a><span data-ttu-id="a97a8-103">DSC リソース</span><span class="sxs-lookup"><span data-stu-id="a97a8-103">DSC Resources</span></span>

><span data-ttu-id="a97a8-104">適用先: Windows PowerShell 4.0、Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="a97a8-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.0</span></span>

<span data-ttu-id="a97a8-105">Desired State Configuration (DSC) リソースは、DSC 構成の構成要素を提供します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-105">Desired State Configuration (DSC) Resources provide the building blocks for a DSC configuration.</span></span> <span data-ttu-id="a97a8-106">リソースは、構成 (スキーマ) 可能なプロパティを公開し、また、指定されたことを実現するためにローカル構成マネージャー (LCM) が呼び出す PowerShell スクリプト関数が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a97a8-106">A resource exposes properties that can be configured (schema) and contains the PowerShell script functions that the Local Configuration Manager (LCM) calls to "make it so".</span></span>

<span data-ttu-id="a97a8-107">リソースでは、ファイルのように汎用的なものをモデル化したり、IIS サーバー設定のように具体的なものをモデル化したりできます。</span><span class="sxs-lookup"><span data-stu-id="a97a8-107">A resource can model something as generic as a file or as specific as an IIS server setting.</span></span>  <span data-ttu-id="a97a8-108">リソースなどのグループは、DSC モジュールに結合されます。DSC モジュールでは、リソースの使用目的を識別するためのメタデータが含まれている移植可能な構造にすべての必須ファイルが編成されます。</span><span class="sxs-lookup"><span data-stu-id="a97a8-108">Groups of like resources are combined in to a DSC Module, which organizes all the required files in to a structure that is portable and includes metadata to identify how the resources are intended to be used.</span></span>  

<span data-ttu-id="a97a8-109">次のトピックでは、DSC リソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a97a8-109">The following topics describe DSC resources:</span></span>

- [<span data-ttu-id="a97a8-110">組み込み DSC リソース</span><span class="sxs-lookup"><span data-stu-id="a97a8-110">Built-In DSC resources</span></span>](builtInResource.md)
- [<span data-ttu-id="a97a8-111">カスタム DSC リソースのビルド</span><span class="sxs-lookup"><span data-stu-id="a97a8-111">Build custom DSC resources</span></span>](authoringResource.md)
- [<span data-ttu-id="a97a8-112">Linux 用組み込み DSC リソース</span><span class="sxs-lookup"><span data-stu-id="a97a8-112">Built-In DSC resources for Linux</span></span>](lnxBuiltInResources.md)

