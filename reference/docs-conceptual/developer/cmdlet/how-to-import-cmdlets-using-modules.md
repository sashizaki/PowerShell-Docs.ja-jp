---
title: モジュールを使用してコマンドレットをインポートする方法 |Microsoft Docs
ms.custom: ''
ms.date: 08/28/2019
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a41d9e5f-de6f-47b7-9601-c108609320d0
caps.latest.revision: 8
ms.openlocfilehash: 2f145795a57c988da0cb4ed294142aa141c53cae
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72364461"
---
# <a name="how-to-import-cmdlets-using-modules"></a>モジュールを使用してコマンドレットをインポートする方法

この記事では、バイナリモジュールを使用して PowerShell セッションにコマンドレットをインポートする方法について説明します。

> [!NOTE]
> モジュールのメンバーには、コマンドレット、プロバイダー、関数、変数、別名などを含めることができます。 スナップインには、コマンドレットとプロバイダーのみを含めることができます。

## <a name="how-to-load-cmdlets-using-a-module"></a>モジュールを使用してコマンドレットを読み込む方法

1. コマンドレットが実装されているアセンブリファイルと同じ名前のモジュールフォルダーを作成します。 この手順では、Windows の `system32` フォルダーにモジュールフォルダーが作成されます。

   `%SystemRoot%\system32\WindowsPowerShell\v1.0\Modules\mymodule`

1. `PSModulePath` 環境変数に、新しいモジュールフォルダーへのパスが含まれていることを確認します。 既定では、システムフォルダーは `PSModulePath` 環境変数に既に追加されています。 `PSModulePath`を表示するには、「`$env:PSModulePath`」と入力します。

1. コマンドレットアセンブリをモジュールフォルダーにコピーします。

1. モジュールのルートフォルダーにモジュールマニフェストファイル (`.psd1`) を追加します。 PowerShell はモジュールマニフェストを使用してモジュールをインポートします。 詳細については、「 [PowerShell モジュールマニフェストを記述する方法](../module/how-to-write-a-powershell-module-manifest.md)」を参照してください。

1. 次のコマンドを実行して、コマンドレットをセッションに追加します。

   `Import-Module [Module_Name]`

   この手順は、コマンドレットをテストするために使用できます。 これにより、アセンブリ内のすべてのコマンドレットがセッションに追加されます。 モジュールの詳細については、「 [Windows PowerShell モジュールの記述](../module/writing-a-windows-powershell-module.md)」を参照してください。

## <a name="see-also"></a>関連項目

[PowerShell モジュールマニフェストを記述する方法](../module/how-to-write-a-powershell-module-manifest.md)

[PowerShell モジュールのインポート](../module/importing-a-powershell-module.md)

[Import-Module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)

[モジュールのインストール](../module/installing-a-powershell-module.md)

[PSModulePath インストールパスの変更](../module/modifying-the-psmodulepath-installation-path.md)

[Windows PowerShell コマンドレットの記述](./writing-a-windows-powershell-cmdlet.md)
