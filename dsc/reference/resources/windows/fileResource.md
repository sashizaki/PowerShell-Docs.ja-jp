---
ms.date: 06/12/2017
keywords: DSC, PowerShell, 構成, セットアップ
title: DSC ファイル リソース
ms.openlocfilehash: b5bc2c305b8cfccbd044274811df631264a24279
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62077332"
---
# <a name="dsc-file-resource"></a>DSC ファイル リソース

> 適用先:Windows PowerShell 4.0、Windows PowerShell 5.0

Windows PowerShell Desired State Configuration (DSC) の File リソースは、ターゲット ノード上でファイルとフォルダーを管理するためのメカニズムを備えています。 **DestinationPath** と **SourcePath** は両方ともターゲット ノードからアクセスできる必要があります。

## <a name="syntax"></a>構文

```
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present } ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ DependsOn = [string[]] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
}
```

## <a name="properties"></a>プロパティ

|プロパティ       |説明                                                                   |必須|既定|
|---------------|------------------------------------------------------------------------------|--------|-------|
|DestinationPath|確保するターゲット ノード上の場所は `Present` または `Absent` です。|可|いいえ|
|属性     |対象となるファイルまたはディレクトリの属性の望ましい状態。 有効な値は、**Archive**、**Hidden**、**ReadOnly**、**System** です。|いいえ|None|
|チェックサム      |2 つのファイルが同じであるかどうかを決定するときに使用するチェックサム タイプ。 有効な値は、次のとおりです。SHA-1、SHA-256、SHA-512、createdDate、modifiedDate。|いいえ|ファイルまたはディレクトリの名前のみが比較されます。|
|内容       |`File` 型に使用した場合にのみ有効です。 確認 (Ensure) するコンテンツがターゲット ファイルの `Present` または `Absent` であることを示します。 |いいえ|None|
|Credential     |ソース ファイルなどのリソースにアクセスするために必要な資格情報。|いいえ|ターゲット ノードのコンピューター アカウント。 ("*注を参照*")|
|Ensure         |対象となるファイルまたはディレクトリの望ましい状態。 |いいえ|**Present**|
|Force          |結果としてエラーになるアクセス操作 (ファイルの上書き、空でないディレクトリの削除など) をオーバーライドします。|いいえ|`$false`|
|Recurse        |`Directory` 型に使用した場合にのみ有効です。 すべてのサブディレクトリに対して状態操作を再帰的に実行します。|いいえ|`$false`|
|DependsOn      |指定したリソースに依存関係を設定します。 このリソースは、依存リソースが正常に実行された後にのみ実行されます。 構文 `"[ResourceType]ResourceName"` を使用して依存リソースを指定できます。 「[about_DependsOn](../../../configurations/resource-depends-on.md)」を参照してください|いいえ|None|
|SourcePath     |ファイルまたはフォルダー リソースのコピー元のパス。|いいえ|None|
|種類           |構成されるリソースの種類。 有効な値は `Directory` と `File` です。|いいえ|`File`|
|MatchSource    |最初のコピー後にソース ディレクトリに追加された新しいファイルをリソースで監視するかどうかを決定します。 `$true` の値は、最初のコピー後、すべての新しいソース ファイルが指定した場所にコピーされることを示します。 `$False` に設定した場合、リソースではソース ディレクトリの内容がキャッシュされ、最初のコピー後に追加されたファイルはすべて無視されます。|いいえ|`$false`|

> [!WARNING]
> `Credential` または `PSRunAsCredential` (PS V.5) の値を指定しない場合、リソースはターゲット ノードのコンピューター アカウントを使用して `SourcePath` にアクセスします。  `SourcePath` が UNC 共有の場合、"アクセスが拒否されました" エラーが発生する可能性があります。 アクセス許可が適切に設定されていることを確認するか、`Credential` または `PSRunAsCredential` プロパティを使用して、使用するアカウントを指定します。

## <a name="present-vs-absent"></a>Present とAbsent

各 DSC リソースでは、`Ensure` プロパティに指定した値に基づいて異なる操作が実行されます。 上記のプロパティに指定した値によって、実行される状態操作が決まります。

### <a name="existence"></a>存在

`DestinationPath` のみを指定した場合、リソースではパスが存在すること (`Present`) または存在しないこと (`Absent`) が確認されます。

### <a name="copy-operations"></a>コピー操作

`Type` の値が **Directory** の `SourcePath` と `DestinationPath` を指定すると、リソースではソース ディレクトリが対象パスにコピーされます。 プロパティ `Recurse`、`Force`、および `MatchSource` で実行されるコピー操作の種類が変更され、`Credential` ではソース ディレクトリへのアクセスに使用するアカウントが決まります。

### <a name="limitations"></a>制限事項

`Attributes` プロパティに `DestinationPath` と一緒に `ReadOnly` の値を指定した場合、`Ensure = "Present"` によって指定したパスが作成され、`Contents` によってファイルの内容が設定されます。  `Absent` 状態操作では `Attributes` プロパティが完全に無視され、指定したパスにあるすべてのファイルが削除されます。

## <a name="example"></a>例

次の例では、ファイル リソースを使用して、ディレクトリとそのサブディレクトリをプル サーバーからターゲット ノードにコピーします。 操作が成功すると、Log リソースで確認メッセージがイベント ログに書き込まれます。

ソース ディレクトリは、プル サーバーから共有されている UNC パス (`\\PullServer\DemoSource`) です。 `Recurse` プロパティを使用すると、すべてのサブディレクトリも確実にコピーされます。

> [!IMPORTANT]
> ターゲット ノード上の LCM は、既定でローカル システム アカウントのコンテキストで実行されます。 **SourcePath** へのアクセスを許可するには、ターゲット ノードのコンピューター アカウントに適切なアクセス許可を付与します。 **Credential** と **PSDSCRunAsCredential** (v5) のいずれでも、LCM が **SourcePath** にアクセスするために使用するコンテキストが変更されます。 それでも **SourcePath** へのアクセスに使用されるアカウントへのアクセスを許可する必要があります。

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

DSC で**資格情報**を使用する方法の詳細については、[実行ユーザー](../../../configurations/runAsUser.md)または[データの資格情報の構成](../../../configurations/configDataCredentials.md)に関する記事を参照してください。
