---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: アイテムを削除する
ms.openlocfilehash: 454cd404437bf1c31b9a1b81cd9dd0ac81e6b0f6
ms.sourcegitcommit: 8b076ebde7ef971d7465bab834a3c2a32471ef6f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37893095"
---
# <a name="deleting-items"></a>アイテムを削除する

PowerShell ギャラリーでは、アイテムを完全に削除することはできません。アイテムの依存関係がなくなるためです。

代わりに、PowerShell ギャラリーでは、Web サイトのアイテム管理ページでアイテムを "リストから外す" ことができます。
アイテムがリストから外されると、PowerShell ギャラリーでも、PowerShellGet コマンドを使用しても、検索やアイテム リストにそのアイテムが表示されなくなります。
ただし、正しいバージョンを指定すればダウンロードできます。正しいバージョンを指定することで、自動スクリプトが引き続き動作します。

アイテムを削除しなければならない、例外的な状況になった場合、PowerShell ギャラリー チームが手動で削除します。
たとえば、著作権の侵害や有害なコンテンツがあれば、それはアイテムを削除する正当な理由となります。
その場合、[PowerShell ギャラリー](http://www.PowerShellGallery.com)からサポート要求を提出してください。