---
title: "WMF 5.1 (プレビュー) の新しいシナリオと機能"
ms.date: 2016-07-06
keywords: PowerShell, DSC, WMF
description: 
ms.topic: article
author: keithb
manager: dongill
ms.prod: powershell
ms.technology: WMF
translationtype: Human Translation
ms.sourcegitcommit: dcccf6880873c3f5c1b58fb1a8c546901b173879
ms.openlocfilehash: 9341b7fc3feea20cc2434065c3e512d1a8dd2b54

---

# WMF 5.1 (プレビュー) の新しいシナリオと機能 #

> 注意: この情報は暫定版であり、変更することがあります。

## PowerShell のエディション ##
バージョン 5.1 から、PowerShell はさまざまな機能セットとプラットフォーム互換性を備える別のエディションで使用できます。

- **デスクトップ エディション:** .NET Framework 上に構築されており、Server Core や Windows Desktop などの Windows の完全エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。
- **コア エディション:** .NET Core 上に構築されており、Nano Server や Windows IoT などの Windows の縮小エディションで実行する PowerShell のバージョンを対象とするスクリプトおよびモジュールとの互換性を提供します。

**PowerShell のエディションの使用に関する詳細**
- [PowerShell の実行エディションを特定する]()
- [特定の PowerShell バージョンに対するモジュールの互換性を宣言する]()
- [CompatiblePSEditions で Get-Module の結果をフィルターする]()
- [互換性のある PowerShell のエディションで実行しない場合はスクリプトを実行させない]()

## モジュール分析キャッシュ ##
WMF 5.1 以降の PowerShell では、エクスポートするコマンドなど、モジュールに関するデータのキャッシュに使用されるファイルを制御できます。

既定では、このキャッシュは `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` ファイルに格納されます。
キャッシュは、通常、起動時にコマンドを検索するときに読み取られ、モジュールのインポート後しばらくしてバックグラウンド スレッドで書き込まれます。

キャッシュの既定の場所を変更するには、PowerShell を開始する前に、環境変数 PSModuleAnalysisCachePath を設定します。 この環境変数の変更は、子プロセスのみに影響します。
値には、PowerShell がファイルの作成および書き込みアクセス許可を持つ完全なパス (ファイル名を含む) を指定する必要があります。
ファイル キャッシュを無効にするには、たとえば次のような無効な場所をこの値に設定します。

```PowerShell
$env:PSModuleAnalysisCachePath = 'nul'
```

これは、パスを無効なデバイスに設定します。 PowerShell がパスに書き込めない場合、エラーは返されませんが、トレーサーでエラー レポートを見ることができます。

```PowerShell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

キャッシュの書き込み時、PowerShell は存在しなくなったモジュールを確認することで、キャッシュが不必要に大きくなるのを防ぎます。
このような確認が望ましくないことがあり、その場合は無効に設定できます。

```PowerShell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

この環境変数の設定は、現在のプロセスで直ちに有効になります。

##モジュールのバージョンの指定

WMF 5.1 では、`using module` は PowerShell の他のモジュール関連構造と同様に動作します。 以前は、モジュールの特定のバージョンを指定する方法はありませんでした。複数のバージョンが存在する場合、エラーが発生しました。


WMF 5.1 では次のようになります。

* `ModuleSpecification` [ハッシュ テーブル](https://msdn.microsoft.com/en-us/library/jj136290(v=vs.85).aspx)を使用できます。 このハッシュテーブルの形式は `Get-Module -FullyQualifiedName` と同じです。

**次に例を示します。** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`

* モジュールに複数のバージョンがある場合、PowerShell は**同じ解決ロジック**を `Import-Module` として使用し、エラーを返しません。`Import-Module` および `Import-DscResource` と同じ動作です。

## PowerShell コンソールの機能強化

コンソールのエクスペリエンスを改善するため、WMF 5.1 の Powershell.exe が次のように変更されました。

###VT100 のサポート

Windows 10 では、[VT100 エスケープ シーケンス](https://msdn.microsoft.com/en-us/library/windows/desktop/mt638032(v=vs.85).aspx)のサポートが追加されました。
PowerShell は、テーブルの幅を計算するとき、特定の VT100 書式指定エスケープ シーケンスを無視します。

また、PowerShell に追加された新しい API を書式指定コードで使用すると、VT100 がサポートされているかどうかを判定できます。 たとえば、次のように入力します。

```
if ($host.UI.SupportsVirtualTerminal)
{
    $esc = [char]0x1b
    "A yellow ${esc}[93mhello${esc}[0m"
}
else
{
    "A default hello"
}
```
これは、Select-String からの一致を強調表示するために使用できる完全な[例](https://gist.github.com/lzybkr/dcb973dccd54900b67783c48083c28f7)です。
例を `MatchInfo.format.ps1xml` という名前のファイルに保存した後、使用するには、プロファイルまたはその他の場所で、`Update-FormatData -Prepend MatchInfo.format.ps1xml` を実行します。

VT100 エスケープ シーケンスは、Windows 10 Anniversary 更新以降でのみサポートされることに注意してください。それより前のシステムではサポートされません。   

### PSReadline での vi モードのサポート

[PSReadline](https://github.com/lzybkr/PSReadLine) は、vi モードのサポートを追加します。 vi モードを使用するには、`Set-PSReadline -EditMode vi` を実行します。

### 対話型の入力を使用する stdin のリダイレクト 

以前のバージョンでは、stdin がリダイレクトされ、コマンドを対話的に入力するときは、PowerShell を `powershell -File -` で起動する必要がありました。

WMF 5.1 では、この見つけにくいオプションは不要になり、`powershell` といったオプションを何も使わずに PowerShell を起動できます。

PSReadline は現在はリダイレクトされた stdin をサポートせず、リダイレクトされた stdin での組み込みコマンド ライン編集エクスペリエンスは非常に限られたものであることに注意してください (たとえば、方向キーは機能しません)。  PSReadline の将来のリリースではこの問題が対処されるはずです。   

##PowerShell エンジンの機能強化

コア PowerShell エンジンに対する以下の機能強化が WMF 5.1 に実装されました。


## パフォーマンス ##

いくつかの重要な部分でパフォーマンスが向上しました。

- 起動
- ForEach-Object や Where-Object などのコマンドレットに対するパイプライン処理が、約 50% 速くなりました 

機能強化の例をいくつか示します (結果はハードウェアによって異なる場合があります)。 

| シナリオ | 5.0 の時間 (ミリ秒) | 5.1 の時間 (ミリ秒) |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | 900 | 250 |
| PowerShell の初めての実行: `powershell -command "Unknown-Command"` | 30000 | 13000 |
| コマンド分析キャッシュの構築: `powershell -command "Unknown-Command"` | 7000 | 520 |
| `1..1000000 | % { }` | 1400 | 750 |
  
> [!NOTE]  
> 起動に関連する 1 つの変更が、一部のサポートされていないシナリオに影響を与える可能性があります。 PowerShell は `$pshome\*.ps1xml` ファイルを読み込まなくなりました。これらのファイルは、XML ファイルの処理でファイルと CPU にオーバーヘッドが発生しないよう、C# に変換されています。 これらのファイルは V2 のサイド バイ サイド インストールをサポートするためにまだ存在するので、ファイルの内容を変更した場合、V5 には影響がなく、影響を受けるのは V2 だけです。 これらのファイルの内容を変更するシナリオはサポートされていないことに注意してください。

もう 1 つの明らかな変更は、システムにインストールされているモジュールのために PowerShell がエクスポートしたコマンドと他の情報をキャッシュするしくみです。 これまでは、このキャッシュは `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis` ディレクトリに保存されていました。 WMF 5.1 では、キャッシュは `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache` ファイル 1 つだけになっています。
詳細については、「[analysis_cache.md]()」を参照してください。



## バグ修正 ##

次の重要なバグが修正されました。

### モジュールの自動検出の完全な受け入れ `$env:PSModulePath` ###

モジュールの自動検出 (コマンド呼び出し時に Import-Module を明示的に指定しないモジュールの自動的な読み込み) が、WMF 3 で導入されました。 導入時、PowerShell は `$env:PSModulePath` を使用する前に `$PSHome\Modules` のコマンドを確認していました。

WMF 5.1 では、この動作が `$env:PSModulePath` を完全に受け入れるように変更されています。 これにより、PowerShell によって提供されるコマンド (`Get-ChildItem` など) を定義するユーザー作成のモジュールを、自動的に読み込み、組み込みコマンドを正しくオーバーライドできます。

### ファイルのリダイレクトの非ハードコード化 `-Encoding Unicode` ###

PowerShell のこれまでのすべてのバージョンでは、PowerShell が `-Encoding Unicode` を追加していたため、ファイル リダイレクト演算子 (`get-childitem > out.txt` など) によって使用されるファイル エンコードを制御できませんでした。

WMF 5.1 からは、`$PSDefaultParameterValues` を設定することによってリダイレクトのファイル エンコードを変更できます。次に例を示します。

```
$PSDefaultParameterValues["Out-File:Encoding"] = "Ascii"
```

### メンバーへのアクセスでのバグ再発の修正 `System.Reflection.TypeInfo` ###

WMF 5.0 で新しく発生したバグにより、`System.Reflection.RuntimeType` のメンバーにアクセスできませんでした (`[int].ImplementedInterfaces` など)。
WMF5.1 ではこのバグが修正されています。


### COM オブジェクトでのいくつかの問題の修正 ###

WMF 5.0 では、COM オブジェクト上のメソッドを呼び出して COM オブジェクトのプロパティにアクセスする新しい COM バインダーが導入されました。
この新しいバインダーによりパフォーマンスが大幅に向上しましたが、バグもいくつか含まれていました。WMF5.1 ではそれが修正されました。

#### 引数の変換が正常に実行されないことがあった ####

次に例を示します。

```
$obj = new-object -com wscript.shell
$obj.SendKeys([char]173)
```

SendKeys メソッドは string を受け取りますが、PowerShell は char を string に変換せず、変換を IDispatch::Invoke に延期していました。このメソッドは VariantChangeType を使用して変換を行います。この例では、結果として、期待される Volume.Mute キーではなくキー "1"、"7"、"3" が送られます。

#### 列挙可能な COM オブジェクトが正しく処理されないことがある ####

PowerShell は通常ほとんどの列挙可能なオブジェクトを列挙しますが、WMF 5.0 で発生したバグにより、IEnumerable を実装する COM オブジェクトの列挙が行われませんでした。  たとえば、次のように入力します。

```
function Get-COMDictionary
{
    $d = New-Object -ComObject Scripting.Dictionary
    $d.Add('a', 2)
    $d.Add('b', 2)
    return $d
}

$x = Get-COMDictionary
```

上の例の WMF 5.0 は、キーと値のペアを列挙するのではなく、Scripting.Dictionary をパイプラインに誤って書き込みます。


### `[ordered]` がクラス内で許可されなかった ###

WMF5 では、クラスで使用されるリテラル形を検証するクラスが導入されました。  `[ordered]` はリテラル形のように見えますが、真の .Net 型ではありません。  WMF5 は、クラスの内の `[ordered]` で誤ってエラーを報告しました。

```
class CThing
{
    [object] foo($i)
    {
        [ordered]@{ Thing = $i }
    }
}
```


### 複数のバージョンがあるトピックについてのヘルプが機能しない ###

WMF 5.1 より前では、複数のバージョンのモジュールがインストールされていて、そのすべてがヘルプ トピック (about_PSReadline など) を共有している場合、`help about_PSReadline` は複数のトピックを返し、実際のヘルプを表示する明確な方法はありませんでした。

WMF 5.1 では、最新バージョンのトピックのヘルプを返すことでこれが解決されています。

Get-Help では、必要なヘルプのバージョンを指定する方法はありません。 これを回避するには、モジュール ディレクトリに移動し、好みのエディターなどのツールで直接ヘルプを表示します。 

## OneGet の機能強化
WMF 5.1 には、WMF 5.0 リリースにあったユーザー エクスペリエンスのギャップの一部に対処するための、いくつかの修正と機能強化が含まれます。 

###バージョン エイリアスの削除

**シナリオ**: パッケージ P1 のバージョン 1.0 および 2.0 がシステムにインストールされていて、バージョン 1.0 をアンインストールしたい場合、"uninstall-package -name P1 -version 1.0" を実行し、このコマンドを実行するとバージョン 1.0 がアンインストールされるものと期待します。 しかし、結果はバージョン 2.0 がアンインストールされます。 
    
このようになるのは、"-version" パラメーターが "-minimumversion" パラメーターのエイリアスであるためです。 OneGet は、最小バージョンが 1.0 という条件を満たすパッケージを探して、最新のバージョンを返します。 たいていの場合は最新バージョンを探すのが目的の結果なので、この動作は通常であれば想定したものです。 しかし、uninstall-package の場合には当てはまりません。
    
**解決策**: WMF 5.1 では、OneGet および PowerShellGet から -version エイリアスが完全に削除されています。 

###NuGet プロバイダーのブートストラップに対する複数のプロンプト

**シナリオ**: Find-Module、Install-module、または他の OneGet コマンドレットをコンピューターで初めて実行すると、OneGet は NuGet プロバイダーをブートストラップしようとします。 これは、PowerShellGet プロバイダーは PowerShell モジュールをダウンロードするために NuGet プロバイダーも使用するためです。 そのとき、OneGet は NuGet プロバイダーをインストールする許可をユーザーに求めます。 ユーザーがブートストラップに対して "はい" を選択すると、最新バージョンの NuGet プロバイダーがインストールされます。 
    
ただし、古いバージョンの NuGet プロバイダーがコンピューターにインストールされている場合があり、古いバージョンの NuGet が PowerShell セッションに最初に読み込まれることがあります (OneGet での競合状態)。 ただし、PowerShellGet が動作するには新しいバージョンの NuGet プロバイダーが必要なので、PowerShellGet は OneGet に NuGet プロバイダーのブートストラップを再び要求します。 これにより、NuGet プロバイダーのブートストラップで複数のプロンプトが表示されます。

**解決策**: WMF 5.1 では、OneGet は、NuGet プロバイダーのブートストラップに対して複数のプロンプトが表示されるのを避けるため、NuGet プロバイダーの最新バージョンを読み込むようになっています。

この問題を回避策することもできます。古いバージョンの NuGet プロバイダー (NuGet-Anycpu.exe) が存在する場合は、$env:ProgramFiles\PackageManagement\ProviderAssemblies または $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies から手動で削除します。


###イントラネット アクセスのみのコンピューターでの OneGet のサポート

**シナリオ**: WMF 5.0 の OneGet は、イントラネット アクセスしかない (インターネットにアクセスできない) コンピューターをサポートしませんでした。

**解決策**: WMF 5.1 では、以下のようにして、イントラネット接続のみのコンピューターで OneGet を使用できます。

1. インターネットに接続できる別のコンピューターで、Install-PackageProvider NuGet を使用して、NuGet プロバイダーをダウンロードします。

2. $env:ProgramFiles\PackageManagement\ProviderAssemblies\nuget または $env:LOCALAPPDATA\PackageManagement\ProviderAssemblies\nuget で NuGet プロバイダーを探します。 

3. イントラネット コンピューターがアクセスできるフォルダーまたはネットワーク共有の場所にバイナリをコピーし、"Install-PackageProvider NuGet -Source <Path to folder>" を使用して NuGet プロバイダーをインストールします。


###イベント ログの機能強化

パッケージをインストールすると、コンピューターの状態が変化します。 WMF 5.1 の OneGet は、install、uninstall、save-package アクティビティのイベントを Windows イベント ログに記録するようになりました。 イベント チャネルは PowerShell と同じで、Microsoft-Windows-PowerShell, Operational です。

###基本認証のサポート

WMF 5.1 の OneGet は、基本認証を必要とするリポジトリからのパッケージの検索とインストールをサポートします。 Find-Package および Install-Package コマンドレットに資格情報を渡すことができます。 たとえば、次のように入力します。

``` PowerShell
Find-Package -Source <SourceWithCredential> -Credential (Get-Credential)
```
###プロキシの背後での OneGet の使用のサポート

WMF 5.1 の OneGet は、新しいプロキシ パラメーター -ProxyCredential と -Proxy を受け取るようになりました。 これらのパラメーターを使用すると、プロキシの URL と資格情報を OneGet コマンドレットに対して指定できます。 既定では、システムのプロキシ設定が使用されます。 たとえば、次のように入力します。

``` PowerShell
Find-Package -Source http://www.nuget.org/api/v2/ -Proxy http://www.myproxyserver.com -ProxyCredential (Get-Credential)
```



<!--HONumber=Jul16_HO1-->


