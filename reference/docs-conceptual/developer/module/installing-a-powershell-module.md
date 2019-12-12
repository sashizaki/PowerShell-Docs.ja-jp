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
ms.openlocfilehash: 60ac4bf9089232a9fa879e835e32da53422489fd
ms.sourcegitcommit: debd2b38fb8070a7357bf1a4bf9cc736f3702f31
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "72367071"
---
# <a name="installing-a-powershell-module"></a>PowerShell モジュールをインストールする

PowerShell モジュールを作成した後は、システムにモジュールをインストールして、自分や他のユーザーが使用できるようにすることができます。 一般に、これは、モジュールファイル (ie、hbase-runner.psm1、バイナリアセンブリ、モジュールマニフェスト、およびその他の関連ファイル) をそのコンピューター上のディレクトリにコピーすることで構成されます。 非常に小さなプロジェクトでは、Windows エクスプローラーを使用して1台のリモートコンピューターにファイルをコピーして貼り付けるのと同じように簡単に行うことができます。ただし、大規模なソリューションの場合は、より高度なインストールプロセスを使用することをお勧めします。 モジュールをシステムに取り込む方法に関係なく、PowerShell では、ユーザーがモジュールを見つけて使用できるようにするさまざまな手法を使用できます。 そのため、インストールの主な問題は、PowerShell がモジュールを検出できるようにすることです。 詳細については、「 [PowerShell モジュールのインポート](./importing-a-powershell-module.md)」を参照してください。

## <a name="rules-for-installing-modules"></a>モジュールをインストールするための規則

次の情報は、自分で使用するために作成したモジュール、他のパーティから取得したモジュール、他のユーザーに配布するモジュールなど、すべてのモジュールに関連しています。

### <a name="install-modules-in-psmodulepath"></a>PSModulePath にモジュールをインストールする

可能な限り、 **PSModulePath**環境変数に記載されているパスにすべてのモジュールをインストールするか、 **PSModulePath**環境変数の値にモジュールパスを追加します。

**PSModulePath**環境変数 ($Env:P SModulePath) には、Windows PowerShell モジュールの場所が含まれています。 コマンドレットは、この環境変数の値に依存してモジュールを検索します。

既定では、 **PSModulePath**環境変数の値には、次のシステムおよびユーザーモジュールのディレクトリが含まれていますが、値を追加して編集することができます。

- `$PSHome\Modules` (%Windir%\System32\WindowsPowerShell\v1.0\Modules)

  > [!WARNING]
  > この場所は、Windows に付属するモジュール用に予約されています。 この場所にモジュールをインストールしないでください。

- `$Home\Documents\WindowsPowerShell\Modules` (%UserProfile%\Documents\WindowsPowerShell\Modules)

- `$Env:ProgramFiles\WindowsPowerShell\Modules` (%ProgramFiles%\WindowsPowerShell\Modules)

  **PSModulePath**環境変数の値を取得するには、次のいずれかのコマンドを使用します。

  ```powershell
  $Env:PSModulePath
  [Environment]::GetEnvironmentVariable("PSModulePath")
  ```

  **PSModulePath**環境変数の値の値にモジュールパスを追加するには、次のコマンド形式を使用します。 この形式で**は、SetEnvironmentVariable クラスの**メソッドを使用して、 **PSModulePath**環境変数に対するセッションに依存しない変更を行います。

  ```powershell
  #Save the current value in the $p variable.
  $p = [Environment]::GetEnvironmentVariable("PSModulePath")

  #Add the new path to the $p variable. Begin with a semi-colon separator.
  $p += ";C:\Program Files (x86)\MyCompany\Modules\"

  #Add the paths in $p to the PSModulePath value.
  [Environment]::SetEnvironmentVariable("PSModulePath",$p)

  ```

  > [!IMPORTANT]
  > パスを**PSModulePath**に追加したら、変更に関する環境メッセージをブロードキャストする必要があります。 変更をブロードキャストすると、シェルなどの他のアプリケーションが変更を取得できるようになります。 変更をブロードキャストするには、製品のインストールコードで、`lParam` が文字列 "Environment" に設定された**WM_SETTINGCHANGE**メッセージを送信するようにします。 モジュールのインストールコードが**PSModulePath**を更新した後に、必ずメッセージを送信してください。

### <a name="use-the-correct-module-directory-name"></a>正しいモジュールディレクトリ名を使用する

適切な形式のモジュールは、モジュールディレクトリ内の少なくとも1つのファイルの基本名と同じ名前のディレクトリに格納されているモジュールです。 モジュールが整形式でない場合、Windows PowerShell はそれをモジュールとして認識しません。

ファイルの "ベース名" は、ファイル名拡張子のない名前です。 適切な形式のモジュールでは、モジュールファイルが格納されているディレクトリの名前が、モジュール内の少なくとも1つのファイルの基本名と一致している必要があります。

たとえば、サンプルの Fabrikam モジュールでは、モジュールファイルを含むディレクトリの名前は "Fabrikam" で、少なくとも1つのファイルには "Fabrikam" という基本名があります。 この場合、.psd1 と Fabrikam の両方に "Fabrikam" という基本名があります。

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

### <a name="effect-of-incorrect-installation"></a>不適切なインストールの影響

モジュールが整形式ではなく、その場所が**PSModulePath**環境変数の値に含まれていない場合、次のような Windows PowerShell の基本的な検出機能は機能しません。

- モジュールの自動読み込み機能では、モジュールを自動的にインポートすることはできません。

- [Get モジュール](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットの `ListAvailable` パラメーターがモジュールを見つけることができません。

- モジュールの[インポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットがモジュールを見つけることができません。 モジュールをインポートするには、ルートモジュールファイルまたはモジュールマニフェストファイルへの完全パスを指定する必要があります。

  次のような追加機能は、モジュールがセッションにインポートされない限り機能しません。 **PSModulePath**環境変数の適切な形式のモジュールでは、モジュールがセッションにインポートされていない場合でも、これらの機能は機能します。

- [Get Command](/powershell/module/Microsoft.PowerShell.Core/Get-Command)コマンドレットは、モジュール内のコマンドを見つけることができません。

- [Update-help](/powershell/module/Microsoft.PowerShell.Core/Update-Help)および update-help コマンドレットは、モジュールの[ヘルプを更新](/powershell/module/Microsoft.PowerShell.Core/Save-Help)したり、保存したりできません。

- [コマンド](/powershell/module/Microsoft.PowerShell.Utility/Show-Command)レットでは、モジュール内のコマンドを見つけて表示することはできません。

  モジュール内のコマンドが、Windows PowerShell Integrated Scripting Environment (ISE) の [`Show-Command`] ウィンドウに表示されていません。

## <a name="where-to-install-modules"></a>モジュールをインストールする場所

このセクションでは、Windows PowerShell モジュールをインストールするファイルシステム内の場所について説明します。 場所は、モジュールの使用方法によって異なります。

### <a name="installing-modules-for-a-specific-user"></a>特定のユーザーのモジュールのインストール

独自のモジュールを作成する場合、または Windows PowerShell コミュニティ web サイトなどの別のパーティからモジュールを取得し、そのモジュールをユーザーアカウントでのみ使用できるようにする場合は、ユーザー固有の Modules ディレクトリにモジュールをインストールします。

`$home\Documents\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

既定では、ユーザー固有の Modules ディレクトリが**PSModulePath**環境変数の値に追加されます。

### <a name="installing-modules-for-all-users-in-program-files"></a>プログラムファイル内のすべてのユーザーのモジュールをインストールする

コンピューター上のすべてのユーザーアカウントでモジュールを使用できるようにするには、プログラムファイルの場所にモジュールをインストールします。

`$Env:ProgramFiles\WindowsPowerShell\Modules\<Module Folder>\<Module Files>`

> [!NOTE]
> Windows PowerShell 4.0 以降では、Program Files の場所は既定で PSModulePath 環境変数の値に追加されます。 以前のバージョンの Windows PowerShell では、プログラムファイルの場所 (%ProgramFiles%\WindowsPowerShell\Modules) を手動で作成し、前述のように PSModulePath 環境変数にこのパスを追加することができます。

### <a name="installing-modules-in-a-product-directory"></a>製品ディレクトリへのモジュールのインストール

他のパーティにモジュールを配布する場合は、上記の既定のプログラムファイルの場所を使用するか、% ProgramFiles% ディレクトリの会社固有または製品固有のサブディレクトリを作成します。

たとえば、架空の企業である Fabrikam テクノロジは、Fabrikam Manager 製品用の Windows PowerShell モジュールを出荷しています。 モジュールインストーラーによって、Fabrikam Manager 製品サブディレクトリに Modules サブディレクトリが作成されます。

```
C:\Program Files
  Fabrikam Technologies
    Fabrikam Manager
      Modules
        Fabrikam
          Fabrikam.psd1 (module manifest)
          Fabrikam.dll (module assembly)

```

Windows PowerShell モジュール検出機能を有効にして Fabrikam モジュールを見つけるには、Fabrikam モジュールインストーラーによって、モジュールの場所が**PSModulePath**環境変数の値に追加されます。

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam Technologies\Fabrikam Manager\Modules\"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

### <a name="installing-modules-in-the-common-files-directory"></a>Common Files ディレクトリへのモジュールのインストール

1つの製品の複数のコンポーネントまたは複数のバージョンの製品でモジュールが使用されている場合は、%ProgramFiles%\Common Files\Modules サブディレクトリのモジュール固有のサブディレクトリにモジュールをインストールします。

次の例では、Fabrikam モジュールは `%ProgramFiles%\Common Files\Modules` サブディレクトリの Fabrikam サブディレクトリにインストールされます。 各モジュールは Modules サブディレクトリ内の独自のサブディレクトリに存在することに注意してください。

```
C:\Program Files
  Common Files
    Modules
      Fabrikam
        Fabrikam.psd1 (module manifest)
        Fabrikam.dll (module assembly)
```

次に、インストーラーによって、 **PSModulePath**環境変数の値に common files modules サブディレクトリのパスが確実に含まれるようになります。

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

## <a name="installing-multiple-versions-of-a-module"></a>モジュールの複数のバージョンのインストール

同じモジュールの複数のバージョンをインストールするには、次の手順を使用します。

1. モジュールのバージョンごとにディレクトリを作成します。 ディレクトリ名にバージョン番号を含めます。
2. モジュールのバージョンごとにモジュールマニフェストを作成します。 マニフェストの**ModuleVersion**キーの値に、モジュールのバージョン番号を入力します。 マニフェストファイル (.psd1) をモジュールのバージョン固有のディレクトリに保存します。
3. 次の例に示すように、モジュールルートフォルダーのパスを**PSModulePath**環境変数の値に追加します。

モジュールの特定のバージョンをインポートするために、エンドユーザーは、[モジュールのインポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットの `MinimumVersion` パラメーターまたは `RequiredVersion` パラメーターを使用できます。

たとえば、Fabrikam モジュールをバージョン8.0 および9.0 で使用できる場合、Fabrikam モジュールのディレクトリ構造は次のようになります。

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

インストーラーによって、両方のモジュールパスが**PSModulePath**環境変数の値に追加されます。

```powershell
$p = [Environment]::GetEnvironmentVariable("PSModulePath")
$p += ";C:\Program Files\Fabrikam\Fabrikam8;C:\Program Files\Fabrikam\Fabrikam9"
[Environment]::SetEnvironmentVariable("PSModulePath",$p)
```

これらの手順が完了すると、 [Get Module](/powershell/module/Microsoft.PowerShell.Core/Get-Module)コマンドレットの**ListAvailable**パラメーターは、両方の Fabrikam モジュールを取得します。 特定のモジュールをインポートするには、[モジュールのインポート](/powershell/module/Microsoft.PowerShell.Core/Import-Module)コマンドレットの `MinimumVersion` パラメーターまたは `RequiredVersion` パラメーターを使用します。

両方のモジュールが同じセッションにインポートされ、モジュールに同じ名前のコマンドレットが含まれている場合、最後にインポートされたコマンドレットはセッションで有効になります。

## <a name="handling-command-name-conflicts"></a>コマンド名の競合の処理

コマンド名の競合は、モジュールがエクスポートするコマンドの名前がユーザーのセッションのコマンドと同じである場合に発生する可能性があります。

セッションに同じ名前の2つのコマンドが含まれている場合、Windows PowerShell は、優先されるコマンドの種類を実行します。 セッションに同じ名前と同じ種類の2つのコマンドが含まれている場合、Windows PowerShell は、直前にセッションに追加されたコマンドを実行します。 既定では実行されないコマンドを実行する場合、ユーザーはコマンド名をモジュール名で修飾できます。

たとえば、セッションに `Get-Date` 関数と `Get-Date` コマンドレットが含まれている場合、Windows PowerShell は既定で関数を実行します。 コマンドレットを実行するには、次のように、コマンドの先頭にモジュール名を付けます。

```powershell
Microsoft.PowerShell.Utility\Get-Date
```

名前の競合を防ぐために、モジュールの作成者はモジュールマニフェストの**Defaultcommandprefix**キーを使用して、モジュールからエクスポートされたすべてのコマンドの名詞プレフィックスを指定できます。

ユーザーは、`Import-Module` コマンドレットの**prefix**パラメーターを使用して、代替のプレフィックスを使用できます。 **Prefix**パラメーターの値は、 **defaultcommandprefix**キーの値よりも優先されます。

## <a name="see-also"></a>参照

[about_Command_Precedence](/powershell/module/microsoft.powershell.core/about/about_command_precedence)

[Windows PowerShell モジュールの作成](./writing-a-windows-powershell-module.md)
