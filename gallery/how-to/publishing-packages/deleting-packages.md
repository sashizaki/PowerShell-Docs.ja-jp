---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: パッケージを削除する
ms.openlocfilehash: ca5e68fcad52e4c7561d2c2b3858228652f22e0b
ms.sourcegitcommit: 98b7cfd8ad5718efa8e320526ca76c3cc4141d78
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003862"
---
# <a name="deleting-packages"></a>パッケージを削除する

PowerShell ギャラリーでは、パッケージを完全に削除することはできません。パッケージの依存関係がなくなるためです。

代わりに、PowerShell ギャラリーでは、Web サイトのパッケージ管理ページでパッケージを "リストから外す" ことができます。
パッケージがリストから外されると、PowerShell ギャラリーでも、PowerShellGet コマンドを使用しても、検索やパッケージ リストにそのパッケージが表示されなくなります。
ただし、正しいバージョンを指定すればダウンロードできます。正しいバージョンを指定することで、自動スクリプトが引き続き動作します。

パッケージを削除しなければならない、例外的な状況になった場合、PowerShell ギャラリー チームが手動で削除します。
たとえば、著作権の侵害や有害なコンテンツがあれば、それはアイテムを削除する正当な理由となります。
その場合、[PowerShell ギャラリー](http://www.PowerShellGallery.com)からサポート要求を提出してください。
