---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: Linux 用 Desired State Configuration の組み込みリソース
ms.openlocfilehash: ea700d24c7ff4377af671944184abb3f201852e8
ms.sourcegitcommit: e04292a9c10de9a8391d529b7f7aa3753b362dbe
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 01/04/2019
ms.locfileid: "54047705"
---
# <a name="built-in-desired-state-configuration-resources-for-linux"></a><span data-ttu-id="64f4f-103">Linux 用 Desired State Configuration の組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="64f4f-103">Built-In Desired State Configuration Resources for Linux</span></span>

<span data-ttu-id="64f4f-104">リソースは、PowerShell Desired State Configuration (DSC) スクリプトの作成に使用できる構成要素です。</span><span class="sxs-lookup"><span data-stu-id="64f4f-104">Resources are building blocks that you can use to write a PowerShell Desired State Configuration (DSC) script.</span></span> <span data-ttu-id="64f4f-105">Linux 用 DSC には、ファイルとフォルダー、パッケージ、環境変数、サービスとプロセスなど、リソースを構成するための一連の組み込み機能が付属します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-105">DSC for Linux comes with a set of built-in functionality for configuring resources such as files and folders, packages, environment variables, and services and processes.</span></span>

## <a name="built-in-resources"></a><span data-ttu-id="64f4f-106">組み込みリソース</span><span class="sxs-lookup"><span data-stu-id="64f4f-106">Built-in resources</span></span>

<span data-ttu-id="64f4f-107">次の表は、これらのリソースや詳細を説明するトピックへのリンクの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-107">The following table provides a list of these resources and links to topics that describe them in detail.</span></span>

* <span data-ttu-id="64f4f-108">[nxArchive リソース](lnxArchiveResource.md) -- 特定のパスでアーカイブ (.tar、.zip) ファイルをアンパックするメカニズムを備えています。</span><span class="sxs-lookup"><span data-stu-id="64f4f-108">[nxArchive Resource](lnxArchiveResource.md)--Provides a mechanism to unpack archive (.tar, .zip) files at a specific path.</span></span>
* <span data-ttu-id="64f4f-109">[nxEnvironment リソース](lnxEnvironmentResource.md) -- ターゲット ノード上の環境変数を管理します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-109">[nxEnvironment Resource](lnxEnvironmentResource.md)--Manages environment variables on target nodes.</span></span>
* <span data-ttu-id="64f4f-110">[nxFile リソース](lnxFileResource.md) -- Linux ファイルとディレクトリを管理します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-110">[nxFile Resource](lnxFileResource.md)--Manages Linux files and directories.</span></span>
* <span data-ttu-id="64f4f-111">[nxFileLine リソース](lnxFileLineResource.md) -- Linux ファイルの個別の行を管理します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-111">[nxFileLine Resource](lnxFileLineResource.md)--Manages individual lines in a Linux file.</span></span>
* <span data-ttu-id="64f4f-112">[nxGroup リソース](lnxGroupResource.md) -- ローカル Linux グループを管理します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-112">[nxGroup Resource](lnxGroupResource.md)--Manages local Linux groups.</span></span>
* <span data-ttu-id="64f4f-113">[nxPackage リソース](lnxPackageResource.md) -- Linux ノード上のパッケージを管理します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-113">[nxPackage Resource](lnxPackageResource.md)--Manages packages on Linux nodes.</span></span>
* <span data-ttu-id="64f4f-114">[nxScript リソース](lnxScriptResource.md) -- ターゲット ノードでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-114">[nxScript Resource](lnxScriptResource.md)--Runs scripts on target nodes.</span></span>
* <span data-ttu-id="64f4f-115">[nxService リソース](lnxServiceResource.md) -- Linux サービス (デーモン) を管理します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-115">[nxService Resource](lnxServiceResource.md)--Manages Linux services (daemons).</span></span>
* <span data-ttu-id="64f4f-116">[nxSshAuthorizedKeys リソース](lnxSshAuthorizedKeysResource.md) -- Linux ユーザーの公開 ssh キーを管理します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-116">[nxSshAuthorizedKeys Resource](lnxSshAuthorizedKeysResource.md)--Manages public ssh keys for a Linux user.</span></span>
* <span data-ttu-id="64f4f-117">[nxUser リソース](lnxUserResource.md) -- ローカル Linux ユーザーを管理します。</span><span class="sxs-lookup"><span data-stu-id="64f4f-117">[nxUser Resource](lnxUserResource.md)--Manages local Linux users.</span></span>