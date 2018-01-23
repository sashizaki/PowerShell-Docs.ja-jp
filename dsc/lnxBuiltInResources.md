---
ms.date: 2017-06-12
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 Desired State Configuration の組み込みリソース"
ms.openlocfilehash: e268cb2ee8a246f18216b34e5e2a6d512f15e18c
ms.sourcegitcommit: a444406120e5af4e746cbbc0558fe89a7e78aef6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="built-in-desired-state-configuration-resources-for-linux"></a>Linux 用 Desired State Configuration の組み込みリソース

リソースは、PowerShell Desired State Configuration (DSC) スクリプトの作成に使用できる構成要素です。 Linux 用 DSC には、ファイルとフォルダー、パッケージ、環境変数、サービスとプロセスなど、リソースを構成するための一連の組み込み機能が付属します。

## <a name="built-in-resources"></a>組み込みリソース 

次の表は、これらのリソースや詳細を説明するトピックへのリンクの一覧を示します。

* [nxArchive リソース](lnxArchiveResource.md) -- 特定のパスでアーカイブ (.tar、.zip) ファイルをアンパックするメカニズムを備えています。
* [nxEnvironment リソース](lnxEnvironmentResource.md) -- ターゲット ノード上の環境変数を管理します。 
* [nxFile リソース](lnxFileResource.md) -- Linux ファイルとディレクトリを管理します。 
* [nxFileLine リソース](lnxFileLineResource.md) -- Linux ファイルの個別の行を管理します。 
* [nxGroup リソース](lnxGroupResource.md) -- ローカル Linux グループを管理します。 
* [nxPackage リソース](lnxPackageResource.md) -- Linux ノード上のパッケージを管理します。
* [nxScript リソース](lnxScriptResource.md) -- ターゲット ノードでスクリプトを実行します。
* [nxService リソース](lnxServiceResource.md) -- Linux サービス (デーモン) を管理します。
* [nxSshAuthorizedKeys リソース](lnxSshAuthorizedKeysResource.md) -- Linux ユーザーの公開 ssh キーを管理します。 
* [nxUser リソース](lnxUserResource.md) -- ローカル Linux ユーザーを管理します。 
  
