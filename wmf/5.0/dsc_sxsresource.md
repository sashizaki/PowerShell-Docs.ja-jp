---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: a565f2befddc32f5088fa3e158f58d2dd78d41b4
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="side-by-side-module-versioning-support-for-dsc-resources"></a>DSC リソースのサイド バイ サイドのモジュール バージョン管理サポート

DSC リソースに含まれるモジュールは、サイド バイ サイドでインストールして、システムにインストールされるリソースの特定のバージョンを DSC 構成が使うようにできます。

詳細については、「[複数のバージョンがあるリソースの使用](https://msdn.microsoft.com/powershell/dsc/sxsresource)」を参照してください。

## <a name="known-issues"></a>既知の問題

このリリースでは、サイド バイ サイドのインストールについて次に挙げる既知の問題があります。

-   同じ構成内で DSC リソースの 2 つの異なるバージョンを使うことはサポートされていません。