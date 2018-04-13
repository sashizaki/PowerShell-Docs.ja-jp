---
ms.date: 06/12/2017
contributor: JKeithB
ms.topic: conceptual
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: アイテムを削除する
ms.openlocfilehash: f82d80a35f51227c4671bd2b15a7d1c16f0ba0a8
ms.sourcegitcommit: cf195b090b3223fa4917206dfec7f0b603873cdf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/09/2018
---
# <a name="deleting-items"></a>アイテムを削除する

PowerShell ギャラリーでは、アイテムを完全に削除することはできません。アイテムの依存関係がなくなるためです。

代わりに、PowerShell ギャラリーでは、Web サイトのアイテム管理ページでアイテムを "リストから外す" ことができます。
アイテムがリストから外されると、PowerShell ギャラリーでも、PowerShellGet コマンドを使用しても、検索やアイテム リストにそのアイテムが表示されなくなります。
ただし、正しいバージョンを指定すればダウンロードできます。正しいバージョンを指定することで、自動スクリプトが引き続き動作します。

アイテムを削除しなければならない、例外的な状況になった場合、PowerShell ギャラリー チームが手動で削除します。
たとえば、著作権の侵害や有害なコンテンツがあれば、それはアイテムを削除する正当な理由となります。
その場合、[PowerShell ギャラリー] (http://www.PowerShellGallery.com)) からサポート依頼を提出してください。