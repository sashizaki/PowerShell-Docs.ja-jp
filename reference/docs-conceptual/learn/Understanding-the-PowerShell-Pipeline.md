---
ms.date: 08/23/2018
keywords: PowerShell, コマンドレット
title: PowerShell パイプラインの概要
ms.assetid: 6be50926-7943-4ef7-9499-4490d72a63fb
ms.openlocfilehash: 05ab98b7261f4d41ade1788a924193eccda6318c
ms.sourcegitcommit: f268dce5b5e72be669be0c6634b8db11369bbae2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "58623961"
---
# <a name="understanding-pipelines"></a>パイプラインの概要

パイプラインは、複数の管を 1 つに継ぎ合わせた管路のような役割を果たします。 パイプラインに沿って移動する項目は、個々の管を通過します。 PowerShell でパイプラインを作成するには、パイプ演算子 (|) を使ってコマンドを接続します。 接続すると、各コマンドの出力が、次のコマンドの入力として使用されるようになります。

パイプラインで使用される表記は、他のシェルで使用される表記とほぼ同じです。 PowerShell でのパイプラインの違いは、一目見ただけではわかりにくいかもしれません。 画面にはテキストが表示されますが、PowerShell は、コマンド間ではテキストではなくオブジェクトを受け渡します。

## <a name="the-powershell-pipeline"></a>PowerShell のパイプライン

パイプラインは、コマンドライン インターフェイスで使用される最も重要な概念と言っても過言ではありません。 適切に利用すれば、パイプラインによって複雑なコマンドを使用する負荷が軽減され、より簡単にコマンドのワークフローを確認できるようになります。 パイプラインの各コマンド (パイプライン要素と呼ばれる) は、出力をパイプライン内の次のコマンドに項目単位で渡します。 コマンドでは、一度に複数の項目を処理する必要がなくなります。 結果として、リソース使用量が低下すると共に、出力の取得をすぐに開始できるようになります。

たとえば、`Out-Host` コマンドレットを使用して、別のコマンドからの出力をページ単位で表示させると、通常のテキストがページごとに分割されて画面上に表示されているだけのように見えます。

```powershell
Get-ChildItem -Path C:\WINDOWS\System32 | Out-Host -Paging
```

```Output
    Directory: C:\WINDOWS\system32

Mode                LastWriteTime         Length Name
----                -------------         ------ ----
d-----        4/12/2018   2:15 AM                0409
d-----        5/13/2018  11:31 PM                1033
d-----        4/11/2018   4:38 PM                AdvancedInstallers
d-----        5/13/2018  11:13 PM                af-ZA
d-----        5/13/2018  11:13 PM                am-et
d-----        4/11/2018   4:38 PM                AppLocker
d-----        5/13/2018  11:31 PM                appmgmt
d-----        7/11/2018   2:05 AM                appraiser
d---s-        4/12/2018   2:20 AM                AppV
d-----        5/13/2018  11:10 PM                ar-SA
d-----        5/13/2018  11:13 PM                as-IN
d-----        8/14/2018   9:03 PM                az-Latn-AZ
d-----        5/13/2018  11:13 PM                be-BY
d-----        5/13/2018  11:10 PM                BestPractices
d-----        5/13/2018  11:10 PM                bg-BG
d-----        5/13/2018  11:13 PM                bn-BD
d-----        5/13/2018  11:13 PM                bn-IN
d-----        8/14/2018   9:03 PM                Boot
d-----        8/14/2018   9:03 PM                bs-Latn-BA
d-----        4/11/2018   4:38 PM                Bthprops
d-----        4/12/2018   2:19 AM                ca-ES
d-----        8/14/2018   9:03 PM                ca-ES-valencia
d-----        5/13/2018  10:46 PM                CatRoot
d-----        8/23/2018   5:07 PM                catroot2
<SPACE> next page; <CR> next line; Q quit
...
```

また、表示する完全なページが準備できると、`Out-Host` コマンドレットに処理が転送されるため、ページングによって CPU 使用率が低下します。 パイプライン内で先行するコマンドレットは、次のページの出力が利用可能になるまで、実行を一時停止します。

この時間差は、PowerShell で使用される CPU およびメモリを監視する Windows タスク マネージャーで確認できます。 コマンド `Get-ChildItem C:\Windows -Recurse` を実行します。 `Get-ChildItem C:\Windows -Recurse | Out-Host -Paging` を使って、このコマンドに対する CPU とメモリの使用量を比較します。

> [!NOTE]
> **Paging** パラメーターは、すべての PowerShell ホストでサポートされているわけではありません。 たとえば、PowerShell ISE で **Paging** パラメーターを使おうとすると、次のエラーが表示されます。
>
> ```Output
> out-lineoutput : The method or operation is not implemented.
> At line:1 char:1
> + Get-ChildItem C:\Windows -Recurse | Out-Host -Paging
> + ~~~~~~~~~~~~~~~~~~~~~~~~~~~
>     + CategoryInfo          : NotSpecified: (:) [out-lineoutput], NotImplementedException
>     + FullyQualifiedErrorId : System.NotImplementedException,Microsoft.PowerShell.Commands.OutLineOutputCommand
> ```

## <a name="objects-in-the-pipeline"></a>パイプライン内のオブジェクト

PowerShell でコマンドレットを実行した場合、コンソール ウィンドウではオブジェクトをテキストで表す必要があるため、テキストが表示されます。 テキスト出力では、出力されるオブジェクトのすべてのプロパティが必ず表示されるわけではありません。

たとえば、`Get-Location` コマンドレットについて考えてみます。 現在の場所が C ドライブのルートである場合に `Get-Location` を実行すると、次のような出力が表示されます。

```
PS> Get-Location

Path
----
C:\
```

テキストの出力は情報の要約であり、`Get-Location` から返されたオブジェクトの完全な表現ではありません。 出力の見出しは、画面の表示用にデータを書式設定する処理によって、追加されます。

出力を `Get-Member` コマンドレットにパイプ処理するときに、`Get-Location` から返されたオブジェクトに関する情報を取得します。

```powershell
Get-Location | Get-Member
```

```Output
   TypeName: System.Management.Automation.PathInfo

Name         MemberType Definition
----         ---------- ----------
Equals       Method     bool Equals(System.Object obj)
GetHashCode  Method     int GetHashCode()
GetType      Method     type GetType()
ToString     Method     string ToString()
Drive        Property   System.Management.Automation.PSDriveInfo Drive {get;}
Path         Property   string Path {get;}
Provider     Property   System.Management.Automation.ProviderInfo Provider {get;}
ProviderPath Property   string ProviderPath {get;}
```

`Get-Location` は、現在のパスとその他の情報を含む **PathInfo** オブジェクトを返します。
