---
title: PSModulePath のインストールパスを変更する |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: 639d3a28dd2af09fcc498caedc5fe74c1493445d
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2019
ms.locfileid: "72360671"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>PSModulePath インストール パスを変更する

@No__t 0 環境変数は、ディスクにインストールされているモジュールの場所へのパスを格納します。 ユーザーがモジュールへの完全パスを指定していない場合、Windows PowerShell はこの変数を使用してモジュールを検索します。 この変数のパスは、表示されている順序で検索されます。

Windows PowerShell が起動すると、`PSModulePath` は、次の既定値を持つシステム環境変数として作成されます: `$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`。

## <a name="to-view-the-psmodulepath-variable"></a>PSModulePath 変数を表示するには

@No__t 0 変数に指定されているパスを表示するには、次のコマンドを入力します。

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>PSModulePath 変数に場所を追加するには

この変数にパスを追加するには、次のいずれかの方法を使用します。

- 現在のセッションでのみ使用できる一時的な値を追加するには、コマンドラインで次のコマンドを実行します。

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- セッションが開かれるたびに使用できる永続的な値を追加するには、次のコマンドを Windows PowerShell プロファイルに追加します。

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  プロファイルの詳細については、Microsoft TechNet ライブラリの「 [about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) 」を参照してください。

- 永続変数をレジストリに追加するには、**システムのプロパティ** ダイアログボックスの 環境変数エディター を使用して、`PSModulePath` という名前の新しいユーザー環境変数を作成します。

- スクリプトを使用して永続変数を追加するには、環境クラスで**SetEnvironmentVariable**メソッドを使用します。 たとえば、次のスクリプトは、"C:\Program Files\Fabrikam\Module path をコンピューターの PSModulePath 環境変数の値に追加します。 このパスを user PSModulePath 環境変数に追加するには、ターゲットを "User" に設定します。

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>PSModulePath から場所を削除するには

同様の方法を使用して、変数からパスを削除できます。たとえば、`$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"` は、現在のセッションから**C:\ モジュールパス**パスを削除します。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの作成](./writing-a-windows-powershell-module.md)
