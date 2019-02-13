---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: レジストリ エントリの操作
ms.assetid: fd254570-27ac-4cc9-81d4-011afd29b7dc
ms.openlocfilehash: 8483b6f98739697b24a13055dfffbc7b5bacc2cc
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MTE95
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2019
ms.locfileid: "55681541"
---
# <a name="working-with-registry-entries"></a>レジストリ エントリの操作

レジストリ エントリはキーのプロパティであり直接参照できないため、利用するときは少し異なる方法を取る必要があります。

### <a name="listing-registry-entries"></a>レジストリ エントリの一覧表示

レジストリ エントリを確認するには、多くのさまざまな方法があります。 最も簡単な方法は、キーに関連付けられているプロパティの名前を取得することです。 たとえば、レジストリ キー内のエントリの名前を表示する`HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion`を使用して、`Get-Item`します。 レジストリ キーは、キーのレジストリ エントリの一覧であり、"Property"という汎用的な名前のプロパティを持っています。
次のコマンドは、Property プロパティを選択し、一覧に表示されるように項目を拡張します。

```powershell
Get-Item -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion |
  Select-Object -ExpandProperty Property
```

```Output
DevicePath
MediaPathUnexpanded
ProgramFilesDir
CommonFilesDir
ProductId
```

読みやすい形式でレジストリ エントリを表示するには使用`Get-ItemProperty`:

```powershell
Get-ItemProperty -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

```Output
PSPath              : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows\CurrentVersion
PSParentPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows
PSChildName         : CurrentVersion
PSDrive             : HKLM
PSProvider          : Microsoft.PowerShell.Core\Registry
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
CommonFilesDir      : C:\Program Files\Common Files
ProductId           : 76487-338-1167776-22465
WallPaperDir        : C:\WINDOWS\Web\Wallpaper
MediaPath           : C:\WINDOWS\Media
ProgramFilesPath    : C:\Program Files
PF_AccessoriesName  : Accessories
(default)           :
```

キーの Windows PowerShell 関連のプロパティには、**PSPath**、**PSParentPath**、**PSChildName**、および **PSProvider** のように、すべて先頭に "PS" が付きます。

現在の場所を参照するには、"`*.*`." 表記法を使用できます。 使用することができます`Set-Location`に変更する、 **CurrentVersion**レジストリのコンテナー最初。

```powershell
Set-Location -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

組み込みの HKLM PSDrive を使用する代わりに、 `Set-Location`:

```powershell
Set-Location -Path hklm:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

現在の場所に対して "`*.*`." 表記法を使用して、完全パスを指定しないでプロパティの一覧を表示することができます。

```powershell
Get-ItemProperty -Path .
```

```Output
...
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
...
```

この場所から取得できるように、ファイル システム内と同じパスの展開動作、 **ItemProperty**の`HKLM:\SOFTWARE\Microsoft\Windows\Help`を使用して`Get-ItemProperty -Path ..\Help`します。

### <a name="getting-a-single-registry-entry"></a>1 つのレジストリ エントリの取得

レジストリ キーの特定のエントリを取得する場合は、いくつかの可能なアプローチのいずれかを使用できます。 この例の値を検索する**DevicePath**で`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`します。

使用して`Get-ItemProperty`を使用して、**パス**、キーの名前を指定するパラメーター、および**名前**の名前を指定するパラメーター、 **DevicePath**エントリ。

```powershell
Get-ItemProperty -Path HKLM:\Software\Microsoft\Windows\CurrentVersion -Name DevicePath
```

```Output
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows\CurrentVersion
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows
PSChildName  : CurrentVersion
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
DevicePath   : C:\WINDOWS\inf
```

このコマンドは、標準の Windows PowerShell のプロパティと **DevicePath** プロパティを返します。

> [!NOTE]
> `Get-ItemProperty`が**フィルター**、 **Include**、および**除外**パラメーター、プロパティ名でフィルター処理には使用できません。 これらのパラメーターは、項目のパスは、レジストリ エントリではないレジストリ キーを参照してください。 項目のプロパティのレジストリ エントリ。

別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。 Reg.exe のヘルプを表示するには、入力`reg.exe /?`コマンド プロンプトでします。 DevicePath エントリを検索するには、次のコマンドに示すように reg.exe を使用します。

```powershell
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion /v DevicePath
```

```Output
! REG.EXE VERSION 3.0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
    DevicePath  REG_EXPAND_SZ   %SystemRoot%\inf
```

また、**WshShell COM** オブジェクトを使用していくつかのレジストリ エントリを検索することもできますが、この方法は、大きなバイナリ データや、名前に "\\" を含むレジストリ エントリでは利用できません。 プロパティ名を区切り記号 \\ と共に項目のパスに追加します。

```powershell
(New-Object -ComObject WScript.Shell).RegRead("HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\DevicePath")
```

```Output
%SystemRoot%\inf
```

### <a name="setting-a-single-registry-entry"></a>1 つのレジストリ エントリの設定

レジストリ キーの特定のエントリを変更する場合は、いくつかの可能なアプローチのいずれかを使用できます。 この例の変更、**パス**エントリ`HKEY_CURRENT_USER\Environment`。 **パス**エントリは、実行可能ファイルを検索する場所を指定します。

1. 現在の値を取得、**パス**を使用してエントリ`Get-ItemProperty`します。
2. 分離することで、新しい値を追加、`;`します。
3. 使用`Set-ItemProperty`指定したキー、エントリ名、およびレジストリ エントリを変更する値。

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path += ";C:\src\bin\"
Set-ItemProperty -Path HKCU:\Environment -Name Path -Value $newpath
```

> [!NOTE]
> `Set-ItemProperty`が**フィルター**、 **Include**、および**除外**パラメーター、プロパティ名でフィルター処理には使用できません。 これらのパラメーターはレジストリ キー (項目のパス) を参照し、レジストリ エントリ (項目のプロパティ) を参照するのではありません。

別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。 reg.exe のヘルプを表示するには、コマンド プロンプトで「**reg.exe /?**」と入力します。
at a command prompt.

次の例の変更、**パス**上記の例で追加のパスを削除することで入力します。
`Get-ItemProperty` 返された文字列を解析しなくてもすむように、現在の値を取得するために使用がまだ`reg query`します。 **SubString**と**LastIndexOf**に追加された最後のパスの取得に使用する方法、**パス**エントリ。

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path.SubString(0, $value.Path.LastIndexOf(';'))
reg add HKCU\Environment /v Path /d $newpath /f
```

```Output
The operation completed successfully.
```

### <a name="creating-new-registry-entries"></a>新しいレジストリ エントリの作成

"PowerShellPath"という名前の新しいエントリを追加する、 **CurrentVersion**キーを使用して`New-ItemProperty`キー、エントリ名、およびエントリの値へのパス。 この例では、Windows PowerShell 変数の値を取得しましたが`$PSHome`、Windows PowerShell のインストール ディレクトリへのパスを格納します。

キーに新しいエントリを追加するには、次のコマンドを使用します。このコマンドは、新しいエントリに関する情報も返します。

```powershell
New-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -PropertyType String -Value $PSHome
```

```Output
PSPath         : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
PSParentPath   : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows
PSChildName    : CurrentVersion
PSDrive        : HKLM
PSProvider     : Microsoft.PowerShell.Core\Registry
PowerShellPath : C:\Program Files\Windows PowerShell\v1.0
```

**PropertyType** は、次の表の **Microsoft.Win32.RegistryValueKind** 列挙体のメンバーの名前にする必要があります。

|PropertyType の値|意味|
|----------------------|-----------|
|Binary|バイナリ データ|
|DWord|有効な UInt32 である数字|
|ExpandString|動的に展開される環境変数を含むことができる文字列|
|MultiString|複数行文字列|
|String|任意の文字列値|
|QWord|8 バイトのバイナリ データ|

> [!NOTE]
> **Path** パラメーターに値の配列を指定して、レジストリ エントリを複数の場所に追加できます。

```powershell
New-ItemProperty -Name PowerShellPath -PropertyType String -Value $PSHome `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion, HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

追加することで、既存のレジストリ エントリの値を上書きすることも、 **Force**パラメーターを`New-ItemProperty`コマンド。

### <a name="renaming-registry-entries"></a>レジストリ エントリの名前変更

名前を変更する、 **PowerShellPath**エントリを"PSHome"、" `Rename-ItemProperty`:

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome
```

名前が変更された値を表示するには、**PassThru** パラメーターをコマンドに追加します。

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome -passthru
```

### <a name="deleting-registry-entries"></a>レジストリ エントリの削除

PSHome と PowerShellPath の両方のレジストリ エントリを削除するには使用`Remove-ItemProperty`:

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PSHome
Remove-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath
```
