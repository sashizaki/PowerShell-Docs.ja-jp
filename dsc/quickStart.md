---
ms.date: 2017-06-12T00:00:00.000Z
author: eslesar
ms.topic: conceptual
keywords: "DSC, PowerShell, 構成, セットアップ"
title: "Desired State Configuration クイック スタート"
ms.openlocfilehash: e8a73296827297bab3229392c4193fed940c53bf
ms.sourcegitcommit: 46feddbc753523f464f139b5d272794620072fc8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2017
---
> 適用先: Windows PowerShell 4.0、Windows PowerShell 5.0

# <a name="desired-state-configuration-quick-start"></a>Desired State Configuration クイック スタート

この演習では、Desired State Configuration (DSC) の構成の作成と適用について最初から最後まで説明します。
これから使用するサンプルでは、サーバーの `Web-Server` (IIS) 機能が有効になっており、そのサーバのディレクトリ `intetpub\wwwroot` に「Hello World」サンプルのコンテンツが存在することを確認します。

DSC の概要としくみついては、「[意思決定者向け Desired State Configuration の概要](decisionMaker.md)」をご覧ください。

## <a name="requirements"></a>要件

このサンプルを実行するには、Windows Server 2012 以降と PowerShell 4.0 以降が動作しているコンピューターが必要です。

## <a name="write-and-place-the-indexhtm-file"></a>index.htm ファイルを記述し、配置する

最初に、Web サイトのコンテンツとして使用する HTML ファイルを作成します。

ルート フォルダーに `test` という名前のフォルダを作成します。

テキスト エディターで、次のテキストを入力します。

```html
<head></head>
<body>
<p>Hello World!</p>
</body>
```

これを先ほど作成した `test` フォルダに `index.htm` というファイル名でこのファイルを保存します。 

## <a name="write-the-configuration"></a>構成を記述する

[DSC 構成](configurations.md)は 1 つまたは複数のターゲット コンピューター (ノード) を構成する方法を定義する特別な PowerShell 関数です。

PowerShell ISE で、次のように入力します。

```powershell
Configuration WebsiteTest {

    # Import the module that contains the resources we're using.
    Import-DscResource -ModuleName PsDesiredStateConfiguration

    # The Node statement specifies which targets this configuration will be applied to.
    Node 'localhost' {

        # The first resource block ensures that the Web-Server (IIS) feature is enabled.
        WindowsFeature WebServer {
            Ensure = "Present"
            Name   = "Web-Server"
        }

        # The second resource block ensures that the website content copied to the website root folder.
        File WebsiteContent {
            Ensure = 'Present'
            SourcePath = 'c:\test\index.htm'
            DestinationPath = 'c:\inetpub\wwwroot'
        }
    }
}
```

このファイルを `WebsiteTest.ps1` として保存します。

関数名の前に **Configuration** というキーワードを追加することで、PowerShell の関数のように表示されます。

`localhost` 場合、**ノード**ブロックは構成するターゲット ノードを指定します。

構成は 2 つの[リソース](resources.md) ([WindowsFeature](windowsFeatureResource.md) と[ファイル](fileResource.md)) を呼び出します。
リソースは、ターゲット ノードが構成によって定義された状態になっているか確認します。

## <a name="compile-the-configuration"></a>構成をコンパイルする

DSC 構成をノードに適用するには、最初にコンパイルを行い、MOF ファイルを出力する必要があります。
これを行うには、構成を関数のように実行します。
PowerShell コンソールで構成が保存されているフォルダーに移動し、次のコマンドを実行して構成のコンパイルを行い、MOF ファイルを出力します。

```powershell
. .\WebsiteTest.ps1
WebsiteTest
```

これにより、次の出力が生成されます。

```
Directory: C:\ConfigurationTest\WebsiteTest


Mode                LastWriteTime         Length Name
----                -------------         ------ ----
-a----        3/13/2017   5:20 PM           2746 localhost.mof
```

最初の行では、コンソールで利用可能な構成関数を作成します。
2 行目では構成を実行します。
その結果、現在のフォルダのサブ フォルダとして `WebsiteTest` という名前の新しいフォルダが作成されます。
`WebsiteTest` フォルダーには、`localhost.mof` という名前のファイルが含まれています。
これは後にターゲット ノードに適用できるファイルです。

## <a name="apply-the-configuration"></a>構成を適用する

コンパイル済みの MOF があるため、[Start-DscConfiguration](/reference/5.1/PSDesiredStateConfiguration/Start-DscConfiguration) コマンドレットを呼び出すことで、ターゲット ノード (今回の場合はローカル コンピューター) に構成を適用できます。

`Start-DscConfiguration` コマンドレットから DSC のエンジンである [Local Configuration Manager (LCM)](metaConfig.md) に対して構成の適用を指示します。
LCM はDSC リソースを呼び出し、構成を適用します。

PowerShell コンソールで構成が保存されているフォルダーに移動し、次のコマンドを実行します。

```powershell
Start-DscConfiguration .\WebsiteTest
```

## <a name="test-the-configuration"></a>構成をテストする

[Get-DscConfigurationStatus](/reference/5.1/PSDesiredStateConfiguration/Get-DscConfigurationStatus) コマンドレットを呼び出すことで、構成の適用が正しく行われたか確認できます。 

今回の場合は、Web ブラウザーで `http://localhost/` を参照することで、結果を直接テストすることもできます。
この例の最初の手順として、作成した「Hello World」 HTML ページが表示されます。

## <a name="next-steps"></a>次の手順

- 「[DSC 構成](configurations.md)」で DSC 構成の詳細を確認する。
- 「[DSC リソース](resources.md)」で利用可能な DSC リソースとカスタム DSC リソースの作成方法を確認する。
- 「[PowerShell ギャラリー](https://www.powershellgallery.com/)」で DSC の構成とリソースを検索する。



