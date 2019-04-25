---
ms.date: 06/12/2017
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 5b31fe833fb0f9d0f3f2733e777e4608a697d583
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62057929"
---
# <a name="side-by-side-module-versioning-support-for-dsc-resources"></a>DSC リソースのサイド バイ サイドのモジュール バージョン管理サポート

DSC リソースに含まれるモジュールは、サイド バイ サイドでインストールして、システムにインストールされるリソースの特定のバージョンを DSC 構成が使うようにできます。

詳細については、「[複数のバージョンがあるリソースの使用](https://msdn.microsoft.com/powershell/dsc/sxsresource)」を参照してください。

## <a name="known-issues"></a>既知の問題

このリリースでは、サイド バイ サイドのインストールについて次に挙げる既知の問題があります。

-   同じ構成内で DSC リソースの 2 つの異なるバージョンを使うことはサポートされていません。
