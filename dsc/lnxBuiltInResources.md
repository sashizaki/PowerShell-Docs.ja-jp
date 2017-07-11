---
ms.date: 2017-06-12
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Linux 用 Desired State Configuration の組み込みリソース"
ms.openlocfilehash: b85f32f7559d89bda566d35462cc613d73424c50
ms.sourcegitcommit: 75f70c7df01eea5e7a2c16f9a3ab1dd437a1f8fd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2017
---
<a id="built-in-desired-state-configuration-resources-for-linux" class="xliff"></a>

# Linux 用 Desired State Configuration の組み込みリソース

リソースは、PowerShell Desired State Configuration (DSC) スクリプトの作成に使用できる構成要素です。 Linux 用 DSC には、ファイルとフォルダー、パッケージ、環境変数、サービスとプロセスなど、リソースを構成するための一連の組み込み機能が付属します。

<a id="built-in-resources" class="xliff"></a>

## 組み込みリソース 

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
  
