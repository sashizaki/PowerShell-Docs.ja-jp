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
ms.openlocfilehash: b176d8439025ac132962859f79e72ae6f9703e82
ms.sourcegitcommit: 4a26c05f162c4fa347a9d67e339f8a33e230b9ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78405049"
---
# <a name="modifying-the-psmodulepath-installation-path"></a>PSModulePath インストール パスを変更する

`PSModulePath` 環境変数には、ディスクにインストールされているモジュールの場所へのパスが格納されます。 PowerShell では、モジュールへの完全パスをユーザーが指定しない場合、この変数を使用してモジュールを検索します。 この変数のパスは、表示されている順序で検索されます。

PowerShell を起動すると、`PSModulePath` がシステム環境変数として作成されます。既定値は、Windows の場合は `$HOME\Documents\PowerShell\Modules; $PSHOME\Modules`、Linux または Mac の場合は `$HOME/.local/share/powershell/Modules: usr/local/share/powershell/Modules`、Windows PowerShell の場合は `$HOME\Documents\WindowsPowerShell\Modules; $PSHOME\Modules` です。

> [!NOTE]
> ユーザー固有の**CurrentUser**の場所は、ユーザープロファイル内の**ドキュメント**の場所にある `WindowsPowerShell\Modules` フォルダーです。 その場所の特定のパスは、Windows のバージョンと、フォルダーリダイレクトを使用しているかどうかによって異なります。 既定では、Windows 10 の場合、その場所は `$HOME\Documents\WindowsPowerShell\Modules`です。

## <a name="to-view-the-psmodulepath-variable"></a>PSModulePath 変数を表示するには

`PSModulePath` 変数に指定されているパスを表示するには、次のコマンドを入力します。

`$env:PSModulePath`

## <a name="to-add-locations-to-the-psmodulepath-variable"></a>PSModulePath 変数に場所を追加するには

この変数にパスを追加するには、次のいずれかの方法を使用します。

- 現在のセッションでのみ使用できる一時的な値を追加するには、コマンドラインで次のコマンドを実行します。

  `$env:PSModulePath = $env:PSModulePath + "$([System.IO.Path]::PathSeparator)$MyModulePath"`

- セッションが開かれるたびに使用できる永続的な値を追加するには、上記のコマンドを PowerShell プロファイルファイル (`$PROFILE`) に追加し >

  プロファイルの詳細については、「[about_Profiles](/powershell/module/microsoft.powershell.core/about/about_profiles)」を参照してください。

- 永続変数をレジストリに追加するには、**システムのプロパティ** ダイアログボックスの 環境変数エディター を使用して、`PSModulePath` という名前の新しいユーザー環境変数を作成します。

- スクリプトを使用して永続変数を追加する[には、](https://docs.microsoft.com/dotnet/api/system.environment) [SetEnvironmentVariable](https://docs.microsoft.com/dotnet/api/system.environment.setenvironmentvariable)クラスの .net メソッドを使用します。 たとえば、次のスクリプトは、コンピューターの `PSModulePath` 環境変数の値に `C:\Program Files\Fabrikam\Module` パスを追加します。 ユーザー `PSModulePath` 環境変数にパスを追加するには、ターゲットを "User" に設定します。

  ```powershell
  $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine")
  [Environment]::SetEnvironmentVariable("PSModulePath", $CurrentValue + [System.IO.Path]::PathSeparator + "C:\Program Files\Fabrikam\Modules", "Machine")

  ```

## <a name="to-remove-locations-from-the-psmodulepath"></a>PSModulePath から場所を削除するには

同様のメソッドを使用して、変数からパスを削除できます。たとえば、`$env:PSModulePath = $env:PSModulePath -replace "$([System.IO.Path]::PathSeparator)c:\\ModulePath"` によって、現在のセッションから**C:\ モジュールパス**パスが削除されます。

## <a name="see-also"></a>参照

[Windows PowerShell モジュールの作成](./writing-a-windows-powershell-module.md)

[about_Modules](/powershell/module/microsoft.powershell.core/about/about_modules)
