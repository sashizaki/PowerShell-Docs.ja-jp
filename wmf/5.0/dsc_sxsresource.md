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
<a id="side-by-side-module-versioning-support-for-dsc-resources" class="xliff"></a>

# DSC リソースのサイド バイ サイドのモジュール バージョン管理サポート

DSC リソースに含まれるモジュールは、サイド バイ サイドでインストールして、システムにインストールされるリソースの特定のバージョンを DSC 構成が使うようにできます。

詳細については、「[複数のバージョンがあるリソースの使用](https://msdn.microsoft.com/powershell/dsc/sxsresource)」を参照してください。

<a id="known-issues" class="xliff"></a>

## 既知の問題

このリリースでは、サイド バイ サイドのインストールについて次に挙げる既知の問題があります。

-   同じ構成内で DSC リソースの 2 つの異なるバージョンを使うことはサポートされていません。

