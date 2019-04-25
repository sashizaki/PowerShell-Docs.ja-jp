---
title: PowerShell モジュールのインストール |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb82827e-fdb7-4cbf-b3d4-093e72b3ff0e
caps.latest.revision: 28
ms.openlocfilehash: 7c2bfca50de4645676eafc01bbf23d9797e8b758
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62082194"
---
# <a name="installing-a-powershell-module"></a>PowerShell モジュールをインストールする

PowerShell モジュールを作成した後は可能性がありますするシステムでは、モジュールをインストールするか他者が使用可能性がありますようにします。 一般的に言えば、これだけで構成されるモジュール ファイル (ie、.psm1 またはバイナリ アセンブリ、モジュール マニフェストおよび他の関連ファイル) ディレクトリにそのコンピューターでをコピーします。 非常に小さいプロジェクトでは、コピーして、単一のリモート コンピューター上に Windows エクスプ ローラーでファイルを貼り付けるだけでこの可能性があります。ただし、大規模なソリューションのより高度なインストール プロセスを使用することがあります。 PowerShell は、システム上に、モジュールを取得する方法に関係なく、さまざまな手法は、ユーザーを検索して、モジュールを使用できるを使用できます。 (詳細については、次を参照してください[PowerShell モジュールをインポートする](./importing-a-powershell-module.md)。)。そのため、インストールの主な問題では、PowerShell がモジュールを検索できることが確認します。

このトピックには、次のセクションが含まれます。

- モジュールをインストールするための規則

- モジュールをインストールする場所

- モジュールの複数のバージョンをインストールします。

- コマンド名の競合の処理

## <a name="rules-for-installing-modules"></a>モジュールをインストールするための規則

次の情報は、独自の使用、他のパーティから取得したモジュールや他のユーザーに配布するモジュールを作成するモジュールを含む、すべてのモジュールに関連します。

### <a name="install-modules-in-psmodulepath"></a>Psmodulepath 環境変数でモジュールをインストールします。

可能であればに記載されているパスにすべてのモジュールをインストール、 **PSModulePath**環境変数またはモジュールのパスを追加、 **PSModulePath**環境変数の値。

**PSModulePath**環境変数 ($env:path: PSModulePath) Windows PowerShell モジュールの場所が格納されます。 コマンドレットは、モジュールを検索するには、この環境変数の値に依存します。

既定で、 **PSModulePath**環境変数の値には、次のシステムとユーザー モジュール ディレクトリが含まれていますに追加し、値を編集することができます。

- $PSHome\Modules (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > この場所は、Windows に付属するモジュールの予約されています。 この場所にモジュールをインストールしないでください。

- $Home\Documents\WindowsPowerShell\Modules (%UserProfile%\Documents\WindowsPowerShell\Modules)

- $Env:ProgramFiles\WindowsPowerShell\Modules (%ProgramFiles%\WindowsPowerShell\Modules)

  値を取得する、 **PSModulePath**環境変数では、次のコマンドのいずれかを使用します。

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  値にモジュールのパスを追加する、 **PSModulePath**環境変数値には、次のコマンド形式を使用します。 この形式を使用して、 **SetEnvironmentVariable**のメソッド、 **System.Environment**クラスを変更するセッションに依存しない、 **PSModulePath**環境変数。

  ```powershell

  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > パスを追加した後**PSModulePath**、変更に関する、環境のメッセージをブロードキャストする必要があります。 他のアプリケーション、シェルなど、変更を認識するを変更をブロードキャストできます。 変更をブロードキャストする送信製品インストール コードがある、 **WM_SETTINGCHANGE**メッセージである`lParam`文字列「環境」に設定します。 モジュールのインストール コードが更新された後にメッセージを送信することを確認する**PSModulePath**します。

### <a name="use-the-correct-module-directory-name"></a>適切なモジュールのディレクトリ名を使用して、

「的確な」モジュールとは、モジュール ディレクトリ内の少なくとも 1 つのファイルの基本名と同じ名前を持つディレクトリに格納されているモジュールです。 モジュールが適切な形式でない場合は、Windows PowerShell で認識されませんをモジュールとして。

ファイルの「基本名」は、ファイル名拡張子を除いた名前です。 整形式のモジュールでモジュール ファイルを含むディレクトリの名前がモジュール内の少なくとも 1 つのファイルの基本名と一致する必要があります。

たとえば、サンプル Fabrikam モジュールで、"Fabrikam"という名前のモジュール ファイルを含むディレクトリし、を少なくとも 1 つのファイルは、"Fabrikam"基本名前。 この場合、Fabrikam.psd1 と Fabrikam.dll の両方には、"Fabrikam"ベース名があります。

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a>あったり、インストールの影響

モジュールが整形式ではなくの値にその場所が含まれていない場合、 **PSModulePath**環境変数に次のよう Windows PowerShell での探索の基本的な機能が機能しません。

- モジュールの自動読み込み機能は、自動的にモジュールをインポートできません。

- `ListAvailable`のパラメーター、 [Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットは、モジュールを見つけることができません。

- [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットは、モジュールを見つけることができません。 モジュールをインポートするには、ルート モジュール ファイルまたはモジュール マニフェスト ファイルへの完全パスを指定する必要があります。

  モジュールがセッションにインポートしない限り、次などの追加機能が機能しません。 整形式のモジュールで、 **PSModulePath**モジュールは、セッションにインポートされていない場合でもに環境変数では、これらの機能の動作します。

- [Get-command](/powershell/module/Microsoft.PowerShell.Core/Get-Command)コマンドレットは、モジュールのコマンドを検索することはできません。

- [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)と[Save-help](/powershell/module/Microsoft.PowerShell.Core/Save-Help)コマンドレットを更新またはモジュールのヘルプを保存できません。

- [Show-command](/powershell/module/Microsoft.PowerShell.Utility/Show-Command)コマンドレットは、検索し、モジュールのコマンドを表示することはできません。

  モジュールのコマンドは表示されない、`Show-Command`ウィンドウで Windows PowerShell Integrated Scripting Environment (ISE)。

## <a name="where-to-install-modules"></a>モジュールをインストールする場所

このセクションでは、Windows PowerShell モジュールをインストールするファイル システムで場所について説明します。 場所は、モジュールの使用方法によって異なります。

### <a name="installing-modules-for-a-specific-user"></a>特定のユーザーのモジュールをインストールします。

独自のモジュールを作成するか、Windows PowerShell コミュニティ web サイトなどの別のパーティからモジュールを取得するユーザー アカウントのみで使用できるモジュールをする場合は、ユーザー固有の Modules ディレクトリで、モジュールをインストールします。

```
$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>
```

ユーザー固有のモジュール ディレクトリがの値に追加、 **PSModulePath**既定の環境変数。

### <a name="installing-modules-for-all-users-in-program-files"></a>すべてのユーザーのプログラム ファイルのモジュールをインストールします。

モジュールをコンピューター上のすべてのユーザー アカウントに使用可能な場合は、プログラム ファイルの場所にモジュールをインストールします。

```
$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>
```

> [!NOTE]
> プログラム ファイルの場所は、既定では Windows PowerShell 4.0 以降、PSModulePath 環境変数の値に追加されます。 以前のバージョンの Windows PowerShell は、手動でプログラム ファイルの場所の ((%ProgramFiles%\WindowsPowerShell\Modules) を作成し、前述のように、このパスを PSModulePath 環境変数に追加することができます。

### <a name="installing-modules-in-a-product-directory"></a>製品ディレクトリ内のモジュールをインストールします。

他の当事者にモジュールを配布する場合は、上記で説明した既定のプログラム ファイルの場所を使用して、または %programfiles% ディレクトリの独自に固有の会社または製品に固有のサブディレクトリを作成します。

たとえば、Fabrikam テクノロジ、架空の会社では、Fabrikam Manager 製品用の Windows PowerShell モジュールは出荷します。 そのモジュール インストーラーには、Fabrikam Manager 製品のサブディレクトリでモジュールのサブディレクトリが作成されます。

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Fabrikam モジュールを検索する Windows PowerShell モジュールの検出機能を有効にするには、Fabrikam モジュール インストーラーでは、値にモジュールの場所を追加、 **PSModulePath**環境変数。

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += "C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>一般的なファイルのディレクトリにモジュールをインストールします。

製品の複数のコンポーネントまたは製品の複数のバージョン、モジュールを使用する場合は、%ProgramFiles%\Common Files\Modules サブディレクトリのモジュールに固有のサブディレクトリに、モジュールをインストールします。

次の例では、Fabrikam モジュールは Fabrikam %ProgramFiles%\Common Files\Modules サブディレクトリのサブディレクトリにインストールされます。 各モジュールがモジュールのサブディレクトリでは、そのサブディレクトリに格納されているに注意してください。

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)

```

インストーラーがの値を保証し、 **PSModulePath**環境変数には、一般的なファイル モジュールのサブディレクトリのパスが含まれています。

```powershell
$m = $env:ProgramFiles + '\Common Files\Modules'
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$q = $p -split ';'
if ($q -notContains $m) {
    $q += ";$m"
}
$p = $q -join ';'
[Environment]::SetEnvironmentVariable("PSModulePath", $p)
```

## <a name="installing-multiple-versions-of-a-module"></a>モジュールの複数のバージョンをインストールします。

同じモジュールの複数のバージョンをインストールするには、次の手順を使用します。

1. モジュールの各バージョン用のディレクトリを作成します。 ディレクトリ名にバージョン番号を含めます。

2. モジュールの各バージョンのモジュール マニフェストを作成します。 値で、 **ModuleVersion**マニフェストでキーに、モジュールのバージョン番号を入力します。 モジュールのバージョン固有のディレクトリでマニフェスト ファイル (.psd1) を保存します。

3. 値にモジュールのルート フォルダーのパスを追加、 **PSModulePath**環境変数は、次の例に示すようにします。

特定のバージョンのモジュールをインポートする、エンドユーザーが使用できます、`MinimumVersion`または`RequiredVersion`のパラメーター、 [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレット。

たとえば、Fabrikam モジュールをバージョン 8.0、9.0 で使用できる場合、Fabrikam のモジュールのディレクトリ構造は、次のようになります。

 ```
C:\Program Files
Fabrikam Manager
  Fabrikam8
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "8.0")
      Fabrikam.dll (module assembly)
  Fabrikam9
    Fabrikam
      Fabrikam.psd1 (module manifest: ModuleVersion = "9.0")
      Fabrikam.dll (module assembly)
```

インストーラーの追加モジュールのパスの両方、 **PSModulePath**環境変数の値。

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

これらの手順の完了時に、 **ListAvailable**のパラメーター、 [Get-module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットは、Fabrikam のモジュールの両方を取得します。 特定のモジュールをインポートするには、使用、`MinimumVersion`または`RequiredVersion`のパラメーター、 [Import-module](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレット。

両方のモジュールは、同じセッションでインポート モジュールにはと同じ名前では、コマンドレットが含まれて、最後にインポートされているコマンドレットは、セッションで有効です。

## <a name="handling-command-name-conflicts"></a>コマンド名の競合の処理

モジュールがエクスポートするコマンドがユーザーのセッションでコマンドと同じ名前を指定、コマンド名の競合が発生します。

セッションに同じ名前を持つ 2 つのコマンドが含まれている場合、Windows PowerShell には、優先するコマンドの種類が実行されます。 セッションに同じ名前と同じ型を持つ 2 つのコマンドが含まれている場合、Windows PowerShell は、最も最近のセッションに追加されたコマンドを実行します。 既定では、実行されないコマンドを実行するには、ユーザーは、モジュール名でコマンド名を修飾できます。

セッションに含まれる場合など、`Get-Date`関数と`Get-Date`コマンドレットでは、Windows PowerShell は、既定では、関数を実行します。 コマンドレットを実行するには、など、モジュールの名前を持つコマンドを前します。

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

名前の競合を防ぐためには、モジュールの作成者が使用できる、 **DefaultCommandPrefix**モジュールからすべてのコマンドの名詞プレフィックスを指定するモジュール マニフェストでキーをエクスポートします。

ユーザーが使用できる、**プレフィックス**のパラメーター、`Import-Module`代替プレフィックスを使用するコマンドレットです。 値、**プレフィックス**パラメーターの値よりも優先、 **DefaultCommandPrefix**キー。

## <a name="see-also"></a>参照

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[Windows PowerShell モジュールの記述](./writing-a-windows-powershell-module.md)
