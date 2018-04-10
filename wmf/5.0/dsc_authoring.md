---
ms.date: 06/12/2017
author: JKeithB
ms.topic: reference
keywords: WMF, PowerShell, セットアップ
ms.openlocfilehash: 3b2c268cd10d7c421b3d1fc73a7bbeaa4714f5fc
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="authoring-improvements-using-powershell-ise"></a>PowerShell ISE を使ったオーサリングの強化

Windows PowerShell ISE での DSC 構成のオーサリングが、はるかに簡単になりました。強化された点は次のとおりです。

- **構成**ブロック内や**ノード** ブロック内の空白行に **Ctrl+Space** を入力して、DSC リソースをすべて一覧表示する。
- **列挙**型のリソース プロパティにおけるオート コンプリート。
- 構成内の他のリソース インスタンスに応じた、DSC リソースの **DependsOn** プロパティにおけるオート コンプリート。
- リソース プロパティ値のタブ補完の強化。

**注:** Ctrl+Space を使ってオプションを一覧表示するには、リソース プロパティ値に空の文字列が必要です。 **タブ**を押して、オプションを順番に切り替えます。