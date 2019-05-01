---
ms.date: 06/05/2017
keywords: PowerShell, コマンドレット
title: レジストリ エントリの操作
ms.assetid: fd254570-27ac-4cc9-81d4-011afd29b7dc
ms.openlocfilehash: 667d17d0d62745a27ffef5f1912336b72f74c2a9
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62086036"
---
# <a name="working-with-registry-entries"></a>レジストリ エントリの操作

レジストリ エントリはキーのプロパティであり直接参照できないため、利用するときは少し異なる方法を取る必要があります。

## <a name="listing-registry-entries"></a>レジストリ エントリの一覧表示

レジストリ エントリを確認するには、多くのさまざまな方法があります。 最も簡単な方法は、キーに関連付けられているプロパティの名前を取得することです。 たとえば、レジストリ キー `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion` のエントリの名前を確認するには、`Get-Item` を使います。 レジストリ キーは、キーのレジストリ エントリの一覧であり、"Property"という汎用的な名前のプロパティを持っています。
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

レジストリ エントリをさらに読みやすい形式で表示するには、`Get-ItemProperty` を使います。

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

現在の場所を参照するために、`*.*` 表記を使用できます。 `Set-Location` を使用して、まず **CurrentVersion** レジストリのコンテナーに変更します。

```powershell
Set-Location -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

または、`Set-Location` と共に組み込みの HKLM PSDrive を使用できます。

```powershell
Set-Location -Path hklm:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

次に、現在の場所に対して `*.*` 表記を使用して、完全パスを指定することなくプロパティを一覧表示できます。

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

パスの展開は、ファイル システム内の場合と同様に機能します。そのため、この場所から `Get-ItemProperty -Path ..\Help` を使って `HKLM:\SOFTWARE\Microsoft\Windows\Help` の **ItemProperty** の一覧を取得できます。

## <a name="getting-a-single-registry-entry"></a>1 つのレジストリ エントリの取得

レジストリ キーの特定のエントリを取得する場合は、いくつかの可能なアプローチのいずれかを使用できます。 この例では、`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion` の **DevicePath** の値を検索します。

`Get-ItemProperty` を使用する場合、**Path** パラメーターを使用してキーの名前を指定し、**Name** パラメーターを使用して **DevicePath** のエントリの名前を指定します。

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
> `Get-ItemProperty` には **Filter**、**Include**、**Exclude** パラメーターが含まれていますが、これらはプロパティ名でフィルター処理するためには使えません。 これらのパラメーターではレジストリ キーを参照します。これは項目のパスであり、レジストリ エントリではありません。 項目のプロパティであるレジストリ エントリです。

別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。 reg.exe のヘルプを表示するには、コマンド プロンプトで `reg.exe /?` と入力します。 DevicePath エントリを検索するには、次のコマンドに示すように reg.exe を使用します。

```powershell
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion /v DevicePath
```

```Output
! REG.EXE VERSION 3.0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
    DevicePath  REG_EXPAND_SZ   %SystemRoot%\inf
```

また、**WshShell** COM オブジェクトを使っていくつかのレジストリ エントリを検索することもできますが、大きなバイナリ データや、"\\" のような文字を含むレジストリ エントリ名を使う場合、この方法は機能しません。 プロパティ名を区切り記号 \\ と共に項目のパスに追加します。

```powershell
(New-Object -ComObject WScript.Shell).RegRead("HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\DevicePath")
```

```Output
%SystemRoot%\inf
```

## <a name="setting-a-single-registry-entry"></a>1 つのレジストリ エントリの設定

レジストリ キーの特定のエントリを変更する場合は、いくつかある可能なアプローチのいずれかを使用できます。 この例では、`HKEY_CURRENT_USER\Environment` 下の **Path** エントリを変更します。 **Path** エントリでは、実行可能ファイルを検索する場所を指定します。

1. `Get-ItemProperty` を使って **Path** エントリの現在の値を取得します。
2. `;` で区切りながら新しい値を追加します。
3. 指定したキー、エントリ名、およびレジストリ エントリを変更する値と共に `Set-ItemProperty` を使います。

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path += ";C:\src\bin\"
Set-ItemProperty -Path HKCU:\Environment -Name Path -Value $newpath
```

> [!NOTE]
> `Set-ItemProperty` には **Filter**、**Include**、**Exclude** パラメーターが含まれていますが、これらはプロパティ名でフィルター処理するためには使えません。 これらのパラメーターはレジストリ キー (項目のパス) を参照し、レジストリ エントリ (項目のプロパティ) を参照するのではありません。

別のオプションとして、Reg.exe コマンド ライン ツールを使用することもできます。 reg.exe のヘルプを表示するには、コマンド プロンプトで「**reg.exe /?**」と入力します。
at a command prompt.

次の例では、上記の例で追加したパスを削除することで **Path** エントリを変更します。
`reg query` から返された文字列を解析しなくて済むようにするため、`Get-ItemProperty` を引き続き使って現在の値を取得します。 **Path** エントリに追加された最後のパスを取得するために、**SubString** および **LastIndexOf** メソッドを使います。

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path.SubString(0, $value.Path.LastIndexOf(';'))
reg add HKCU\Environment /v Path /d $newpath /f
```

```Output
The operation completed successfully.
```

## <a name="creating-new-registry-entries"></a>新しいレジストリ エントリの作成

"PowerShellPath" という名前の新しいエントリを **CurrentVersion** キーに追加するには、キーのパス、エントリ名、エントリの値と共に `New-ItemProperty` を使用します。 この例では、Windows PowerShell の変数 `$PSHome` の値を取得します。これには、Windows PowerShell のインストール ディレクトリへのパスが格納されます。

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

また、**Force** パラメーターを任意の `New-ItemProperty` コマンドに追加して、既存のレジストリ エントリの値を上書きすることもできます。

## <a name="renaming-registry-entries"></a>レジストリ エントリの名前変更

**PowerShellPath** エントリの名前を "PSHome" に変更するには、`Rename-ItemProperty` を使用します。

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome
```

名前が変更された値を表示するには、**PassThru** パラメーターをコマンドに追加します。

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome -passthru
```

## <a name="deleting-registry-entries"></a>レジストリ エントリの削除

PSHome と PowerShellPath の両方のレジストリ エントリを削除するには、`Remove-ItemProperty` を使用します。

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PSHome
Remove-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath
```
