---
title: モジュールを使用してコマンドレットをインポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: c007bb11324e10ffd100797dccd9e6ab0d09a73e
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62067979"
---
# <a name="how-to-import-cmdlets-using-modules"></a>モジュールを使用してコマンドレットをインポートする方法

このトピックでは、バイナリ モジュールを使用して Windows PowerShell セッションにコマンドレットをインポートする方法について説明します。

> [!NOTE]
> モジュールのメンバーには、コマンドレット、プロバイダー、関数、変数、エイリアス、およびその他を含めることができます。 スナップインには、コマンドレットとプロバイダーのみを含めることができます。

## <a name="how-to-load-cmdlets-using-a-module"></a>モジュールを使用してコマンドレットを読み込む方法

1. コマンドレットが実装されているアセンブリ ファイルと同じ名前を持つモジュール フォルダーを作成します。 この手順でモジュール フォルダーを作成、`system32`フォルダー。

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

2. 必ず、`PSModulePath`環境変数には、新しいモジュール フォルダーへのパスが含まれています。 既定では、システム フォルダーは既にに追加、`PSModulePath`環境変数。

3. モジュール フォルダーには、コマンドレットのアセンブリをコピーします。

4. コマンドレットをセッションに追加するには、次のコマンドを実行します。

   `import-module [Module_Name]`

   この手順は、テスト、コマンドレットを使用できます。 セッションにアセンブリ内のすべてのコマンドレットを追加します。 モジュールの詳細については、モジュール、モジュール、およびエクスポートされるモジュールの要素を制限する方法を読み込むためのさまざまな方法のさまざまな種類を参照してください[Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)します。

## <a name="see-also"></a>参照

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)

[モジュールのインストール](../module/installing-a-powershell-module.md)