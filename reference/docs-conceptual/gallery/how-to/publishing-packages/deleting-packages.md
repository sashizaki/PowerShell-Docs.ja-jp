---
ms.date: 06/12/2017
contributor: JKeithB
keywords: ギャラリー, PowerShell, コマンドレット, PSGallery
title: パッケージを削除する
ms.openlocfilehash: 6bfb43b95e51d38bd606198cb8d2d9af0aa0be1e
ms.sourcegitcommit: 4a2cf30351620a58ba95ff5d76b247e601907589
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "71327933"
---
# <a name="deleting-packages"></a>パッケージを削除する

PowerShell ギャラリーでは、パッケージを完全に削除することはできません。パッケージの依存関係がなくなるためです。

代わりに、PowerShell ギャラリーでは、Web サイトのパッケージ管理ページでパッケージを "リストから外す" ことができます。
パッケージがリストから外されると、PowerShell ギャラリーでも、PowerShellGet コマンドを使用しても、検索やパッケージ リストにそのパッケージが表示されなくなります。
ただし、正しいバージョンを指定すればダウンロードできます。正しいバージョンを指定することで、自動スクリプトが引き続き動作します。

パッケージを削除しなければならない、例外的な状況になった場合、PowerShell ギャラリー チームが手動で削除します。
たとえば、著作権の侵害や有害なコンテンツがあれば、それはアイテムを削除する正当な理由となります。
その場合、[PowerShell ギャラリー](https://www.PowerShellGallery.com)からサポート要求を提出してください。
