---
title: モジュールとスナップイン |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d342f91-23e0-467f-8de2-f9657d820693
caps.latest.revision: 6
ms.openlocfilehash: 157cd64e286392f3fd770e1e34542682b1e63625
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067622"
---
# <a name="modules-and-snap-ins"></a>モジュールとスナップイン

コマンドレットは、(Windows PowerShell 2.0 で導入) のモジュールまたはスナップインを使用してセッションに追加できます。コマンドレットは、ホスト アプリケーションによって、またはコマンドラインで対話的にプログラムで実行することができます、セッションに追加されます。

コマンドレットを次の理由でセッションに追加する配信方法としては、モジュールを使用することをお勧めします。

- モジュールを使用すると、コマンドレットを追加するには、アセンブリの読み込み、コマンドレットが定義されています。 スナップイン クラスを実装する必要はありません。

- モジュールを使用して、変数、関数、スクリプト、型と書式設定ファイル、および詳細などの他のリソースを追加できます。

- スナップインは、コマンドレットとプロバイダーをセッションに追加する場合にのみ使用できます。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
