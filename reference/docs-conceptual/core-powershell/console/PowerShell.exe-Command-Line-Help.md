---
ms.date: 2017-06-05
keywords: "PowerShell, コマンドレット"
title: "PowerShell.exe コマンドラインのヘルプ"
ms.assetid: 1ab7b93b-6785-42c6-a1c9-35ff686a958f
ms.openlocfilehash: c2583dac14f32db414f0a4377b1694ab7fa7523b
ms.sourcegitcommit: cd66d4f49ea762a31887af2c72d087b219ddbe10
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/11/2017
---
# <a name="powershellexe-command-line-help"></a>PowerShell.exe コマンドラインのヘルプ
Windows PowerShell セッションを開始します。 PowerShell.exe を使用して、Cmd.exe などの別のツールのコマンド ラインから Windows PowerShell セッションを起動したり、PowerShell.exe を Windows PowerShell コマンド ラインで使用して、新しいセッションを開始したりすることができます。 パラメーターを使用して、セッションをカスタマイズします。

## <a name="syntax"></a>構文

```syntax
PowerShell[.exe]
       [-Command { - | <script-block> [-args <arg-array>]
                     | <string> [<CommandParameters>] } ]
       [-EncodedCommand <Base64EncodedCommand>]
       [-ExecutionPolicy <ExecutionPolicy>]
       [-File <FilePath> [<Args>]]
       [-InputFormat {Text | XML}] 
       [-Mta]
       [-NoExit]
       [-NoLogo]
       [-NonInteractive] 
       [-NoProfile] 
       [-OutputFormat {Text | XML}] 
       [-PSConsoleFile <FilePath> | -Version <Windows PowerShell version>]
       [-Sta]
       [-WindowStyle <style>]
        

PowerShell[.exe] -Help | -? | /?
```

## <a name="parameters"></a>パラメーター

### <a name="-encodedcommand-base64encodedcommand"></a>-EncodedCommand <Base64EncodedCommand>
Base 64 エンコード文字列版のコマンドを許可します。 このパラメーターは、複雑な引用符や中かっこを必要とするコマンドを Windows PowerShell に渡す場合に使用します。

### <a name="-executionpolicy-executionpolicy"></a>-ExecutionPolicy <ExecutionPolicy>
現在のセッションの既定の実行ポリシーを設定し、$env:PSExecutionPolicyPreference 環境変数に保存します。 このパラメーターを指定しても、レジストリで設定された Windows PowerShell の実行ポリシーが変更されるわけではありません。 使用できる値の一覧など、Windows PowerShell 実行ポリシーの詳細については、「about_Execution_Policies (http://go.microsoft.com/fwlink/?LinkID=135170)」をご覧ください。

### <a name="-file-filepath-parameters"></a>-File <FilePath> \[<Parameters>]
スクリプトで作成される関数と変数を現在のセッションで使用できるように、指定したスクリプトをローカル スコープ ("ドット ソース形式") で実行します。 スクリプト ファイルのパスと (存在する場合) パラメーターを入力します。 **File** はコマンド内の最後のパラメーターにする必要があります。これは、**File** パラメーター名の後に入力されるすべての文字が、スクリプト ファイルのパス、およびその後に続くスクリプト パラメーターとその値として解釈されるためです。

**File** パラメーターの値には、スクリプトのパラメーターとパラメーター値を含めることができます。 例: `-File .\Get-Script.ps1 -Domain Central`スクリプトに渡されるパラメーターは、リテラル文字列として渡されます (現在のシェルによる解釈の後で)。
たとえば、cmd.exe で環境変数値を渡す場合は、次の cmd.exe 構文を使用します: `powershell -File .\test.ps1 -Sample %windir%` PowerShell 構文を使用するとしたら、この例では、リテラル "$env:windir" を受け取り、その環境変数の値は受け取りません: `powershell -File .\test.ps1 -Sample $env:windir`

通常、スクリプトのスイッチ パラメーターは、含めるか省略するかのいずれかです。 たとえば、次のコマンドは、Get-Script.ps1 スクリプト ファイルの **All** パラメーターを使用します。`-File .\Get-Script.ps1 -All`

### <a name="-inputformat-text--xml"></a>\-InputFormat {Text | XML}
Windows PowerShell に送信されるデータ形式を記述します。 使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。

### <a name="-mta"></a>-Mta
マルチスレッド アパートメントを使用して、Windows PowerShell を起動します。 このパラメーターは、Windows PowerShell 3.0 で導入されました。 Windows PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。 Windows PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。

### <a name="-noexit"></a>-NoExit
スタートアップ コマンドを実行後、終了しません。

### <a name="-nologo"></a>-NoLogo
スタートアップ時に著作権の見出しを非表示にします。

### <a name="-noninteractive"></a>-NonInteractive
ユーザーに対話的なプロンプトを表示しません。

### <a name="-noprofile"></a>-NoProfile
Windows PowerShell プロファイルを読み込みません。

### <a name="-outputformat-text--xml"></a>-OutputFormat {Text | XML}
Windows PowerShell からの出力の形式を決定します。 使用できる値は、"Text" (テキスト文字列) と "XML" (シリアル化された CLIXML 形式) です。

### <a name="-psconsolefile-filepath"></a>-PSConsoleFile <FilePath>
指定された Windows PowerShell コンソール ファイルを読み込みます。 コンソール ファイルの名前とパスを入力します。 コンソール ファイルを作成するには、Windows PowerShell で [Export-Console](https://technet.microsoft.com/en-us/library/4bab1c02-9e61-4aaf-9957-11d1934ef4ef) コマンドレットを使用します。

### <a name="-sta"></a>-Sta
シングルスレッド アパートメントを使用して、Windows PowerShell を起動します。 Windows PowerShell 3.0 では、シングルスレッド アパートメント (STA) が既定値です。 Windows PowerShell 2.0 では、マルチスレッド アパートメント (MTA) が既定値です。

### <a name="-version-windows-powershell-version"></a>-Version <Windows PowerShell Version>
指定したバージョンの Windows PowerShell を起動します。 指定するバージョンがシステムにインストールされている必要があります。 Windows PowerShell 3.0 がコンピューターにインストールされている場合、使用できる値は "2.0" と "3.0" です。 既定値は "3.0" です。

Windows PowerShell 3.0 がコンピューターにインストールされていない場合、使用できる値は "2.0" のみです。 他の値は無視されます。

詳細については、「[Windows PowerShell ファースト ステップ ガイド [OLD MSDN]](https://technet.microsoft.com/en-us/library/69555d95-b481-43e1-86e7-b46d68b3e2dd)」の「Windows PowerShell のインストール」をご覧ください。

### <a name="-windowstyle-window-style"></a>-WindowStyle <Window style>
セッションのウィンドウ スタイルを設定します。 使用できる値は、Normal、Minimized、Maximized、Hidden です。

### <a name="-command"></a>-Command
Windows PowerShell のコマンド プロンプトに入力された場合と同様に、指定されたコマンド (および任意のパラメーター) を実行します。NoExit パラメーターが指定されていない場合は、そのまま終了します。
基本的に、`-Command` の後の任意のテキストは、単一のコマンドラインとして PowerShell に送信されます (これは、`-File` がスクリプトに送信されるパラメーターを処理する方法とは異なります)。

Command の値には、"-"、文字列、またはスクリプト ブロックを指定できます。 またはスクリプト ブロックを指定できます。 Command の値が "-" の場合、コマンド テキストは標準入力から読み取られます。

スクリプト ブロックは中かっこ ({}) で囲む必要があります。 スクリプト ブロックを指定できるのは、PowerShell.exe を Windows PowerShell で実行する場合だけです。 スクリプトの結果は、ライブ オブジェクトとしてではなく、逆シリアル化された XML オブジェクトとして親シェルに返されます。

Command の値が文字列の場合、**Command** はコマンドの最後のパラメーターでなければなりません。コマンドの後に入力された文字は、コマンド引数として解釈されるためです。

Windows PowerShell コマンドを実行する文字列を記述するには、次の形式を使用します。

```
"& {<command>}"
```

引用符によりこれが文字列であることを示し、呼び出し演算子 (&) によりコマンドが実行されます。

### <a name="-help---"></a>-Help、-?、/?
このメッセージを表示します。 Windows PowerShell で PowerShell.exe のコマンドを入力している場合、コマンド パラメーターの前にスラッシュ (/) ではなくハイフン (-) を入力してください。 Cmd.exe では、ハイフンとスラッシュのいずれかを使用できます。

> [!NOTE]
> トラブルシューティング上の注意: Windows PowerShell 2.0 では、一部のプログラムを Windows PowerShell コンソールで開始すると、LastExitCode 0xc0000142 で失敗します。

## <a name="examples"></a>例

```
# Create a new PowerShell session and load a saved console file
PowerShell -PSConsoleFile sqlsnapin.psc1

# Create a new PowerShell V2 session with text input, XML output, and no logo
PowerShell -Version 2.0 -NoLogo -InputFormat text -OutputFormat XML

# Execute a Powerhell Command in a session
PowerShell -Command "Get-EventLog -LogName security"

# Run a script block in a session
PowerShell -Command {Get-EventLog -LogName security}

# An alternate wayh to run a command in a new session
PowerShell -Command "& {Get-EventLog -LogName security}"

# To use the -EncodedCommand parameter:
$command = "dir 'c:\program files' "
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encodedCommand = [Convert]::ToBase64String($bytes)
powershell.exe -encodedCommand $encodedCommand
```

