---
title: モジュールとスナップイン |Microsoft Docs
ms.date: 09/13/2016
ms.openlocfilehash: 07cdc55fd6d1462130f1a81deb30056623a525e6
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787310"
---
# <a name="modules-and-snap-ins"></a>モジュールとスナップイン

コマンドレットは、(Windows PowerShell 2.0 によって導入された) モジュールまたはスナップインを使用してセッションに追加できます。コマンドレットをセッションに追加すると、ホストアプリケーションまたはコマンドラインで対話形式で実行できます。

次の理由により、セッションにコマンドレットを追加するための配信方法としてモジュールを使用することをお勧めします。

- モジュールを使用すると、コマンドレットが定義されているアセンブリを読み込むことによってコマンドレットを追加できます。 スナップインクラスを実装する必要はありません。

- モジュールを使用すると、変数、関数、スクリプト、型、書式設定ファイルなどの他のリソースを追加できます。

- スナップインは、セッションにコマンドレットとプロバイダーを追加するためにのみ使用できます。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールを記述する](writing-a-windows-powershell-module.md)

[Writing a Windows PowerShell Cmdlet (Windows PowerShell コマンドレットの記述)](../cmdlet/cmdlet-overview.md)
