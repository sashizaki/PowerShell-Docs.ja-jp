---
title: PSModulePath インストール パスの変更 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc5ce5a2-50e9-4c88-abf1-ac148a8a6b7b
caps.latest.revision: 15
ms.openlocfilehash: 639d3a28dd2af09fcc498caedc5fe74c1493445d
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855568"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>PSModulePath インストール パスを変更する

`PSModulePath`環境変数には、ディスクにインストールされているモジュールの場所へのパスが格納されます。 Windows PowerShell では、この変数を使用して、ユーザーは、モジュールへの完全パスを指定しない場合に、モジュールを見つけます。 この変数のパスが表示される順序で検索されます。

Windows PowerShell の起動時、`PSModulePath`で既定値は、次のシステム環境変数として作成されます:`$home\Documents\WindowsPowerShell\Modules; $pshome\Modules`します。

## <a name="to-view-the-psmodulepath-variable"></a>PSModulePath 変数を表示するには

指定されているパスを表示する、`PSModulePath`変数、次のコマンドを入力します。

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>PSModulePath 変数に場所を追加

パスをこの変数を追加するには、次のメソッドのいずれかを使用します。

- 現在のセッションでのみ使用できる一時的な値を追加するには、コマンド ラインで、次のコマンドを実行します。

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

- セッションが開かれるたびに使用できる永続的な値を追加するには、Windows PowerShell プロファイルに、次のコマンドを追加します。

  `$env:PSModulePath = $env:PSModulePath + ";c:\ModulePath"`

  プロファイルの詳細については、[about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles) 、Microsoft TechNet ライブラリを参照してください。

- レジストリに永続的な変数を追加するには、という新しいユーザーの環境変数を作成`PSModulePath`で環境変数エディターを使用して、**システム プロパティ** ダイアログ ボックス。

- スクリプトを使用して永続的な変数を追加するには、使用、 **SetEnvironmentVariable**環境クラスのメソッド。 たとえば、次のスクリプト パスに追加します"C:\Program Files\Fabrikam\Module コンピューターの PSModulePath 環境変数の値にします。 ユーザーの PSModulePath 環境変数には、パスを追加するには、「ユーザー」、ターゲットを設定します。

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + ";C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>PSModulePath の場所を削除するには

同様のメソッドを使用して、変数からのパスを削除することができます。 たとえば、`$env:PSModulePath = $env:PSModulePath -replace ";c:\\ModulePath"`が削除されます、 **c:\ModulePath** 、現在のセッションからのパス。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの記述](./writing-a-windows-powershell-module.md)
